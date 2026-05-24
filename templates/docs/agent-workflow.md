---
summary: The common Codex app working loop.
read_when:
  - You are deciding whether to edit, verify, commit, or push.
  - You are resuming or handing off work.
---

# Agent Workflow

## Task Brief

For nontrivial work, turn the request into a compact brief before editing:

```text
Goal:
Context:
Constraints:
Done when:
```

Use the brief to keep Codex out of guesswork. If the goal, data exposure,
architecture, or publish path is ambiguous, clarify or present options before
coding.

## Mode Choice

- Discuss: use when the request is fuzzy, product-shaped, risky, or strategic.
- Plan: use when the change spans files, touches architecture, or has several
  valid approaches.
- Code: use when success criteria and proof are clear.
- Review: use a fresh pass for important diffs, security-sensitive changes, and
  contributor PRs.
- Automate: use only after the workflow has worked manually and has reviewable
  output.

## Loop

1. Read AGENTS.md, then this file.
2. Check docs/queue.md for current work.
3. Check docs/knowledge.md for durable facts.
4. Check docs/project-routing.md before cross-repo, GitHub, release, or publish
   work.
5. Check docs/tools.md before using repo-specific or user-local tools.
6. Define success criteria before editing.
7. Make the smallest coherent change.
8. Run the narrowest useful proof.
9. Record status, changed files, verification, and next action.
10. Commit and push finished repo-visible work unless the user asked for
   local-only work.

## Context

- Current task state belongs in the active thread, shared context, or queue.
- Durable facts belong in docs/knowledge.md.
- Project, GitHub, release, and related-repo routing belong in
  docs/project-routing.md.
- Tool commands, auth source names, permissions, and known limits belong in
  docs/tools.md.
- Stable behavior belongs in AGENTS.md.
- Around 80% context used, compact or hand off after recording status.

## Start Packet

Before editing, know:

- request and success criteria;
- branch, dirty state, and publish mode;
- relevant project routing and tool constraints;
- narrowest useful proof.

If one of these changes while working, adjust the plan before touching more
files.

## Parallel Work

- Split only when tasks have clear file ownership or read-only scope.
- Use one Codex thread per task, feature slice, or proof.
- Do not let two sessions edit the same file unless one session sequences the work.
- Finished sessions report changed files, verification, residual risk, and ship status.
- Use separate threads or subagents for noisy exploration, logs, broad search,
  long tests, and independent review so the main thread stays focused.

## Review Loop

- Inspect the diff before calling work done.
- Run the narrowest proof that can fail for the change.
- For UI work, capture or inspect the actual screen when possible.
- For bugs, prefer a reproducer or regression test before the fix.
- For high-risk changes, use a fresh review context so the reviewer is not
  anchored to the implementation path.

## Publish Path

- Follow the `AGENTS.md` publish path.
- Confirm branch and origin before publishing.
- Confirm the active GitHub repo/account before commenting, opening PRs, pushing,
  or releasing.
- Include changed files, verification, residual risk, and ship status in the
  handoff.

## Finish Packet

Report:

- changed files;
- verification run and result;
- residual risk or unverified area;
- commit, push, PR, or local-only state.
