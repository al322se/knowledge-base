---
name: escalation
description: Decide whether an on-call question requires human escalation, service ownership, incident process, or explicit uncertainty in the final answer.
---

# Escalation

## Goal

Identify whether the session needs human involvement and prepare a clear escalation recommendation.

## Inputs

- `QUESTION.md`
- `ROUTING.md`
- Available findings.
- KB escalation policy when present.

## Procedure

1. Check for user impact, production risk, missing authority, action requests, and unclear ownership.
2. Compare findings against known escalation policy.
3. Decide `required`, `recommended`, or `not_needed`.
4. Identify owner, team, or process when known.
5. Draft a short escalation message if useful.

## Output

`ESCALATION.md` with decision, reason, urgency, target, and evidence to attach.

## Safety rules

- Do not page, message, or trigger incident workflows by itself.
- Do not use MCP by default.
- Do not downplay uncertainty.
- Mark missing policy or ownership as `[требует уточнения]`.

## State files touched

- `ESCALATION.md`
