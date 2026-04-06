# Toolstack by Content Type

Version: 1.0 | Date: 2026-04-06 | Decision: C-020

## Overview

Each content type has a different production pipeline. This doc maps the tools needed per format, organized by phase (create → produce → publish).

---

## Instagram Carousel

| Phase | Tool | Role | Cost |
|-------|------|------|------|
| **Ideation** | Claude / ChatGPT | Ideas Translator agent | Existing subs |
| **Writing** | Claude / ChatGPT | Carousel Writer + Caption Writer agents | Existing subs |
| **Image Prompts** | Claude / ChatGPT | Image Prompter agent generates prompts | Existing subs |
| **Image Generation** | Gemini (Google AI Studio) | Generate cover + inner slide visuals | Free tier |
| **Assembly** | Canva | Combine images + text overlays into carousel | Free / Pro $13/mo |
| **Alt: Assembly** | Direct upload | If images have text baked in from Gemini | Free |
| **Publishing** | Instagram App | Upload, add caption, hashtags | Free |
| **Scheduling** | Later / Buffer | Schedule posts in advance | Free tier available |

### Minimal Stack (Today)
Claude + Gemini + Instagram App = **$0 additional** (assuming existing Claude/ChatGPT subs)

### Upgraded Stack (When Ready)
Add Canva Pro ($13/mo) for better templates, or Later ($25/mo) for scheduling + analytics.

---

## YouTube Podcast (15–20 min)

| Phase | Tool | Role | Cost | Notes |
|-------|------|------|------|-------|
| **Raw Material** | Claude / ChatGPT / Gemini | AI debate sessions (the actual conversation) | Existing subs | The content IS the AI conversation |
| **Script** | Claude / ChatGPT | Podcast Scripter agent | Existing subs | Structures raw debate into narrative |
| **Audio — Option A** | NotebookLM (Google) | Upload script → auto-generates conversational podcast audio | Free | Best for quick production. Two AI voices discuss the topic naturally. Limitation: less control over pacing |
| **Audio — Option B** | ElevenLabs | Text-to-speech with custom voice cloning | Free tier (10k chars/mo) / $5–22/mo | More control. Can clone Fred's voice. Better for branded feel |
| **Audio — Option C** | Fred records himself | Read from script, natural delivery | Free (needs mic) | Most authentic but slower to produce |
| **Background Art** | Gemini | Static episode artwork (dark aesthetic) | Free | One image per episode |
| **Video Assembly — Option A** | CapCut (Desktop) | Combine audio + static image + auto-captions | Free | Best free option. Auto-captions are solid |
| **Video Assembly — Option B** | Canva Video | Simple timeline editor + text overlays | Free / Pro | Good if already using Canva for carousels |
| **Video Assembly — Option C** | DaVinci Resolve | Professional editor, overkill but free | Free | Only if Fred wants full control |
| **Captions/Subtitles** | CapCut / Descript | Auto-generated, styled captions | Free / $24/mo | Essential for accessibility + watch time |
| **Publishing** | YouTube Studio | Upload, title, description, timestamps, tags | Free | |
| **Clip Extraction** | CapCut / Opus Clip | Pull 30–60s highlights for IG Reels | Free / $15/mo | Opus Clip uses AI to find best moments |

### Recommended Phase 1 Stack (Minimum Viable Podcast)
```
Debate with AI (existing workflow)
  → Podcast Scripter agent (Claude)
  → NotebookLM (free — auto-generates audio)
  → Gemini (free — episode artwork)
  → CapCut Desktop (free — assemble video + captions)
  → YouTube Studio (free — upload)
  → CapCut (free — extract IG Reel clips)

Total additional cost: $0
```

### Recommended Phase 2 Stack (Branded Production)
```
Same as Phase 1, but swap:
  → ElevenLabs ($5/mo — voice-cloned narration)
  → Descript ($24/mo — transcript-based editing, better captions)
  → Opus Clip ($15/mo — AI clip extraction for Reels)

Total additional cost: ~$44/mo
```

---

## Instagram Reels (30–60s)

| Phase | Tool | Role | Cost |
|-------|------|------|------|
| **Source** | Podcast episode / hot take | Extract clip or record quick take | — |
| **Script** | Claude / ChatGPT | Short-form caption | Existing subs |
| **Video — Option A** | CapCut Mobile | Quick edits, trending templates, auto-captions | Free |
| **Video — Option B** | Screen recording | Demo an agent, system, or workflow in action | Free |
| **Captions** | CapCut | Auto-captions (essential for Reels) | Free |
| **Publishing** | Instagram App | Upload as Reel, add caption + hashtags | Free |

### Reel Types for Fred
1. **Podcast clips** — best 60s from an episode
2. **Hot takes** — react to AI news or trend (timely, high reach)
3. **Screen demos** — show agents working, code running, systems in action
4. **Before/after** — "Here's what most people do vs. what I built"

---

## Lead Magnet Posts

| Phase | Tool | Role | Cost |
|-------|------|------|------|
| **Resource Creation** | Claude / ChatGPT | Lead Magnet Creator agent | Existing subs |
| **PDF Formatting** | Canva | Convert markdown to branded PDF | Free / Pro |
| **Alt: PDF** | Notion → Export | Write in Notion, export as PDF | Free |
| **Alt: PDF** | md-to-pdf (CLI) | For Fred the dev — markdown to styled PDF | Free |
| **Hosting** | Google Drive / Gumroad | Host the PDF for download link | Free |
| **DM Automation** | ManyChat | Auto-reply when someone DMs the keyword | Free (up to 1000 contacts) |
| **Alt: DM** | Manual | Reply yourself for first 50 DMs | Free |

### Recommended Flow
```
Lead Magnet Creator agent (Claude)
  → Canva (format as branded 1–3 page PDF)
  → Google Drive (host with shareable link)
  → ManyChat (auto-DM the link when keyword received)
  → Track: which keywords get most DMs

Total additional cost: $0 (all free tiers)
```

---

## Text Posts / Single Image Posts

| Phase | Tool | Role | Cost |
|-------|------|------|------|
| **Writing** | Claude / ChatGPT | Caption Writer agent (text_post variant) | Existing subs |
| **Image (optional)** | Gemini / Canva | Quote card, simple visual, or photo | Free |
| **Publishing** | Instagram App | Upload + caption | Free |

Low effort, high frequency potential. Good for filling gaps between carousels.

---

## Tool Summary (All Platforms)

| Tool | Used For | Cost | Priority |
|------|----------|------|----------|
| **Claude** | All agents (primary AI) | Existing sub | 🟢 Have |
| **ChatGPT** | Agents + Deep Research | Existing sub | 🟢 Have |
| **Gemini** | Image generation + NotebookLM audio | Free | 🟢 Have |
| **Instagram App** | Publishing | Free | 🟢 Have |
| **YouTube Studio** | Publishing | Free | 🟢 Have |
| **CapCut Desktop** | Video assembly + captions + clips | Free | 🟡 Get |
| **Canva** | PDF formatting + carousel assembly | Free / $13/mo | 🟡 Get (free tier first) |
| **ManyChat** | DM automation | Free (1000 contacts) | 🟡 Get (when lead magnets start) |
| **ElevenLabs** | Voice cloning for podcast | $5–22/mo | ⚪ Phase 2 |
| **Descript** | Transcript-based audio/video editing | $24/mo | ⚪ Phase 2 |
| **Opus Clip** | AI Reel extraction from podcasts | $15/mo | ⚪ Phase 2 |
| **Later / Buffer** | Post scheduling + analytics | Free / $25/mo | ⚪ Phase 2 |

### Phase 1 Monthly Cost: $0 additional
### Phase 2 Monthly Cost: ~$44–77/mo (when metrics justify it)

---

## Decision Criteria for Upgrading

Move from Phase 1 → Phase 2 when:
- Posting consistently for 4+ weeks (proven habit)
- Reaching 500+ followers (audience worth optimizing for)
- DM volume exceeds manual capacity (need ManyChat)
- Podcast production time exceeds 3 hours per episode (need Descript)
- Reel clip selection takes too long manually (need Opus Clip)
