# Pipeline: Company Bootstrap

```text
bootstrapper
  ↓
asks for or discovers input sources
  - folder with company/on-call docs
  - existing runbooks
  - neighbouring repositories
  - wiki/docs exports
  - MCP configuration
  ↓
creates .local/bootstrap/<session>/
  ↓
mcp-inventory skill
  - lists available MCP
  - marks read-only vs action-capable
  - marks safe vs requires confirmation
  ↓
company-bootstrap skill
  - extracts company-specific on-call context
  - identifies authoritative sources
  - proposes agent overrides
  - proposes immediate skill customizations
  ↓
human review checkpoint
  - do not silently finalize company-specific access policy
```

## Required artifacts

Bootstrapper creates markdown artifacts in:

```text
.local/bootstrap/YYYY-MM-DD-HHMM-company-bootstrap/
```

Required files:

- `STATE.md`
- `INPUT_SOURCES.md`
- `DETECTED_MCP.md`
- `COMPANY_CONTEXT.md`
- `ONCALL_CONTEXT.md`
- `GENERATED_AGENT_OVERRIDES.md`
- `GENERATED_SKILLS.md`
- `HUMAN_REVIEW.md`

## Safety rules

- Do not commit secrets, tokens, credentials, or sensitive private URLs.
- Do not silently finalize company-specific access policy.
- Use MCP discovery/read-only calls by default.
- Require explicit human confirmation before any dangerous write/action call.
- Put generated company-specific proposals in `.local/bootstrap/<session>/` until reviewed.

## Review outcome

After human review, accepted policy and customization can be copied into committed docs as templates or instructions with sensitive details removed.
