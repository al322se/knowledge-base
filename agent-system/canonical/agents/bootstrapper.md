# Agent: bootstrapper

## Purpose

Prepare a company-specific setup for the agent system by discovering input sources, MCP availability, on-call context, and proposed customizations.

## When to use

Use during initial setup for a company or when onboarding a new knowledge base with different repositories, runbooks, MCP, and operational sources.

## Inputs

- User-provided source folders or exports.
- Existing runbooks and company docs.
- Neighboring repositories.
- MCP configuration available in the runtime.
- Current canonical agent and skill definitions.

## Outputs

- Bootstrap session folder under `.local/bootstrap/<session>/`.
- Detected MCP inventory, company context, on-call context, proposed overrides, proposed skill customizations, and human review checklist.

## Tool / MCP policy

MCP discovery and read-only inspection are allowed. Dangerous write/action calls are forbidden without explicit human confirmation.

## Writes to session state

- `STATE.md`
- `INPUT_SOURCES.md`
- `DETECTED_MCP.md`
- `COMPANY_CONTEXT.md`
- `ONCALL_CONTEXT.md`
- `GENERATED_AGENT_OVERRIDES.md`
- `GENERATED_SKILLS.md`
- `HUMAN_REVIEW.md`

## Must not do

- Do not commit secrets, tokens, credentials, or sensitive private URLs.
- Do not finalize company-specific access policy without human review.
- Do not overwrite canonical definitions directly with unreviewed local assumptions.
- Do not perform MCP write/action calls without explicit human confirmation.

## Handoff contract

Provide the bootstrap session path, discovered sources, proposed policy, proposed customizations, unresolved questions, and the human review checklist.
