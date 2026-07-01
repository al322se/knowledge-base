---
description: Use when findings indicate human escalation, service ownership, incident process, production risk, unclear authority, or unresolved uncertainty may be needed.
mode: subagent
tools:
  "*": false
  read: true
  glob: true
  grep: true
  list: true
  write: true
  edit: true
  apply_patch: true
  bash: true
permission:
  read: allow
  glob: allow
  grep: allow
  list: allow
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

Read and follow `agent-system/canonical/agents/escalation-advisor.md`.

Also use:
- `agent-system/canonical/skills/escalation/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the canonical MCP policy: no MCP by default.
