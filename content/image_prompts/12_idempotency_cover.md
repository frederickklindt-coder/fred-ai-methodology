# Image Prompts — Post 12: Idempotency

**Post number:** 12
**Visual theme:** Circuit safety net / defensive architecture / retry loop
**Date:** 2026-05-06
**Model:** Nano Banana (via Gemini)
**Format:** 1080x1350 (4:5)

---

## Cover Image (Slide 1)

**Prompt:**

Dark tech illustration, 1080x1350, portrait. Background: deep blue-black (#0D1117). 

Center: a large electric-blue (#58A6FF) shield icon built from circuit-board lines and nodes. Inside the shield, a white bold text label reads "IDEMPOTENT" in a terminal monospace font. Below the shield, a faint dashed loop arrow in bright green (#3FB950) curves back around — symbolizing retry loops that resolve to the same result.

Top of image: soft white (#E6EDF3) headline text in two lines:
Line 1: "Your agent ran twice."
Line 2: "Here's what saves you."

Bottom: small electric-blue text tag "@frederickklindt" in terminal/code font.

Atmosphere: calm, technical, slightly ominous — like a system under pressure that holds. No faces, no stock imagery, no logos. Dark grid overlay at 10% opacity on background.

---

## Inner Slide Template — Slide 3 (When You Must Care)

**Prompt:**

Dark tech UI panel, 1080x1350, portrait. Background: #0D1117. Grid overlay at 10% opacity.

Four stacked rows, each as a terminal-style log entry with a bright green (#3FB950) indicator dot on the left:

Row 1: "● Webhook handlers — Stripe, GHL, Bland retry on timeout"
Row 2: "● Background jobs — crons can overlap on restart"
Row 3: "● Message queues — at-least-once is the default"
Row 4: "● AI API calls — every re-run = wasted tokens + money"

Each row has a subtle electric-blue (#58A6FF) horizontal rule separator. Soft white (#E6EDF3) for all text. Monospace/terminal font throughout.

Top: small header label in muted blue: "WHEN YOU MUST CARE"
Bottom: "@frederickklindt" tag.

---

## Inner Slide Template — Slide 4 (Pattern 1: Idempotency Key)

**Prompt:**

Dark tech diagram, 1080x1350. Background: #0D1117.

Center: a two-column flow diagram. 

Left column (CLIENT box, dark navy border, electric blue header):
- "Generate UUID"
- Arrow down: "Attach to request"
- Arrow down: "Send → API"

Right column (SERVER box, dark navy border, bright green header):
- "Check cache for key"
- Arrow: YES branch (green) → "Return cached result"
- Arrow: NO branch (blue) → "Process + cache 24h"

Between the two columns: a dashed horizontal arrow labeled "Idempotency-Key: uuid4()" in monospace white.

Top header in white: "PATTERN 1 — IDEMPOTENCY KEY"
Bottom: "@frederickklindt" tag.

---

## Inner Slide Template — Slide 8 (Proof)

**Prompt:**

Dark tech dashboard layout, 1080x1350. Background: #0D1117.

Three stacked system cards, each with a title in electric blue (#58A6FF) and bullet points in soft white (#E6EDF3):

Card 1 — "inbox-intel"
- stable_doc_id() → Pattern 2
- collection.upsert() → Pattern 3
- _id_exists() skip → Pattern 4

Card 2 — "ALT Webhooks (GHL + Bland)"
- webhook_id → natural key
- double fire → silent no-op

Card 3 — "ai-ops email sync"
- message-ID → SQLite dedup
- 0 duplicates in production

Bottom of each card: a small green "✓ IDEMPOTENT" badge.

Top header: "35 agents. 3 platforms. All idempotent."
Bottom: "@frederickklindt" tag.

No faces, no stock images. Terminal/code aesthetic throughout.
