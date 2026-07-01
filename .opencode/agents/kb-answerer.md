---
description: Use after intake routing to search the committed knowledge base for a ready or partial answer.
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

Read and follow `agent-system/canonical/agents/kb-answerer.md`.

Also use:
- `agent-system/canonical/skills/kb-answering/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the canonical MCP policy: no MCP.
