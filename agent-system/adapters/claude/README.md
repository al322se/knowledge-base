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

`.claude/agents/*` should point to the matching canonical agent file and relevant canonical skill. Claude Code subagent frontmatter is intentionally minimal.

MCP permissions should be restricted by agent where the installed Claude Code version supports it. `mcp-investigator` and `bootstrapper` are the only agents expected to use MCP.

## Skill wrappers

`.claude/skills/*/SKILL.md` mirrors canonical skill metadata and points back to the canonical skill body.

## MCP expectations

- No MCP: `intake-router`, `kb-answerer`, `repo-investigator`, `escalation-advisor`, `answer-synthesizer`.
- MCP read-only expected: `mcp-investigator`.
- MCP discovery/read-only allowed during setup: `bootstrapper`.
- Write/action MCP calls require explicit human confirmation.
