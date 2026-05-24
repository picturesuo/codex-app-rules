# Codex App Rules

Portable Codex app rules, templates, and workflow docs for repo-local agent
setup.

This repo packages the Codex-app-first workflow that came out of the
cmux/Ghostty launcher work:

- `AGENTS.md` as the durable agent contract.
- `docs/agent-workflow.md` as the session loop.
- `docs/workflow-packaging-audit.md` as the "should this become a skill,
  subagent, automation, extension, or skip?" playbook.
- `.codex/config.toml` as repo-scoped Codex defaults.
- `docs/queue.md` and `docs/knowledge.md` as small mutable/durable context
  surfaces.

## Install Into A Project

From a target repo:

```bash
cp /Users/bensuo/Desktop/codex-app-rules/templates/AGENTS.md AGENTS.md
mkdir -p docs .codex
cp /Users/bensuo/Desktop/codex-app-rules/templates/docs/*.md docs/
cp /Users/bensuo/Desktop/codex-app-rules/templates/.codex/config.toml .codex/config.toml
```

If a project already has any of those files, merge by hand instead of
overwriting. The target repo's own rules win.

## What The Rules Do

The seeded `AGENTS.md` adapts the Karpathy-inspired `CLAUDE.md` rules into
Codex:

- Think before coding.
- Simplicity first.
- Surgical changes.
- Goal-driven execution.

It also carries a Steinberger-style publish path: inspect branch and dirty
state, preserve user changes, verify, commit, and push finished repo-visible
work unless the user asks for local-only work.

## Sources

- OpenAI Codex best practices: https://developers.openai.com/codex/learn/best-practices
- OpenAI Codex Memories: https://developers.openai.com/codex/memories
- OpenAI Codex Chronicle: https://developers.openai.com/codex/memories/chronicle
- Karpathy autoresearch: https://github.com/karpathy/autoresearch
- Karpathy `program.md`: https://github.com/karpathy/autoresearch/blob/master/program.md
- Karpathy-inspired `CLAUDE.md`: https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md
- Steinberger agent scripts: https://github.com/steipete/agent-scripts
- Simon Willison on parallel coding agents: https://simonwillison.net/2025/Oct/5/parallel-coding-agents/
