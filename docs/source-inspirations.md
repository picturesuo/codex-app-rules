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
- Define the proof and measurement before editing.
- Keep measured wins; discard failures; log the reason.
- Prefer simpler code when outcomes tie.
- Use skill-sized instructions for repeated workflows instead of loading every
  detail into the standing prompt.
- Use four coding rules: think before coding, simplicity first, surgical
  changes, and goal-driven execution.

## Steinberger

Sources:

- https://steipete.me/posts/just-talk-to-it
- https://github.com/steipete/agent-scripts/blob/main/AGENTS.MD
- https://github.com/steipete/agent-scripts/blob/main/tools.md
- https://github.com/steipete/agent-scripts/blob/main/README.md
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
- Think about blast radius before fanning out work.
- Use screenshots and runtime feedback when visual or UI context matters.
- Prefer simple local CLIs over context-heavy integrations unless the
  integration clearly removes a repeated manual loop.

## X And Agent Markdown

Sources:

- https://docs.x.com/tools/llms-txt
- https://x.com/itsolelehmann/status/2026559843109306774
- https://x.com/Aizcalibur/status/2039808212107505700
- https://x.com/alex_prompter/status/2039853870810108384
- https://x.com/karpathy/status/1872038630405054853
- https://x.com/blader/status/2058303538674217319

Adapted patterns:

- Treat Markdown files as an agent-readable interface, not just prose.
- Give agents an index and small summaries so they know what to open.
- Keep behavior, tools, routing, queue, and knowledge in separate files with
  clear ownership.
- Capture tool gotchas where they are read, not in scattered conversation
  history.
- Reduce cognitive load by making the next action and the right file obvious.
- Keep architecture-forming work in one main context until the decision, proof,
  and user alignment are clear.
- Capture durable architectural decisions as short ADRs with invariants and file
  references.
- Dogfood user-facing work through the closest real runtime or UI loop before
  handoff when feasible.
- For long goal runs, use a fresh adversarial review gate before marking work
  done so missed proof, regressions, and overbuilt paths surface early.

## OpenAI Codex

Sources:

- https://developers.openai.com/codex/learn/best-practices
- https://developers.openai.com/codex/memories
- https://developers.openai.com/codex/memories/chronicle
- https://developers.openai.com/codex/guides/agents-md
- https://openai.com/business/guides-and-resources/how-openai-uses-codex/
- https://openai.com/index/introducing-the-codex-app/
- https://openai.com/index/unrolling-the-codex-agent-loop/
- https://openai.com/index/unlocking-the-codex-harness/

Adapted patterns:

- Personal defaults belong in `~/.codex/config.toml`.
- Repo behavior belongs in `.codex/config.toml`, `AGENTS.md`, and docs.
- Skills are for narrow repeated workflows.
- Automations are for repeatable scheduled work.
- Memories and Chronicle are discovery aids; confirm important facts in source
  systems.
- Strong prompts name goal, context, constraints, and done condition.
- Codex app work should be organized as durable threads with reviewable output.
- App skills package workflows that are hard to define consistently.
- Automations combine stable instructions with cadence and a review queue.
- Keep one thread per coherent task to prevent bloated context.
- Treat setup, startup scripts, env vars, and tool availability as part of the
  product surface for Codex.

## Anthropic And Claude Code

Sources:

- https://code.claude.com/docs/en/best-practices
- https://code.claude.com/docs/en/features-overview
- https://code.claude.com/docs/en/sub-agents
- https://code.claude.com/docs/en/hooks
- https://support.claude.com/en/articles/14554000-claude-code-power-user-tips
- https://www.anthropic.com/news/how-anthropic-teams-use-claude-code
- https://www.anthropic.com/engineering/building-effective-agents
- https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- https://www.infoq.com/news/2026/01/claude-code-creator-workflow/

Adapted patterns:

- Verify with tests, screenshots, or expected output.
- Explore first, then plan, then implement for ambiguous work.
- Keep always-on instruction files short; move occasional workflows into skills.
- Use isolated workers for noisy research, long logs, and independent review.
- Use deterministic scripts or checks for rules that must fire every time.
- Manage context aggressively; summarize or split when the thread stops helping.
- Treat parallel agents as a coordination problem with clear ownership, status,
  and proof.
- Let the agent interview the user for large, unclear features before coding.

## YC Agent Startups

Sources:

- https://www.ycombinator.com/companies/conductor
- https://www.ycombinator.com/companies/compyle
- https://www.ycombinator.com/companies/syntropy
- https://www.ycombinator.com/companies/stagewise
- https://www.ycombinator.com/companies/superagent

Adapted patterns:

- Parallel agents need isolated workspaces, visible status, and human review.
- Open-ended tasks need specification, questions, checkpoints, and ownership
  more than raw autonomy.
- Browser/runtime context matters for frontend agents.
- Long-horizon work should decompose into dependencies and produce a tested PR.
- Agent security needs sandboxing, permission boundaries, and audit trails.

## Simon Willison

Source:

- https://simonwillison.net/2025/Oct/5/parallel-coding-agents/

Adapted patterns:

- Parallel agents work best for research, archaeology, small maintenance, and
  clearly specified implementation.
- Save useful findings so later sessions start with better local knowledge.
