---
description: Use to bootstrap company-specific on-call context, MCP inventory, agent overrides, and skill customizations into local review artifacts.
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

Read and follow `agent-system/canonical/agents/bootstrapper.md`.

Also use:
- `agent-system/canonical/skills/company-bootstrap/SKILL.md`
- `agent-system/canonical/skills/mcp-inventory/SKILL.md`
- current bootstrap files under `.local/bootstrap/<session>/`

This committed OpenCode wrapper disables MCP by default so only `mcp-investigator` inherits MCP tools. For a dedicated bootstrap run that needs MCP discovery, enable named read-only MCP server patterns in a local override and require explicit human confirmation for any write/action call.
