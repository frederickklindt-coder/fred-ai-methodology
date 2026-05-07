# Caption 12c — How I Made 35 Agents Idempotent

**Angle:** E — Proof / Personal Story
**Post number:** 12c
**Keyword CTA:** IDEM
**Date:** 2026-05-06

---

## Caption

A webhook fired twice in production. Two records created. Two emails sent.

The code was fine. The system wasn't designed for reality.

That incident is the reason every agent I've shipped since then handles the retry — whether the caller knows it or not.

The word: **idempotency.** Same result, no matter how many times you run it.

Here's how it shows up across my stack:

→ **inbox-intel:** `stable_doc_id()` as natural hash key + `collection.upsert()` in ChromaDB + `_id_exists()` skip before calling OpenAI. Three patterns in one pipeline.

→ **ALT webhook handlers (GHL + Bland):** `webhook_id` and `call_id` as natural dedup keys. Same call fires twice → second one is a silent 200. Caller satisfied. System untouched.

→ **ai-ops email sync:** `message-ID` header → SQLite dedup. Zero duplicate records across months of daily syncs.

35 agents. 3 platforms. All idempotent.

Not because I'm disciplined. Because one incident taught me that "it worked in testing" is not enough.

Production retries. Your systems need to be ready.

Comment **IDEM** and I'll send you the full 4-pattern reference — with code from my real systems, the checklist I use before every new handler, and the 7 gotchas that catch most people.

Follow if you want to see how production AI systems are actually built.

#buildinpublic #aibuilder #aiagents #systemsthinking #softwareengineering #webhooks #aipipeline #productionready #aiengineer #automation #aitools #devtips #backenddev #aiops #nocode

---

## Alt Hooks

- "35 agents. 3 platforms. Every single one handles what happens when it fires twice."
- "A webhook double-fired in production. Here's the one concept I've applied to every system since."
- "I learned idempotency from an incident. You don't have to."
