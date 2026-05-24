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
- https://github.com/forrestchang/andrej-karpathy-skills/tree/main/skills/karpathy-guidelines

Adapted patterns:

- Markdown is the agent program.
- The harness should be small enough to understand.
- Name editable and read-only surfaces.
- Define the proof before editing.
- Keep measured wins; discard failures.
- Prefer simpler code when outcomes tie.
- Use skill-sized instructions for repeated workflows instead of loading every
  detail into the standing prompt.
- Use four coding rules: think before coding, simplicity first, surgical
  changes, and goal-driven execution.

## Steinberger

Sources:

- https://github.com/steipete/agent-scripts/blob/main/AGENTS.MD
- https://github.com/steipete/agent-scripts/blob/main/tools.md
- https://github.com/steipete/agent-scripts/blob/main/README.md
- https://steipete.me/posts/just-talk-to-it
- https://zenn.dev/seyz/articles/20260308-steipete-codex-how-to

Adapted patterns:

- Keep agent rules terse.
- Put secrets, git, release, and CI behavior where agents will see it.
- Prefer exact local commands.
- Keep local tool catalogs separate from hard rules.
- Prefer `gh` for GitHub issue, PR, CI, release, and repo-identity work.
- Record auth source names, permissions, and known limits without exposing
  secret values.
- Treat dirty worktrees as state, not noise.
- Make publish policy explicit.

## X And Agent Markdown

Sources:

- https://docs.x.com/tools/llms-txt
- https://x.com/itsolelehmann/status/2026559843109306774
- https://x.com/Aizcalibur/status/2039808212107505700
- https://x.com/alex_prompter/status/2039853870810108384
- https://x.com/karpathy/status/1872038630405054853

Adapted patterns:

- Treat Markdown files as an agent-readable interface, not just prose.
- Give agents an index and small summaries so they know what to open.
- Keep behavior, tools, routing, queue, and knowledge in separate files with
  clear ownership.
- Capture tool gotchas where they are read, not in scattered conversation
  history.
- Reduce cognitive load by making the next action and the right file obvious.

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
