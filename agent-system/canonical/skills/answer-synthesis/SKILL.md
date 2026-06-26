---
name: answer-synthesis
description: Synthesize a final chat answer from existing session findings while separating confirmed facts, assumptions, unknowns, escalation, and KB follow-up.
---

# Answer Synthesis

## Goal

Produce a concise final answer without doing new research.

## Inputs

- `QUESTION.md`
- `ROUTING.md`
- `KB_FINDINGS.md`
- `REPO_FINDINGS.md`
- `MCP_FINDINGS.md`
- `ESCALATION.md`

## Procedure

1. Read all available session findings.
2. Do not open new sources.
3. Extract confirmed facts, assumptions, unknowns, and escalation recommendation.
4. Write a chat-ready answer in `FINAL_ANSWER.md`.
5. Write KB maintenance suggestions in `KB_FOLLOW_UP.md`.
6. Keep operational caveats visible and concise.

## Output

- Final answer for the requester.
- Separate KB follow-up notes.

## Safety rules

- Do not use MCP.
- Do not perform new research.
- Do not hide uncertainty.
- Do not mix internal KB maintenance tasks into the user-facing answer.

## State files touched

- `FINAL_ANSWER.md`
- `KB_FOLLOW_UP.md`
