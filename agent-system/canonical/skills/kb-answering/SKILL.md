---
name: kb-answering
description: Search committed knowledge-base markdown for an existing answer to an on-call question without using MCP or external systems.
---

# KB Answering

## Goal

Find a ready or partial answer in the KB before deeper investigation.

## Inputs

- `QUESTION.md`
- `ROUTING.md`
- KB index and committed documentation.

## Procedure

1. Read the question and routing decision.
2. Search high-level indexes first.
3. Follow links to repository maps, business rules, architecture pages, runbooks, and source summaries.
4. Record confirmed facts with source links.
5. Mark the result as `answer_found`, `partial_answer`, or `not_found`.
6. List gaps and suggested next branches.

## Output

`KB_FINDINGS.md` with answer status, evidence, gaps, and suggested next steps.

## Safety rules

- Do not use MCP.
- Do not inspect new external sources.
- Do not update KB pages during the answering session.
- Mark unsupported claims as `[требует уточнения]`.

## State files touched

- `KB_FINDINGS.md`
