# Image Prompts — Post 12b: Idempotency (Angle C — 4 Patterns)

**Post number:** 12b
**Visual theme:** Decision tree / pattern selector / engineering reference card
**Date:** 2026-05-06
**Model:** Nano Banana (via Gemini)
**Format:** 1080x1350 (4:5)

---

## Cover Image (Slide 1)

**Prompt:**

Dark tech poster, 1080x1350, portrait. Background: deep blue-black (#0D1117). Dark grid overlay at 10% opacity.

Center: four numbered cards stacked in a 2x2 grid layout, each with a bright electric-blue (#58A6FF) number label:

- Card 1: "Idempotency Key"
- Card 2: "Natural Unique ID"
- Card 3: "Upsert"
- Card 4: "State Check"

Each card has a dark navy (#0D1B2A) background with thin electric-blue border. Card labels in soft white (#E6EDF3) monospace font.

A bright green (#3FB950) dashed arrow points from a central label "RETRY →" to the 2x2 grid, implying the patterns handle the retry.

Top of image — bold white headline in two lines:
Line 1: "Your pipeline will retry."
Line 2: "Pick one of these 4 patterns."

Bottom: "@frederickklindt" in small electric-blue terminal font.

No faces, no logos, no stock imagery. Clean, reference-card aesthetic.

---

## Inner Slide — Slide 3 (Pattern 1: Idempotency Key)

**Prompt:**

Dark tech UI diagram, 1080x1350. Background: #0D1117. Grid overlay 10%.

Two labeled boxes side by side connected by arrows:

Left box (electric blue border, header "CLIENT"):
- Step 1: "generate uuid4()"
- Step 2: "attach to request header"
- Arrow down + right

Center: dashed horizontal arrow labeled in white monospace: `Idempotency-Key: a3f7c9d1-...`

Right box (bright green border, header "SERVER"):
- "Check cache for key"
- Green branch "FOUND →" → "Return cached result"
- Blue branch "NEW →" → "Process + cache 24h"

Top header: "PATTERN 1 — IDEMPOTENCY KEY" in white.
Bottom right corner: small tag "@frederickklindt".

---

## Inner Slide — Slide 6 (Decision Framework)

**Prompt:**

Dark terminal-style checklist card, 1080x1350. Background: #0D1117. Subtle grid at 10%.

A vertical stack of 5 checkbox rows, each in monospace soft white text:

```
□ Can this fire more than once?
□ Natural unique ID in payload?
   YES → Pattern 2
   NO  → Pattern 1
□ Writing to a database?
   YES → Pattern 3 (upsert)
□ State transition?
   YES → Pattern 4
□ Costs money per call?
   MANDATORY → add idempotency
```

Checkboxes as glowing electric-blue squares. YES/NO branch arrows in bright green. MANDATORY label in bold red-orange (#FF6B6B) for emphasis.

Header: "THE CHECKLIST" in electric blue.
Bottom: "@frederickklindt".

---

## Inner Slide — Slide 8 (Proof Table)

**Prompt:**

Dark data table layout, 1080x1350. Background: #0D1117.

A two-column table with electric-blue (#58A6FF) header row:
Column 1: "SYSTEM" — Column 2: "PATTERNS USED"

Rows in soft white (#E6EDF3):
- inbox-intel → P2 + P3 + P4
- ALT Webhooks (GHL + Bland) → P2
- ai-ops email sync → P2
- ChromaDB ingestion → P3

Each row separated by a subtle dark-navy horizontal rule. Bright green (#3FB950) dot indicator at the start of each row.

Below the table: a bold white counter — "35 agents. 3 platforms. All idempotent."

Bottom: "@frederickklindt".
