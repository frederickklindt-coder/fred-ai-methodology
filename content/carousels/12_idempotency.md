# Carousel 12 — Idempotency: The Word Every AI Builder Needs to Know

**Post number:** 12
**Keyword CTA:** IDEM
**Category:** Systems / Builds
**Date:** 2026-05-06

---

## Slide 1 — HOOK

**Your AI agent just ran twice.**
**A user got charged twice.**
**You didn't even know.**

There's one engineering concept that prevents this.
And almost no one in the AI builder space is talking about it.

**Idempotency.**

---

## Slide 2 — WHAT IT ACTUALLY MEANS

Idempotent = **same result, no matter how many times you run it.**

Think of it as a safety switch.

| Operation | Idempotent? |
|-----------|------------|
| Turn on a light that's already on | ✅ Yes |
| Charge a card again for the same order | ❌ No |

If your operation can fire more than once —
network retry, webhook replay, cron overlap —
it **must** be idempotent.

Otherwise: duplicates, double-charges, corrupted state.

---

## Slide 3 — WHEN YOU MUST CARE

You need idempotency whenever the same action can fire more than once:

**→ Webhook handlers**
Stripe, GHL, Bland, Twilio — all retry on timeout or non-2xx.

**→ Background jobs / crons**
Jobs can overlap, restart, or fire twice on container restart.

**→ Message queues**
"At-least-once delivery" is the default. Exactly-once doesn't exist at the network layer.

**→ Any AI API call you pay for**
Re-running an embedding or LLM call = wasted money. Every time.

If you're building agents — you're in all 4 categories.

---

## Slide 4 — PATTERN 1: IDEMPOTENCY KEY

No natural unique ID? Create one.

The client generates a random UUID and sends it with every request.
The server stores `{key → result}` for a time window.
On retry → return the cached result. No reprocessing.

```
Idempotency-Key: a3f7c9d1-...
```

This is exactly what Stripe does for payments.
Why? Because POST requests are not idempotent by default.
And money cannot be safely retried without a key.

**Rule of thumb:** TTL should be longer than your maximum retry delay.
Stripe uses 24h. Match or beat that.

---

## Slide 5 — PATTERN 2: NATURAL UNIQUE ID

Most of the time — you already have the key.

Use a field already in the payload:
`event_id`, `message_id`, `webhook_id`, `file_checksum`

```python
# Webhook handler — idempotent via event_id
if db.exists("processed_events", event_id):
    return 200  # Already handled. Acknowledge again.
process(webhook_payload)
db.insert("processed_events", event_id)
```

This is Pattern 2 — and it's the most common one in real systems.

No new infrastructure. Just use what's already there.

---

## Slide 6 — PATTERN 3 + 4: UPSERT & STATE CHECK

Two patterns that don't need a dedup table at all:

**Pattern 3 — Upsert instead of insert**
"Update if exists. Insert if not."
Inherently idempotent for "make this row look like X."

```python
collection.upsert(ids=[doc_id], ...)
# Re-running with same ID overwrites. Never duplicates.
```

**Pattern 4 — State check before action**
Before doing the work — check if it's already done.

```python
if order.status == "cancelled":
    return  # Already there. Nothing to do.
```

Pick the pattern that fits your operation.
Often, you'll combine 2 or 3 in the same system.

---

## Slide 7 — MYTH / SHIFT

**"It worked fine in testing. Why would it run twice?"**

Because production isn't your laptop.

Networks fail. Timeouts happen. Containers restart.
External services retry automatically — and they don't tell you.

Your webhook handler that "never failed" in staging?
It's firing 3x in production right now for a subset of users.

Idempotency isn't defensive programming.
It's **the minimum bar for production-grade systems.**

---

## Slide 8 — PROOF / STORY

Every system I've shipped uses at least one of these patterns.

**inbox-intel** (AI email pipeline):
- `stable_doc_id()` — natural hash ID (Pattern 2)
- `collection.upsert()` — ChromaDB never duplicates (Pattern 3)
- `_id_exists()` skip — don't re-embed what's already there (Pattern 4)

**ALT webhook handlers** (GHL + Bland.ai):
- `webhook_id` and `call_id` used as natural keys
- Same call fires twice → second one is a silent no-op

**ai-ops email sync**:
- `message-ID` dedup via SQLite — 0 duplicates in production

35 agents, 3 platforms. Idempotency is in all of them.
Not because I'm disciplined — because production forced me to learn.

---

## Slide 9 — SIGNATURE + CTA

AI can automate the pipeline.
It can't protect the pipeline from itself.

That part's on you.

**Comment IDEM** and I'll send you the full 4-pattern reference —
with code snippets, the design checklist, and the 7 gotchas to avoid.

→ Save this for the next time a webhook fires twice.
→ Follow for systems that actually hold up in production.
