# Carousel 12c — How I Made 35 Agents Idempotent

**Angle:** E — Proof / Personal Story
**Post number:** 12c
**Keyword CTA:** IDEM
**Category:** Systems / Builds — Meta/Growth
**Date:** 2026-05-06

---

## Slide 1 — HOOK

**35 agents. 3 platforms. 254+ commits.**

Every single system I've shipped
handles what happens when the same operation fires twice.

Not because I planned it from day one.

Because production taught me the word
no one says out loud in AI builder spaces:

**Idempotency.**

---

## Slide 2 — THE INCIDENT THAT TAUGHT ME

Early on: a webhook handler with no dedup logic.

External service retried on a timeout.
Same call. 5 seconds later.
Two records created. Two emails sent.

The code was correct.
The system wasn't designed for reality.

Reality: **networks retry. always.**

Idempotent = same result, no matter how many times you run it.
After that incident, this became a constraint in everything I build.

---

## Slide 3 — SYSTEM 1: INBOX-INTEL

**My AI email + meeting pipeline. Three patterns in one system.**

→ **Pattern 2 — Natural ID:**
`stable_doc_id()` hashes message_id + source + date.
Same email ingested twice → same ID → upsert, not duplicate.

→ **Pattern 3 — Upsert:**
`collection.upsert()` in ChromaDB.
Re-run the ingestion pipeline → same vectors, no bloat.

→ **Pattern 4 — State check:**
`_id_exists()` skips re-embedding before calling OpenAI.
Already embedded? Skip. Save the tokens. Save the money.

One pipeline. Three layers of protection.

---

## Slide 4 — SYSTEM 2: ALT WEBHOOK HANDLERS

**GHL + Bland.ai calling my endpoints. Both retry.**

GoHighLevel retries on timeout.
Bland.ai retries on non-2xx.

My handler extracts `webhook_id` or `call_id` from the payload.
Checks: processed this before?

YES → return 200. Silent no-op.
NO → process + store ID.

The caller gets its confirmation.
My system never double-processes.

This is Pattern 2 — and it's the first thing I wire up
in any new webhook handler before writing the business logic.

---

## Slide 5 — SYSTEM 3: AI-OPS EMAIL SYNC

**Daily email sync to a local SQLite cache.**

Gmail and Outlook both provide `message-ID` in headers.
Stable. Unique. Perfect natural key.

Before inserting anything:
```python
if message_id in already_synced:
    continue
```

0 duplicates across months of daily syncs.
No complex infrastructure. Just one check.

Pattern 2 again — because the data already had the answer.

---

## Slide 6 — THE DECISION FRAMEWORK I USE NOW

Before writing any new endpoint, handler, or job:

```
□ Can this fire more than once for the same operation?
□ Is there a natural unique ID in the payload?
  YES → Pattern 2 (natural key dedup)
  NO  → Pattern 1 (client generates UUID)
□ Am I writing to a database?
  YES → Pattern 3 (upsert, not insert)
□ Is this a state transition?
  YES → Pattern 4 (check before acting)
□ Does this make an API call I pay for?
  MANDATORY → add idempotency. No exceptions.
```

10 minutes upfront.
Prevents hours of incident cleanup.

---

## Slide 7 — MYTH / SHIFT

**"This is backend stuff. Not relevant for AI builders."**

If you're building agents — you ARE the backend.

Your agent calls a webhook → retries happen.
Your pipeline runs on a cron → overlaps happen.
Your LLM call fails → you retry → you pay twice.

There's no separate "backend team" to handle this.
You're it.

The builders who ship stable systems
aren't the ones with more infrastructure.
They're the ones who understood the constraints early.

---

## Slide 8 — WHAT CHANGED AFTER I INTERNALIZED THIS

Before: build fast, fix bugs when they hit production.
After: 10-minute checklist before every handler.

Not slower. Just deliberate about one thing.

The result: 35 agents running across 3 platforms
with no duplicate records, no double-charges,
no "why did this email go out three times?" incidents.

Clean data in. Clean data out.
Every time. Even on the retries you don't see.

---

## Slide 9 — SIGNATURE + CTA

AI can build the agent.
It can't design the system that keeps the agent honest.

That judgment — knowing what breaks in production
and building around it before it breaks —
that's the part that's still yours.

**Comment IDEM** and I'll send you my full 4-pattern reference —
with real code from my systems, the checklist I use,
and the 7 gotchas that will bite you if you don't know them.

→ Save this. The incident it prevents is real.
→ Follow for systems that hold up — not just demos that look good.
