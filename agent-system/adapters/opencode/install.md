# OpenCode Install Notes

This repository contains `.opencode/agent/`, `.opencode/agents/`, and `.opencode/skills/` wrappers. Current OpenCode docs use `.opencode/agents/`; `.opencode/agent/` is kept for compatibility with the original template structure.

## Setup

1. Keep `agent-system/canonical/` committed.
2. Keep `.opencode/agents/`, `.opencode/agent/`, and `.opencode/skills/` committed as thin wrappers.
3. Use the committed agent frontmatter to keep MCP denied for all agents except `mcp-investigator`.
4. Allow only configured read-only MCP tools for `mcp-investigator`.
5. For company bootstrap MCP discovery, create a local override that enables the exact read-only MCP server patterns.

## Version-dependent TODO

Do not invent MCP tool names; use the names from the local OpenCode configuration. If a local OpenCode version changes frontmatter syntax, keep the same policy: deny MCP everywhere except `mcp-investigator`, and expose bootstrap MCP only through a local named-server override.
