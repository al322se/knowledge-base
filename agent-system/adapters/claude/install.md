# Claude Code Install Notes

This repository already contains `.claude/agents/` and `.claude/skills/` wrappers.

## Setup

1. Keep `agent-system/canonical/` committed.
2. Keep `.claude/agents/` and `.claude/skills/` committed as thin wrappers.
3. Use the committed `.claude/agents/*` frontmatter to keep MCP denied for all agents except `mcp-investigator`.
4. Allow only read-only MCP use for `mcp-investigator`.
5. For company bootstrap MCP discovery, create a local override that names the exact read-only MCP servers to expose.

## Version-dependent TODO

If a local Claude Code version changes frontmatter syntax, keep the same policy: deny `mcp__*` everywhere except `mcp-investigator`, and expose bootstrap MCP only through a local named-server override.
