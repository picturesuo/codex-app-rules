---
summary: Session loop, context reset, parallel work, and publish path.
read_when:
  - You need the Codex app working loop.
  - You are deciding whether to edit, verify, commit, or push.
---

# Agent Workflow

## Loop

1. Read `AGENTS.md`, then this file.
2. Check `docs/queue.md` for the next task.
3. Check `docs/knowledge.md` for durable facts and user preferences.
4. Define success criteria before editing.
5. Make the smallest coherent change.
6. Run the narrowest useful proof.
7. Update status, changed files, verification, and next action.
8. Commit and push finished repo-visible work unless the user asked for
   local-only work.

## Context Reset

- Treat about 80% context used as the reset point.
- Before compacting or starting a fresh thread, update current status.
- Keep current task state outside `AGENTS.md`.
- Keep durable reusable knowledge in `docs/knowledge.md`.

## Parallel Work

- Split only when tasks have clear file ownership.
- Prefer one Codex app thread per file, feature slice, or proof.
- Do not let two sessions edit the same file unless one lead session sequences
  the work.
- Finished sessions should report changed files, verification, residual risk,
  and ship status.

## Publish Path

- Start with `git status --short --branch`.
- Confirm branch and origin before publishing.
- Preserve user or other-agent changes.
- Commit and push only verified repo-visible work.
- Prefer focused commits; use one commit per finished file when practical.
- Keep private, scratch, partial, failing, and unverified work out of the
  publish path.

## Decision Discipline

- Ask only when ambiguity changes scope, data exposure, architecture, or
  publish behavior.
- Prefer the simplest complete change.
- Add regression coverage when a bug was observed and the check is cheap.
- Do not edit adjacent code, docs, formatting, or config unless the request
  requires it.
