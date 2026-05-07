# Image Prompts — Post 12c: Idempotency (Angle E — 35 Agents Story)

**Post number:** 12c
**Visual theme:** System map / multi-system architecture / builder's war room
**Date:** 2026-05-06
**Model:** Nano Banana (via Gemini)
**Format:** 1080x1350 (4:5)

---

## Cover Image (Slide 1)

**Prompt:**

Dark tech illustration, 1080x1350, portrait. Background: deep blue-black (#0D1117) with cosmic variant (faint deep-navy purple, subtle star scatter) — cover only.

Center: a glowing node diagram. Three large labeled nodes connected by electric-blue (#58A6FF) lines:
- Node 1: "inbox-intel" 
- Node 2: "ALT Webhooks"
- Node 3: "ai-ops"

Each node is a dark-navy hexagon with a bright green (#3FB950) "✓ IDEMPOTENT" badge at the bottom corner.

Above the diagram: large white bold counter text — "35 agents. 3 platforms."

Below the diagram: electric-blue subheader — "One concept. Baked into all of them."

Bottom: "@frederickklindt" tag in terminal font.

No faces, no logos, no stock imagery. Architecture-diagram aesthetic with warm avatar color hints optional in the node glows.

---

## Inner Slide — Slide 3 (inbox-intel system)

**Prompt:**

Dark terminal log UI, 1080x1350. Background: #0D1117. Grid overlay 10%.

A single system card titled "inbox-intel" in electric-blue (#58A6FF) with three stacked log entries:

Entry 1 — green indicator dot:
Label: "PATTERN 2" | Description: "stable_doc_id() → hash of message_id + source + date"

Entry 2 — green indicator dot:
Label: "PATTERN 3" | Description: "collection.upsert() → ChromaDB, never duplicates"

Entry 3 — green indicator dot:
Label: "PATTERN 4" | Description: "_id_exists() → skip re-embed, save tokens + money"

Each entry has a thin dark-navy separator. Monospace white text throughout.

Bottom of card: a subtle bright green "3 LAYERS OF PROTECTION" badge.

Header above card: "HOW IT LOOKS IN A REAL SYSTEM" in muted blue.
Bottom: "@frederickklindt".

---

## Inner Slide — Slide 4 (ALT Webhooks)

**Prompt:**

Dark tech sequence diagram, 1080x1350. Background: #0D1117.

A vertical timeline / flow with two columns:

Left column header: "CALLER (GHL / Bland)" — dark navy box, electric-blue border.
Right column header: "MY HANDLER" — dark navy box, bright green border.

Step 1 row:
Left: "fires webhook"  →  Right: "extract webhook_id"

Step 2 row:
Left: ""  →  Right: "check: seen before?"

Step 3a (green path, label "YES"):
Right: "return 200. silent no-op."

Step 3b (blue path, label "NO"):
Right: "process + store ID"

Step 4 row:
Left: "retries (timeout)"  →  Right: "return 200 again. still no-op."

All text in soft white (#E6EDF3) monospace. Green for the YES path arrows. Electric blue for NO path. Red-orange (#FF6B6B) small label on LEFT: "RETRIES AUTOMATICALLY."

Header: "PATTERN 2 IN PRODUCTION" in white.
Bottom: "@frederickklindt".

---

## Inner Slide — Slide 8 (Before / After)

**Prompt:**

Dark split-panel layout, 1080x1350. Background: #0D1117.

Left panel (slightly red-tinted dark border, header "BEFORE" in red-orange #FF6B6B):
- "Build fast"
- "Fix duplicates in prod"
- "Explain to users why they got charged twice"
- "Hours of incident cleanup"

Right panel (bright green border, header "AFTER" in #3FB950):
- "10-min checklist per handler"
- "0 duplicate records"
- "0 double-charges"
- "0 unexpected email blasts"

Center divider: vertical electric-blue (#58A6FF) line with a small lightning bolt icon in the middle.

Below both panels: bold white text centered — "Same time to build. Different results in production."

Header: "WHAT CHANGED" in muted white.
Bottom: "@frederickklindt".
