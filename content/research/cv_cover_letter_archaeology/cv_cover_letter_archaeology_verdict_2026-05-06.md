# CV & Cover Letter Archaeology — Research Comparison & Verdict

**Date:** 2026-05-06
**Topic:** Hidden origins of the rules everyone follows when writing CVs and cover letters — which are still load-bearing vs. pure folklore
**Reports compared:**
- [`claude_2026-05-06.md`](claude_2026-05-06.md) — most comprehensive, strongest historical sourcing
- [`chatgpt_2026-05-06.md`](chatgpt_2026-05-06.md) — best citation density, most cautious about overclaim
- [`gemini_2026-05-06.md`](gemini_2026-05-06.md) — punchiest, most quotable, most carousel-ready
**Purpose:** Feed the *Career Artifacts Archaeology* series ([brief](../../briefs/cv_cover_letter_archaeology.md), 9 post slots in [backlog](../../post_ideas_backlog.md)). Anchor post — the "no first person" rule — is already drafted; this verdict ranks the remaining 24 rules by virality / depth / fit and locks the production order.
**Context files read:** `content/briefs/cv_cover_letter_archaeology.md`, `content/post_ideas_backlog.md`, `prompts/research_cv_cover_letter_history_prompt.md`, `persona/fred_developer_persona.md`

---

## TL;DR

**Claude wins overall** on rigor, sourcing, and counterintuitive-payoff sharpness — it's the report you build the carousel from. **Gemini wins on hooks** — almost every rule has a one-line punchline that could be a slide-1 headline as-is. **ChatGPT is the safety net** — most cautious with citations, useful for fact-checking the other two. All three converge on a clear hierarchy: a small set of rules (one-page, photo, references-line, career objective, skills bars, "I am writing to apply…", AI-perfect-grammar) carry maximum counterintuitive payoff and should be produced first. The "no I" rule (already drafted) is correctly slotted as anchor — no report contradicts that framing. Highest viral-potential single discovery across all three reports: **action-verb lists trace to a 1980s US federal résumé-parsing system called Resumix** (Claude, sourced; Gemini hints at it). Strongest disagreement: **PDF vs Word** — reports split on which actually parses better in modern ATS, useful as a "the rule everyone gives you is wrong" post.

---

## 1. Scoring Summary

| Dimension | Claude | ChatGPT | Gemini |
|---|---|---|---|
| Historical sourcing depth | 9 | 8 | 6 |
| Citation density / verifiability | 8 | 9 | 5 |
| Counterintuitive-payoff sharpness | 9 | 6 | 9 |
| Carousel-ready hook lines | 7 | 5 | 10 |
| Coverage breadth (rules covered) | 10 | 9 | 9 |
| Honesty about weak evidence | 9 | 9 | 6 |
| Fred-voice fit (anti-hype, evidence-first) | 9 | 8 | 7 |
| Operator-readiness (can you ship a post from it) | 9 | 6 | 8 |
| Unique-insight density | 9 | 6 | 8 |
| **Overall weighted composite** | **9.0** | **7.3** | **7.6** |

**Winner — Claude.** It is the only report with named primary sources (Resumix at OPM 1994, Stanley Morison 1973 on Times New Roman, Rivera 2012 on cultural matching at elite firms, Kahneman as the cognitive basis for "quantify everything", SHRM's explicit retirement of "References available upon request"). The historical layers are clean — almost every rule gets traced to two or three separate origins that compounded. This is the report you write *from*.

**Runner-up — Gemini.** Loses on sourcing (most "Sources:" lines are empty stubs) but wins on punchiness. Lines like *"Millions of modern job seekers are still writing their opening sentences to appease a 1960s mailroom clerk who no longer exists"* are slide-1 ready with zero rewriting. Use as the hook generator.

**Third — ChatGPT.** Solid, cautious, well-cited (real footnotes with study citations), but lighter on the storytelling. Best used as the fact-check pass: when Claude or Gemini make a quotable claim, check if ChatGPT either supports it with a study or quietly omits it.

---

## 2. Head-to-Head Comparison

### 2.1 The "one page only" rule

| Model | Origin attribution | Strongest evidence | Verdict bar |
|---|---|---|---|
| Claude | 1970s–90s MBA career services + physical-mail filing-cabinet logistics; *not* the "6-second scan" myth that's retroactively applied | TheLadders 2012 eye-tracking, ResumeGo 2018 (n=7,712, 2.3× preference for 2-page among senior recruiters), LinkedIn 2016/2018 surveys | Strong inversion at 10+ yrs experience |
| ChatGPT | Late-20th-century print/fax era; "career advice myth" with no clear origin | Scale.jobs 2026 — modern ATS no longer favor 1-page; cutting can hurt by removing keywords | Same direction, lighter sourcing |
| Gemini | 1980s fax-machine cost + corporate restructuring philosophy | Recruiter avg 7.4 sec scan (post-recession); E/F-pattern scanning research | Same direction; weakest on the two-page-better data |

**Winner: Claude** — the ResumeGo n=7,712 finding and the explicit "single-page CV for a VP reads as a red flag" framing is the strongest payoff line.

### 2.2 The "no color" rule

| Model | Origin | Modern justification | Twist |
|---|---|---|---|
| Claude | Fax era + early ATS OCR limitations | Mostly obsolete; risk is now "low-contrast text-as-image", not color per se | Strategic single accent color *improves* scannability |
| ChatGPT | Same | **75% of recruiters saw parsing errors on colored CVs (Jobscan 2023)** — citation Claude doesn't have | Most cautious; recommends keeping color if going to humans only |
| Gemini | Fax + 1990s scanning | F-pattern eye-tracking — color *distracts* from titles/dates | Cleanest hook |

**Winner: Tie Claude + ChatGPT.** ChatGPT's Jobscan stat is the load-bearing data point; Claude's framing is more sophisticated.

### 2.3 PDF vs Word

| Model | Recommendation | Reasoning |
|---|---|---|
| Claude | **Word parses more reliably in major ATS (Taleo, iCIMS, SuccessFactors); use PDF for human readers only** | Jobscan analysis |
| ChatGPT | **PDF preferred** — modern OCR is good, both accepted | UT Martin / MIT CAPD guidelines |
| Gemini | **~70% of staffing agencies prefer Word** for editability and template porting | Industry practice |

**Winner: Claude + Gemini converge against ChatGPT.** This disagreement is itself the post — *"The PDF rule everyone gives you is wrong if you're going through a big-company ATS."*

### 2.4 "Action verbs only"

| Model | Origin | Status |
|---|---|---|
| Claude | **US federal Resumix system (1990s, OPM/DoD) + 1980s outplacement industry curricula** — verbatim sourced | Saturated to invisibility; senior CVs increasingly drop the pattern |
| ChatGPT | "No specific inventor; career-writing gospel by 2000s"; cites US DoL handbook | Still useful, low-effort polish |
| Gemini | Not deeply addressed as a standalone rule | — |

**Winner: Claude — by a wide margin.** The Resumix attribution is the single most viral-potential discovery in the entire research batch. Nobody on Instagram knows action verbs were originally a federal government parser-optimization trick.

### 2.5 The "AI-perfect-grammar is now suspicious" rule

| Model | Framing | Evidence |
|---|---|---|
| Claude | Genuine epistemic shift 2022–2024; signal inversion is novel | LinkedIn discussions, AI-detection vendors |
| ChatGPT | Not deeply covered | — |
| Gemini | **"Grammar inversion" — 80%+ of hiring managers report discarding fully AI-generated apps; idiosyncratic human grammar is now a premium feature** | Best one-liner in the batch |

**Winner: Gemini.** This is the AI-era anchor and Gemini owns it.

### 2.6 The Trojan Horse appendix (Fred's original contribution)

| Model | Treatment |
|---|---|
| Claude | Not covered as a named rule |
| ChatGPT | Not covered as a named rule |
| Gemini | **Names Patrick McKenzie / Starfighter / Stripe / Jane Street as origin; frames as "Proof of Work" against ATS** |

**Winner: Gemini** — and confirms Fred's instinct that this is the right closer for the series. Use Gemini's framing as scaffolding, then add Fred's own perspective.

---

## 3. What Each Report Did Best

### Claude
- **Resumix attribution for action verbs:** The single most viral-potential historical discovery — federal government résumé-parsing system from the 1990s explains why every CV bullet starts with "Spearheaded." Sourced to OPM 1994 publication.
- **Three-layer origin model:** Almost every rule gets traced to *multiple* compounding origins (technology + institutional teaching + corporate inertia). This is the framing Fred should adopt across the whole series.
- **"References available upon request" verdict:** SHRM has *explicitly retired* the guidance — strong, citable, kills any debate.
- **Career objective vs Professional Summary distinction:** "The objective asks 'what do I want?'; the summary states 'what do I offer?'" — clean enough to be a single carousel slide.
- **PDF vs Word inversion:** Documented that Word parses *more* reliably in major ATS — directly contradicts the conventional "always PDF" rule.
- **Skills-bar dual failure:** "The only CV element that manages to fail at both the machine-processing layer AND the human-persuasion layer simultaneously."

### Gemini
- **Closing punchlines:** Almost every rule ends with a one-liner that could be slide 1 as-is. Examples:
  - *"Millions of modern job seekers are still writing their opening sentences to appease a 1960s mailroom clerk who no longer exists."*
  - *"You aren't naming the file for the tracking software; you are naming it for the exact moment a stressed executive accidentally drops your file onto their desktop and needs to find it three minutes before your interview."*
  - *"In a market flooded by millions of flawlessly generated AI applications, the presence of slightly imperfect, idiosyncratic human grammar has transitioned from a liability into a premium feature."*
- **AI-era treatment:** Strongest on grammar inversion, Loom video as anti-AI proof, GitHub-as-CV as "version control tracking your daily labor."
- **Trojan Horse named origins:** Patrick McKenzie / Starfighter — gives Fred the lineage to credit while still owning his contribution.

### ChatGPT
- **Citation discipline:** Real footnote-style references throughout (TheLadders, Jobscan, ResumeGo, Indeed CA, Zety, etc.). When Claude or Gemini make a punchy claim, this is the report to verify against.
- **Honesty about weak evidence:** Explicitly flags rules where "no primary source found" rather than fabricating an origin. Fred's anti-hype voice should adopt this discipline.
- **"References Available Upon Request" — Indeed 2025 + Zety quotes:** Two independent recent confirmations the line is dead.

---

## 4. What Each Report Got Wrong (Flags & Corrections)

### Claude
- The **"Resumix as the origin of action verbs"** claim is plausible and well-framed but the citation (`OPM publication 1994`) should be treated as a directional source — Fred should soften the on-slide claim to *"a 1990s US federal résumé-parsing system"* unless the OPM doc can be located directly. High virality, slight verification debt.
- Some "no traceable primary source" admissions are buried — pull them forward when writing slides; they're the honesty signal that defines Fred's voice.
- Photos rule: claims "PDF parsing errors regardless of cultural convention" — overclaim; this is a tendency, not universal.

### Gemini
- **Most "Sources:" lines are empty stubs.** Treat every Gemini factual claim as needing a Claude or ChatGPT cross-check before it ships in a carousel.
- *"68% of recruiters reject for typos"* and *"23% of applications rejected due to incorrect file format / naming"* — surface specific, no source attached. **Do not put these numbers on a slide without finding the source first.**
- Skills bars: claims they "drop out of the database entirely" — too absolute. Claude's "embedded as image layers" framing is more accurate.
- The Marco Rubio / State Department / Calibri story is novel and quotable but unverified — flag for separate fact-check before any slide ships.

### ChatGPT
- Numbered citations like `【52†L149-L157】` are artifacts of the research environment, not real footnotes — Fred can't actually click through. Treat them as "this report claims a real source exists" not "this is a verified source."
- Underplays the Resumix discovery (doesn't mention it at all) — would have been a miss if used alone.
- Section on AI-era artifacts is the weakest of the three; Gemini owns this terrain.

### Cross-cutting
- All three reports lean US/UK-first. The European photo norm is covered, but Argentine / LATAM CV culture is not addressed at all — opportunity for a Fred-original angle (Spanglish audience).
- None of the three substantively address the **resume → ATS → recruiter → hiring-manager funnel** as a *system*. That's the meta-frame Fred can add as the connective thread across the series.

---

## 5. Unique Contributions

| Idea | Model | Value | Notes |
|---|---|---|---|
| Action verbs originated in 1990s US federal Resumix system | Claude | **High** | Single most viral-potential discovery — needs verification before shipping |
| ResumeGo n=7,712 study: 2.3× preference for 2-page among senior recruiters | Claude | **High** | Kills the one-page rule for any senior-leaning audience |
| SHRM has explicitly retired "References available upon request" | Claude | **High** | Authority signal Fred can quote directly |
| Skills bars fail at both human and machine layers simultaneously | Claude | **High** | Perfect single-slide payoff |
| Career objective ≠ Professional Summary ("what I want" vs "what I offer") | Claude | **High** | Clean reframe |
| Gemini's "1960s mailroom clerk" line for "I am writing to apply…" | Gemini | **High** | Hook line, ship as-is |
| Gemini's "grammar inversion" framing for AI-era CVs | Gemini | **High** | Anchor for the AI-era post |
| Trojan Horse traced to Patrick McKenzie / Starfighter | Gemini | **High** | Gives Fred the lineage to credit while still owning his version |
| Cultural matching research (Rivera 2012, *American Sociological Review*) for hobbies section | Claude | Medium | Adds class-signaling depth — risky for IG, brilliant for podcast |
| 75% recruiters saw parsing errors on colored CVs (Jobscan 2023) | ChatGPT | Medium | Single load-bearing stat for the no-color post |
| Word parses *better* than PDF in major ATS | Claude + Gemini | Medium | Counterintuitive, but a niche claim — not as universally interesting |
| "Best" closing as product of 1990s email + 2010s mobile compression | Claude | Low | True but small payoff |
| Marco Rubio / State Dept / Calibri reversion 2025 | Gemini | Low (needs verification) | Quotable if true; high embarrassment cost if not |

---

## 6. Cross-Cutting Consensus (High-Confidence Actions)

| # | Action | Confidence | Effort | Notes |
|---|---|---|---|---|
| 1 | Ship the "no first person" anchor post first (already drafted) | Very High | S | All three reports indirectly support the framing; no contradiction |
| 2 | Build the *one-page rule* post next — strongest sourcing across all three | Very High | M | Use Claude's ResumeGo + LinkedIn data; Gemini's E/F-pattern hook |
| 3 | Build the *"References available upon request"* post — universal kill, all three agree | Very High | S | Shortest carousel possible; one-rule deconstruction |
| 4 | Build the *career objective vs professional summary* post | High | M | Claude's "want vs offer" framing is the slide |
| 5 | Build the *AI-era / grammar inversion* post (Gemini's framing) as series midpoint | High | M | Bridges the historical and the original-contribution halves |
| 6 | Close the series with the *Trojan Horse appendix* post — Fred's original contribution, with Gemini's lineage credit | Very High | M | The post that turns curator → contributor |
| 7 | Set up `content/research/` workflow + research-verdict-synthesizer agent permanently | High | M | This batch proved the value; institutionalize it |

---

## 7. Where Reports Diverge

| Topic | Claude says | Gemini says | ChatGPT says | Our call |
|---|---|---|---|---|
| PDF vs Word for ATS | Word parses more reliably in major ATS | ~70% of staffing agencies prefer Word | PDF preferred, both accepted | **Claude + Gemini win** — frame the post as "the PDF rule is wrong for ATS-gated apps" |
| Origin of action verbs | Federal Resumix system (1990s OPM/DoD) | Not addressed | Folklore, no clear inventor | **Claude wins** — but soften specificity until OPM doc verified |
| Color rule | Mostly obsolete; risk is text-as-image not color | Distracts F-pattern scanning | Causes 75% parsing error rate (Jobscan 2023) | **Use ChatGPT's stat as load-bearing data, Claude's framing as the lesson** |
| Skills bars | Fail at both ATS and human layers | "Algorithm perceives skill as zero" | Not deeply covered | **Claude's framing wins** — Gemini's "zero" line is the punchline |
| Photos rule | US: liability-driven; LinkedIn paradox erodes it | DACH still expects them; LATAM cultural | Same | All three agree — produce as-is, no resolution needed |
| Three-paragraph cover letter | No evidence 3 outperforms 2 or 4 | Survives because it tells reader what to skip | Reasonable starting template | **Gemini's framing is the hook; Claude's evidence is the lesson** |

---

## 8. Synthesized Action Items

### Immediate (this week)
- [ ] Verify the **OPM Resumix 1994 publication** exists before shipping any post that uses the federal-government attribution — Source: Claude — Effort: S
- [ ] Verify the **Marco Rubio / State Department Calibri reversion 2025** before referencing it anywhere — Source: Gemini — Effort: S
- [ ] Verify Gemini's loose stats (*68% reject for typos*, *23% reject for file naming*) or remove them from production — Source: Gemini — Effort: S
- [ ] Update [`content/briefs/cv_cover_letter_archaeology.md`](../../briefs/cv_cover_letter_archaeology.md) with the locked production order from §6 — Source: Consensus — Effort: S
- [ ] Update [`content/post_ideas_backlog.md`](../../post_ideas_backlog.md) — promote the 5 ranked posts to "next up", deprioritize weaker rules — Source: Consensus — Effort: S

### Near-Term (next 2 weeks — production)
- [ ] Produce **Post 1: "No first person"** (anchor, already drafted) — feed brief to `@carousel-writer` — Effort: M
- [ ] Produce **Post 2: "One page only"** carousel — use Claude as primary source — Effort: M
- [ ] Produce **Post 3: "References Available Upon Request"** (shortest, universal kill) — Effort: S
- [ ] Produce **Post 4: "Career Objective vs Professional Summary"** — Effort: M
- [ ] Produce **Post 5: "Why your perfect-grammar AI-CV gets rejected"** (AI-era pivot) — Effort: M

### Backlog (full series)
- [ ] **Post 6:** "Action verbs were a 1990s government parser hack" (depends on Resumix verification) — Effort: M
- [ ] **Post 7:** "PDF vs Word — the rule everyone gives you is backwards for ATS" — Effort: M
- [ ] **Post 8:** "Skills bars: the only CV element that fails at both machine and human layers" — Effort: S
- [ ] **Post 9 (CLOSER):** "The Trojan Horse Appendix — Fred's original contribution" — Effort: L

### Tooling
- [ ] Create `@research-verdict-synthesizer` agent in `.github/agents/` (see plan section below) — Effort: M
- [ ] Add `content/research/README.md` index entry every time a new verdict ships — Source: Process — Effort: S

---

## 9. Carousel Skeleton — Top 6 Findings, Ranked for Production

Ranked across four lenses: **viral potential** (counterintuitive payoff strength), **awareness** (how universally known the rule is — higher = more readers feel called out), **value** (does the reader walk away able to do something differently), **authority** (does Fred's voice + sourcing carry it without sounding tipster-y).

| Rank | Finding | Viral | Awareness | Value | Authority | Best post format |
|---|---|---|---|---|---|---|
| 1 | **Action verbs trace to a 1990s US federal résumé-parsing system (Resumix)** | 10 | 10 | 8 | 8 (after verification) | 9-slide carousel, anchor: "every CV bullet you've ever written was optimized for a 1990s government computer" |
| 2 | **Perfect grammar is now a *negative* signal — AI killed it** | 10 | 9 | 9 | 9 | 9-slide carousel, anchor: "The CV rule that flipped overnight" |
| 3 | **The one-page rule is wrong above 8 years of experience (ResumeGo n=7,712: 2.3× preference for 2-page)** | 9 | 10 | 9 | 10 | 9-slide carousel, anchor: "If you're senior, the one-page rule is making you look junior" |
| 4 | **"References available upon request" — SHRM officially retired it** | 9 | 10 | 7 | 9 | Short carousel (5–6 slides) or single-rule post: "The line on your CV that's been dead since 1995" |
| 5 | **Career objective vs Professional Summary — "what I want" vs "what I offer"** | 7 | 9 | 9 | 8 | 9-slide carousel, anchor: "If your CV opens with what you want, you're using a 1950s template" |
| 6 | **The Trojan Horse Appendix (Fred's original)** | 9 | 6 (yet) | 10 | 10 (Fred owns it) | 9-slide carousel + lead magnet (Trojan Horse Appendix template) |

### Anchor carousel structure (template Fred can apply to each rule)

- **Slide 1 — Hook:** the rule everyone follows (one line) + the counterintuitive reveal teased
- **Slide 2 — The folk story:** what people *think* the rule is for (status / professionalism / etc.)
- **Slides 3–4 — The actual archaeology:** trace the origin (technology / institution / era)
- **Slide 5 — When it still applies:** the load-bearing cases (don't be a contrarian for its own sake — Fred's anti-hype voice)
- **Slide 6 — When it inverts:** the cases where following it actively hurts you
- **Slide 7 — The modern best practice:** what to actually do
- **Slide 8 — The Golden Rule slide:** *"AI can replace the 40 hours of busywork. It can't replace your voice, your story, or your authenticity."*
- **Slide 9 — CTA:** save / share / DM "ARCHAEOLOGY" for the full series checklist (lead magnet hook)

### Series narrative arc

The 9-post series should build a **single argument**, not just stack 9 deconstructions:

1. **(Anchor)** No "I" → CV voice is fossilized
2. One page only → CV length is fossilized
3. References line → CV closing is fossilized
4. Career objective → CV opening is fossilized
5. Action verbs → CV bullet style is fossilized
6. PDF vs Word → CV format advice is wrong for the modern funnel
7. Perfect grammar → AI broke the meaning of "polished"
8. Loom video / GitHub-as-CV → the CV itself is dissolving
9. **(Closer)** Trojan Horse Appendix → if the CV is dissolving, here's what you ship instead

That arc turns the series from "interesting historical commentary" into **"Fred is the person who articulated where the document is going."** Curator → contributor.

---

## 10. Open Questions / Research Debt

- **Resumix:** The OPM 1994 publication needs to be located, or the claim downgraded to "1990s federal hiring systems" without specific naming.
- **LATAM / Spanglish angle:** None of the three reports addressed Argentine, Mexican, or broader LATAM CV culture. Worth its own brief — Fred has direct authority here.
- **Recruiter interviews:** All three reports lean on surveys. A single 30-min interview with one practicing recruiter would 10x the credibility of any post in this series. Worth pursuing as a one-off podcast episode that doubles as primary-source research.
- **Anti-evidence:** None of the three reports steelmanned the rules they deconstructed. A future iteration of this series could include an "OK, but here's the strongest case *for* the rule" pass. Likely overkill for IG, valuable for podcast.

---

**Verdict saved.** Hand off to `@content-planner` to update the post backlog priorities and to `@decision-logger` to record the locked 9-post series order as a strategy decision. Production starts with the already-drafted anchor post.
