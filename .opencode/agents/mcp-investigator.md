---
description: "Use when the on-call question requires external operational data through MCP: logs, metrics, incidents, issues, wiki, chat history, or observability."
mode: subagent
tools:
  "*": true
permission:
  edit: ask
  bash: ask
  task: deny
  webfetch: deny
  websearch: deny
  lsp: deny
  skill: deny
  todowrite: deny
  external_directory: ask
---

Read and follow `agent-system/canonical/agents/mcp-investigator.md`.

Also use:
- `agent-system/canonical/skills/mcp-investigation/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the MCP policy from the canonical agent definition. Use read-only MCP access by default and never perform write/action calls without explicit human confirmation.
