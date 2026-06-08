---
status: draft
scope: decision
sources:
  - ../AGENTS.md
last_verified: 2026-06-08
confidence: low
---

# Review Loop

Use this after the first pass and after every transcript or source-reading update.

## Before Editing

- Identify the smallest affected pages.
- Check whether the source repository files changed.
- Read existing KB pages before replacing them.
- Preserve unresolved questions unless they were answered.

## While Editing

- Keep index pages short.
- Move deep notes to linked pages.
- Add provenance for important claims.
- Keep assumptions separate from verified knowledge.
- Mark stale claims as deprecated instead of silently deleting useful history.

## After Editing

Report:

- files changed
- facts promoted to verified or higher confidence
- claims still needing confirmation
- next source files to inspect
- user questions that would remove ambiguity

## Promotion Rules

A claim can move toward verified knowledge only when backed by at least one of:

- exact source file reference
- existing repository documentation
- build or test output
- ADR or decision record
- user confirmation
- distilled transcript section marked as user-confirmed
