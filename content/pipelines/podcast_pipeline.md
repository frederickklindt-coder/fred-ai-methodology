# Pipeline: YouTube Podcast (15–20 min)

From AI debate to published episode — every stage, every agent, every file.

---

## Visual Pipeline

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                        STAGE 1: RAW DEBATE                                  ║
║                        ⏱ 20–60 min (Fred + AI — this is the content)        ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   Fred has a philosophical / technical debate                                ║
║   with Claude, ChatGPT, Gemini, or multi-model session                      ║
║                                                                              ║
║   Examples:                                                                  ║
║   • "Is AI creativity real or just remixing?"                                ║
║   • "Should I build agents with code or no-code?"                            ║
║   • "What happens when AI can build AI?"                                     ║
║                                                                              ║
║   ┌─────────────────────────────────┐                                        ║
║   │   Save the raw conversation     │                                        ║
║   │                                 │                                        ║
║   │   Copy/paste full transcript    │                                        ║
║   │   (Fred's prompts + AI         │                                        ║
║   │    responses, all of it)        │                                        ║
║   │                                 │                                        ║
║   │   📄 content/podcast_scripts/   │                                        ║
║   │      XX_slug_raw_transcript.md  │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 2: TRIAGE                                   ║
║                  │         ⏱ ~5 min (Fred + AI)                              ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │                                        ║
║   │                                 │  "I had this debate about [topic],     ║
║   │   Classifies as: IDEA → Content │   is this podcast-worthy?"             ║
║   │   OR: DEBATE → flag for content │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @content-angles            │                                        ║
║   │                                 │  Evaluates:                            ║
║   │  • Is this debate interesting   │  • Does it have real tension?          ║
║   │    enough for 15–20 min?        │  • Do the AIs disagree on something?  ║
║   │  • Which audience cares?        │  • Is Fred's take surprising?          ║
║   │  • Could this also be a         │  • What's the one-line hook?           ║
║   │    carousel? (flag for later)   │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║        ◆ FRED DECIDES ◆                                                      ║
║        "Yes, make this an episode"                                           ║
║        Picks the angle to center on                                          ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 3: STRUCTURING                              ║
║                  │         ⏱ ~3 min (AI)                                     ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @ideas-translator          │                                        ║
║   │                                 │  Produces brief with:                  ║
║   │  INPUT:                         │  • content_type: podcast               ║
║   │  • Debate topic + angle         │  • audience segment                    ║
║   │  • Which AI models were in it   │  • key tension points                  ║
║   │  • Fred's verdict               │  • execution_plan: podcast-scripter    ║
║   │                                 │                                        ║
║   │  OUTPUT:                        │                                        ║
║   │  📄 content/briefs/             │                                        ║
║   │     XX_slug_brief.md            │                                        ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
╚══════════════════╪═══════════════════════════════════════════════════════════╝
                   │
╔══════════════════╪═══════════════════════════════════════════════════════════╗
║                  │         STAGE 4: SCRIPT PRODUCTION                        ║
║                  │         ⏱ ~10 min (AI — Pauli runs agents)                ║
╠══════════════════╪═══════════════════════════════════════════════════════════╣
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │         @pauli                  │  Reads brief + raw transcript          ║
║   │   Executes the plan:            │  Calls agents in order:                ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║                  ▼                                                            ║
║   ┌─────────────────────────────────┐                                        ║
║   │      @podcast-scripter          │                                        ║
║   │                                 │  Transforms messy transcript           ║
║   │  INPUT:                         │  into produced show structure:         ║
║   │  • Raw transcript               │                                        ║
║   │  • Brief                        │  ┌──────────────────────────┐          ║
║   │  • Target: 15 or 20 min         │  │ 0:00  Cold Open (30s)   │          ║
║   │                                 │  │ 0:30  Intro (60s)       │          ║
║   │  OUTPUT:                        │  │ 1:30  Context (2 min)   │          ║
║   │  📄 content/podcast_scripts/    │  │ 3:30  Debate Rounds     │          ║
║   │     XX_slug.md                  │  │       (8–12 min)        │          ║
║   │                                 │  │ 14:00 Fred's Take       │          ║
║   │  Also flags:                    │  │       (2–3 min)         │          ║
║   │  • Best 2-3 quotes for Reels   │  │ 17:00 Builder Takeaway  │          ║
║   │  • Suggested artwork mood       │  │       (1 min)           │          ║
║   │  • Carousel spin-off ideas      │  │ 18:30 Outro (30s)      │          ║
║   │                                 │  └──────────────────────────┘          ║
║   └──────────────┬──────────────────┘                                        ║
║                  │                                                            ║
║          ┌───────┴────────┐                                                  ║
║          ▼                ▼                                                  ║
║   ┌──────────────┐ ┌──────────────┐                                          ║
║   │@caption-     │ │@image-       │  ← Run in PARALLEL                       ║
║   │ writer       │ │ prompter     │                                          ║
║   │              │ │              │                                          ║
║   │INPUT:        │ │INPUT:        │                                          ║
║   │• Script      │ │• Script      │                                          ║
║   │• type:       │ │• type:       │                                          ║
║   │  podcast     │ │  podcast_art │                                          ║
║   │              │ │              │                                          ║
║   │OUTPUT:       │ │OUTPUT:       │                                          ║
║   │📄 content/   │ │📄 content/   │                                          ║
║   │ captions/    │ │ image_prompts│                                          ║
║   │ XX_slug_     │ │ /podcast_    │                                          ║
║   │ yt_desc.md   │ │ XX_slug.md   │                                          ║
║   │              │ │              │                                          ║
║   │Contains:     │ │Contains:     │                                          ║
║   │• YT title    │ │• Episode     │                                          ║
║   │• YT descr.   │ │  artwork     │                                          ║
║   │  w/timestamps│ │  prompt      │                                          ║
║   │• YT tags     │ │  (1920x1080) │                                          ║
║   │• IG clip     │ │• Thumbnail   │                                          ║
║   │  caption     │ │  prompt      │                                          ║
║   └──────┬───────┘ └──────┬───────┘                                          ║
║          │                │                                                  ║
╚══════════╪════════════════╪══════════════════════════════════════════════════╝
           │                │
╔══════════╪════════════════╪══════════════════════════════════════════════════╗
║          │                │    STAGE 5: AUDIO GENERATION                     ║
║          │                │    ⏱ ~15 min (MANUAL)                            ║
╠══════════╪════════════════╪══════════════════════════════════════════════════╣
║          │                │                                                  ║
║          │   Pick ONE audio path:                                            ║
║          │                │                                                  ║
║          │   ┌────────────┴──────────────────────────────────────┐           ║
║          │   │                                                    │           ║
║          │   ▼                        ▼                          ▼           ║
║          │   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐           ║
║          │   │ OPTION A:    │  │ OPTION B:    │  │ OPTION C:    │           ║
║          │   │ NotebookLM   │  │ ElevenLabs   │  │ Fred reads   │           ║
║          │   │ (FREE)       │  │ ($5–22/mo)   │  │ (FREE)       │           ║
║          │   │              │  │              │  │              │           ║
║          │   │Upload script │  │Paste script  │  │Read from     │           ║
║          │   │→ auto-gen    │  │→ voice clone │  │script into   │           ║
║          │   │conversational│  │→ branded     │  │mic           │           ║
║          │   │podcast audio │  │narration     │  │              │           ║
║          │   │              │  │              │  │Most authentic│           ║
║          │   │Fastest,      │  │Most control, │  │but slowest   │           ║
║          │   │least control │  │costs money   │  │              │           ║
║          │   └──────┬───────┘  └──────┬───────┘  └──────┬───────┘           ║
║          │          └────────────┬─────┘                 │                   ║
║          │                      │◄──────────────────────┘                   ║
║          │                      ▼                                            ║
║          │          📁 audio/XX_slug.mp3                                     ║
║          │          (~15–20 min audio file)                                  ║
║          │                      │                                            ║
╚══════════╪══════════════════════╪════════════════════════════════════════════╝
           │                      │
╔══════════╪══════════════════════╪════════════════════════════════════════════╗
║          │                      │    STAGE 6: VIDEO ASSEMBLY                 ║
║          │                      │    ⏱ ~20 min (MANUAL)                      ║
╠══════════╪══════════════════════╪════════════════════════════════════════════╣
║          │                      │                                            ║
║          │   ┌──────────────────▼───────────────┐                            ║
║          │   │   MANUAL: Gemini                  │                            ║
║          │   │                                   │                            ║
║          │   │ Paste artwork prompt from          │                            ║
║          │   │ podcast_XX_slug.md                 │                            ║
║          │   │ → Generate episode art (1920x1080) │                            ║
║          │   │ → Download PNG                     │                            ║
║          │   │                                   │                            ║
║          │   │ 📁 images/podcast_XX/              │                            ║
║          │   │    episode_art.png                 │                            ║
║          │   └──────────────────┬────────────────┘                            ║
║          │                      │                                            ║
║          │                      ▼                                            ║
║          │   ┌──────────────────────────────────┐                            ║
║          │   │   MANUAL: CapCut Desktop (FREE)   │                            ║
║          │   │                                   │                            ║
║          │   │ 1. Import audio (.mp3)            │                            ║
║          │   │ 2. Import episode art (.png)       │                            ║
║          │   │ 3. Set art as background           │                            ║
║          │   │    (static or subtle zoom)         │                            ║
║          │   │ 4. Enable auto-captions            │                            ║
║          │   │ 5. Style captions (white text,     │                            ║
║          │   │    dark outline, bottom third)      │                            ║
║          │   │ 6. Export as MP4 (1920x1080)       │                            ║
║          │   │                                   │                            ║
║          │   │ 📁 video/XX_slug_episode.mp4       │                            ║
║          │   └──────────────────┬────────────────┘                            ║
║          │                      │                                            ║
╚══════════╪══════════════════════╪════════════════════════════════════════════╝
           │                      │
╔══════════╪══════════════════════╪════════════════════════════════════════════╗
║          │                      │    STAGE 7: PUBLISH                        ║
║          │                      │    ⏱ ~10 min (MANUAL)                      ║
╠══════════╪══════════════════════╪════════════════════════════════════════════╣
║          │                      ▼                                            ║
║          │   ┌──────────────────────────────────┐                            ║
║          │   │   MANUAL: YouTube Studio          │                            ║
║          │   │                                   │                            ║
║          │   │ 1. Upload MP4                     │                            ║
║          ├──▶│ 2. Paste title from yt_desc.md    │                            ║
║          │   │ 3. Paste description              │                            ║
║          │   │    (includes timestamps)          │                            ║
║          │   │ 4. Add tags from yt_desc.md       │                            ║
║          │   │ 5. Upload thumbnail               │                            ║
║          │   │    (episode_art.png)              │                            ║
║          │   │ 6. Publish or schedule            │                            ║
║          │   └──────────────────┬────────────────┘                            ║
║          │                      │                                            ║
║          │                      ▼                                            ║
║          │   ┌──────────────────────────────────┐                            ║
║          │   │   @decision-logger                │                            ║
║          │   │                                   │                            ║
║          │   │   Logs: episode topic, audience,  │                            ║
║          │   │   models in debate, date, link    │                            ║
║          │   └──────────────────────────────────┘                            ║
║          │                                                                   ║
║          │   ★ Episode also feeds → REEL PIPELINE                            ║
║          │     (see reels_pipeline.md)                                        ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## Pauli's Delivery Checklist

When Pauli finishes Stage 4 (Script Production), she delivers:

```
══════════════════════════════════════════════
🎙️ PODCAST READY: Episode [N] — [Title]
══════════════════════════════════════════════

📄 FILES CREATED:

1. RAW TRANSCRIPT (archived)
   → content/podcast_scripts/XX_slug_raw_transcript.md

2. BRIEF
   → content/briefs/XX_slug_brief.md

3. EPISODE SCRIPT (15–20 min)
   → content/podcast_scripts/XX_slug.md
   This is what you read/upload to NotebookLM/ElevenLabs

4. YOUTUBE TITLE + DESCRIPTION + TAGS
   → content/captions/XX_slug_yt_desc.md
   Copy title → YT title field
   Copy description (has timestamps) → YT description
   Copy tags → YT tags

5. EPISODE ARTWORK PROMPT
   → content/image_prompts/podcast_XX_slug.md
   Copy → paste into Gemini → download PNG (1920x1080)

══════════════════════════════════════════════

🎯 MANUAL STEPS REMAINING:

□ Generate audio:
  Option A: Upload script to NotebookLM (free, fastest)
  Option B: Paste into ElevenLabs ($5/mo, branded voice)
  Option C: Record yourself reading the script
  → Save as audio/XX_slug.mp3

□ Generate episode art in Gemini (paste from file 5)
  → Save as images/podcast_XX/episode_art.png

□ Assemble video in CapCut Desktop:
  - Import audio + art
  - Enable auto-captions
  - Export as MP4 (1920x1080)

□ Upload to YouTube Studio:
  - MP4 video
  - Paste title + description from file 4
  - Upload episode_art.png as thumbnail

□ Mark best quotes for Reel clips (flagged in script file 3)
  → Run REEL PIPELINE for each clip

□ Tell @decision-logger to log the episode

══════════════════════════════════════════════

🔁 REEL CLIPS FLAGGED IN SCRIPT:
  Quote 1: "[quote]" (~timestamp)
  Quote 2: "[quote]" (~timestamp)
  → Use @pauli with "chop reels from episode XX"

══════════════════════════════════════════════
```

---

## File Map

```
fred-ai-methodology/
├── content/
│   ├── briefs/
│   │   └── XX_slug_brief.md                ← Structured brief
│   ├── podcast_scripts/
│   │   ├── XX_slug_raw_transcript.md       ← Original AI debate (archive)
│   │   └── XX_slug.md                      ← Produced script (the deliverable)
│   ├── captions/
│   │   └── XX_slug_yt_desc.md              ← YT title + description + tags
│   └── image_prompts/
│       └── podcast_XX_slug.md              ← Episode artwork prompt
├── images/
│   └── podcast_XX/
│       └── episode_art.png                 ← Generated artwork
├── audio/
│   └── XX_slug.mp3                         ← Generated/recorded audio
├── video/
│   └── XX_slug_episode.mp4                 ← Final assembled video
└── decisions/
    └── decision_log.md                     ← Episode logged
```

---

## Time Estimate

| Stage | Who | Time |
|-------|-----|------|
| 1. Raw Debate | Fred + AI | ~20–60 min (this IS the content) |
| 2. Triage | Fred + AI | ~5 min |
| 3. Structuring | AI | ~3 min |
| 4. Script Production | AI (Pauli runs agents) | ~10 min |
| 5. Audio Generation | Fred (manual) | ~15 min |
| 6. Video Assembly | Fred (manual, CapCut) | ~20 min |
| 7. Publish | Fred (manual, YouTube) | ~10 min |
| **Total** | | **~85–125 min per episode** |
| (excluding the debate itself) | | **~65 min production** |
