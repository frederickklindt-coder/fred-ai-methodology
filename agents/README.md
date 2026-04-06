# Agents

Two agent systems working together:

## 1. VS Code Copilot Agents (`.github/agents/`)

Interactive agents that run inside VS Code. These are your live thinking partners.

| Agent | File | Purpose |
|-------|------|---------|
| **Pauli** (Master Orchestrator) | `.github/agents/pauli.agent.md` | Single entry point for ALL requests — classifies, routes, orchestrates, delivers. The boss. |
| **Content Angles Advisor** | `.github/agents/content-angles.agent.md` | Debates ideas, suggests content angles, refines into actionable briefs |
| **Carousel Reviewer** | `.github/agents/carousel-reviewer.agent.md` | Quality gate — structural critique on draft carousels (hook, flow, proof, Golden Rule) |
| **Caption Critic** | `.github/agents/caption-critic.agent.md` | Editorial eye — tone, scroll-stop factor, authenticity scoring on draft captions |
| **Competitor Scout** | `.github/agents/competitor-scout.agent.md` | Strategic intel — analyzes competitor posts + designs Fred's counter-angle |

**Usage:** Type `@pauli` in VS Code chat to invoke the orchestrator for any request.

## 2. Content Pipeline Agents (this folder)

| # | Agent | Status | File | Purpose |
|---|-------|--------|------|---------|
| 00 | **Ideas Translator** | 🔲 To Build | [00_ideas_translator.md](00_ideas_translator.md) | Universal entry point — raw idea → structured brief + execution plan |
| 01 | **Carousel Writer** | ✅ Prompt Exists | [01_carousel_writer.md](01_carousel_writer.md) | Structured brief → 9-slide carousel markdown |
| 02 | **Caption Writer** | ✅ Prompt Exists | [02_caption_writer.md](02_caption_writer.md) | Carousel/reel content → Instagram caption + hashtags |
| 03 | **Image Prompter** | 🔲 To Build | [03_image_prompter.md](03_image_prompter.md) | Content → Gemini-ready image prompts (covers, inner slides, podcast art) |
| 04 | **Podcast Scripter** | 🔲 To Build | [04_podcast_scripter.md](04_podcast_scripter.md) | AI debate transcript → structured 15–20 min podcast script |
| 05 | **Lead Magnet Creator** | 🔲 To Build | [05_lead_magnet_creator.md](05_lead_magnet_creator.md) | Carousel topic → downloadable resource (checklist, template, guide) |
| 06 | **Content Planner** | 🔲 To Build | [06_content_planner.md](06_content_planner.md) | Backlog + metrics → weekly content recommendation |
| 07 | **Decision Logger** | 🔲 To Build | [07_decision_logger.md](07_decision_logger.md) | Logs content strategy decisions to decision_log.md |

## Pipeline Flow

```
                          ┌─────────────┐
          Fred (anything) │   @pauli    │ ← Master Orchestrator
                          └──────┬──────┘
                                 │ classifies & routes
                    ┌────────────┼────────────┐
                    ▼            ▼             ▼
            @content-angles  [06 Planner]  [direct execution]
                    │
                    ▼
Raw Idea → [00 Ideas Translator] → Structured Brief
                                        │
                    ┌───────────────────┼───────────────────┐
                    ▼                   ▼                   ▼
            [01 Carousel Writer] [04 Podcast Scripter] [05 Lead Magnet]
                    │                   │                   │
              ┌─────┼─────┐             │                   │
              ▼     ▼     ▼             ▼                   ▼
          [02]   [03]   [07]        [02] [03] [07]      [02] [07]
        Caption Image  Decision   Caption Image Decision Caption Decision
```

## Design Principles

- **Prompt = Agent.** No code infrastructure needed. Each agent is a master prompt with structured I/O.
- **Tool-agnostic.** Same prompt works in Claude, ChatGPT, or any LLM.
- **Composable.** Agents chain together via structured briefs (YAML).
- **Human-in-the-loop.** Fred reviews every output before publishing. Agents draft, Fred decides.

## Related Documents

- [Content Process Map](../content/content_process_map.md)
- [Toolstack by Content Type](../content/toolstack_by_content_type.md)
- [Post Ideas Backlog](../content/post_ideas_backlog.md)
