# Research Prompt — CV & Cover Letter Rule Archaeology

**Purpose:** Send this prompt to a fresh agent session (Claude, ChatGPT with Deep Research, or Gemini) to deepen the *Career Artifacts Archaeology* content series in `/content/briefs/cv_cover_letter_archaeology.md`.

**Recommended model:** ChatGPT with Deep Research enabled, OR Claude Opus with web search. Run the same prompt in both and compare outputs (Fred standard pattern).

**How to use:**
1. Copy everything below the `---` divider into a fresh chat.
2. Run it.
3. Save the output to `/content/briefs/cv_cover_letter_archaeology_research_<modelname>_<date>.md`.
4. Compare across models, extract the strongest claims (with sources), fold into the brief.

---

# PROMPT START

You are a research agent helping me build a content series called *"Career Artifacts Archaeology"* — a series of educational social posts (Instagram carousels, mainly) that trace the hidden origins of common CV and cover-letter rules, evaluate which ones still earn their keep in 2026, and identify which ones are folklore that needs to die.

The audience is professional knowledge workers, founders, freelancers, and AI-native builders — people who write CVs but are skeptical of conventional wisdom and want the real *why* behind any rule before they follow it.

## What I already have

I have a draft post on the *"never use first person on a CV"* rule, traced to three origins:
1. CV's academic-Latin origin as a third-party-written credential ledger (1700s onward)
2. 1980s–2000s corporate "professional formality" overlay (status signaling)
3. ATS / recruiter 6-second-scan era (mid-2000s onward) — the only origin with a real functional justification today

That post concludes that the rule is **strong for high-volume cold applications**, but **weakens or inverts** for referrals, senior roles, creative roles, and any application where the reader is the decision-maker rather than a gatekeeper.

I want to apply the same archaeological treatment to **15-20 other CV and cover-letter conventions** so I can build a multi-post content series.

## What I want from you

For **each** of the rules in the list below, produce a structured analysis with these exact sections:

### Rule: [name of the rule]

**The conventional wisdom (one sentence):** What everyone says you should do.

**Historical origin:** Where the rule actually came from. Trace it to:
- The decade or era it emerged
- The institutional pressure or technology that produced it (e.g., "fax machines," "1980s HR-training-industry boom," "rise of ATS in mid-2000s," "MBA career-services standardization in the 1980s")
- The original problem it was solving

**Functional justification today (if any):** Is there still a real mechanism that makes this rule load-bearing? If yes, what is it? Cite evidence (eye-tracking studies, ATS parser behavior, recruiter surveys, etc.) where possible. If no, say so plainly.

**When the rule still applies:** List 2-3 concrete situations where following it is correct.

**When the rule breaks down or inverts:** List 2-3 concrete situations where following it actively hurts the applicant.

**The counterintuitive payoff:** A single line that captures the surprising insight non-experts will not have considered. (This is what makes the post worth posting.)

**Sources:** At least 2 citations per rule (academic, journalistic, industry survey, or primary-source). Prefer datable, verifiable sources over generic career-blog claims. If a claim is folklore with no traceable source, say "no traceable primary source — circulates as common practice since [decade]."

## Rules to analyze

### Format & layout
1. The "one page only" rule
2. The "Times New Roman / Arial / Calibri only" typography conformity
3. Reverse-chronological order as default structure
4. The 1-inch margin rule
5. The photo on CV — required in Europe/LATAM, taboo in US/UK
6. The "no color" rule

### Content
7. "Action verbs only" / power-verb lists
8. "Quantify everything with numbers" rule
9. "References available upon request" closing line
10. The "career objective" section
11. The "hobbies & interests" section
12. Skills-bar visualizations and 5-star rating graphics

### Cover letters
13. "Dear Hiring Manager" salutation when name is unknown
14. The three-paragraph structure convention
15. The "don't just repeat your CV" rule
16. Opening-line conventions ("I am writing to apply for…" vs hook openings)
17. Closing salutations ("Sincerely" vs "Best regards" vs "Best") and their formality decay over time
18. The "why this company specifically" paragraph

### Submission & meta
19. PDF vs Word file format debate
20. File-naming conventions (`Resume.pdf` vs `[Name]_CV_[Company].pdf`)
21. Whether recruiters actually read cover letters (cite the survey data)

### AI-era artifacts (these will have less history but are still worth examining)
22. The "AI-written CV" detection problem and the new "perfect grammar is suspicious" signal
23. The Trojan Horse appendix tactic (free work attached to application) — trace to Patrick McKenzie, Stripe culture, Jane Street, etc.
24. Loom video as cover letter — emerging norm, when it works, when it backfires
25. GitHub-as-CV for engineers

## Output format

Markdown. One section per rule, in the order listed. Use the exact section headings from the template above (Rule / The conventional wisdom / Historical origin / Functional justification today / When the rule still applies / When the rule breaks down or inverts / The counterintuitive payoff / Sources).

Where two rules have shared origins (e.g., the 1-inch margin and the Times New Roman rule both descend from Word defaults), say so explicitly and cross-reference rather than repeating yourself.

## Quality bar

- **No filler.** If a rule has no interesting archaeology and no functional justification today, say so in 2 lines and move on.
- **Cite real sources.** Eye-tracking studies, recruiter surveys, ATS vendor documentation, career-services textbooks, dated industry blog posts. Avoid generic "experts say" claims.
- **Be willing to say "this is folklore with no evidence base."** That's often the most interesting finding.
- **Surface the surprising insights.** I want every section to have at least one line that makes a reader stop and reconsider what they thought they knew.

## What NOT to do

- Don't summarize "tips for writing a great CV." That's the noise this whole project is trying to push past.
- Don't quote LinkedIn influencers or generic Indeed/Monster blog posts as primary sources.
- Don't add rules I didn't ask about (yet) — stick to the 25 listed.
- Don't recommend tools or services. This is content research, not a product roundup.

# PROMPT END
