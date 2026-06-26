---
name: question-routing
description: Route on-call chat questions by creating local session state, classifying intent, and selecting KB, repository, MCP, escalation, and synthesis agents.
---

# Question Routing

## Goal

Create resumable state for an on-call question and decide which agents are required.

## Inputs

- User question and chat context.
- Existing session path when resuming.
- KB index and repository inventory.

## Procedure

1. If no session exists, create `.local/answer-sessions/YYYY-MM-DD-HHMM-question-slug/`.
2. Write `QUESTION.md` with the original question, context, requester, time, and constraints.
3. Read existing `STATE.md` when resuming.
4. Classify intent, urgency, affected system, evidence needed, and risk.
5. Choose required branches: KB, repo, MCP, escalation.
6. Write `ROUTING.md` with decisions and reasons.
7. Write or update `STATE.md` with ordered steps and current status.

## Output

A session folder with routing state and a clear next-agent list.

## Safety rules

- Do not answer finally.
- Do not use MCP.
- Do not mark unverified facts as confirmed.
- Write `[требует уточнения]` for unknowns that affect routing.

## State files touched

- `STATE.md`
- `QUESTION.md`
- `ROUTING.md`
