---
summary: Source patterns behind the common Codex app rules.
read_when:
  - You are changing AGENTS.md or templates.
  - You need to know why a rule exists.
---

# Source Inspirations

## Patterns

| Source | Adapted Rules |
| --- | --- |
| Karpathy `autoresearch` and `program.md`: https://github.com/karpathy/autoresearch | Markdown is the agent program. Name editable/read-only surfaces, proof, metric, budget, keep/discard rule. Prefer simpler code when outcomes tie. |
| Karpathy-inspired `CLAUDE.md`: https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md | Keep always-on coding rules small: think before coding, simplicity first, surgical changes, goal-driven execution. Move repeated methods into skills. |
| Steinberger agent scripts and tools catalog: https://github.com/steipete/agent-scripts | Keep rules terse. Put git, release, tool, auth-source, and CI behavior where agents read it. Treat dirty worktrees as state. Prefer exact local commands and `gh` for GitHub. |
| OpenAI Codex docs: https://developers.openai.com/codex/learn/best-practices | Prompts should name goal, context, constraints, and done. Use `AGENTS.md` for durable repo guidance. Keep the main file concise and link task-specific docs. |
| OpenAI Codex app docs: https://developers.openai.com/codex/app/features | Codex app work spans local/worktree/cloud threads, built-in Git, in-app browser, computer use, automations, skills, MCP, and review. Repo docs should route those surfaces explicitly. |
| OpenAI execution plans: https://developers.openai.com/cookbook/articles/codex_exec_plans | Long tasks need a compact packet with target, plan, acceptance, proof, risks, and handoff. |
| OpenAI subagents: https://developers.openai.com/codex/concepts/subagents | Keep requirements and decisions in the main thread. Split noisy research, tests, logs, archaeology, and review into bounded workers. |
| OpenAI Memories and Chronicle: https://developers.openai.com/codex/memories | Use memory-like sources for discovery; confirm important facts in repo docs, code, or source systems before making durable rules. |
| Agent Markdown and ADR references: https://agents.md and https://docs.arc42.org/tips/9-5/ | Treat Markdown as an agent-readable interface. Keep behavior, tools, routing, queue, knowledge, and ADRs in separate files with clear ownership. |
| Anthropic agent engineering: https://www.anthropic.com/engineering/building-effective-agents and https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents | Verify with tests or runtime evidence. Explore, plan, then implement for ambiguous work. Manage context aggressively. |
| YC agent startups and Simon Willison on parallel coding agents: https://www.ycombinator.com/companies/conductor and https://simonwillison.net/2025/Oct/5/parallel-coding-agents/ | Parallel agents need isolated workspaces, clear ownership, visible status, proof, and human review. Browser/runtime context matters for frontend agents. |
