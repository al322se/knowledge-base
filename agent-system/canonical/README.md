# Canonical agent system

The canonical layer is the main source of truth for this agent system. Adapters may add runtime-specific wrappers, but they should not redefine behavior that belongs here.

## Contents

- `pipelines/` describes end-to-end workflows.
- `agents/` defines each agent role, policy, state outputs, and handoff contract.
- `skills/` defines reusable procedures that are not tied to Claude Code, OpenCode, or any other runtime.
- `state-templates/` contains markdown templates for resumable local sessions.

## Operating rules

- Keep runtime-specific permission details in adapters.
- Keep canonical MCP policy here.
- Store real session state under `.local/`.
- Write unconfirmed facts as `[требует уточнения]`.
- Keep final user answers separate from KB update suggestions.
