# Pauli Delivery Protocol

When Pauli finishes producing content through the agent pipeline, she MUST end with a **delivery checklist** that tells Fred exactly what was created and what manual steps remain.

## Why This Matters

Fred (Pauli the person) does the final manual work — generating images in Gemini, assembling in Canva/CapCut, uploading to Instagram/YouTube. She needs to know:
1. **Where every file is** (exact paths)
2. **What to copy-paste where** (which file → which platform field)
3. **What manual steps remain** (in order)

## Delivery Templates by Content Type

### For Carousels

```
══════════════════════════════════════════════
📋 CAROUSEL READY: [Title]
══════════════════════════════════════════════

📄 FILES CREATED:

1. BRIEF
   → content/briefs/XX_slug_brief.md

2. CAROUSEL SLIDES (9 slides)
   → content/carousels/XX_slug.md
   Copy slide text → overlay on images in Canva

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

🎯 MANUAL STEPS:

□ Generate cover image in Gemini (from file 4)
□ Generate inner slides in Gemini (from file 5)
□ Assemble in Canva: text from file 2 + generated images
□ Instagram → New Post → Carousel → Upload 9 slides
□ Paste caption from file 3
□ Post or schedule

══════════════════════════════════════════════
```

### For Podcast Episodes

```
══════════════════════════════════════════════
🎙️ PODCAST READY: Episode [N] — [Title]
══════════════════════════════════════════════

📄 FILES CREATED:

1. BRIEF → content/briefs/XX_slug_brief.md

2. EPISODE SCRIPT → content/podcast_scripts/XX_slug.md
   Upload to NotebookLM / read aloud / paste to ElevenLabs

3. YT TITLE + DESCRIPTION → content/captions/XX_slug_yt_desc.md
   Copy title → YouTube title field
   Copy description (has timestamps) → YouTube description
   Copy tags → YouTube tags

4. ARTWORK PROMPT → content/image_prompts/podcast_XX_slug.md
   Copy → paste into Gemini → download PNG (1920x1080)

══════════════════════════════════════════════

🎯 MANUAL STEPS:

□ Generate audio (NotebookLM / ElevenLabs / record)
□ Generate artwork in Gemini (from file 4)
□ Assemble in CapCut: audio + art + auto-captions → MP4
□ YouTube Studio → Upload → paste from file 3
□ Use flagged quotes for Reel clips (see script file)

══════════════════════════════════════════════
```

### For Reels (Podcast Clips)

```
══════════════════════════════════════════════
🎬 REELS READY: [N] clips from Episode [XX]
══════════════════════════════════════════════

CLIP 1: "[Hook line]"
  Caption → content/captions/reel_XX_clip_1_caption.md
  Timestamp: ~[MM:SS] in episode video

CLIP 2: "[Hook line]"
  Caption → content/captions/reel_XX_clip_2_caption.md
  Timestamp: ~[MM:SS]

══════════════════════════════════════════════

🎯 PER CLIP:

□ Open episode MP4 in CapCut → locate timestamp
□ Cut 30–60s → reformat to 9:16 (1080×1920)
□ Add large auto-captions + hook text overlay
□ Export → Instagram → New Reel → paste caption

══════════════════════════════════════════════
```

### For Standalone Reels

```
══════════════════════════════════════════════
🎬 REEL READY: "[Topic]"
══════════════════════════════════════════════

SCRIPT: [inline — 60s structure]
CAPTION → content/captions/reel_standalone_XX_caption.md

══════════════════════════════════════════════

🎯 MANUAL:

□ Record (screen demo / camera / audio + art)
□ Edit in CapCut: captions + hook overlay + trim
□ Instagram → New Reel → paste caption

══════════════════════════════════════════════
```

## Rules

- **Always include exact file paths** — no vague references
- **Always list manual steps in order** — she follows them top to bottom
- **Always specify what to copy where** — "copy from file 3 → paste into Instagram caption field"
- **Number the files** so she can reference them easily ("from file 4")
- Full pipeline details: `content/pipelines/carousel_pipeline.md`, `podcast_pipeline.md`, `reels_pipeline.md`
