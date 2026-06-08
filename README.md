# knowledge-base

Markdown-only, git-native knowledge base for multi-repository engineering systems.

This repository is designed to live next to the repositories it documents:

```text
workspace/
  knowledge-base/
  api-gateway/
  auth-service/
  frontend-app/
  worker-service/
```

There is no CLI, service, database, package, or generated code in this project. The operating model is: an agent reads `AGENTS.md`, inspects sibling repositories, and maintains structured markdown with progressive disclosure and source links.

## Core Idea

Do not create one huge `PROJECT_KNOWLEDGE.md`.

Use layers:

1. `KB_INDEX.md` - short routing map.
2. `inventory/repositories.md` - repository list and source links.
3. `repos/*.md` - concise repo cards.
4. `systems/*.md` - cross-repo domain pages.
5. `architecture/*.md` and ADRs - dependencies, data flow, decisions.
6. `transcripts/distilled/*.md` - reviewed summaries of raw transcripts.
7. Source repositories - exact code references when a claim needs verification.

## First Pass

Ask an agent to follow [First Pass](workflow/first-pass.md).

The expected first pass creates or updates:

- `inventory/repositories.md`
- `repos/<repo-name>.md`
- `architecture/dependencies.md`
- `decisions/open-questions.md`
- `glossary.md`
- `links.md`

## Review Loop

Use [Review Loop](workflow/review-loop.md) after every pass. The agent should report:

- what changed
- which claims are source-backed
- which claims need confirmation
- which files should be read next
- which user questions remain

## Transcripts

Raw transcripts go to `transcripts/raw/`. They are evidence, not verified knowledge. Distill them through [Transcript Distillation](workflow/transcripts.md) before promoting facts into active KB pages.

## Publication Boundary

This repository can be public, but concrete repo cards may reveal private repository names, local paths, internal domains, or business context. Keep private workspace inventory uncommitted unless it is intentionally publishable.
