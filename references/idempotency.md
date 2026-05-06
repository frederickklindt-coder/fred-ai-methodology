# Engineering Reference — Idempotency

> Personal reference. Come back here whenever you need to design or review an operation that might be retried.

---

## TL;DR

**Idempotent = same result no matter how many times you run it.**

If an operation can fire more than once (network retry, cron overlap, webhook replay, user double-click), it must be idempotent — otherwise retries cause duplicates, double-charges, double-writes, or corrupted state.

---

## When you must care

- **Any HTTP endpoint that mutates state.** Networks fail; clients retry.
- **Any webhook handler.** External services (Stripe, GHL, Bland, Twilio, GitHub) retry on timeout or non-2xx response.
- **Any background job / cron / scheduler.** Jobs can overlap, restart, or fire twice on container restarts.
- **Any message queue consumer.** "At-least-once delivery" is the default — exactly-once is impossible at the network layer.
- **Any payment / financial / billing operation.** Always. No exceptions.
- **Any AI API call you pay for.** Re-running an embedding/completion when you didn't have to is wasted money.

---

## The mental model

| Property | Meaning | Example |
|---|---|---|
| **Safe** | Does not modify state (read-only) | `GET /users/42` |
| **Idempotent** | Can be repeated with the same result | `PUT /users/42 {name: "Fred"}` |
| **Neither** | Each call changes state in a new way | `POST /orders` (default) |

> All safe operations are idempotent. **Not all idempotent operations are safe.** PUT and DELETE change state but are still idempotent.

### HTTP method conventions

| Method | Idempotent by convention? |
|---|---|
| `GET` | ✅ Yes |
| `PUT` | ✅ Yes |
| `DELETE` | ✅ Yes |
| `POST` | ❌ No (by default) |
| `PATCH` | ⚠️ Depends ("set X to Y" yes; "increment by 1" no) |

This is **why payment APIs require an `Idempotency-Key` header on POST requests** — POST is not idempotent by default and money operations cannot be safely retried without one.

---

## The 4 patterns to make something idempotent

### Pattern 1 — Idempotency key (client-generated unique ID)

The client generates a random ID and sends it with every request. The server stores `{key → result}` for some time window (Stripe uses 24h). On retry, server returns the cached result instead of re-running.

```python
# Client side
import uuid
idempotency_key = str(uuid.uuid4())
requests.post("/orders", json=order, headers={"Idempotency-Key": idempotency_key})

# Server side (pseudocode)
if cache.has(idempotency_key):
    return cache.get(idempotency_key)
result = process_order(order)
cache.set(idempotency_key, result, ttl=24h)
return result
```

**Use when:** the client has no natural unique identifier for the operation (e.g., "create a new order"). Stripe is the canonical example.

---

### Pattern 2 — Natural unique ID (use the data itself)

Use a field already in the payload as the dedup key — message ID, webhook event ID, transaction hash, file checksum.

```python
# Webhook handler — idempotent via event_id
event_id = webhook_payload["event_id"]
if db.exists("processed_events", event_id):
    return 200  # Already handled, acknowledge again
process(webhook_payload)
db.insert("processed_events", event_id)
```

**Use when:** the source already provides a stable identifier. This is what your inbox-intel ingestion does — `message_id` (Gmail), `graph_message_id` (Outlook), `meeting_id` (ReadAI) all feed into `entry_key` for `stable_doc_id()`.

---

### Pattern 3 — Upsert instead of insert

`UPSERT` = "update if exists, insert if not." Inherently idempotent for "make this row look like X."

```sql
INSERT INTO users (id, name) VALUES (42, 'Frederick')
ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;
```

```python
# ChromaDB
collection.upsert(ids=[doc_id], documents=[text], metadatas=[meta])
# Re-running with same doc_id overwrites instead of duplicating.
```

**Use when:** you have a stable ID and the desired end-state is "row exists with these values." This is what `IngestionPipeline.ingest()` in inbox-intel does — `collection.upsert()` not `collection.add()`.

---

### Pattern 4 — State check before action

Before doing the work, check if the desired end-state is already reached.

```python
def cancel_order(order_id):
    order = db.get(order_id)
    if order.status == "cancelled":
        return  # Already done, nothing to do
    order.status = "cancelled"
    db.save(order)
```

**Use when:** the operation is a state transition with a clear terminal state. This is what makes `DELETE /resource/42` idempotent — second call sees "already gone" and is a no-op. Also what `_id_exists()` in inbox-intel pipeline does before re-embedding.

---

## How to design something idempotent (checklist)

When you're about to write a new endpoint, webhook handler, or job, ask:

- [ ] **Can this fire more than once for the same logical operation?** (If no → done, no idempotency needed.)
- [ ] **What's the unit of "the same operation"?** (Order? Message? User-event? Day?)
- [ ] **Is there a natural unique ID in the payload?** (If yes → Pattern 2.)
- [ ] **If no natural ID, can the client generate one?** (If yes → Pattern 1.)
- [ ] **Does the operation reduce to "set state X"?** (If yes → Pattern 3 or 4.)
- [ ] **Does the operation cost real money per call?** (Embeddings, LLM calls, payment API → idempotency is mandatory, not optional.)
- [ ] **What's the dedup window?** (Forever? 24h like Stripe? Until next sync?)
- [ ] **Where does the dedup state live?** (Database table? Redis cache? In-memory `set()` won't survive restarts.)
- [ ] **What happens to the second caller?** (Return cached response? 200 OK with no body? Same response as first call?)

---

## Common gotchas

1. **In-memory deduplication does not survive restarts.** A `set()` in process memory loses everything on container restart. Use persistent storage (DB table, Redis) for any non-trivial dedup window.

2. **Race conditions between concurrent retries.** If two retries arrive within milliseconds and both check `if not exists` before either inserts, both will insert. Fix with a unique constraint on the dedup column + handle the `IntegrityError`, OR use a transactional upsert.

3. **Idempotency key TTL too short.** If your TTL is 1 hour and a client retries 2 hours later, you'll process twice. Stripe uses 24h. Pick a TTL longer than the maximum plausible retry delay.

4. **Idempotent at one layer, not at the outer layer.** Your DB write might be idempotent (upsert), but your API endpoint still re-runs the entire pipeline (re-extracts attachments, re-embeds chunks, re-pays OpenAI). Costs money, doesn't corrupt data — but is still wasteful.

5. **Side effects outside your transaction.** Sending an email inside a webhook handler that gets retried = duplicate email sent. Email sending is rarely idempotent — wrap it in its own dedup check.

6. **Natural keys that aren't actually stable.** A "natural" ID that contains a timestamp or random nonce is NOT stable across retries. Test that the same payload genuinely produces the same key.

7. **Schema changes break old keys.** If your `stable_doc_id()` formula changes, IDs generated before vs after will not collide → you'll get duplicates on the boundary. Treat the ID formula as a stable contract.

---

## Where you've already used this

- **inbox-intel** — `stable_doc_id()` (Pattern 2 + hash), `collection.upsert()` (Pattern 3), `_id_exists()` skip (Pattern 4), in-batch `seen` set dedup. See `/ingestion/chunker.py` and `/ingestion/pipeline.py`.
- **ai-ops daily email sync** — message-ID dedup via SQLite (Pattern 2).
- **ALT webhook handlers** — `webhook_id` / `call_id` from GHL/Bland used as natural keys (Pattern 2).
- **ChromaDB collections in general** — `add()` with explicit IDs is implicitly upsert-like for IDs you've already inserted; explicit `upsert()` makes it guaranteed (Pattern 3).

---

## When NOT to bother

- **Pure read operations.** GET endpoints that don't mutate state are already idempotent.
- **One-shot scripts you run manually.** Ad-hoc analysis scripts you'll never retry don't need idempotency machinery.
- **Operations with no cost and no side effects on duplicate.** "Recalculate the cached aggregate" can be safely re-run; idempotency is bonus, not requirement.
- **Internal-only operations behind a transaction.** If the entire operation is wrapped in a single DB transaction and rollback handles failure cleanly, you may not need an explicit idempotency layer.

---

## Vocabulary you'll hear

- **idempotent** — the property
- **idempotency** — the noun form ("we need to add idempotency to the orders endpoint")
- **idempotency key** — the unique identifier passed in the header or payload
- **dedup** / **deduplication** — the practice of removing duplicates
- **at-least-once delivery** — message queue pattern that requires consumers to be idempotent
- **exactly-once** — usually impossible at the network layer; achieved by combining at-least-once + idempotent consumer
- **upsert** — insert-or-update operation

---

## Reference sources

- Stripe API documentation — [Idempotent Requests](https://stripe.com/docs/api/idempotent_requests) (canonical industry pattern)
- HTTP spec — RFC 9110 §9.2.2 ([Idempotent Methods](https://www.rfc-editor.org/rfc/rfc9110.html#name-idempotent-methods))
- Designing Data-Intensive Applications (Kleppmann) — Chapter 8 covers idempotency in distributed systems
