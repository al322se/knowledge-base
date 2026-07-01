---
description: Use first for any on-call chat question; creates or resumes local session state and routes KB, repo, MCP, escalation, and synthesis work.
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

Read and follow `agent-system/canonical/agents/intake-router.md`.

Also use:
- `agent-system/canonical/skills/question-routing/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the canonical MCP policy: no MCP.
