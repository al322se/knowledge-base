---
status: draft
scope: decision
sources:
  - ../AGENTS.md
last_verified: 2026-06-08
confidence: low
---

# First Pass

Goal: create a useful map without pretending to understand more than the evidence supports.

## Steps

1. Read `AGENTS.md` and `KB_INDEX.md`.
2. List sibling repositories that should be part of this KB.
3. Update `inventory/repositories.md` with relative paths and known remotes.
4. For each repository, create `repos/<repo-name>.md` from `templates/repo-card.md`.
5. Read only small high-signal files first: README, AGENTS, solution/project manifests, package manifests, docker compose, entrypoints, tests.
6. Update each repo card with purpose, entrypoints, test commands, source links, and open questions.
7. Update `architecture/dependencies.md` only with relationships backed by evidence.
8. Add unknowns to `decisions/open-questions.md`.
9. Update `glossary.md` and `links.md` only for terms and links that appeared in sources.
10. End with a short report: created files, verified facts, uncertainties, and next probes.

## First Pass Constraints

- Do not read entire source trees before building the index.
- Do not copy long code blocks into KB pages.
- Do not infer ownership from repository names alone.
- Do not mark a page `verified` unless its important claims have provenance.
- Prefer `unknown` or `needs-confirmation` over a guess.

## Suggested Repo Inspection Order

1. Repository root files.
2. Existing docs.
3. Build and package manifests.
4. Entrypoints.
5. Tests.
6. Configuration.
7. Source files only for specific claims.
