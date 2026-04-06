# Pipeline: Instagram Carousel

From raw idea to published post — every stage, every agent, every file.

---

## Visual Pipeline

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                        STAGE 1: IDEATION                                    ║
║                        ⏱ ~5 min (Fred) + ~3 min (AI)                       ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   Fred dumps raw idea                                                        ║
║   (Google Keep, voice note, chat, brain dump)                                ║
║           │                                                                  ║
║           ▼                                                                  ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │  "I have this idea about..."           ║
║   │   Classifies as: IDEA → Content │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @content-angles            │  Debates the idea                      ║
║   │                                 │  Suggests 6 category angles            ║
║   │  OUTPUT:                        │  Picks strongest angle                 ║
║   │  • Recommended angle            │  Drafts 3 hook variations              ║
║   │  • 3 hook options               │  Flags if weak or duplicate            ║
║   │  • Golden Rule variation        │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║        ◆ FRED DECIDES ◆                                                      ║
║        Pick angle + hook                                                     ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 2: STRUCTURING                              ║
║                  │         ⏱ ~3 min (AI)                                     ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @ideas-translator          │                                        ║
║   │                                 │  Produces structured YAML brief:       ║
║   │  INPUT:                         │  • content_type: carousel              ║
║   │  • Raw idea + chosen angle      │  • audience segment                    ║
║   │  • Chosen hook                  │  • key_points (4-5)                    ║
║   │  • Fred's notes                 │  • myth_or_contrast                    ║
║   │                                 │  • proof_element                       ║
║   │  OUTPUT:                        │  • cta keyword                         ║
║   │  📄 content/briefs/             │  • lead_magnet potential               ║
║   │     XX_slug_brief.md            │  • execution_plan (which agents next)  ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║        ◆ FRED REVIEWS BRIEF ◆                                                ║
║        Adjust points, confirm                                                ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 3: PRODUCTION                               ║
║                  │         ⏱ ~10 min (AI) — Pauli runs 3 agents              ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │  Reads the brief                       ║
║   │   Executes the plan:            │  Calls agents in order:                ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║          ┌───────┴────────┐                                                  ║
║          ▼                │                                                  ║
║   ┌──────────────────┐    │                                                  ║
║   │ @carousel-writer │    │                                                  ║
║   │                  │    │                                                  ║
║   │ INPUT:           │    │                                                  ║
║   │ • Brief YAML     │    │                                                  ║
║   │ • Persona context│    │                                                  ║
║   │                  │    │                                                  ║
║   │ OUTPUT:          │    │  9 slides:                                       ║
║   │ 📄 content/      │    │  1. Hook / Cover                                ║
║   │  carousels/      │    │  2–6. Value (one insight each)                   ║
║   │  XX_slug.md      │    │  7. Myth break                                   ║
║   │                  │    │  8. Proof / story                                ║
║   │                  │    │  9. CTA + Golden Rule                            ║
║   └────────┬─────────┘    │                                                  ║
║            │              │                                                  ║
║            ▼              ▼                                                  ║
║   ┌──────────────┐ ┌──────────────┐                                          ║
║   │@caption-     │ │@image-       │  ← These run in PARALLEL                 ║
║   │ writer       │ │ prompter     │                                          ║
║   │              │ │              │                                          ║
║   │INPUT:        │ │INPUT:        │                                          ║
║   │• Carousel md │ │• Carousel md │                                          ║
║   │• Brief       │ │• Brief       │                                          ║
║   │• type:       │ │• Style guide │                                          ║
║   │  carousel    │ │              │                                          ║
║   │              │ │OUTPUT:       │                                          ║
║   │OUTPUT:       │ │📄 content/   │                                          ║
║   │📄 content/   │ │ image_prompts│                                          ║
║   │ captions/    │ │ /XX_slug_    │                                          ║
║   │ XX_slug_     │ │ cover.md     │                                          ║
║   │ caption.md   │ │📄 ...XX_slug_│                                          ║
║   │              │ │ inner.md     │                                          ║
║   │Contains:     │ │              │                                          ║
║   │• Hook line   │ │Contains:     │                                          ║
║   │• Value block │ │• Cover prompt│                                          ║
║   │• Proof       │ │  (Gemini)    │                                          ║
║   │• CTA         │ │• Inner slide │                                          ║
║   │• 15-20 #tags │ │  prompts     │                                          ║
║   └──────┬───────┘ └──────┬───────┘                                          ║
║          │                │                                                  ║
╚══════════╪════════════════╪══════════════════════════════════════════════════╝
           │                │
╔══════════╪════════════════╪══════════════════════════════════════════════════╗
║          │                │    STAGE 4: QUALITY CHECK                        ║
║          │                │    ⏱ ~5 min (AI + Fred)                          ║
╠══════════╪════════════════╪══════════════════════════════════════════════════╣
║          ▼                │                                                  ║
║   ┌──────────────┐        │                                                  ║
║   │@caption-     │        │                                                  ║
║   │ critic       │        │                                                  ║
║   │              │        │                                                  ║
║   │Reviews:      │        │                                                  ║
║   │• Tone        │        │                                                  ║
║   │• Scroll-stop │        │                                                  ║
║   │• Authenticity│        │                                                  ║
║   │• CTA quality │        │                                                  ║
║   └──────┬───────┘        │                                                  ║
║          │                │                                                  ║
║          ▼                │                                                  ║
║   ┌──────────────┐        │                                                  ║
║   │@carousel-    │        │                                                  ║
║   │ reviewer     │        │                                                  ║
║   │              │        │                                                  ║
║   │Reviews:      │        │                                                  ║
║   │• Hook power  │        │                                                  ║
║   │• Slide flow  │        │                                                  ║
║   │• Value density│       │                                                  ║
║   │• Proof check │        │                                                  ║
║   │• Fred's voice│        │                                                  ║
║   └──────┬───────┘        │                                                  ║
║          │                │                                                  ║
║   ◆ FRED REVIEWS + EDITS ◆                                                  ║
║   Final tweaks to slides + caption                                           ║
║          │                │                                                  ║
╚══════════╪════════════════╪══════════════════════════════════════════════════╝
           │                │
╔══════════╪════════════════╪══════════════════════════════════════════════════╗
║          │                │    STAGE 5: VISUAL GENERATION                    ║
║          │                │    ⏱ ~15 min (MANUAL)                            ║
╠══════════╪════════════════╪══════════════════════════════════════════════════╣
║          │                ▼                                                  ║
║          │   ┌───────────────────────┐                                       ║
║          │   │   MANUAL: Gemini      │                                       ║
║          │   │                       │                                       ║
║          │   │ 1. Open Google AI     │                                       ║
║          │   │    Studio / Gemini    │                                       ║
║          │   │ 2. Paste cover prompt │                                       ║
║          │   │    from XX_cover.md   │                                       ║
║          │   │ 3. Generate + download│                                       ║
║          │   │ 4. Paste inner slide  │                                       ║
║          │   │    prompts            │                                       ║
║          │   │ 5. Generate + download│                                       ║
║          │   │                       │                                       ║
║          │   │ SAVE TO:              │                                       ║
║          │   │ 📁 images/XX_slug/    │                                       ║
║          │   │   cover.png           │                                       ║
║          │   │   slide_01.png        │                                       ║
║          │   │   slide_02.png ...    │                                       ║
║          │   └───────────┬───────────┘                                       ║
║          │               │                                                   ║
║          │               ▼                                                   ║
║          │   ┌───────────────────────┐                                       ║
║          │   │  MANUAL: Assembly     │                                       ║
║          │   │  (Canva or direct)    │                                       ║
║          │   │                       │                                       ║
║          │   │ • Place text from     │                                       ║
║          │   │   carousel .md on     │                                       ║
║          │   │   each slide image    │                                       ║
║          │   │ • Export as 9 PNGs    │                                       ║
║          │   │   or 1 PDF            │                                       ║
║          │   └───────────┬───────────┘                                       ║
║          │               │                                                   ║
╚══════════╪═══════════════╪═══════════════════════════════════════════════════╝
           │               │
╔══════════╪═══════════════╪═══════════════════════════════════════════════════╗
║          │               │    STAGE 6: PUBLISH                               ║
║          │               │    ⏱ ~5 min (MANUAL)                              ║
╠══════════╪═══════════════╪═══════════════════════════════════════════════════╣
║          │               │                                                   ║
║          │   ┌───────────▼───────────┐                                       ║
║          │   │   MANUAL: Instagram   │                                       ║
║          │   │                       │                                       ║
║          │   │ 1. Upload 9 slides    │                                       ║
║          ├──▶│ 2. Paste caption from │                                       ║
║          │   │    XX_caption.md      │                                       ║
║          │   │ 3. Add hashtags       │                                       ║
║          │   │ 4. Post or schedule   │                                       ║
║          │   └───────────┬───────────┘                                       ║
║          │               │                                                   ║
║          │               ▼                                                   ║
║          │   ┌───────────────────────┐                                       ║
║          │   │   @decision-logger    │                                       ║
║          │   │                       │                                       ║
║          │   │ Logs: what was posted,│                                       ║
║          │   │ which audience, CTA   │                                       ║
║          │   │ keyword, date         │                                       ║
║          │   │                       │                                       ║
║          │   │ 📄 decisions/         │                                       ║
║          │   │    decision_log.md    │                                       ║
║          │   └───────────────────────┘                                       ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## Pauli's Delivery Checklist

When Pauli finishes Stage 3 (Production), she delivers this summary:

```
══════════════════════════════════════════════
📋 CAROUSEL READY: [Title]
══════════════════════════════════════════════

📄 FILES CREATED:

1. BRIEF
   → content/briefs/XX_slug_brief.md

2. CAROUSEL SLIDES (9 slides)
   → content/carousels/XX_slug.md
   Copy slide text to overlay on images

3. CAPTION + HASHTAGS
   → content/captions/XX_slug_caption.md
   Copy full text → paste into Instagram caption field

4. COVER IMAGE PROMPT
   → content/image_prompts/XX_slug_cover.md
   Copy → paste into Gemini → download PNG

5. INNER SLIDE PROMPTS
   → content/image_prompts/XX_slug_inner.md
   Copy each prompt → paste into Gemini → download PNGs

══════════════════════════════════════════════

🎯 MANUAL STEPS REMAINING:

□ Generate cover image in Gemini (paste from file 4)
□ Generate inner slides in Gemini (paste from file 5)
□ Assemble slides in Canva (text from file 2 + images)
□ Open Instagram → New Post → Carousel
□ Upload 9 slides
□ Paste caption from file 3
□ Post or schedule
□ Tell @decision-logger to log it

══════════════════════════════════════════════
```

---

## File Map (Where Everything Lives)

```
fred-ai-methodology/
├── content/
│   ├── briefs/
│   │   └── XX_slug_brief.md          ← Structured brief (YAML)
│   ├── carousels/
│   │   └── XX_slug.md                ← 9-slide text content
│   ├── captions/
│   │   └── XX_slug_caption.md        ← Caption + hashtags
│   ├── image_prompts/
│   │   ├── XX_slug_cover.md          ← Gemini prompt for cover
│   │   └── XX_slug_inner.md          ← Gemini prompts for inner slides
│   └── lead_magnets/
│       └── XX_slug_resource.md       ← (if lead magnet applies)
├── images/
│   └── XX_slug/                      ← Downloaded PNGs from Gemini
│       ├── cover.png
│       ├── slide_01.png
│       └── ...
└── decisions/
    └── decision_log.md               ← Post logged after publish
```

---

## Time Estimate (Total)

| Stage | Who | Time |
|-------|-----|------|
| 1. Ideation | Fred + AI | ~5–8 min |
| 2. Structuring | AI + Fred review | ~3–5 min |
| 3. Production | AI (Pauli runs agents) | ~10 min |
| 4. Quality Check | AI + Fred review | ~5 min |
| 5. Visual Generation | Fred (manual, Gemini) | ~15 min |
| 6. Publish | Fred (manual, Instagram) | ~5 min |
| **Total** | | **~45–50 min per carousel** |
