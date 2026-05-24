---
summary: Codex-app-first workflow and seeded project files.
read_when:
  - You are installing these rules in a repo.
  - You are deciding how Codex app sessions should replace terminal-first workflow.
---

# Codex App Workflow

## Goal

Make the Codex desktop app the primary work surface while preserving the useful
parts of terminal launchers:

- repo-local Markdown that programs the agent loop;
- shared task context and durable knowledge;
- clear verification, commit, and push behavior;
- small reusable workflow audits instead of giant prompts.

## Seeded Files

The template set is:

- `AGENTS.md`
- `docs/agent-workflow.md`
- `docs/workflow-packaging-audit.md`
- `docs/queue.md`
- `docs/knowledge.md`
- `.codex/config.toml`

Existing target files should be merged by hand, not overwritten.

## Operating Model

1. Open Codex on the target checkout.
2. Tell Codex the task in normal language.
3. Let Codex read `AGENTS.md`, `docs/agent-workflow.md`, `docs/queue.md`,
   `docs/knowledge.md`, and any shared context file.
4. Define success criteria before editing.
5. Make the smallest coherent change.
6. Run the proof that matches the risk.
7. Commit and push verified repo-visible work unless the user asks for
   local-only work.

## Parallel Work

- Use one Codex thread per coherent unit of work.
- Split only when file ownership or proof boundaries are clear.
- Use subagents for bounded research, tests, triage, or archaeology.
- Finished sessions should report changed files, verification, residual risk,
  and ship status.

## Adapted Patterns

- Karpathy: Markdown is the program; name editable and read-only surfaces;
  measure outputs; keep only changes that improve the result or simplify.
- Karpathy-inspired `CLAUDE.md`: think before coding, simplicity first,
  surgical changes, and goal-driven execution.
- Steinberger: terse rules, explicit routing, exact local commands, visible
  publish policy, and small verified commits.
- OpenAI Codex docs: personal defaults live in `~/.codex/config.toml`; repo
  behavior lives in `.codex/config.toml`, `AGENTS.md`, and repo docs.
