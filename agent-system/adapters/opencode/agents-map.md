# OpenCode Agent Map

| OpenCode wrapper | Canonical agent | Canonical skill | MCP policy |
| --- | --- | --- | --- |
| `.opencode/agent/intake-router.md` and `.opencode/agents/intake-router.md` | `agent-system/canonical/agents/intake-router.md` | `question-routing` | No MCP |
| `.opencode/agent/kb-answerer.md` and `.opencode/agents/kb-answerer.md` | `agent-system/canonical/agents/kb-answerer.md` | `kb-answering` | No MCP |
| `.opencode/agent/repo-investigator.md` and `.opencode/agents/repo-investigator.md` | `agent-system/canonical/agents/repo-investigator.md` | `repo-investigation` | No MCP |
| `.opencode/agent/mcp-investigator.md` and `.opencode/agents/mcp-investigator.md` | `agent-system/canonical/agents/mcp-investigator.md` | `mcp-investigation` | Inherits configured MCP |
| `.opencode/agent/escalation-advisor.md` and `.opencode/agents/escalation-advisor.md` | `agent-system/canonical/agents/escalation-advisor.md` | `escalation` | No MCP by default |
| `.opencode/agent/answer-synthesizer.md` and `.opencode/agents/answer-synthesizer.md` | `agent-system/canonical/agents/answer-synthesizer.md` | `answer-synthesis` | No MCP |
