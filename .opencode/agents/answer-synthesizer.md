---
description: Use after routed investigation is complete to write the final chat answer and separate KB follow-up.
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

Read and follow `agent-system/canonical/agents/answer-synthesizer.md`.

Also use:
- `agent-system/canonical/skills/answer-synthesis/SKILL.md`
- current session files under `.local/answer-sessions/<session>/`

Respect the canonical MCP policy: no MCP and no new research.
