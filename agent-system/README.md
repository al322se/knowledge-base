# Markdown-first on-call agent system

This directory defines a portable, markdown-first agent system for answering on-call chat questions from a knowledge base, local repositories, and optional external operational sources.

## Canonical layer

`agent-system/canonical/` is the source of truth. It describes the pipelines, agents, reusable skills, and state templates that every adapter must follow.

## Adapters

`agent-system/adapters/` explains how to expose the canonical definitions to specific agent runtimes. The committed `.claude/` and `.opencode/` directories contain thin wrappers that point back to canonical markdown.

## Question answering

Start with `intake-router`. It creates `.local/answer-sessions/<session>/`, writes the question and routing state, and chooses which branches are needed:

- `kb-answerer` for existing KB answers, without MCP.
- `repo-investigator` for local or sibling repository reading, without MCP.
- `mcp-investigator` for logs, dashboards, issues, wiki, chat history, and other configured external sources through MCP.
- `escalation-advisor` when a human, team, service owner, or incident process may be needed.
- `answer-synthesizer` for the final chat-ready answer and KB follow-up.

## State and resume

Real session state lives under `.local/answer-sessions/`. This folder is local only and must not be committed.

If work stops, resume by reading the session `STATE.md`, then continue from the first incomplete step. Each agent writes only its own state file.

## MCP policy

By default, agents do not use MCP. The regular question-answering agent expected to use MCP is `mcp-investigator`, and it should use read-only access wherever possible. No agent should perform write or action calls through MCP without explicit human confirmation.
