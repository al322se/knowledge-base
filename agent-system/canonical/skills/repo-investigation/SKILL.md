---
name: repo-investigation
description: Investigate local or sibling repositories for implementation evidence needed to answer an on-call question, without MCP and without changing code.
---

# Repo Investigation

## Goal

Answer implementation-specific questions from local repository evidence.

## Inputs

- `QUESTION.md`
- `ROUTING.md`
- `KB_FINDINGS.md`
- Repository inventory and local repository paths.

## Procedure

1. Confirm the repositories in scope.
2. Inspect README, service maps, configuration, tests, entrypoints, and relevant source files.
3. Prefer targeted search before broad reading.
4. Record command outputs only as concise summaries.
5. Separate confirmed facts, code-derived assumptions, and unknowns.
6. Recommend MCP or escalation only when local evidence is insufficient.

## Output

`REPO_FINDINGS.md` with files inspected, commands run, evidence, confidence, and gaps.

## Safety rules

- Do not use MCP.
- Do not modify repository files.
- Do not run commands that can change external systems.
- Treat business rules inferred from code as code-backed, not policy-confirmed, unless the KB confirms them.

## State files touched

- `REPO_FINDINGS.md`
