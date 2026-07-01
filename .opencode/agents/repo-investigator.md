---
description: Use when an on-call question needs implementation evidence from local or sibling repositories.
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

Read and follow `agent-system/canonical/agents/repo-investigator.md`.

Also use:
- `agent-system/canonical/skills/repo-investigation/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the canonical MCP policy: no MCP and no code changes.
