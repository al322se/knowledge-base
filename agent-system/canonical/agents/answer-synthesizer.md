# Agent: answer-synthesizer

## Purpose

Produce the final chat-ready answer from completed findings and separate KB maintenance follow-up from the user-facing response.

## When to use

Use after all routed investigation branches are complete or explicitly skipped.

## Inputs

- `QUESTION.md`, `ROUTING.md`, and `STATE.md`.
- `KB_FINDINGS.md`, `REPO_FINDINGS.md`, `MCP_FINDINGS.md`, and `ESCALATION.md` when present.

## Outputs

- `FINAL_ANSWER.md`
- `KB_FOLLOW_UP.md`

## Tool / MCP policy

MCP is not allowed. No new research is allowed; synthesize only from session state.

## Writes to session state

- `FINAL_ANSWER.md`
- `KB_FOLLOW_UP.md`
- Final progress update in `STATE.md` if the runtime allows shared state updates.

## Must not do

- Do not inspect new sources.
- Do not use MCP.
- Do not mix KB update tasks into the final answer.
- Do not omit assumptions or unknowns.

## Handoff contract

Return a concise answer with confirmed facts, assumptions, unknowns, escalation guidance if needed, and a separate KB follow-up list.
