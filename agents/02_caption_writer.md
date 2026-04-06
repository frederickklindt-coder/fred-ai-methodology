# Agent: Caption Writer

Version: 1.0 | Date: 2026-04-06 | Status: ✅ Prompt Exists → Agent Spec Needed

## Purpose

Generates Instagram captions optimized for engagement, following the structure in `caption_master_prompt.md`. Adapts tone per audience segment and content type.

## Trigger

- Carousel Writer completes a carousel
- Reel or single post needs a caption
- Lead Magnet post needs a DM-trigger caption

## Input

```yaml
content_source: "[Carousel markdown or brief]"
content_type: carousel | reel | lead_magnet_post | text_post
audience: beginners | builders | deep_thinkers
cta_keyword: "[SYSTEM, AGENTS, DEBATE, META, SOLO, LEVEL, or custom]"
lead_magnet_cta: "[Optional — e.g., 'DM SYSTEM for the free checklist']"
```

## Output

A markdown file at `content/captions/XX_slug_caption.md` with:
- Hook line (first line visible before "...more")
- Context paragraph
- Value / insight block
- Proof element
- CTA (save, follow, DM keyword)
- Hashtag block (15–20 hashtags, mixed reach tiers)
- Word count: 220–300 words (carousel), 80–120 words (reel)

## Caption Variants by Content Type

| Type | Length | CTA Style | Tone |
|------|--------|-----------|------|
| Carousel | 220–300 words | "Save this + follow" | Educational, proof-driven |
| Reel | 80–120 words | "Follow for more" | Punchy, direct |
| Lead Magnet | 220–300 words | "DM [KEYWORD] for free [resource]" | Value + scarcity |
| Text Post | 100–200 words | Question or "Drop a 🔥" | Conversational |

## Core Prompt

Uses `prompts/caption_master_prompt.md` (v2) — already built.

## Dependencies

- Reads: carousel content or brief, `prompts/caption_master_prompt.md`
- Writes: `content/captions/XX_slug_caption.md`

## Notes

- Hashtag strategy from competitive analysis: mix of high-reach (#AI, #Automation) + niche (#AIagents, #BuildingInPublic, #NoCodeDev) + branded (#FredBuilds — future).
- Caption must work as standalone content even without the carousel.
