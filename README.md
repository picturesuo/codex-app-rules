# Codex App Rules

A small Markdown operating kit for Codex-ready repos.

The package gives every checkout the same durable surface:

- a behavior contract Codex reads before acting;
- a working loop that turns vague requests into verifiable outcomes;
- safe places to store routing, tools, task state, and durable knowledge;
- a publish path that commits and pushes only verified repo-visible work.

## File Map

| File | Job |
| --- | --- |
| `AGENTS.md` | Hard rules, coding posture, and publish policy. |
| `docs/agent-workflow.md` | The enter, edit, verify, and ship loop. |
| `docs/project-routing.md` | Repo identity, GitHub, publish, and related-project routing. |
| `docs/tools.md` | Local tool catalog, auth source names, permissions, and known limits. |
| `docs/workflow-packaging-audit.md` | When repeated work deserves a skill, subagent, automation, doc, or script. |
| `docs/queue.md` | The next task and clean handoff state. |
| `docs/knowledge.md` | Durable project facts and user preferences. |
| `.codex/config.toml` | Repo-scoped Codex defaults. |

## Install

From this repo:

```bash
bin/install-codex-rules /path/to/project
```

From a target repo:

```bash
/Users/bensuo/Desktop/codex-app-rules/bin/install-codex-rules
```

The installer copies only missing files. Existing project instructions are left
alone and should be merged by hand.

## Contract

The shared rules adapt the Karpathy-inspired `CLAUDE.md` pattern for Codex:

- think before coding;
- simplicity first;
- surgical changes;
- goal-driven execution.

They also define the publish path: inspect branch and dirty state, preserve
other people's changes, verify, commit, and push finished repo-visible work
unless the user asks for local-only work.

Project-specific GitHub accounts, remotes, release rules, tool paths, and
related repos belong in the installed target repo docs. The shared templates
provide safe places to record them without storing secrets.

The design bias is deliberately plain: one file per job, exact local commands
over lore, compact summaries over sprawling context, and no secrets anywhere an
agent may quote, commit, or publish.

## Workflow Biases

- Brief tasks like GitHub issues: goal, context, constraints, done condition.
- Keep always-on instructions short; move occasional workflows into skills.
- Use separate threads or subagents for noisy exploration, logs, long tests, and
  independent review.
- Prefer repo scripts and CLIs before heavier integrations; add MCP or browser
  tools when they close a real feedback loop.
- Use automations only after the manual workflow is stable and the result is
  easy to review.
- Feed repeated mistakes back into the smallest durable file that prevents them.

## Sources

- OpenAI Codex best practices: https://developers.openai.com/codex/learn/best-practices
- OpenAI Codex Memories: https://developers.openai.com/codex/memories
- OpenAI Codex Chronicle: https://developers.openai.com/codex/memories/chronicle
- Karpathy `autoresearch`: https://github.com/karpathy/autoresearch
- Karpathy `program.md`: https://github.com/karpathy/autoresearch/blob/master/program.md
- Karpathy-inspired `CLAUDE.md`: https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md
- Steinberger agent scripts: https://github.com/steipete/agent-scripts
- Steinberger tools catalog: https://github.com/steipete/agent-scripts/blob/main/tools.md
- X agent-resource docs: https://docs.x.com/tools/llms-txt
- Anthropic Claude Code best practices: https://code.claude.com/docs/en/best-practices
- Anthropic effective agents: https://www.anthropic.com/engineering/building-effective-agents
- Anthropic context engineering: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- AGENTS.md format: https://agents.md
- YC Conductor: https://www.ycombinator.com/companies/conductor
- Simon Willison on parallel coding agents: https://simonwillison.net/2025/Oct/5/parallel-coding-agents/
