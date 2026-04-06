# Agent: Carousel Writer

Version: 1.0 | Date: 2026-04-06 | Status: ✅ Prompt Exists → Agent Spec Needed

## Purpose

Takes a structured content brief and produces a full 9-slide Instagram carousel in markdown, following the proven structure from `carousel_master_prompt.md`.

## Trigger

- Ideas Translator outputs `content_type: carousel`
- Manual invocation when Fred has a brief ready

## Input

```yaml
source_brief: "[Path to brief or inline brief from Ideas Translator]"
audience: beginners | builders | deep_thinkers
tone_override: "[Optional — default is direct/zero-fluff]"
```

## Output

A markdown file at `content/carousels/XX_slug.md` with:
- 9 slides (hook, 5 value, myth break, proof/story, CTA)
- Each slide formatted with headline + 3–6 lines of copy
- Optimized for 1080x1350 format (text density that reads on mobile)

## Core Prompt

Uses `prompts/carousel_master_prompt.md` (v2) — already built.

Key additions for the agent wrapper:
- Auto-inject persona context from `fred_developer_persona.md`
- Auto-inject brief from Ideas Translator
- Auto-number the file based on existing carousels in the directory

## Slide Structure Reference

| Slide | Purpose | Pattern |
|-------|---------|---------|
| 1 | Hook / Cover | Bold statement, question, or myth-break |
| 2–6 | Value delivery | One insight per slide, progressive build |
| 7 | Myth break / contrast | "Most people think X. Actually Y." |
| 8 | Proof / personal story | Fred's real numbers, real experience |
| 9 | CTA | Keyword trigger + follow + save prompt |

## Dependencies

- Reads: structured brief, `fred_developer_persona.md`, `prompts/carousel_master_prompt.md`
- Writes: `content/carousels/XX_slug.md`
- Triggers: Caption Writer + Image Prompter (in parallel)

## Notes

- Already have 10 carousels produced with this flow — the pattern is proven.
- The prompt is the agent. No code infrastructure needed — paste into Claude or ChatGPT.
