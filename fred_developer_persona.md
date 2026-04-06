# Fred — Developer Persona Card

> Auto-generated April 6, 2026 from evidence across three projects:
> **ai-ops** (254 commits, Feb 14 – Apr 5 2026), **inbox-intel** (10 commits, Mar 9 – Mar 27 2026), and **ALT** (sub-project inside ai-ops, ~100+ commits, Mar 18 – Apr 5 2026).
> Based on git history, prompt files, agent definitions, architecture docs, state manifests, test plans, and observed interaction patterns with VS Code AI agents.

---

## TL;DR

Fred is a **solo AI-native builder** who treats LLMs as a full engineering team. He doesn't write code with AI — he **architects systems through AI**, using prompts as specs, agents as teammates, structured debate as QA, and version-controlled state as the source of truth. He ships production systems in weeks, not months, by compressing the idea → spec → build → test → deploy cycle into a continuous loop where every AI output gets reviewed, questioned, and refined before it earns trust.

---

## 1. Identity & Working Style

| Attribute | Description |
|-----------|-------------|
| **Role** | Solo founder-developer building production SaaS + client systems |
| **Stack** | Python / FastAPI / Railway / ChromaDB / OpenAI / GHL / Bland.ai |
| **AI models used** | GPT-4.1-mini (production), Claude Opus (architecture/debate), ChatGPT Deep Research (toolstack research) |
| **Editor** | VS Code with GitHub Copilot agents (Claude Opus 4.6 via Jarvis router) |
| **Commit cadence** | 254 commits in 51 days = ~5 commits/day average; spikes to 10–15 on build days |
| **Time zone** | UTC-3 (working hours span 10 AM – 2 AM, with intensity clustering around evenings) |
| **Projects running concurrently** | 3 (ai-ops production, ALT client build, inbox-intel white-label template) |

---

## 2. How Fred Goes from Idea to Production System

Fred's development cycle is not linear — it's a **tightening spiral** where each loop adds specificity, validation, and hardening. Here's the pattern observed across all three projects:

### Phase 1: Context Dump & Brain Extraction

Fred starts by dumping everything he knows into structured markdown. He doesn't begin with code — he begins with **operating context**.

**Evidence:**
- ALT started with `prompt_master_context.md` — a 200+ line document covering business identity, TCSL portfolio, pricing, care types, MVP market, competitor framing, and key people. This was written *before a single line of code*.
- ai-ops started with `repo_architecture.md` — a full system architecture document describing agents, data flows, and deployment before the agents existed.
- inbox-intel started with `MASTER_PLAN.md` — architecture, onboarding flow, tenant model, and commercial tiers documented on Day 1.

**The pattern:** Write the operating manual first. The code implements the manual.

### Phase 2: Decision Logging & Blocker Identification

Before building, Fred maps every blocking decision and pre-fills recommendations.

**Evidence:**
- `ALT_decision_register_for_chip.md` — **107 questions, 75 pre-filled** with recommended answers, sent to the client (Chip) for approval.
- `decision_log.md` — 48 tracked decisions (D-001 through D-048), each with ID, status, owner, source, date, and build impact.
- `ALT_strategic_gaps_and_blockers.md` — strategic gap analysis identifying risks *before* build starts.
- `ALT_top20_blockers_for_chip.md` — top 20 blocking questions packaged as a single approval request to unblock the build.

**The pattern:** Never assume. Log every decision. Pre-fill answers to speed approval. Track who owns the answer.

### Phase 3: Prompt-Driven Architecture & Model Comparison

Fred doesn't design in his head — he designs by **prompting multiple AI models and comparing their outputs**. He writes detailed context prompts, feeds them to ChatGPT and Claude, reviews both outputs, debates the differences, questions assumptions, and only then makes implementation decisions.

**Evidence:**
- `chatgpt_prompt_bland_integration_architecture.md` — a prompt designed specifically for ChatGPT with Deep Research enabled, instructing it to search Bland.ai docs, verify API contracts, and propose an integration architecture. Includes the line: *"Do NOT hallucinate API endpoints or payload formats. If you can't find something in the docs, say so."*
- `deep_research_prompt_visual_system_map.md` — a prompt for ChatGPT to research the best toolstack for building an interactive 3D pipeline visualization. Not code — a *research assignment* to an AI.
- `ghl_ai_builder_prompt_acknowledge_assign_v2.md` — a copy-paste prompt designed for GHL's AI Workflow Builder, with exact instructions, shared logic consolidation, and the explicit note: *"Replaces the messy v1 workflow with 3 duplicate UTM branches."*
- `prompt_website_audit_seo_compliance.md` — a website audit prompt for SEO, compliance, conversion analysis, and copy drafting.

**The output review cycle:**
1. Write a detailed context prompt with explicit constraints.
2. Send to ChatGPT (often with web search/Deep Research) AND Claude.
3. Compare outputs side by side.
4. Question and debate — challenge AI assumptions, ask for evidence, push back on generic advice.
5. Make a decision, log it (D-ID), and proceed to implementation.

**Example from the user's own words:**
> *"I compare outputs between ChatGPT and Claude. The output is reviewed, debated, questioned and I start making decisions."*

### Phase 4: Iterative Build with Versioned Artifacts

Fred builds in named versions (v1, v2, v1.2 → v1.7) and captures the *reason* for each version bump.

**Evidence — Bland.ai Ava Pathway:**
- v1.2 — initial proof-of-concept, 19 nodes, 34 edges
- v1.3 — anti-loop improvements (timeline/intent handling), tested by live call
- v1.4 — further refinements
- v1.5 — Q4 routing bug fix (edge descriptions too narrow for "none"/"first call")
- v1.6 — Q4 fast-path, tour ban prompt, broadened edge descriptions
- v1.7 — regression fixes, synced to `bland_manifest.json`, retest pending
- Each version has a **JSON export** stored in `alt/02_build/` — the exact import-ready file.

**Evidence — GHL Workflows:**
- `qualification_rules.md` → `qualification_rules_v2.md` (V2 defers clinical screening, limits to Bryan's 5 questions)
- `ghl_build_plan.md` → `ghl_build_plan_v2.md` (V2 adds Go To actions, eliminates 3 duplicate UTM branches)
- `prompt_master_context.md` → `prompt_master_context_v2.md` (V2 references live manifests instead of hardcoded counts)

**The pattern:** Version everything. Name what changed. Keep V1 for rollback. The repo *is* the changelog.

### Phase 5: Agent Creation & Workflow Delegation

Once the project reaches operational complexity, Fred creates **specialist AI agents** — each with a tight scope, required startup reads, explicit write permissions, and guardrails.

**Evidence — Agent Architecture (19 agents in ai-ops, 8 in inbox-intel):**

**ai-ops agents (8 AI-Ops specialists):**
| Agent | Purpose |
|-------|---------|
| `aiops-sync-incident-responder` | First responder for broken syncs, stale checkpoints, GitHub Actions failures |
| `aiops-chroma-auditor` | Audits document counts, duplicates, metadata drift in ChromaDB |
| `aiops-query-contract-reviewer` | Protects source hierarchy, API action enforcement, route behavior |
| `aiops-extraction-refactorer` | Sharpens KPI extraction, taxonomy, entity routing |
| `aiops-artifact-regression-watcher` | Detects quality drops in daily briefs and weekly reports |
| `aiops-commit-archaeologist` | Uses git history to explain behavior changes and propose minimal fixes |
| `aiops-ops-workflow-maintainer` | Owns deployment config, env vars, scheduling, workflow YAML |
| `aiops-template-porting-scout` | Decides what ai-ops features should port to inbox-intel |

**ALT agents (8 + 1 daily sync + 1 router):**
| Agent | Purpose |
|-------|---------|
| `alt-decision-miner` | Extracts decisions from meeting transcripts, updates decision log |
| `alt-status-syncer` | Propagates confirmed decisions across all ALT docs |
| `alt-compliance-packager` | Audits compliance gaps, drafts Warm Media/Chip emails |
| `alt-ghl-builder` | Converts decisions into GHL assets (fields, tags, workflows, forms) |
| `alt-routing-script-architect` | Designs call routing, Bland pathway flow, escalation rules |
| `alt-bland-middleware-builder` | FastAPI endpoints, webhook handlers, GHL writeback |
| `alt-webhook-qa` | Tests endpoints, verifies payloads, runs pytest |
| `alt-scope-guard` | Reviews proposals for scope creep against MVP boundaries |
| `alt-daily-progress-sync` | End-of-day capture of everything built, decided, or changed |
| `jarvis` | Master router that delegates to all agents based on plain-language requests |

**inbox-intel agents (8 onboarding specialists):**
| Agent | Purpose |
|-------|---------|
| `inbox-discovery-digester` | Takes client meeting transcripts, produces tenant delta plan |
| `inbox-tenant-scaffolder` | Creates tenant config from template, runs validation |
| `inbox-connector-onboarder` | Wires client data sources (Outlook, Gmail, webhooks) |
| `inbox-agent-pack-tailor` | Customizes agent recipes for client terminology/KPIs |
| `inbox-tenant-verifier` | Runs full health check on tenant configuration |
| `inbox-api-scheduler-builder` | Sets up scheduled jobs and API routes per tenant |
| `inbox-access-brief-writer` | Produces credential/access requirements doc for clients |
| `inbox-template-drift-manager` | Keeps client repos synced with template improvements |

**Each agent follows the same structural contract:**
1. YAML frontmatter with `description:` and `tools:` declaration
2. Startup reads — numbered list of exact file paths to read before every task
3. "Your Job" — bullet list of responsibilities
4. Write scope — which files/folders the agent may edit
5. Output style — numbered template for response structure
6. Guardrails — what the agent must NOT do
7. Test infrastructure — venv path, pytest command, test files

**The pattern:** Each agent gets a tight write scope, required startup reads, one explicit "must not do" rule, and a handoff artifact. This prevents vague super-agents.

### Phase 6: Observability & State-as-Source-of-Truth

Fred builds observability *into* the development workflow, not after deployment.

**Evidence:**
- `ghl_manifest.json` — live snapshot of GHL state (fields, tags, pipelines, workflows, forms), auto-synced nightly via GitHub Actions
- `bland_manifest.json` — Bland pathway version, phone config, webhook contract, dynamic variables, auto-synced nightly
- `build_status.json` — middleware endpoint status (live|stub|not_built), wiring evidence, missing pieces
- `ghl_change_ledger.md` — every GHL UI change logged with date, category, what needs syncing, sync status
- `integration_architecture.md` — how GHL, Bland, and middleware connect
- `detect_drift.py` — script that detects state drift between GHL manifests and repo docs
- Nightly GitHub Actions for manifest sync + daily brief artifact generation
- `DEGRADATION_NOTICE` pattern in agents — if ChromaDB unavailable, agents still run but output includes visible warning

**The pattern:** State lives in JSON manifests that are version-controlled and auto-synced. Agents read manifests, not hardcoded values. Drift is detected automatically. Every degradation is visible, never silent.

### Phase 7: Testing with Exact Assertions

Fred doesn't just test — he writes test plans with **exact personas, scripts, and pass/fail criteria** before running them.

**Evidence — Ava Test Plan v1:**
- 4 test cases, each with a named persona (Mark, Sarah, etc.) and exact dialog scripts
- Node-by-node expected path through the Bland pathway
- Pass criteria specify exact field values: `outcome_tag` must be `"qualified_callback"`, `guide_offered` must be present, no unresolved `{{tokens}}`
- After each pathway version bump (v1.3 → v1.5 → v1.7), all 4 tests are re-run
- Regression discovered in v1.5 Test 1 → fix applied in v1.6 → verified in v1.7

**Evidence — ai-ops test structure:**
- 22+ test files in `/tests` covering agents, contracts, GHL integration, Bland webhooks, ChromaDB, query agents, E2E pipeline
- `conftest.py` with fixtures for mock ChromaDB, tenant config trees, fake delivery adapters
- Integration tests test the *contract*, not implementation details

### Phase 8: Consolidation & Refactoring

After the first build works, Fred consolidates. He removes duplication, extracts shared logic, and documents what changed and why.

**Evidence:**
- GHL workflow v1 → v2: 3 duplicate UTM source branches consolidated via Go To actions into shared logic sections. Zero duplication.
- `qualification_rules.md` → `qualification_rules_v2.md`: clinical screening deferred to V2, V1 limited to 5 simple questions. Explicit scope control.
- ai-ops → inbox-intel: modules copied verbatim on Day 1, then refactored into tenant-aware abstractions (`TenantLoader`, `AgentRegistry`, `BaseConnector`, `BaseDelivery`) on Day 2–5.
- Agent file references updated from hardcoded `current_status_v2.md` to dynamic "latest `current_status_v*.md` (highest version number)" — prevents stale references.

---

## 3. How Fred Uses AI in the Development Process

### The Prompt → Enhance → Robustify Cycle

Fred's interaction with AI is not "ask → accept." It follows a distinct pattern:

1. **Raw brain dump** — Fred shares unstructured notes, meeting transcripts, ideas, business context. No formatting. Stream of consciousness.
2. **AI produces first draft** — the agent or model generates a structured output (spec, plan, code, decision summary).
3. **Fred reviews and debates** — he questions assumptions, challenges the output, asks "why not X?", pushes back on generic advice, compares against what he already knows.
4. **Enhanced re-prompt** — Fred takes the AI's structure but rewrites the prompt with corrections, additional constraints, and clearer scope.
5. **Second-pass output** — the re-prompted AI produces a tighter, more accurate version.
6. **Model comparison** — Fred runs the same enhanced prompt through ChatGPT and Claude, compares the results, and picks the best elements from each.
7. **Decision & implementation** — Fred logs the decision (D-ID), creates the agent or code, and moves on.

### Cross-Model Strategy

| Model | Fred's Use Case |
|-------|----------------|
| **ChatGPT (Deep Research)** | Toolstack research, API documentation lookup, integration architecture proposals. Fred explicitly tells it to search the web and not hallucinate. |
| **ChatGPT (standard)** | GHL AI Workflow Builder prompts, quick copy-paste specs, compliance language drafts. |
| **Claude Opus (VS Code agents)** | Architecture decisions, code implementation, agent creation, refactoring, state sync, daily operations. Claude is the "hands" — it has file access and terminal. |
| **Both, compared** | Any high-stakes decision. Fred sends the same context to both models, compares their outputs, and picks the stronger reasoning per section. |

### Agent Creation Philosophy

Fred's agent design pattern (observed from 35 agents across 3 projects):

```
1. Identify a repeating task pattern
2. Write the agent's job description (what it does, what it reads, what it writes)
3. Define guardrails (what it must NOT do — this is non-negotiable)
4. Set startup reads (files the agent must read before every task)
5. Specify handoff artifacts (what the agent must produce for the next agent in the chain)
6. Test by running the agent against real tasks
7. Refine based on output quality
```

**Key design rule (Fred's own words):**
> *"Each agent gets a tight write scope, a required handoff artifact, and one explicit 'must not do' rule. That keeps them useful instead of becoming vague super-agents."*

### Example: The Prompt That Created 24 Agents

Fred sent one prompt requesting 8 agents per project. The prompt included:

- Full analysis of all three projects' architecture
- Reference to past prompts, git history, and refactoring patterns
- Specific mention of the development cycle phases: git history analysis, refactoring, cleaning, auditing, testing
- A detailed vision for inbox-intel's client onboarding pipeline: meeting transcript → delta plan → credential brief → code execution → testing → scheduled jobs
- Instruction to "take your time, analyze everything you can"

The result: 24 agents (8 per project) with tight scopes, clear routing keywords, startup reads, and handoffs. Plus the meta-agent (`agent-prompt-analyzer`) that validates all future agent prompts.

---

## 4. Architectural Patterns & Coding Philosophy

### Core Principles (Inferred from Code)

| Principle | Evidence |
|-----------|----------|
| **State as source of truth** | JSON manifests synced nightly, not hardcoded values in prompts |
| **YAML as business logic** | Scoring rules, agent specs, connector configs, tenant settings — all data, not code |
| **Degradation transparency** | Systems report what they DON'T have (ChromaDB down, schema mismatch, permissions denied) |
| **Fail-fast at boot** | Missing env vars detected at startup, write-probes for permissions, health endpoints that report real status |
| **Version everything** | V1/V2 naming for prompts, pathway JSONs, workflow specs, qualification rules |
| **Copy first, refactor later** | ai-ops modules copied verbatim into inbox-intel on Day 1, then refactored into tenant-aware abstractions |
| **Abstraction over inheritance** | `BaseConnector`, `BaseDelivery`, `AgentRegistry` — pluggable registries, not deep class hierarchies |
| **Configuration-driven** | Env vars, YAML specs, tenant directories → no hardcoding client-specific logic |
| **Error recovery, not error suppression** | Retry transient failures, batch-split poisoned data, log incompatibilities, never swallow errors |

### Deployment Patterns

```
Dockerfile (Python 3.12 slim, non-root appuser)
  → docker-entrypoint.sh (fix volume permissions before dropping privs)
  → railway.toml (health check at /ready, 60s timeout, 5 restart retries)
  → Boot validation (fail-fast on missing env vars, write-probe for permissions)
  → GitHub Actions (nightly manifest sync, scheduled agent runs, daily brief generation)
```

Three requirements files per project: `requirements.txt` (cloud), `requirements.local.txt` (dev), `requirements.scraper-windows.txt` (Windows-specific OCR/PDF libs).

### Multi-Tenant Architecture (inbox-intel)

```
Template repo (inbox-intel)
  → "Use this template" → client-{name}-intel repo
  → Customize tenant_config/
  → Deploy to Railway (one deployment per client repo)
  → Client data isolated via separate repos/secrets/schemas
  → Cherry-pick template improvements back into client repos
```

---

## 5. Communication & Documentation Discipline

### Document Types Fred Creates

| Type | Purpose | Example |
|------|---------|---------|
| **Master Context** | Operating manual for AI agents and builders | `prompt_master_context_v2.md` |
| **Decision Log** | Every blocking decision with ID, status, owner, impact | `decision_log.md` (48 entries) |
| **Decision Register** | Pre-filled questions for client approval | `ALT_decision_register_for_chip.md` (107 Qs) |
| **Build Plan** | Phase-by-phase checklist with status | `ghl_build_plan_v2.md` |
| **AI Builder Prompt** | Copy-paste prompt for external AI tools | `ghl_ai_builder_prompt_acknowledge_assign_v2.md` |
| **Deep Research Prompt** | Research assignment for ChatGPT | `deep_research_prompt_visual_system_map.md` |
| **Test Plan** | Personas, scripts, pass criteria | `ava_test_plan_v1.md` |
| **As-Built Capture** | Post-build documentation of what was actually created | `wf_sms_stop_handler.md` |
| **Change Ledger** | Log of every GHL/Bland UI change | `ghl_change_ledger.md` |
| **Gap Analysis** | Strategic assessment of what's missing and why it matters | `ALT_strategic_gaps_and_blockers.md` |
| **State Manifest** | Auto-synced JSON of live platform state | `ghl_manifest.json`, `bland_manifest.json` |

### Commit Message Conventions

```
feat(alt):   — new ALT feature or capability
fix(alt):    — ALT bug fix
fix(sync):   — sync pipeline fix
chore(alt):  — ALT maintenance, docs, ledger updates
chore(manifests): — nightly auto-sync of state files
docs:        — documentation changes
refactor:    — code cleanup without behavior change
```

Commits are descriptive and include the *why*:
- `fix: Q4 routing failure - broaden edge descriptions, add tour ban to Q4 prompt, add Q4 tour fast-path, fix Qualified Callback condition`
- `feat(alt): Phase 1 observability overhaul — fix drift, add integration architecture, reform agent startup reads`
- `Harden daily email sync against single-doc upload failures`

---

## 6. Strengths & Distinguishing Traits

1. **Systems thinker, not feature builder** — Fred designs entire operating systems (CRM + voice AI + middleware + observability + agents), not individual features.

2. **Decision-driven development** — Nothing gets built without a logged decision. Every assumption becomes a question with an owner and a status.

3. **AI as engineering team** — 35 agents across 3 projects, each with a job description, startup reads, and guardrails. Fred manages AI agents the way a tech lead manages engineers: clear scope, explicit deliverables, no ambiguity.

4. **Transparency over polish** — Degradation notices, visible state drift, explicit "what I don't have" reporting. Fred would rather show an ugly warning than silently return bad data.

5. **Velocity through structure** — 254 commits in 51 days while running 3 projects. The structure (decision logs, manifests, agents, test plans) *enables* speed rather than slowing it down.

6. **Production-first mindset** — Railway deployment, health checks, write-probes, permission detection, graceful degradation, retry strategies — all present from early commits, not added later.

7. **Learns from failure, permanently** — When a production issue occurs (connection resets, poisoned batches, embedding failures), the fix becomes a permanent pattern stored in repo memory and applied to all similar code paths.

8. **Compresses the approval cycle** — Instead of waiting for one answer at a time, Fred pre-fills 75 out of 107 questions and sends them as a batch. This turns weeks of back-and-forth into a single review session.

---

## 7. The Fred Development Methodology — Summary

```
                     ┌─────────────────┐
                     │   Raw Context    │
                     │  (brain dump,    │
                     │   transcripts,   │
                     │   meeting notes) │
                     └────────┬────────┘
                              │
                     ┌────────▼────────┐
                     │  Master Context  │
                     │  Document (V1)   │
                     └────────┬────────┘
                              │
                     ┌────────▼────────┐
                     │ Decision Log +   │
                     │ Blocker Register │
                     │ (pre-filled 70%) │
                     └────────┬────────┘
                              │
              ┌───────────────┼───────────────┐
              │               │               │
     ┌────────▼──────┐ ┌─────▼──────┐ ┌──────▼───────┐
     │ ChatGPT Deep  │ │  Claude    │ │  GHL AI      │
     │ Research      │ │  VS Code   │ │  Builder     │
     │ (toolstack,   │ │  (code,    │ │  (workflow   │
     │  API docs,    │ │  agents,   │ │  prompts)    │
     │  integration) │ │  refactor) │ │              │
     └───────┬───────┘ └─────┬──────┘ └──────┬───────┘
              │               │               │
              └───────┬───────┘               │
                      │                       │
             ┌────────▼────────┐              │
             │ Compare, Debate,│              │
             │ Question, Decide│              │
             └────────┬────────┘              │
                      │                       │
             ┌────────▼────────┐              │
             │  Log Decision   │◄─────────────┘
             │  (D-ID)         │
             └────────┬────────┘
                      │
             ┌────────▼────────┐
             │ Build (versioned│
             │ V1 → V2 → V1.7)│
             └────────┬────────┘
                      │
             ┌────────▼────────┐
             │ Test Plan with  │
             │ exact assertions│
             └────────┬────────┘
                      │
             ┌────────▼────────┐
             │ Observability   │
             │ (manifests,     │
             │  ledgers,       │
             │  drift detect)  │
             └────────┬────────┘
                      │
             ┌────────▼────────┐
             │ Agent Creation  │
             │ (tight scope,   │
             │  guardrails,    │
             │  handoffs)      │
             └────────┬────────┘
                      │
             ┌────────▼────────┐
             │ Refactor &      │
             │ Consolidate     │
             │ (V2 replaces V1)│
             └────────┬────────┘
                      │
                      ▼
              ┌──────────────┐
              │  Production  │
              │  + Nightly   │
              │  Auto-Sync   │
              └──────────────┘
```

---

## 8. Agent Creation — The Full Pattern

This section documents how Fred creates AI agents, including example prompts from actual sessions.

### The Agent Creation Workflow

```
1. Hit a recurring task pattern (3+ times doing the same thing)
     ↓
2. Write a natural-language request describing what agents you need
   — Include: project context, past workflow, development cycle phases
   — Include: what information you look for when developing
   — Include: how to validate and read that information for decisions
     ↓
3. AI analyzes the project (architecture docs, git history, state files, prompt files)
     ↓
4. AI proposes agents with: name, scope, routing keywords, startup reads, guardrails
     ↓
5. Fred reviews, debates, refines — challenges vague scopes, too-broad write permissions
     ↓
6. Agents are created with the structural contract (see below)
     ↓
7. Meta-agent (agent-prompt-analyzer) validates all agent prompts for:
   — Missing YAML frontmatter
   — File paths that don't exist
   — Orphaned files that should be in startup reads
   — Missing guardrails or write scope
   — Missing truth hierarchy
     ↓
8. Agents are committed and routed through Jarvis (master router)
```

### The Structural Contract (Every Agent Must Have)

```yaml
---
description: "One-line summary — what this agent does and when to use it"
tools: [read, edit, search, execute]  # explicit capability declaration
---
```

```markdown
## Startup — Read These First
1. `exact/file/path.md`           # Numbered, ordered
2. `exact/file/path2.json`        # Not vague references — exact paths
3. Latest `dir/prefix_v*.md`      # Dynamic version resolution

## Your Job
- Bullet list of responsibilities (verbs, not nouns)

## Write Scope
- Exact directories/files the agent may create or edit
- Anything not listed is OFF LIMITS

## Output Style
1. Numbered response template
2. Forces consistent format across all tasks

## Guardrails
- What the agent must NOT do (explicit denial list)
- Handoff rules (when to escalate to Jarvis or another agent)

## Test Infrastructure
- Venv path, test framework, pytest command, key test files
```

### Example Prompt That Created 24 Agents

This is the kind of prompt Fred sends mid-build to create agents adapted to his workflow:

> *"Suggest me 8 agents I can create for my workflow based on what we are building for ALT, based on what we built for ai-ops and based on what I'm planning to sell as inbox-intel (C:\Users\frede\inbox-intel) which is a white-label system of the ai-ops system. Propose 8 agents per project that are specific to how I built it, prompts I've sent in the past, maybe something about git history, refactoring, cleaning and auditing, as well as testing. Consider the development cycle and how and what agents should I create for each case. Take your time, analyze everything you can to draw your conclusions and suggest 8 agents per project that would make my life easier and avoid repetitive work and still complying with the scope."*
>
> *"For the white-label business I'm thinking on an agent that takes the meeting with the client transcript, digest it, compares with the template built, plan for the addings and updates we will need to do it, then pass that result to another agent that executes the code changes, a draft/brief must be generated in the middle with the credentials, APIs, access, etc I would need from the client to ingest the data, another agent that tests the code until working fine, meaning sending terminal commands, running jobs post manually and checking scheduled jobs, etc — every part of the cycle I did when creating each system."*

**What the AI analyzed to produce the agents:**
- `prompt_master_context_v2.md`, `ghl_build_plan_v2.md`, `routing_rules.md` (ALT operating docs)
- `repo_architecture.md`, `daily_email_sync.py`, `api_server.py` (ai-ops architecture)
- `MASTER_PLAN.md`, `setup_client.py`, `run_pipeline.py` (inbox-intel template docs)
- Git history patterns across all three repos

**What the AI concluded (Fred's design philosophy distilled):**
- ALT is **decision-driven, compliance-gated, and document-first**
- ai-ops is **ops-heavy: sync jobs, retrieval quality, artifacts, API hardening, refactoring**
- inbox-intel is **onboarding-heavy: tenant bootstrap, connector config, agent spec tailoring, verification**

### Why This Approach Works

The agents **adapt to how Fred develops** because they were created *from* how Fred develops:

1. **Startup reads** reflect what Fred actually reads before making decisions — state manifests, decision logs, build plans.
2. **Write scope** reflects Fred's file organization — state files separate from code, docs separate from config.
3. **Guardrails** reflect Fred's actual scope control — V1/V2 boundaries, MVP-only constraints, "never build what's deferred."
4. **Handoff artifacts** reflect Fred's multi-step workflow — decision log entry → status sync → code change → test → deploy.
5. **Agent chaining** reflects Fred's natural sequence — "process this transcript" → mine decisions → sync docs → update manifests.

The agents aren't generic assistants. They're **crystallized versions of Fred's own decision-making process**, packaged so AI can execute each step without losing context or drifting scope.

---

## 9. Project Comparison — Three Systems, One Methodology

| Dimension | ai-ops | ALT | inbox-intel |
|-----------|--------|-----|-------------|
| **Nature** | Production intelligence system | Client lead-gen build | White-label SaaS template |
| **Commits** | 254 in 51 days | ~100+ (subset of ai-ops) | 10 in 18 days |
| **Agents** | 8 AI-Ops specialists + Jarvis | 8 ALT specialists + daily sync | 8 onboarding specialists |
| **Primary AI use** | Report generation, extraction, query | Voice AI (Ava), workflow prompts | Tenant config, recipe customization |
| **Decision tracking** | Implicit in docs | 48 formal D-IDs | Implicit in MASTER_PLAN |
| **State management** | ChromaDB + Google Sheets | JSON manifests + GHL API | YAML per tenant |
| **Deployment** | Railway (persistent) | Same Railway instance | Template → per-client Railway |
| **Test approach** | 22 test files, contract tests | Persona-based test plans, live calls | 3 fixture-heavy integration tests |
| **Documentation** | Architecture-first | Decision-first | Template-first |
| **Core pattern** | Sync → Extract → Report → Deliver | Capture → Qualify → Notify → Track | Onboard → Configure → Verify → Deliver |

---

*Generated by Jarvis from evidence across ai-ops (254 commits), inbox-intel (10 commits), ALT sub-project (~100+ commits), 35 agent definitions, 15+ prompt files, state manifests, decision logs, test plans, and git history dating Feb 14 – Apr 6, 2026.*
