---
summary: External patterns adapted into these Codex app rules.
read_when:
  - You are changing AGENTS.md or template behavior.
  - You need to understand where the rules came from.
---

# Source Inspirations

## Karpathy Autoresearch

Sources:

- https://github.com/karpathy/autoresearch
- https://github.com/karpathy/autoresearch/blob/master/program.md
- https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md

Adapted patterns:

- Markdown is the agent program.
- Keep the harness small enough for the agent to understand.
- Name editable and read-only surfaces explicitly.
- Use fixed evaluation loops when possible.
- Keep or discard changes based on measured output.
- Prefer simplicity when outcomes are equivalent.
- Use four compact coding-agent rules: think before coding, simplicity first,
  surgical changes, and goal-driven execution.

## Steinberger Agent Scripts

Sources:

- https://github.com/steipete/agent-scripts/blob/main/AGENTS.MD
- https://steipete.me/posts/just-talk-to-it
- https://zenn.dev/seyz/articles/20260308-steipete-codex-how-to

Adapted patterns:

- Keep global agent rules terse.
- Put routing, secrets, git, release, and CI behavior where agents will see it.
- Prefer exact local commands over generic advice.
- Treat dirty worktrees and unknown changes as important state.
- Use explicit publish policy.
- Commit and push finished repo-visible changes after verification.

## OpenAI Codex App Workflows

Sources:

- https://developers.openai.com/codex/learn/best-practices
- https://developers.openai.com/codex/memories
- https://developers.openai.com/codex/memories/chronicle

Adapted patterns:

- Keep personal defaults in `~/.codex/config.toml`.
- Keep repo-specific behavior in `.codex/config.toml`, `AGENTS.md`, and docs.
- Use skills for narrow repeated workflows.
- Use automations for specific repeatable scheduled work.
- Use Memories for stable preferences and Chronicle for discovery, then confirm
  important facts in the source system.

## Simon Willison Parallel Agents

Source:

- https://simonwillison.net/2025/Oct/5/parallel-coding-agents/

Adapted patterns:

- Use parallel agents for research, archaeology, small maintenance, and clearly
  specified implementation work.
- Preserve useful findings in docs or shared context so future prompts start
  with better local knowledge.
