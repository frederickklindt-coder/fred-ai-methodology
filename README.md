# Fred AI Methodology

A living repository that captures how a solo developer ships production systems with AI-native workflows — and turns that process into reusable content, social proof, and a teachable methodology.

## The Meta-Story

This project started with a simple experiment: **ask AI to analyze how I use AI.**

I pointed Claude at my git history — 254 commits across 3 production systems, 35 AI agents, 48 logged decisions, and thousands of lines of prompts — and asked it to generate a developer persona from the evidence.

What came back was a 21-page operating manual of my own methodology. Patterns I'd never named. Workflows I'd built instinctively. A full system documented by the same kind of AI that helped me build it.

Then the realization: **this document IS the content.**

The persona became carousel scripts. The frameworks became slide decks. The numbers became proof. The process of discovering it became the first post.

This repo captures that full loop:

1. **Build** real systems with AI (commits, agents, prompts, decisions)
2. **Extract** a developer persona from the evidence
3. **Condense** it into viral-ready social content
4. **Generate** carousel scripts, captions, and image prompts
5. **Produce** Instagram content using Gemini (images) + ChatGPT (copy) + Claude (strategy)
6. **Document** every decision, prompt, and workflow for reuse

## Repository Structure

```text
fred-ai-methodology/
|-- README.md
|-- fred_developer_persona.md          # root mirror → persona/
|-- persona/
|   `-- fred_developer_persona.md      # 21-page AI-generated persona (canonical)
|-- context/                           # raw source material / AI context files
|   |-- README.md                      # index + interconnection map
|   |-- resume_product_engineer.md     # current resume (April 2026)
|   |-- resume_feb_2026.md             # earlier resume (Feb 2026)
|   |-- chatgpt_user_profile.md        # ChatGPT's model of Fred
|   `-- gemini_user_profile.md         # Gemini's model of Fred
|-- content/
|   |-- instagram_carousel_playbook.md # master playbook (meta-story + all content)
|   |-- carousels/                     # 10 standalone 9-slide scripts
|   |-- captions/                      # 10 publish-ready captions
|   `-- image_prompts/                 # Gemini cover prompts + style guide
|-- prompts/
|   |-- carousel_master_prompt.md      # reusable carousel generation prompt
|   |-- caption_master_prompt.md       # reusable caption generation prompt
|   |-- condensation_prompt.md         # persona-to-any-format converter
|   `-- gemini_image_prompts.md        # aggregated image prompt pack
|-- decisions/
|   `-- decision_log.md                # all content strategy decisions
|-- .github/
|   `-- agents/                        # all VS Code Copilot agents + specs
|       |-- README.md                  # agent registry + pipeline diagram
|       |-- pauli.agent.md             # master orchestrator
|       |-- content-angles.agent.md    # idea debate + angle exploration
|       |-- ideas-translator.agent.md  # raw idea → structured brief
|       |-- carousel-writer.agent.md   # brief → 9-slide carousel
|       |-- caption-writer.agent.md    # content → caption + hashtags
|       |-- image-prompter.agent.md    # content → Gemini image prompts
|       |-- podcast-scripter.agent.md  # transcript → episode script
|       |-- lead-magnet-creator.agent.md # topic → downloadable resource
|       |-- content-planner.agent.md   # backlog → weekly plan
|       |-- decision-logger.agent.md   # logs decisions to decision_log
|       |-- carousel-reviewer.agent.md # draft → quality scorecard
|       |-- caption-critic.agent.md    # draft → editorial feedback
|       |-- competitor-scout.agent.md  # competitor → strategic analysis
|       `-- pauli_delivery_protocol.md # delivery checklist templates
`-- images/                            # generated visual assets
```

## Key Documents

| Document | Purpose |
|----------|---------|
| [persona/fred_developer_persona.md](persona/fred_developer_persona.md) | 21-page developer profile generated from repo evidence |
| [content/instagram_carousel_playbook.md](content/instagram_carousel_playbook.md) | Master playbook: meta-story, carousels, captions, image prompts |
| [content/carousels/](content/carousels/README.md) | 6 standalone 9-slide carousel scripts |
| [content/captions/](content/captions/README.md) | 6 publish-ready Instagram captions |
| [content/image_prompts/](content/image_prompts/README.md) | Gemini visual prompt pack + global style guide |
| [prompts/carousel_master_prompt.md](prompts/carousel_master_prompt.md) | Full v2 carousel generation prompt (from ChatGPT strategy session) |
| [prompts/caption_master_prompt.md](prompts/caption_master_prompt.md) | Full v2 caption generation prompt (from ChatGPT strategy session) |
| [prompts/condensation_prompt.md](prompts/condensation_prompt.md) | Convert persona into any content format (viral-optimized) |
| [decisions/decision_log.md](decisions/decision_log.md) | All content strategy decisions with dates and rationale |
| [.github/agents/](/.github/agents/README.md) | 13 VS Code Copilot agents — orchestrator, pipeline, reviewers, advisors |

## Workflow

```
Git Evidence → AI Analysis → 21-page Persona → Condensation Prompt → Carousel Scripts
                                                                   → Captions
                                                                   → Image Prompts (Gemini)
                                                                   → Image Variations (ChatGPT)
                                                                   → Instagram Posts
```

## AI Model Roles

| Model | Role |
|-------|------|
| **Claude** (VS Code / Copilot) | Strategy, playbook generation, repo architecture |
| **ChatGPT** | Copy variations, carousel scripts, caption writing, image generation |
| **Gemini** | Image generation from cover prompts and style guide |

## Local Context Assets

Root-level profile/image artifacts are preserved and listed in [context/README.md](context/README.md) for traceability.

## Author

**Fred** — solo AI-native builder. 3 production systems. 35 agents. 254 commits in 51 days. No team — just prompts, debate, and version control.
