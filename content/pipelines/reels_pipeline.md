# Pipeline: Instagram Reels (30–60s clips)

From podcast episode or standalone idea to published Reel — every stage, every agent, every file.

**Key difference:** Reels have TWO entry points — chopped from a podcast or created standalone.

---

## Visual Pipeline — Path A: Chopped from Podcast

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                        STAGE 1: CLIP IDENTIFICATION                         ║
║                        ⏱ ~3 min (already done by podcast-scripter)          ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   The @podcast-scripter already flagged the best clips:                      ║
║                                                                              ║
║   📄 content/podcast_scripts/XX_slug.md                                      ║
║   └─ ## Production Notes                                                     ║
║      └─ Key quotes for IG clip extraction:                                   ║
║         • "[Quote 1]" (timestamp ~3:45)                                      ║
║         • "[Quote 2]" (timestamp ~11:20)                                     ║
║         • "[Quote 3]" (timestamp ~16:05)                                     ║
║                                                                              ║
║   Fred tells @pauli:                                                         ║
║   "Chop reels from episode XX"                                               ║
║           │                                                                  ║
║           ▼                                                                  ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │                                        ║
║   │                                 │  Reads the script's flagged quotes     ║
║   │   Classifies as: IDEA → Reel   │  Identifies 2–3 best clip moments      ║
║   │   (from existing podcast)       │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║        ◆ FRED PICKS ◆                                                        ║
║        Which quotes become Reels                                             ║
║        (usually 1–2 per episode)                                             ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 2: CLIP SCRIPT                              ║
║                  │         ⏱ ~5 min (AI)                                     ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   FOR EACH CLIP:                                                             ║
║                                                                              ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @pauli runs inline         │  No separate agent needed —            ║
║   │      (or @ideas-translator      │  Pauli handles this directly:          ║
║   │       for standalone reels)     │                                        ║
║   │                                 │  Produces per clip:                    ║
║   │  INPUT:                         │                                        ║
║   │  • Quote + surrounding context  │  ┌──────────────────────┐              ║
║   │  • Episode topic                │  │ REEL CLIP SCRIPT     │              ║
║   │  • Target: 30s or 60s           │  │                      │              ║
║   │                                 │  │ Hook (first 3s):     │              ║
║   │                                 │  │ "[provocative line]" │              ║
║   │                                 │  │                      │              ║
║   │                                 │  │ Body (25–50s):       │              ║
║   │                                 │  │ [the key argument/   │              ║
║   │                                 │  │  insight condensed]  │              ║
║   │                                 │  │                      │              ║
║   │                                 │  │ Punchline (5s):      │              ║
║   │                                 │  │ "[mic drop or        │              ║
║   │                                 │  │  question to viewer]"│              ║
║   │                                 │  └──────────────────────┘              ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @caption-writer            │                                        ║
║   │                                 │                                        ║
║   │  INPUT:                         │                                        ║
║   │  • Clip script                  │                                        ║
║   │  • type: reel                   │                                        ║
║   │  • Source episode ref           │                                        ║
║   │                                 │                                        ║
║   │  OUTPUT:                        │                                        ║
║   │  📄 content/captions/           │                                        ║
║   │     reel_XX_clip_N_caption.md   │                                        ║
║   │                                 │                                        ║
║   │  Contains:                      │                                        ║
║   │  • Short caption (80–120 words) │                                        ║
║   │  • Hook line                    │                                        ║
║   │  • CTA: "Full episode → link    │                                        ║
║   │    in bio" or "Follow for more" │                                        ║
║   │  • 10–15 hashtags               │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 3: CLIP EXTRACTION + EDIT                   ║
║                  │         ⏱ ~10 min per clip (MANUAL)                       ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌───────────────────────────────────────────┐                              ║
║   │   MANUAL: CapCut Desktop (FREE)            │                              ║
║   │                                             │                              ║
║   │ 1. Open the full episode MP4                │                              ║
║   │    (video/XX_slug_episode.mp4)              │                              ║
║   │                                             │                              ║
║   │ 2. Locate timestamp from script             │                              ║
║   │    (e.g., ~3:45)                            │                              ║
║   │                                             │                              ║
║   │ 3. Cut 30–60s clip around the quote         │                              ║
║   │                                             │                              ║
║   │ 4. REFORMAT for Reels:                      │                              ║
║   │    • Change aspect ratio to 9:16            │                              ║
║   │      (1080 × 1920)                          │                              ║
║   │    • Zoom/crop the background art           │                              ║
║   │    • Re-enable auto-captions                │                              ║
║   │      (large text, center screen)            │                              ║
║   │                                             │                              ║
║   │ 5. Add hook text overlay for first 3s       │                              ║
║   │    (from clip script hook line)             │                              ║
║   │                                             │                              ║
║   │ 6. Export as MP4 (1080 × 1920)              │                              ║
║   │                                             │                              ║
║   │ 📁 video/reels/reel_XX_clip_N.mp4           │                              ║
║   └───────────────────────┬─────────────────────┘                              ║
║                           │                                                  ║
║   ┌───────────────────────┘                                                  ║
║   │   ALT: Opus Clip ($15/mo — Phase 2)                                      ║
║   │   Upload full episode → AI auto-extracts                                 ║
║   │   best 30–60s clips → download + tweak                                   ║
║   │   (Saves ~10 min per clip)                                               ║
║                                                                              ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 4: PUBLISH REEL                             ║
║                  │         ⏱ ~3 min per reel (MANUAL)                        ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌──────────────────────────────────┐                                       ║
║   │   MANUAL: Instagram              │                                       ║
║   │                                  │                                       ║
║   │ 1. New Reel → upload MP4         │                                       ║
║   │ 2. Paste caption from            │                                       ║
║   │    reel_XX_clip_N_caption.md     │                                       ║
║   │ 3. Add hashtags                  │                                       ║
║   │ 4. Add cover frame (auto or pick)│                                       ║
║   │ 5. Post                          │                                       ║
║   └──────────────────────────────────┘                                       ║
║                                                                              ║
║   TIMING STRATEGY:                                                           ║
║   • Post Reel 1-2 days AFTER the full episode goes live                      ║
║   • Space clips 2-3 days apart if multiple from same episode                 ║
║   • Reel caption should tease the full episode                               ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## Visual Pipeline — Path B: Standalone Reel (Hot Take / Demo)

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                        STAGE 1: QUICK CAPTURE                               ║
║                        ⏱ ~3 min                                             ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   Triggered by:                                                              ║
║   • AI news / trend Fred wants to react to                                   ║
║   • Quick system demo (screen recording)                                     ║
║   • A "shower thought" that's too short for a carousel                       ║
║   • Before/after comparison                                                  ║
║                                                                              ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │                                        ║
║   │                                 │  "Hot take: [opinion about X]"         ║
║   │   Classifies as: IDEA → Reel   │  or "I want to demo [system]"          ║
║   │   (standalone, not from podcast)│                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║   No full brief needed — Pauli handles directly:                             ║
║                  │                                                            ║
║                  ▼                                                            ║
║   Pauli produces:                                                            ║
║   ┌──────────────────────────────────────┐                                   ║
║   │  REEL SCRIPT (inline, not saved)     │                                   ║
║   │                                      │                                   ║
║   │  Structure (60s max):                │                                   ║
║   │  0–3s:  HOOK (bold statement/        │                                   ║
║   │         question on screen)          │                                   ║
║   │  3–15s: PROBLEM (what most people    │                                   ║
║   │         get wrong)                   │                                   ║
║   │  15–40s: TURNING POINT (the insight, │                                   ║
║   │          system, or demo)            │                                   ║
║   │  40–55s: RESULT (what changed,       │                                   ║
║   │          the proof)                  │                                   ║
║   │  55–60s: CTA (comment keyword        │                                   ║
║   │          or follow)                  │                                   ║
║   └──────────────────────────────────────┘                                   ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 2: PRODUCTION                               ║
║                  │         ⏱ ~5 min (AI) + ~10 min (Fred)                    ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌──────────────────────┐                                                   ║
║   │    @caption-writer   │                                                   ║
║   │    type: reel        │                                                   ║
║   │                      │                                                   ║
║   │    OUTPUT:            │                                                   ║
║   │    📄 content/captions│                                                   ║
║   │    /reel_standalone_  │                                                   ║
║   │    XX_caption.md     │                                                   ║
║   └──────────┬───────────┘                                                   ║
║              │                                                               ║
║              ▼                                                               ║
║   Fred records (pick one):                                                   ║
║                                                                              ║
║   ┌────────────────┐  ┌────────────────┐  ┌────────────────┐                ║
║   │ Screen record  │  │ Talk to camera │  │ Audio + static  │                ║
║   │ (demo/system)  │  │ (hot take)     │  │ art (like pod)  │                ║
║   │                │  │                │  │                 │                ║
║   │ Phone or OBS   │  │ Phone vertical │  │ ElevenLabs or   │                ║
║   │ → trim in      │  │ → natural,     │  │ record voice    │                ║
║   │   CapCut       │  │   unscripted   │  │ → CapCut +      │                ║
║   │                │  │   feel         │  │   Gemini art     │                ║
║   └────────┬───────┘  └────────┬───────┘  └────────┬────────┘                ║
║            └─────────────┬─────┘                    │                        ║
║                          │◄─────────────────────────┘                        ║
║                          ▼                                                   ║
║   ┌──────────────────────────────────┐                                       ║
║   │   MANUAL: CapCut Mobile/Desktop  │                                       ║
║   │                                  │                                       ║
║   │ • Add auto-captions (essential)  │                                       ║
║   │ • Add hook text overlay (3s)     │                                       ║
║   │ • Trim to 30–60s                 │                                       ║
║   │ • Export 1080×1920               │                                       ║
║   └──────────────┬───────────────────┘                                       ║
║                  │                                                            ║
║                  ▼                                                            ║
║   📁 video/reels/reel_standalone_XX.mp4                                      ║
║                  │                                                            ║
║   ┌──────────────▼───────────────────┐                                       ║
║   │   MANUAL: Instagram → Post Reel  │                                       ║
║   │   Paste caption from file        │                                       ║
║   └──────────────────────────────────┘                                       ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## Pauli's Delivery Checklist — Podcast Clip Reels

```
══════════════════════════════════════════════
🎬 REELS READY: [N] clips from Episode [XX]
══════════════════════════════════════════════

📄 FILES CREATED:

CLIP 1: "[Quote/hook]"
  Script: [inline — see below]
  Caption: → content/captions/reel_XX_clip_1_caption.md
  Timestamp in episode: ~[MM:SS]

CLIP 2: "[Quote/hook]"
  Script: [inline — see below]
  Caption: → content/captions/reel_XX_clip_2_caption.md
  Timestamp in episode: ~[MM:SS]

══════════════════════════════════════════════

🎯 MANUAL STEPS PER CLIP:

□ Open episode video in CapCut Desktop
  → video/XX_slug_episode.mp4

□ Locate timestamp (~MM:SS), cut 30–60s clip

□ Reformat:
  - Aspect ratio → 9:16 (1080×1920)
  - Zoom/crop background art
  - Re-enable large auto-captions (center)
  - Add hook text overlay (first 3s)

□ Export as MP4
  → Save to video/reels/reel_XX_clip_N.mp4

□ Instagram → New Reel → Upload MP4
  → Paste caption from caption file above

□ Post 1-2 days after full episode goes live

══════════════════════════════════════════════
```

## Pauli's Delivery Checklist — Standalone Reel

```
══════════════════════════════════════════════
🎬 STANDALONE REEL READY: "[Topic]"
══════════════════════════════════════════════

📄 FILES CREATED:

1. REEL SCRIPT (60s)
   → [inline in this message]

2. CAPTION
   → content/captions/reel_standalone_XX_caption.md
   Copy → paste into Instagram

══════════════════════════════════════════════

🎯 MANUAL STEPS:

□ Record your reel:
  Option A: Screen record a demo (OBS/phone)
  Option B: Talk to camera (phone, vertical)
  Option C: Record audio + use static art

□ Edit in CapCut:
  - Add auto-captions (essential for Reels)
  - Add hook text overlay (first 3 seconds)
  - Trim to 30–60 seconds
  - Export 1080×1920

□ Instagram → New Reel → Upload
  → Paste caption from file above

══════════════════════════════════════════════
```

---

## Side-by-Side: Both Reel Paths

```
         PATH A: Podcast Clip                PATH B: Standalone
         ═══════════════════                 ═══════════════════

    Podcast episode exists               Fred has a hot take / demo
              │                                     │
              ▼                                     ▼
    Quotes already flagged               @pauli writes 60s script
    in podcast script                    inline (no brief needed)
              │                                     │
              ▼                                     ▼
    @caption-writer                      @caption-writer
    (reel variant)                       (reel variant)
              │                                     │
              ▼                                     ▼
    MANUAL: CapCut                       MANUAL: Record + CapCut
    Cut clip from episode MP4            Create from scratch
    Reformat 16:9 → 9:16                Already 9:16
    Add captions + hook text             Add captions + hook text
              │                                     │
              ▼                                     ▼
    MANUAL: Instagram                    MANUAL: Instagram
    Post Reel + caption                  Post Reel + caption
              │                                     │
              ▼                                     ▼
        ~15 min total                        ~20 min total
```

---

## File Map

```
fred-ai-methodology/
├── content/
│   ├── podcast_scripts/
│   │   └── XX_slug.md                      ← Contains flagged quotes for clips
│   └── captions/
│       ├── reel_XX_clip_1_caption.md       ← Caption for podcast clip reel
│       ├── reel_XX_clip_2_caption.md       ← Caption for podcast clip reel
│       └── reel_standalone_XX_caption.md   ← Caption for standalone reel
├── video/
│   ├── XX_slug_episode.mp4                 ← Source for clip extraction
│   └── reels/
│       ├── reel_XX_clip_1.mp4              ← Podcast clip reel
│       ├── reel_XX_clip_2.mp4              ← Podcast clip reel
│       └── reel_standalone_XX.mp4          ← Standalone reel
└── decisions/
    └── decision_log.md
```

---

## Time Estimates

| Type | AI Time | Manual Time | Total |
|------|---------|-------------|-------|
| Podcast clip reel | ~5 min (script + caption) | ~10 min (cut + edit + post) | **~15 min** |
| Standalone reel | ~3 min (script + caption) | ~15 min (record + edit + post) | **~20 min** |

Reels are the **fastest content type** — especially clips from existing podcasts. 2 clips per episode = ~30 min for 2 pieces of content that were already created.
