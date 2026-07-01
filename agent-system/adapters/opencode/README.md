# OpenCode adapter

OpenCode files in `.opencode/` are thin wrappers around the canonical agent system.

## Source of truth

Canonical files are the source of truth:

- Agents: `agent-system/canonical/agents/*`
- Skills: `agent-system/canonical/skills/*/SKILL.md`
- Pipelines: `agent-system/canonical/pipelines/*`
- State templates: `agent-system/canonical/state-templates/*`

Do not redefine agent behavior in `.opencode/`. Update canonical files first, then adjust wrappers only for OpenCode metadata or permissions.

## Agent wrappers

`.opencode/agent/*` and `.opencode/agents/*` should point to the matching canonical agent file and relevant canonical skill. The plural `.opencode/agents/` path matches current OpenCode docs; the singular `.opencode/agent/` path is kept as a compatibility wrapper from the original template structure.

OpenCode wrappers use agent frontmatter permissions:

- Non-MCP agents use `tools: "*": false` plus an explicit built-in tool allowlist, which keeps MCP tools out of those agents.
- `mcp-investigator` is the only committed wrapper that inherits configured MCP tools.
- `bootstrapper` is local-only by default. For a dedicated company bootstrap that needs MCP discovery, enable named read-only MCP server patterns in a local override.

## Skill wrappers

`.opencode/skills/*/SKILL.md` mirrors canonical skill metadata and points back to the canonical skill body.

## MCP expectations

- No MCP: `intake-router`, `kb-answerer`, `repo-investigator`, `escalation-advisor`, `answer-synthesizer`, `bootstrapper`.
- MCP read-only expected: `mcp-investigator`.
- MCP discovery/read-only for bootstrap: enable only through a local, named-server override.
- Write/action MCP calls require explicit human confirmation.
