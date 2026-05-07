# Carousel 12b — Idempotency: 4 Patterns, Pick One

**Angle:** C — Framework / Actionable
**Post number:** 12b
**Keyword CTA:** PATTERNS
**Category:** Systems / Builds
**Date:** 2026-05-06

---

## Slide 1 — HOOK

**Your pipeline will retry.**
**Your webhook will fire twice.**
**Your cron will overlap.**

Networks guarantee it. You can't prevent the retry.

But you can make sure running twice
produces the same result as running once.

There are exactly **4 patterns** to do that.
Pick the one that fits. Ship it today.

---

## Slide 2 — THE CONCEPT IN ONE LINE

**Idempotent** = same result, no matter how many times you run it.

This is not a backend-only concept.
If you're building AI agents, automations, or pipelines —
**you are writing operations that will retry.**

The question isn't *if* you need this.
It's **which pattern** to reach for.

---

## Slide 3 — PATTERN 1: IDEMPOTENCY KEY

**When to use:** No natural unique ID exists. You're creating something new (order, subscription, charge).

**How it works:**
1. Client generates a UUID before the request
2. Sends it as a header: `Idempotency-Key: <uuid>`
3. Server caches `{key → result}` for a time window (24h is standard)
4. On retry → return cached result, no reprocessing

**Real example:** Every Stripe payment call.
POST is not idempotent by default — money cannot be safely retried without a key.

→ Use when: client has no stable ID for the operation

---

## Slide 4 — PATTERN 2: NATURAL UNIQUE ID

**When to use:** The source already gives you an ID. Use it.

`event_id`, `message_id`, `webhook_id`, `file_checksum` — these are your keys.

**How it works:**
```
1. Extract the ID from the payload
2. Check: have I already processed this ID?
3. YES → acknowledge, return 200, do nothing
4. NO  → process + store the ID
```

**The rule:** Before you write a single line of handler logic,
ask — *does this payload contain a stable, unique identifier?*

If yes → you're 80% done with idempotency. Use it.

→ Use when: source provides a stable ID (Stripe, GHL, Bland, Gmail, Outlook, ReadAI)

---

## Slide 5 — PATTERN 3: UPSERT INSTEAD OF INSERT

**When to use:** You're writing to a database and you have a stable ID.

`UPSERT` = update if exists, insert if not.
Inherently idempotent for "make this row/document look like X."

```python
# ChromaDB — never duplicates, no matter how many times
collection.upsert(ids=[doc_id], documents=[text], metadatas=[meta])

# SQL — same idea
INSERT INTO users (id, name) VALUES (42, 'Fred')
ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;
```

The operation becomes: **"ensure this state exists."**
Running it 5 times produces the same result as running it once.

→ Use when: you have a stable ID and the goal is "make this row exist with these values"

---

## Slide 6 — PATTERN 4: STATE CHECK BEFORE ACTION

**When to use:** The operation is a state transition with a clear terminal state.

Before doing the work — check if it's already done.

```python
def cancel_order(order_id):
    order = db.get(order_id)
    if order.status == "cancelled":
        return  # Already there. Nothing to do.
    order.status = "cancelled"
    db.save(order)
```

This is also why `DELETE /resource/42` is idempotent by convention —
the second call sees "already gone" and is a no-op.

→ Use when: the operation moves something to a known end-state (cancel, archive, mark-as-sent, disable)

---

## Slide 7 — MYTH / SHIFT

**"I'll add idempotency later when it becomes a problem."**

Here's the problem: when it becomes a problem,
it's a user who got charged twice.
A message that went out three times.
An embedding job that cost $40 instead of $4.

Idempotency is not a refactor.
It's a constraint you bake in at the start —
the same way you don't add authentication "later."

The 4 patterns take 10 minutes to implement.
The incident they prevent takes 10 hours to clean up.

---

## Slide 8 — PROOF / STORY

I didn't learn this from a textbook.
I learned it when a webhook fired twice in production.

Now it's a default in everything I ship:

| System | Pattern Used |
|--------|-------------|
| inbox-intel (email pipeline) | P2 + P3 + P4 |
| ALT webhook handlers (GHL + Bland) | P2 |
| ai-ops email sync | P2 (SQLite dedup) |
| ChromaDB ingestion | P3 (upsert) |

35 agents. 3 platforms.
Every one of them handles the retry.

Pick your pattern. Ship it before the incident — not after.

---

## Slide 9 — SIGNATURE + CTA

AI can automate your pipeline.

The pipeline still needs to be designed by someone
who understands what happens when things go wrong.

That part doesn't get automated away.

**Comment PATTERNS** and I'll send you the full reference —
4 patterns with code snippets, the design checklist,
and the 7 production gotchas to watch for.

→ Save this. You'll need it before your next deployment.
→ Follow for systems thinking, not AI hype.
