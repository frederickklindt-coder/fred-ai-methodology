# Caption 12b — Idempotency: 4 Patterns, Pick One

**Angle:** C — Framework / Actionable
**Post number:** 12b
**Keyword CTA:** PATTERNS
**Date:** 2026-05-06

---

## Caption

Your pipeline will retry. Your webhook will fire twice. Your cron will overlap.

You can't stop that. Networks don't care about your code.

What you CAN do: design operations that produce the same result no matter how many times they run.

That property has a name. **Idempotency.**
And there are exactly 4 patterns to get there — pick the one that fits your situation:

**Pattern 1 — Idempotency Key**
Client generates a UUID. Server caches result for 24h. On retry → return cache, no reprocessing.
Use when: you're creating something new with no natural ID (orders, charges, subscriptions).

**Pattern 2 — Natural Unique ID**
Your payload already has the key. `event_id`, `message_id`, `webhook_id`.
Check if you've seen it. If yes → return 200, do nothing. If no → process + store.
This is the most underused pattern. Most of the time, the data already has the answer.

**Pattern 3 — Upsert**
Update if exists. Insert if not. Inherently idempotent.
Use `collection.upsert()` not `collection.add()`. One line change. Total protection.

**Pattern 4 — State Check**
If it's already cancelled, archived, or sent — return early.
"Ensure this state exists" is safer than "do this action."

You won't need all 4 in every system. But you'll need at least one in every system that matters.

Comment **PATTERNS** and I'll send you the full reference with code snippets, the design checklist, and 7 production gotchas.

Save this for your next deployment.

#aibuilder #systemsthinking #aiagents #webhooks #softwareengineering #automation #aipipeline #backenddev #buildinpublic #aiengineer #devtips #nocode #aitools #productionready #aiops

---

## Alt Hooks

- "There are 4 ways to make an operation safe to retry. Most builders know 0 of them."
- "Networks retry. That's a guarantee. Here are the 4 patterns that protect your pipeline."
- "Pick one: idempotency key, natural ID, upsert, or state check. All 4 on the next slide."
