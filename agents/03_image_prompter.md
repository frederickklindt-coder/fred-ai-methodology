# Agent: Image Prompter

Version: 1.0 | Date: 2026-04-06 | Status: 🔲 To Build (style guide exists, agent wrapper needed)

## Purpose

Generates Gemini-ready image prompts for carousel covers, inner slides, podcast artwork, and reel thumbnails. Enforces the global brand style guide on every visual.

## Trigger

- Carousel Writer completes → cover + inner slide prompts needed
- Podcast Script Agent completes → episode artwork needed
- Any visual content needs brand-consistent imagery

## Input

```yaml
content_type: carousel_cover | inner_slides | podcast_art | reel_thumbnail
carousel_title: "[Title of the carousel or episode]"
key_visual_element: "[What should the main visual represent?]"
color_accent: blue | green | purple  # from brand palette
slide_count: [number, for inner slides]
text_on_image: "[Any text that needs to appear on the visual]"
```

## Output

Markdown file(s) at `content/image_prompts/XX_slug_cover.md` (and `_inner.md` if applicable) with:
- Gemini-ready prompt text
- Brand colors embedded
- Format specs (1080x1350 for carousel, 1920x1080 for YouTube thumbnail)
- Variant instructions (if multiple options wanted)

## Brand Rules (from global_style_guide.md)

| Element | Value |
|---------|-------|
| Background | #0D1117 (dark charcoal) |
| Primary accent | #58A6FF (electric blue) |
| Secondary accent | #3FB950 (bright green) |
| Text color | #E6EDF3 (soft white) |
| Format (IG) | 1080 × 1350px |
| Format (YT) | 1920 × 1080px |
| Visual language | Grids, nodes, terminal UI, connected dots, circuit patterns |
| Typography feel | Monospace / tech / clean sans-serif |

## Prompt Template (Cover)

```markdown
Generate a vertical social media cover image (1080x1350px).

STYLE:
- Dark background (#0D1117)
- [COLOR_ACCENT] accent color as primary highlight
- Tech aesthetic: circuit board traces, node graphs, terminal UI elements
- Clean, modern, slightly futuristic
- No photorealistic humans

CONTENT:
- Title text: "[CAROUSEL_TITLE]" in bold, clean font
- Subtitle or tagline: "[HOOK_LINE]"
- Visual element: [KEY_VISUAL_ELEMENT]
- Fred's brand feel: solo builder, systems thinker, AI-native

MOOD: Confident, technical, slightly mysterious. Think GitHub dark mode meets data visualization.

DO NOT: Include stock photo elements, clipart, generic AI imagery (no robot hands, no glowing brains).
```

## Prompt Template (Inner Slides)

```markdown
Generate an inner carousel slide (1080x1350px).

STYLE:
- Dark background (#0D1117)
- Vertical accent bar on the left side in [COLOR_ACCENT]
- Step number "[N]" in top-left, large and bold
- Clean text area for 3–6 lines of copy (do NOT render text — leave blank space)
- Progress indicator dots at bottom (slide [N] of [TOTAL] highlighted)

VARIANT: [blue #58A6FF | green #3FB950 | purple #8B5CF6]
```

## Dependencies

- Reads: `content/image_prompts/00_global_style_guide.md`, `content/image_prompts/99_inner_slide_template.md`, carousel content
- Writes: `content/image_prompts/XX_slug_cover.md`, `content/image_prompts/XX_slug_inner.md`

## Notes

- Current workflow: prompts are generated here, then manually pasted into Gemini.
- Future: could automate via Gemini API if volume justifies it.
- Podcast artwork follows same dark aesthetic but landscape format for YouTube.
