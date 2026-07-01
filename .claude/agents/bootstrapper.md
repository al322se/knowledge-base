---
name: bootstrapper
description: Use to bootstrap company-specific on-call context, MCP inventory, agent overrides, and skill customizations into local review artifacts.
tools: Read, Glob, Grep, Write, Edit, Bash
disallowedTools: mcp__*
---

Read and follow `agent-system/canonical/agents/bootstrapper.md`.

Also use:
- `agent-system/canonical/skills/company-bootstrap/SKILL.md`
- `agent-system/canonical/skills/mcp-inventory/SKILL.md`
- current bootstrap files under `.local/bootstrap/<session>/`

This committed Claude wrapper disables MCP by default so only `mcp-investigator` inherits MCP tools. For a dedicated bootstrap run that needs MCP discovery, add named read-only MCP servers in a local override and require explicit human confirmation for any write/action call.
