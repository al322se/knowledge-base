# Pipeline: Chat Question Answering

```text
User question
  ↓
intake-router
  - creates .local/answer-sessions/<session>/
  - writes QUESTION.md and STATE.md
  - classifies question
  - decides which agents are needed
  ↓
kb-answerer
  - searches existing KB
  - no MCP
  ↓
optional parallel branches:
  repo-investigator
    - reads local/sibling repositories
    - no MCP

  mcp-investigator
    - reads logs, dashboards, issues, incidents, chat/wiki via configured MCP
    - MCP allowed, preferably read-only
  ↓
escalation-advisor, if needed
  - decides whether human escalation is required
  - no MCP by default
  ↓
answer-synthesizer
  - produces answer for chat
  - separates confirmed facts, assumptions, unknowns
  - writes FINAL_ANSWER.md
  - writes KB_FOLLOW_UP.md
```

## Required rules

- Router runs first for every on-call chat question.
- Router does not produce the final answer. It only creates session state and routes work.
- KB answerer searches the existing KB first.
- Repo investigator reads local and sibling repositories without MCP.
- MCP investigator is the only regular question-answering agent with MCP access.
- MCP investigator uses read-only access by default and must not perform write/action calls without explicit human confirmation.
- Answer synthesizer does no new research. It only combines completed findings.
- Each agent writes its result to its own session state file.
- If work stops, the next run must read `STATE.md` and continue from the first incomplete step.
- If a fact is not confirmed, write `[требует уточнения]`.
- If the KB should be updated after the answer, write that in `KB_FOLLOW_UP.md`; do not mix KB maintenance notes into the final chat answer.

## Session state

Real session folders are created under:

```text
.local/answer-sessions/YYYY-MM-DD-HHMM-question-slug/
```

Use the templates from `agent-system/canonical/state-templates/question-session/`.

## Minimal routing outcomes

- `kb_only`: Existing KB likely contains a sufficient answer.
- `kb_plus_repo`: KB context exists, but local code or sibling repositories must be checked.
- `kb_plus_mcp`: External operational sources are needed.
- `repo_only`: The question is about implementation and can be answered from local repositories.
- `mcp_required`: The answer depends on live or external operational data.
- `escalation_required`: Human judgment, ownership, or incident process is needed.

## Evidence discipline

Findings must cite their source path, command output, document name, or MCP source summary. Do not paste secrets, tokens, or sensitive private endpoints into committed docs.
