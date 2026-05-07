# Content Strategy Decisions

| ID | Decision | Status | Date | Notes |
|----|----------|--------|------|-------|
| C-001 | Use dark tech aesthetic for all carousel images | Confirmed | 2026-04-06 | Dark bg (#0D1117), electric blue/green accents, no stock faces |
| C-002 | 6 carousel topics for launch batch | Confirmed | 2026-04-06 | Solo builder, AI agents, Debate process, Meta analysis, Timeline, Level up |
| C-003 | Gemini for image generation, ChatGPT for copy variations | Confirmed | 2026-04-06 | Claude (VS Code) for strategy and playbook generation |
| C-004 | CTA keywords per carousel | Confirmed | 2026-04-06 | SYSTEM, AGENTS, DEBATE, META, SOLO, LEVEL |
| C-005 | Repo serves as both portfolio and content source | Confirmed | 2026-04-06 | Public repo, methodology + content in one place |
| C-006 | Extract playbook into standalone production assets (carousels/captions/image prompts) | Confirmed | 2026-04-06 | Implemented under content/ directories |
| C-007 | Add reusable master prompts for carousel, caption, and condensation workflows | Confirmed | 2026-04-06 | Stored in prompts/ for repeatable content pipeline |
| C-008 | Keep root-level context artifacts synced and documented | Confirmed | 2026-04-06 | Indexed in context/README.md for traceability |
| C-009 | Restore full ChatGPT v2 prompts as canonical versions | Confirmed | 2026-04-06 | Carousel + caption master prompts expanded from condensed to full original versions |
| C-010 | Enhance condensation prompt with viral optimization layer | Confirmed | 2026-04-06 | Added quality checks, viral rules, extra format options (bio, cold DM) |
| C-011 | Document meta-process: how the persona file became content | Confirmed | 2026-04-06 | The 21-page persona was AI-generated from git evidence, then became the source for all content |
| C-012 | Merge carousel sets: keep 6 originals + add 4 new topics | Confirmed | 2026-04-06 | Inbox Intel, Philosophical Debate, No-Code→AI, Lab Identity. Dropped AI Stack (weak carousel) and E-book (future) |
| C-013 | Add SOURCE CONTEXT input to carousel prompt | Confirmed | 2026-04-06 | Grounds carousels in real material instead of generic advice |
| C-014 | Add CAROUSEL SCRIPT input to caption prompt | Confirmed | 2026-04-06 | Captions complement slides instead of repeating them |
| C-015 | Add Mode B (raw idea → structured brief) to condensation prompt | Confirmed | 2026-04-06 | Handles messy notes/brain dumps, not just finished documents |
| C-016 | Create Instagram bio (mix of options E+D+B) | Confirmed | 2026-04-06 | Bold positioning + Spanglish + philosophical identity |
| C-017 | Save 50 post ideas as content backlog | Confirmed | 2026-04-06 | Organized by category with status tracking |
| C-018 | Create competitive analysis from Instagram creator screenshots | Confirmed | 2026-04-06 | 33 screenshots → 3 business models + tool stack → stored in content/competitive_analysis/ |
| C-019 | Golden Rule as signature closing slide on every carousel | Confirmed | 2026-04-06 | "AI can replace the busywork. It can't replace your voice, your story, or your authenticity." Variations encouraged per topic |
| C-020 | Nano Banana confirmed as image generation model (via Gemini) | Confirmed | 2026-04-06 | Updates C-003: Gemini uses Nano Banana model; Sora/Canva/Photopea skipped |
| C-021 | Adopt 4-point growth strategy from competitive analysis | Planned | 2026-04-06 | See adoption roadmap below |

---

## Adoption Roadmap (C-021)

Four validated growth strategies from competitive analysis, mapped to Fred's implementation plan.

### 1. Keyword CTA per post — ✅ ALREADY ACTIVE

- Status: **Done** (C-004)
- Each carousel already has a unique keyword (SYSTEM, AGENTS, DEBATE, META, SOLO, LEVEL)
- Validated by competitor analysis — keep doing this consistently

### 2. "Quick win" principle — 🔜 NEXT PRODUCT

- Status: **Ready when needed**
- Rule: Any future digital product (ebook, template, course) must deliver tangible value in the first 10 minutes
- Action: Embed this as a constraint in whatever product creation prompt/process we build
- Timeline: When Fred creates first digital product

### 3. 3-part DM automation sequence — 🛠️ BUILD AS AI AGENT

- Status: **Design phase**
- Concept: When user comments keyword → trigger automated sequence:
  1. **Immediate:** Deliver freebie (PDF, template, or mini-guide)
  2. **24 hours later:** Send a transformation story (personal, authentic)
  3. **48 hours later:** Soft invite to product/deeper content with urgency
- Action: Design this as a documented AI agent in `agents/` — fits the brand perfectly (building the automation in public)
- Prerequisite: Need a freebie/lead magnet to deliver + Instagram API or ManyChat setup
- Content idea: Document the build as carousel #53 ("The DM automation agent I'd build")
- Timeline: After first digital product exists

### 4. Reels strategy (60-second scripts) — 📋 PLAN

- Status: **Framework ready, execution pending**
- Structure (proven by competitors):
  1. **0–10s:** Relatable daily problem (hook)
  2. **10–30s:** Your turning point / insight
  3. **30–50s:** The result / system you built
  4. **50–60s:** CTA — "comment [KEYWORD] and I'll send you..."
- Action: Create a `reels_master_prompt.md` in `prompts/` when ready
- Prerequisite: Comfort with video + decide on video tool stack (Veed.io, Kling.ai, or phone-native)
- Content idea: Document the transition as carousel #56 ("From carousel to Reel")
- Timeline: After carousel pipeline is running smoothly (post launch batch)
| C-019 | Define content process map with 4 content types + posting cadence | Confirmed | 2026-04-06 | Carousel (weekly), Podcast (biweekly), Reels (repurposed), Lead Magnets (selective). Stored in content/content_process_map.md |
| C-020 | Define toolstack per content type with Phase 1 ($0) and Phase 2 (~$44/mo) | Confirmed | 2026-04-06 | Phase 1: Claude + Gemini + CapCut + NotebookLM (all free). Phase 2: + ElevenLabs + Descript + Opus Clip. Stored in content/toolstack_by_content_type.md |
| C-021 | Build 8-agent content pipeline (Ideas Translator → Carousel/Podcast/Lead Magnet → Caption/Image/Decision) | Confirmed | 2026-04-06 | Prompt-based, tool-agnostic agents. Specs in .github/agents/. Ideas Translator is the universal entry point |
| C-022 | Create Pauli master orchestrator agent | Confirmed | 2026-04-06 | Single entry point for ALL requests. Classifies (idea/build/analyze/plan/debate/maintain), routes to agents, orchestrates pipeline. Named after Fred's partner. VS Code agent at .github/agents/pauli.agent.md |
| C-023 | Consolidate agents/ into .github/agents/ — single source of truth | Confirmed | 2026-04-06 | Merged detailed specs (I/O schemas, prompt templates, dependencies) from agents/00-07 into .github/agents/*.agent.md. Deleted old agents/ folder. README moved to .github/agents/README.md. One folder, one format. |
| C-024 | Create Frederick canonical avatar prompt system | Confirmed | 2026-04-06 | Master reusable caricature prompt with 7 scene variations, consistency checklist, tool-specific tips. Stored in prompts/avatar_master_prompt.md. Robot companion + brain hologram are non-negotiable brand anchors. |
| C-025 | Integrate avatar system into @image-prompter agent | Confirmed | 2026-04-06 | Added `include_avatar` input flag, avatar routing table, and prompts/avatar_master_prompt.md as required context. Updated both image-prompter.agent.md and image-prompter.agent.updated.md. |
| C-026 | Update global style guide with avatar color integration rules | Confirmed | 2026-04-06 | Frederick avatar is warm-toned, tech elements cool-toned. Cosmic backgrounds allowed for covers. See content/image_prompts/00_global_style_guide.md. |
| C-027 | Create Pauli canonical avatar prompt system | Confirmed | 2026-04-07 | Pauli (partner) caricature prompt with 5 solo scenes + 5 duo scenes. Stored in prompts/avatar_pauli_prompt.md. Gold hoops + pink nails are identity anchors. |
| C-028 | Establish VS Code → Gemini avatar generation workflow | Confirmed | 2026-04-07 | Workflow: describe scene to Pauli in VS Code → get Gemini-ready prompt → copy to Gemini + attach canonical images → generate. Added as Section 4G-4H in avatar_master_prompt.md. |
| C-029 | Use two canonical reference images per character (clean face + full scene) | Confirmed | 2026-04-07 | Clean face reference for identity lock in new sessions. Full scene reference for style/mood. Saves as images/[name]_avatar_canonical_v1.png. |
| C-030 | Add research verdict synthesizer agent for multi-model content research batches | Confirmed | 2026-05-06 | Creates a dedicated synthesis step between raw deep-research outputs and production routing. Archives Claude/ChatGPT/Gemini reports, produces a locked verdict format with ranked carousel candidates, updates the research index, and hands off to planning/production agents without writing production content directly. |
