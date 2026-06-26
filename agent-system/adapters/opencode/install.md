# OpenCode Install Notes

This repository already contains `.opencode/agent/` and `.opencode/skills/` wrappers.

## Setup

1. Keep `agent-system/canonical/` committed.
2. Keep `.opencode/agent/` and `.opencode/skills/` committed as thin wrappers.
3. Configure OpenCode permissions so MCP/tool access is denied for agents that do not need it.
4. Allow only configured read-only MCP tools for `mcp-investigator`.
5. Allow `bootstrapper` to perform MCP discovery/read-only inspection during setup.

## Version-dependent TODO

OpenCode permission syntax can vary by version and local configuration. Add exact permission fields here only after confirming the installed runtime supports them. Do not invent MCP tool names; use the names from the local OpenCode configuration.
