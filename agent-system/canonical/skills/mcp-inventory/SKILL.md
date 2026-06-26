---
name: mcp-inventory
description: Inventory configured MCP tools for bootstrap, classify read-only versus action-capable access, and identify which operations require human confirmation.
---

# MCP Inventory

## Goal

Document available MCP capabilities and safe use policy for company bootstrap.

## Inputs

- Runtime MCP configuration.
- Company policy if available.
- Bootstrap session path.

## Procedure

1. List available MCP servers or connectors without exposing secrets.
2. For each source, record purpose and broad data category.
3. Classify capabilities as read-only, action-capable, or unknown.
4. Mark safe default usage and operations requiring explicit confirmation.
5. Record missing policy questions for human review.

## Output

`DETECTED_MCP.md` with a safe inventory and review notes.

## Safety rules

- Do not include tokens, credentials, or secret config values.
- Do not perform write/action calls while inventorying.
- Do not assume unknown capabilities are safe.
- Mark unknown policy as `[требует уточнения]`.

## State files touched

- `DETECTED_MCP.md`
