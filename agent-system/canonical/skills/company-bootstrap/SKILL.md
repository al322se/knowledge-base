---
name: company-bootstrap
description: Bootstrap a company-specific on-call knowledge-base setup by extracting context, authoritative sources, agent overrides, and skill customizations into local review artifacts.
---

# Company Bootstrap

## Goal

Prepare reviewed company-specific configuration proposals without committing sensitive details.

## Inputs

- Source folders, runbooks, exports, neighboring repositories, and MCP inventory.
- Canonical pipeline, agent, and skill definitions.

## Procedure

1. Create `.local/bootstrap/YYYY-MM-DD-HHMM-company-bootstrap/` if needed.
2. Record input sources and authority levels.
3. Extract company context relevant to on-call work.
4. Extract on-call context: services, owners, escalation, runbooks, observability, and known incident patterns.
5. Propose agent overrides only where the company context requires them.
6. Propose immediate skill customizations.
7. Write a human review checkpoint with unresolved decisions.

## Output

Markdown artifacts under `.local/bootstrap/<session>/` ready for human review.

## Safety rules

- Do not commit secrets, tokens, credentials, or sensitive private URLs.
- Do not finalize access policy without human review.
- Do not overwrite canonical docs with unreviewed company assumptions.
- Keep generated company-specific details local until approved.

## State files touched

- `INPUT_SOURCES.md`
- `COMPANY_CONTEXT.md`
- `ONCALL_CONTEXT.md`
- `GENERATED_AGENT_OVERRIDES.md`
- `GENERATED_SKILLS.md`
- `HUMAN_REVIEW.md`
