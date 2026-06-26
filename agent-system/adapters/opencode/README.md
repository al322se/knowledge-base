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

`.opencode/agent/*` should point to the matching canonical agent file and relevant canonical skill.

OpenCode permissions should deny MCP/tool access for agents that do not need it. Only `mcp-investigator` and `bootstrapper` should be allowed to use configured MCP tools.

## Skill wrappers

`.opencode/skills/*/SKILL.md` mirrors canonical skill metadata and points back to the canonical skill body.

## MCP expectations

- No MCP: `intake-router`, `kb-answerer`, `repo-investigator`, `escalation-advisor`, `answer-synthesizer`.
- MCP read-only expected: `mcp-investigator`.
- MCP discovery/read-only allowed during setup: `bootstrapper`.
- Write/action MCP calls require explicit human confirmation.
