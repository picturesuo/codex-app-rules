---
summary: Source patterns behind the common Codex app rules.
read_when:
  - You are changing AGENTS.md or templates.
  - You need to know why a rule exists.
---

# Source Inspirations

## Karpathy

Sources:

- https://github.com/karpathy/autoresearch
- https://github.com/karpathy/autoresearch/blob/master/program.md
- https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md

Adapted patterns:

- Markdown is the agent program.
- The harness should be small enough to understand.
- Name editable and read-only surfaces.
- Define the proof before editing.
- Keep measured wins; discard failures.
- Prefer simpler code when outcomes tie.
- Use four coding rules: think before coding, simplicity first, surgical
  changes, and goal-driven execution.

## Steinberger

Sources:

- https://github.com/steipete/agent-scripts/blob/main/AGENTS.MD
- https://steipete.me/posts/just-talk-to-it
- https://zenn.dev/seyz/articles/20260308-steipete-codex-how-to

Adapted patterns:

- Keep agent rules terse.
- Put secrets, git, release, and CI behavior where agents will see it.
- Prefer exact local commands.
- Treat dirty worktrees as state, not noise.
- Make publish policy explicit.

## OpenAI Codex

Sources:

- https://developers.openai.com/codex/learn/best-practices
- https://developers.openai.com/codex/memories
- https://developers.openai.com/codex/memories/chronicle

Adapted patterns:

- Personal defaults belong in `~/.codex/config.toml`.
- Repo behavior belongs in `.codex/config.toml`, `AGENTS.md`, and docs.
- Skills are for narrow repeated workflows.
- Automations are for repeatable scheduled work.
- Memories and Chronicle are discovery aids; confirm important facts in source
  systems.

## Simon Willison

Source:

- https://simonwillison.net/2025/Oct/5/parallel-coding-agents/

Adapted patterns:

- Parallel agents work best for research, archaeology, small maintenance, and
  clearly specified implementation.
- Save useful findings so later sessions start with better local knowledge.
