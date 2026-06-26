---
name: mcp-investigation
description: Use configured MCP read-only sources to investigate logs, metrics, incidents, issues, wiki, chat history, or observability for an on-call question.
---

# MCP Investigation

## Goal

Collect external operational evidence when KB and repositories are not enough.

## Inputs

- `QUESTION.md`
- `ROUTING.md`
- Existing findings.
- Available MCP tools and company-specific policy.

## Procedure

1. Confirm that routing requires MCP.
2. Identify the minimum source, time range, and query scope needed.
3. Prefer read-only MCP calls.
4. Record source type, safe query summary, time range, and observed facts.
5. Redact sensitive values from state files.
6. Mark uncertain or missing evidence as `[требует уточнения]`.

## Output

`MCP_FINDINGS.md` with checked sources, confirmed facts, unknowns, and escalation signals.

## Safety rules

- Do not perform write/action MCP calls without explicit human confirmation.
- Do not reveal secrets, tokens, or sensitive private endpoints.
- Do not use MCP when local KB or repository evidence is sufficient.
- Do not write the final answer.

## State files touched

- `MCP_FINDINGS.md`
