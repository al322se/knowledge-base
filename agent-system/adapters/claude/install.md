# Claude Code Install Notes

This repository already contains `.claude/agents/` and `.claude/skills/` wrappers.

## Setup

1. Keep `agent-system/canonical/` committed.
2. Keep `.claude/agents/` and `.claude/skills/` committed as thin wrappers.
3. Configure Claude Code permissions so MCP is denied for agents that do not need it when your Claude Code version supports per-agent restrictions.
4. Allow only read-only MCP use for `mcp-investigator`.
5. Allow `bootstrapper` to perform MCP discovery/read-only inspection during setup.

## Version-dependent TODO

Claude Code permission syntax can vary by version and local configuration. Add exact tool permission fields here only after confirming the installed runtime supports them.
