# Research

Archive of multi-model deep-research reports + comparison verdicts that feed the content pipeline.

## Folder structure

```
content/research/
└── {topic_slug}/
    ├── claude_{YYYY-MM-DD}.md
    ├── chatgpt_{YYYY-MM-DD}.md
    ├── gemini_{YYYY-MM-DD}.md
    └── {topic_slug}_verdict_{YYYY-MM-DD}.md
```

One folder per research topic. Raw reports archived as evidence — never edited or merged. Verdict is the synthesis layer that ranks findings, surfaces consensus, and proposes carousel/post candidates.

## Naming

- Topic slug: lowercase snake_case, stable across iterations (e.g. `cv_cover_letter_archaeology`)
- Raw reports: `{model}_{YYYY-MM-DD}.md` where model ∈ `claude | chatgpt | gemini`
- Verdict: `{topic_slug}_verdict_{YYYY-MM-DD}.md`

## Index

| Topic | Date | Verdict | Status | Connected brief |
|---|---|---|---|---|
| CV & Cover Letter Archaeology | 2026-05-06 | [verdict](cv_cover_letter_archaeology/cv_cover_letter_archaeology_verdict_2026-05-06.md) | Ready to produce | [`briefs/cv_cover_letter_archaeology.md`](../briefs/cv_cover_letter_archaeology.md) |

## Workflow

1. Run a deep-research prompt (from `prompts/`) in three models in parallel.
2. Drop the three `.md` outputs into the conversation with `@research-verdict-synthesizer`.
3. Agent saves raw reports under `content/research/{topic_slug}/` with the naming convention.
4. Agent produces the verdict file: scoring, head-to-head, ranked findings, carousel skeleton.
5. Verdict feeds back into the relevant brief and the post ideas backlog.
