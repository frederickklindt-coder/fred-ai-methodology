# Agent: Decision Logger

Version: 1.0 | Date: 2026-04-06 | Status: 🔲 To Build (decision log exists, agent wrapper needed)

## Purpose

Logs content decisions with rationale, maintains the decision log, and ensures every strategic choice is documented. Mirrors the engineering discipline Fred already uses in his dev projects.

## Trigger

- Any content strategy decision is made
- A new content type or format is adopted
- Publishing cadence changes
- Agent pipeline is modified

## Input

```yaml
decision_type: content_strategy | agent_pipeline | brand | toolstack | publishing
summary: "[One-line description of the decision]"
rationale: "[Why this decision was made]"
alternatives_considered: "[What else was on the table]"
reversible: yes | no
```

## Output

Appends to `decisions/decision_log.md`:

```markdown
### C-[NNN] — [Summary]
**Date:** YYYY-MM-DD
**Type:** [decision_type]
**Decision:** [Full description]
**Rationale:** [Why]
**Alternatives:** [What was considered]
**Reversible:** [yes/no]
```

## Dependencies

- Reads: `decisions/decision_log.md` (to get next C-NNN number)
- Writes: `decisions/decision_log.md` (append)

## Notes

- Currently at C-018. Next decision is C-019.
- This agent is lightweight but maintains discipline. Every decision has a paper trail.
- Fred already does this in his dev work — this extends it to content.
