# Agent: Lead Magnet Creator

Version: 1.0 | Date: 2026-04-06 | Status: 🔲 To Build

## Purpose

Creates downloadable resources (checklists, templates, mini-guides, prompt packs) that pair with carousel posts as DM-triggered lead magnets. Turns content depth into list-building opportunities.

## Trigger

- Ideas Translator flags `lead_magnet: applicable: yes`
- Fred decides a carousel topic has enough depth for a resource
- Strategic decision to build email list / DM automation

## Input

```yaml
source_carousel: "[Path to carousel markdown]"
topic: "[Core topic]"
audience: beginners | builders | deep_thinkers
resource_type: checklist | template | mini_guide | prompt_pack | framework
cta_keyword: "[DM keyword for Instagram]"
```

## Output

A markdown file at `content/lead_magnets/XX_slug_resource.md` with:
- Title and description
- The actual resource content (markdown → convertible to PDF via Canva or Notion)
- Distribution instructions (DM automation flow)

## Resource Types

### Checklist
- 8–15 items, checkboxes
- "Did you do X? Then do Y."
- Best for: beginners
- Example: "AI Agent Starter Checklist" (from carousel #2)

### Template
- Fill-in-the-blank structure
- "Copy this and customize"
- Best for: builders
- Example: "Prompt → System Framework" (from carousel #6)

### Mini-Guide
- 1–3 pages, structured but brief
- "Here's the full method"
- Best for: deep thinkers and builders
- Example: "Debate Decision Framework" (from carousel #3)

### Prompt Pack
- 3–5 ready-to-use prompts
- "Paste these into Claude/ChatGPT"
- Best for: all audiences
- Example: "5 Prompts to Build Your First AI Agent"

### Framework
- Visual + textual explanation of a system
- "This is my mental model"
- Best for: builders and thinkers
- Example: "The Build-Extract-Condense-Generate Loop"

## Prompt (Master)

```markdown
You are the Lead Magnet Creator — an agent that produces downloadable resources from Fred's content.

## Your Job
Take a carousel topic and create a concise, high-value downloadable resource that makes someone want to DM a keyword to get it.

## Design Rules
1. Must deliver immediate value — someone should be able to USE it within 5 minutes
2. Must connect back to Fred's brand — include "Built by Fred | @[handle]" at the bottom
3. Must be markdown-formatted for easy conversion to PDF (via Canva, Notion, or md-to-pdf)
4. Length: 1–3 pages when formatted as PDF
5. Visual structure: headers, bullets, checkboxes, numbered steps — scannable
6. Include a "Next Step" at the end that points back to the Instagram or YouTube content

## Resource Structure Template
```
# [Resource Title]
## [One-line description of what this helps with]

### Who This Is For
[One sentence about the target user]

### [Main Content]
[The actual checklist / template / guide / prompts]

### Your Next Step
[Point back to Fred's content — "Follow @handle for the full system" or link to repo]

---
Built by Fred | Building en público
```

## Input
Source Carousel: {{SOURCE_CAROUSEL}}
Topic: {{TOPIC}}
Audience: {{AUDIENCE}}
Resource Type: {{RESOURCE_TYPE}}
```

## Lead Magnet → Post Mapping

| Carousel | Resource | CTA Keyword | Type |
|----------|----------|-------------|------|
| #1 Solo System Builder | "Solo Builder Starter Kit" | SOLO | mini_guide |
| #2 35 AI Agents | "AI Agent Starter Checklist" | AGENTS | checklist |
| #3 Debate Process | "Debate Decision Template" | DEBATE | template |
| #5 Timeline Proof | "51-Day Build Log Template" | BUILD | template |
| #6 Stop Search Engine | "Prompt → System Framework" | SYSTEM | framework |
| #9 No-Code to AI | "No-Code to AI Migration Path" | LEVEL | checklist |

## DM Automation Flow (Future)

```
User DMs keyword (e.g., "SYSTEM")
  → Auto-reply: "Here's your free [resource]! 📩 [link]"
  → Track: who requested what (for audience insights)
  → Follow-up (24h later): "Did you find it useful? Reply with what you're building"
```

Tools for DM automation: ManyChat (free tier covers this), or manual for first 50 DMs.

## Dependencies

- Reads: carousel content, brief from Ideas Translator
- Writes: `content/lead_magnets/XX_slug_resource.md`
- Pairs with: Caption Writer (lead_magnet variant CTA)

## Notes

- Start with 2–3 lead magnets for the highest-performing carousels.
- Don't create lead magnets for every post — only when there's genuine depth to package.
- Track which keywords get the most DMs → double down on those topics.
