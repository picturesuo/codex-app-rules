# Agent Workflow

## Loop

1. Read AGENTS.md, then this file.
2. Check docs/queue.md for current work.
3. Check docs/knowledge.md for durable facts.
4. Define success criteria before editing.
5. Make the smallest coherent change.
6. Run the narrowest useful proof.
7. Record status, changed files, verification, and next action.
8. Commit and push finished repo-visible work unless the user asked for
   local-only work.

## Context

- Current task state belongs in the active thread, shared context, or queue.
- Durable facts belong in docs/knowledge.md.
- Stable behavior belongs in AGENTS.md.
- Around 80% context used, compact or hand off after recording status.

## Parallel Work

- Split only when tasks have clear file ownership.
- Use one Codex thread per file, feature slice, or proof.
- Do not let two sessions edit the same file unless one session sequences the work.
- Finished sessions report changed files, verification, residual risk, and ship status.

## Publish Path

- Follow the `AGENTS.md` publish path.
- Confirm branch and origin before publishing.
- Include changed files, verification, residual risk, and ship status in the
  handoff.
