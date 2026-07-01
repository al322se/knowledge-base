# Claude Code adapter

Claude Code files in `.claude/` are thin wrappers around the canonical agent system.

## Source of truth

Canonical files are the source of truth:

- Agents: `agent-system/canonical/agents/*`
- Skills: `agent-system/canonical/skills/*/SKILL.md`
- Pipelines: `agent-system/canonical/pipelines/*`
- State templates: `agent-system/canonical/state-templates/*`

Do not redefine agent behavior in `.claude/`. Update canonical files first, then adjust wrappers only if the runtime needs different metadata.

## Agent wrappers

`.claude/agents/*` should point to the matching canonical agent file and relevant canonical skill.

MCP permissions are restricted by agent frontmatter:

- Non-MCP agents use a `tools` allowlist for built-in local tools and `disallowedTools: mcp__*`.
- `mcp-investigator` is the only committed wrapper that inherits configured MCP tools.
- `bootstrapper` is local-only by default in the committed wrapper. For a dedicated company bootstrap that needs MCP discovery, add named read-only MCP servers in a local override.

## Skill wrappers

`.claude/skills/*/SKILL.md` mirrors canonical skill metadata and points back to the canonical skill body.

## MCP expectations

- No MCP: `intake-router`, `kb-answerer`, `repo-investigator`, `escalation-advisor`, `answer-synthesizer`, `bootstrapper`.
- MCP read-only expected: `mcp-investigator`.
- MCP discovery/read-only for bootstrap: enable only through a local, named-server override.
- Write/action MCP calls require explicit human confirmation.
