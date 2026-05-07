# Agents

All agents live in `.github/agents/`. Each `.agent.md` file is both the VS Code Copilot agent definition AND the full spec — no separate files needed.

## Agent Registry

### Master Orchestrator

| Agent | File | Purpose |
|-------|------|---------|
| **Pauli** | `pauli.agent.md` | Single entry point for ALL requests — classifies, routes, orchestrates, delivers. The boss. |

**Usage:** Type `@pauli` in VS Code chat to invoke the orchestrator for any request.

### Interactive Advisors

| Agent | File | Purpose |
|-------|------|---------|
| **Content Angles Advisor** | `content-angles.agent.md` | Debates ideas, suggests content angles, refines into actionable briefs |
| **Carousel Reviewer** | `carousel-reviewer.agent.md` | Quality gate — structural critique on draft carousels (hook, flow, proof, Golden Rule) |
| **Caption Critic** | `caption-critic.agent.md` | Editorial eye — tone, scroll-stop factor, authenticity scoring on draft captions |
| **Competitor Scout** | `competitor-scout.agent.md` | Strategic intel — analyzes competitor posts + designs Fred's counter-angle |

### Content Pipeline Agents

| # | Agent | File | Purpose |
|---|-------|------|---------|
| 00 | **Ideas Translator** | `ideas-translator.agent.md` | Universal entry point — raw idea → structured brief + execution plan |
| 01 | **Carousel Writer** | `carousel-writer.agent.md` | Structured brief → 9-slide carousel markdown |
| 02 | **Caption Writer** | `caption-writer.agent.md` | Carousel/reel content → Instagram caption + hashtags |
| 03 | **Image Prompter** | `image-prompter.agent.md` | Content → Gemini-ready image prompts (covers, inner slides, podcast art) |
| 04 | **Podcast Scripter** | `podcast-scripter.agent.md` | AI debate transcript → structured 15–20 min podcast script |
| 05 | **Lead Magnet Creator** | `lead-magnet-creator.agent.md` | Carousel topic → downloadable resource (checklist, template, guide) |
| 06 | **Content Planner** | `content-planner.agent.md` | Backlog + metrics → weekly content recommendation |
| 07 | **Decision Logger** | `decision-logger.agent.md` | Logs content strategy decisions to decision_log.md |
| 08 | **Research Verdict Synthesizer** | `research-verdict-synthesizer.agent.md` | Three-model research batch → archived reports, scored verdict, ranked production candidates |

### Support Files

| File | Purpose |
|------|---------|
| `pauli_delivery_protocol.md` | Delivery checklist templates for carousel, podcast, reel pipelines |

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

Research Batch → [08 Research Verdict] → [06 Planner] / [07 Decision] / [01 Carousel Writer]
```

## Design Principles

- **Prompt = Agent.** No code infrastructure needed. Each agent is a master prompt with structured I/O.
- **Tool-agnostic.** Same prompt works in Claude, ChatGPT, or any LLM.
- **Composable.** Agents chain together via structured briefs (YAML).
- **Human-in-the-loop.** Fred reviews every output before publishing. Agents draft, Fred decides.

## Related Documents

- [Content Process Map](../../content/content_process_map.md)
- [Toolstack by Content Type](../../content/toolstack_by_content_type.md)
- [Post Ideas Backlog](../../content/post_ideas_backlog.md)
