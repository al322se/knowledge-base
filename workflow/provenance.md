---
status: draft
scope: decision
sources:
  - ../AGENTS.md
last_verified: 2026-06-08
confidence: low
---

# Source Links And Provenance

Every important claim should explain where it came from.

## Source Types

- `source-code` - exact repository path, file, symbol, or module.
- `repo-doc` - README, AGENTS, docs, runbook, changelog.
- `command-output` - build, test, lint, schema generation, migration output.
- `user-confirmed` - explicitly confirmed by a human.
- `transcript-distilled` - summarized from transcript and reviewed.
- `agent-inferred` - a temporary inference that needs confirmation.

## Confidence

- `low` - useful lead, not verified.
- `medium` - supported by one source or strong local evidence.
- `high` - backed by source and either tests, docs, ADR, or user confirmation.

## Page Status

- `draft` - useful but incomplete.
- `verified` - key claims have provenance.
- `deprecated` - retained for historical context, not active guidance.

## Rule Of Thumb

If the claim would affect an implementation decision, add a source link or move it to open questions.
