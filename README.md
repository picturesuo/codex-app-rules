# Codex App Rules

Common Codex app rules for any repo.

This repo gives projects a small, durable agent surface:

- `AGENTS.md`: hard rules, coding posture, and publish policy.
- `docs/agent-workflow.md`: the working loop.
- `docs/workflow-packaging-audit.md`: when to create a skill, subagent,
  automation, extension, or skip.
- `docs/queue.md`: the next small task.
- `docs/knowledge.md`: durable project facts and user preferences.
- `.codex/config.toml`: repo-scoped Codex defaults.

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

## Sources

- OpenAI Codex best practices: https://developers.openai.com/codex/learn/best-practices
- OpenAI Codex Memories: https://developers.openai.com/codex/memories
- OpenAI Codex Chronicle: https://developers.openai.com/codex/memories/chronicle
- Karpathy `autoresearch`: https://github.com/karpathy/autoresearch
- Karpathy `program.md`: https://github.com/karpathy/autoresearch/blob/master/program.md
- Karpathy-inspired `CLAUDE.md`: https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md
- Steinberger agent scripts: https://github.com/steipete/agent-scripts
- Simon Willison on parallel coding agents: https://simonwillison.net/2025/Oct/5/parallel-coding-agents/
