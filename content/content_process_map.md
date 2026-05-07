# Content Process Map

Version: 1.0 | Date: 2026-04-06 | Decision: C-019

## Posting Cadence

**Core rhythm:** 1 carousel per week (Sunday or Monday publish).
**Bonus drops:** whenever an idea or debate session is too good to wait — post within 48 hours.
**Podcast:** 1 episode every 2 weeks (batching 2 debate sessions → 1 edited episode).

This means ~4–5 Instagram posts/month + 2 podcast episodes/month. Sustainable for a solo builder with a day job.

---

## Audience Segments & Content Match

| Segment | Description | Best Formats | Hook Style |
|---------|-------------|--------------|------------|
| **Beginners** | Curious about AI, overwhelmed by noise | Carousels, Reels, quick tips | "Stop doing X" / myth-breaking |
| **Builders** | No-code / dev / product people shipping things | Carousels, podcasts, lead magnets | "Here's the system I built" / proof |
| **Deep Thinkers** | Hybrid explorers like Fred — philosophical, meta | Podcasts, debate carousels, long captions | "What if AI is actually..." / questions |

---

## Content Type 1: Instagram Carousel

### Process Flow

```
RAW INPUT                    GATES                          OUTPUT
─────────────────────────────────────────────────────────────────────
Google Keep note        ──→  [GATE 1] Angle Filter     ──→  Chosen angle(s)
or raw idea dump             (mandatory, always runs)        Fred decides
                             Depth scales to idea:
                             • Raw idea → full 4-6 angles
                             • Developed → 2-3 angles
                             • Formed → confirm or flag
                                    │
                                    ▼ Fred picks angle
                             [GATE 2] Research Check
                             • Check content/research/
                               for existing archived research
                             • If missing or thin →
                               print research prompt for
                               Fred to run outside VS Code
                               (ChatGPT/Claude/Gemini)
                             • Fred returns with results →
                               archived under content/research/
                                    │
                                    ▼ Research confirmed
                             Ideas Translator Agent     ──→  Structured Brief
                             (grounded in angle +            (content_type, audience,
                              research output)               hook, key_points, cta)
                                    │
                                    ▼
                             Carousel Writer Agent     ──→  9-slide markdown
                             (carousel_master_prompt)       (carousels/XX_slug.md)
                                    │
                                    ├──→ Caption Writer Agent   ──→  Caption markdown
                                    │    (caption_master_prompt)     (captions/XX_slug.md)
                                    │
                                    └──→ Image Prompt Agent     ──→  Cover + inner slide prompts
                                         (global_style_guide +      (image_prompts/XX_slug.md)
                                          inner_slide_template)
                                                │
                                                ▼
                                         MANUAL: Gemini         ──→  Generated images
                                         (paste prompts,            (saved to images/)
                                          download PNGs)
                                                │
                                                ▼
                                         MANUAL: Assemble       ──→  Final carousel
                                         (Canva or direct            (ready to publish)
                                          upload to IG)
                                                │
                                                ▼
                                         Decision Logger Agent  ──→  decision_log.md updated
                                         (logs what was posted,
                                          audience, metrics later)
```

### Gate Rules (enforced by Pauli)

| Gate | Rule | Flexibility |
|------|------|-------------|
| **Gate 1 — Angle Filter** | Every content idea passes through angle exploration before production starts | Depth scales to idea maturity: full for raw, brief for developed, confirmatory for fully formed |
| **Gate 2 — Research Check** | If no archived research exists for the topic, print research prompt before writing brief | Skip only if research is already in `content/research/` and is current |
| **Gate 3 — Brief** | Brief is only written after angle is chosen and research is confirmed | N/A |

### Files Created Per Carousel
- `carousels/XX_slug.md` — slide content
- `captions/XX_slug_caption.md` — caption + hashtags
- `image_prompts/XX_slug_cover.md` — cover image prompt
- `image_prompts/XX_slug_inner.md` — inner slide prompts (if custom)

### Current Status
- ✅ Carousel master prompt exists
- ✅ Caption master prompt exists
- ✅ Global style guide exists
- ✅ Inner slide template exists
- ✅ 10 carousels + captions drafted
- 🔲 Ideas Translator agent (needs build)
- 🔲 Image Prompt agent (needs build — currently manual)
- 🔲 Automation of Gemini prompt delivery

---

## Content Type 2: YouTube Podcast (15–20 min)

### Process Flow

```
RAW INPUT                    AGENTS                         OUTPUT
─────────────────────────────────────────────────────────────────────
AI debate transcript    ──→  Ideas Translator Agent    ──→  Structured Brief
(Claude, ChatGPT,            (flags as podcast-worthy,      (topic, guests, angle,
 Gemini session)              identifies key moments)        audience segment)
                                    │
                                    ▼
                             Podcast Script Agent      ──→  Script markdown
                             (new — structures raw           (podcast_scripts/XX.md)
                              debate into narrative)
                                    │
                                    ├──→ Audio Generation       ──→  MP3/WAV audio
                                    │    (NotebookLM or             (~15–20 min)
                                    │     ElevenLabs TTS)
                                    │
                                    └──→ Image Prompt Agent     ──→  Static art / loop prompt
                                         (podcast variant)          for video background
                                                │
                                                ▼
                                         MANUAL: Video Assembly ──→  MP4 video
                                         (CapCut / Canva /          (static art + audio +
                                          DaVinci Resolve)           captions overlay)
                                                │
                                                ▼
                                         MANUAL: Upload          ──→  YouTube + cross-post
                                         (title, description,        clips to IG Reels
                                          timestamps, tags)
```

### Files Created Per Episode
- `podcast_scripts/XX_slug.md` — structured script
- `podcast_scripts/XX_slug_raw_transcript.md` — original AI conversation (optional archive)
- `image_prompts/podcast_XX_slug.md` — background art prompt
- Caption/description for YouTube + IG clip

### Podcast Episode Structure (15–20 min)
1. **Cold open** (30s) — most provocative quote from the debate
2. **Intro** (60s) — "I'm Fred, I build AI systems and debate them" + topic setup
3. **Context** (2 min) — why this question matters
4. **The Debate** (8–12 min) — edited highlights from AI conversation, structured as back-and-forth
5. **Fred's Take** (2–3 min) — what he actually thinks after hearing the AI perspectives
6. **Builder Takeaway** (1 min) — one actionable thing for the audience
7. **Outro** (30s) — "building en público" sign-off + CTA

### Phase 1 (Faceless/Audio-First)
- Static dark-aesthetic artwork as video background
- Auto-generated captions (CapCut or Descript)
- Waveform animation optional
- One background image per episode

### Phase 2 (When Ready)
- Animated subtle motion (particle effects, node graphs)
- Multiple scene backgrounds per segment
- Face-to-camera intro (optional)

---

## Content Type 3: Instagram Reels / Short Clips

### Process Flow

```
RAW INPUT                    AGENTS                         OUTPUT
─────────────────────────────────────────────────────────────────────
Podcast episode         ──→  Clip Extractor (manual     ──→ 30–60s clip script
or standalone idea           or Ideas Translator)
                                    │
                                    ▼
                             Caption Writer Agent       ──→  Short caption
                             (reel variant — shorter,       (< 100 words)
                              punchier)
                                    │
                                    ▼
                             MANUAL: Record or           ──→  Reel video
                             extract audio clip +            (upload to IG)
                             add captions
```

### When to Use Reels
- Repurpose best 60s from a podcast episode
- Quick "hot take" on an AI trend (timely content)
- Before/after demos of agents working
- Screen recordings of systems in action

---

## Content Type 4: Lead Magnet Posts

### Process Flow

```
RAW INPUT                    AGENTS                         OUTPUT
─────────────────────────────────────────────────────────────────────
Carousel topic that     ──→  Lead Magnet Agent          ──→  Downloadable resource
has depth to expand          (creates checklist,             (PDF / Notion template /
                              template, or mini-guide)        markdown → PDF)
                                    │
                                    ├──→ Carousel Writer Agent  ──→  Teaser carousel
                                    │    (CTA = "DM SYSTEM                (drives to DM)
                                    │     for free checklist")
                                    │
                                    └──→ Caption Writer Agent   ──→  Caption with DM CTA
                                         (lead magnet variant)
```

### Lead Magnet Ideas (from backlog)
- "AI Agent Starter Checklist" — for #2 (35 AI Agents post)
- "Prompt → System Framework" — for #6 (Stop Using AI Like a Search Engine)
- "My Debate Decision Template" — for #3 (Debate Process)
- "51-Day Build Log Template" — for #5 (Timeline Proof)

---

## Universal Entry Point: The Ideas Translator

Every content piece starts here. This is the most critical agent.

```
┌─────────────────────────────────────────────────────┐
│                 IDEAS TRANSLATOR                      │
│                                                       │
│  INPUT: Raw dump (text, voice note transcript,        │
│         Google Keep note, conversation excerpt)       │
│                                                       │
│  ANALYSIS:                                            │
│  1. What's the core insight?                          │
│  2. Which audience segment cares most?                │
│  3. What format fits best?                            │
│  4. Is there a lead magnet opportunity?               │
│  5. Does this connect to existing content?            │
│  6. Priority score (timeliness × depth × uniqueness)  │
│                                                       │
│  OUTPUT: Structured Brief + Agent Execution Plan      │
│  ┌─────────────────────────────────────────────┐      │
│  │ content_type: carousel | podcast | reel     │      │
│  │ audience: beginners | builders | thinkers   │      │
│  │ hook: "..."                                 │      │
│  │ key_points: [...]                           │      │
│  │ cta_keyword: SYSTEM | AGENTS | DEBATE | ... │      │
│  │ lead_magnet: yes/no + type                  │      │
│  │ connected_posts: [references to backlog]    │      │
│  │ agents_to_invoke:                           │      │
│  │   - carousel_writer (if carousel)           │      │
│  │   - caption_writer (always)                 │      │
│  │   - image_prompter (if visual)              │      │
│  │   - podcast_scripter (if podcast)           │      │
│  │   - lead_magnet_creator (if applicable)     │      │
│  │ priority: high | medium | low               │      │
│  └─────────────────────────────────────────────┘      │
└─────────────────────────────────────────────────────┘
```

---

## Daily/Weekly Workflow

### When Inspiration Hits (Anytime)
1. Dump raw idea → Google Keep or directly into this repo
2. Run **Ideas Translator** → get structured brief
3. If priority = high → execute agent chain immediately
4. If priority = medium/low → add to `post_ideas_backlog.md` with brief attached

### Weekly Content Session (Sunday)
1. Review `post_ideas_backlog.md` — pick 1 carousel for the week
2. Run **Carousel Writer** → **Caption Writer** → **Image Prompter** chain
3. Generate images in Gemini
4. Assemble and schedule for Monday publish

### Biweekly Podcast Session
1. Pick best AI debate from past 2 weeks (or record a new one)
2. Run **Podcast Script Agent** on transcript
3. Generate audio → assemble video
4. Upload to YouTube → extract 1–2 clips for IG Reels

---

## Metrics to Track (Future)

| Metric | Where | Why |
|--------|-------|-----|
| Saves per carousel | IG Insights | Saves = real value delivered |
| DMs triggered by CTA keyword | IG DMs | Measures lead magnet pull |
| Profile visits after post | IG Insights | Are people clicking through? |
| YouTube watch time | YT Studio | Are people staying for the debate? |
| Follower growth rate | IG + YT | Trend line, not vanity |
| Ideas → Published ratio | This repo | Are you shipping or hoarding? |
