# Claude Agent Map

| Claude wrapper | Canonical agent | Canonical skill | MCP policy |
| --- | --- | --- | --- |
| `.claude/agents/intake-router.md` | `agent-system/canonical/agents/intake-router.md` | `question-routing` | No MCP |
| `.claude/agents/kb-answerer.md` | `agent-system/canonical/agents/kb-answerer.md` | `kb-answering` | No MCP |
| `.claude/agents/repo-investigator.md` | `agent-system/canonical/agents/repo-investigator.md` | `repo-investigation` | No MCP |
| `.claude/agents/mcp-investigator.md` | `agent-system/canonical/agents/mcp-investigator.md` | `mcp-investigation` | MCP read-only by default |
| `.claude/agents/escalation-advisor.md` | `agent-system/canonical/agents/escalation-advisor.md` | `escalation` | No MCP by default |
| `.claude/agents/answer-synthesizer.md` | `agent-system/canonical/agents/answer-synthesizer.md` | `answer-synthesis` | No MCP |
