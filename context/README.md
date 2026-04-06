# Context Assets

Raw source material used as AI context across this repository. Feed these into any prompt, agent, or content-generation workflow to ground output in Fred's actual background.

---

## Identity & Background Files

| File | What it is | When to use it |
|------|-----------|----------------|
| `resume_product_engineer.md` | Current resume (April 2026) — structured, clean | Professional framing, positioning, bios |
| `resume_feb_2026.md` | Earlier resume (February 2026, converted from .docx) | Historical comparison, older wording |
| `chatgpt_user_profile.md` | ChatGPT's model of Fred — personal + professional | Quick personality/background snapshot |
| `gemini_user_profile.md` | Gemini's model of Fred — creative + lifestyle angle | Creative identity, photography, aesthetic side |
| `../persona/fred_developer_persona.md` | Deep 21-page AI-generated developer persona from git evidence | AI methodology, engineering patterns, workflow |

---

## How These Files Interconnect

```
resume_product_engineer.md  ──┐
resume_feb_2026.md           ─┤──▶  persona/fred_developer_persona.md
chatgpt_user_profile.md      ─┤       (synthesized identity — canonical)
gemini_user_profile.md       ─┘              │
                                             ▼
                                prompts/condensation_prompt.md
                                       │
                            ┌──────────┴──────────┐
                            ▼                     ▼
                   content/carousels/      content/captions/
```

- The **resume files** provide professional credibility and concrete proof points (stack, clients, metrics).
- The **user profiles** provide tone, personality, and lifestyle context for content that needs to feel human.
- The **developer persona** is the synthesis of all of the above — the canonical doc to feed into content and agent prompts.
- The **condensation prompt** (`prompts/condensation_prompt.md`) knows how to compress any of these into any target format.

---

## Root-Level Mirrors (intentional)

These files exist at root for tooling visibility (AI agents look there first):

- `fred_developer_persona.md` → mirror of `persona/fred_developer_persona.md`
- `instagram_carousel_playbook.md` → mirror of `content/instagram_carousel_playbook.md`

Canonical versions remain in their respective folders.
