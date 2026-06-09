---
summary: The common Codex app working loop.
read_when:
  - You are deciding whether to edit, verify, commit, or push.
  - You are tightening the shared workflow templates.
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

## Alignment Pass

For product-shaped, risky, or architecture-changing work, keep the main Codex
thread responsible for reading the relevant docs, ADRs, and code before
implementation. Use helpers only for noisy search, long logs, or independent
review until the decision is clear.

Report back with the smallest useful set of choices:

- 2-3 viable approaches when the design is not obvious;
- the recommended approach and why it fits the repo;
- up to 5 questions whose answers would materially change architecture, data
  exposure, UX, or publish behavior;
- the proof that should fail if the implementation is wrong.

After alignment, turn any durable architecture decision into a compact ADR in
`docs/adr/`, especially when future sessions must preserve an invariant or use
specific service boundaries.

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

1. Read `AGENTS.md`, then this file.
2. Check `docs/queue.md` for current work.
3. Check `docs/knowledge.md` for durable facts.
4. Check `docs/adr/` when architecture, invariants, or service boundaries
   matter.
5. Check `docs/project-routing.md` before cross-repo, GitHub, release, or
   publish work.
6. Check `docs/tools.md` before using repo-specific or user-local tools.
7. Define success criteria before editing.
8. Make the smallest coherent change.
9. Run the narrowest useful proof.
10. Run the adversarial done gate for nontrivial or `/goal` work.
11. Record status, changed files, verification, and next action.
12. Commit and push finished repo-visible work unless the user asked for
   local-only work.

## Context

- Current task state belongs in the active thread, shared context, or queue.
- Durable facts belong in `docs/knowledge.md`.
- Durable architecture decisions and invariants belong in `docs/adr/`.
- Project, GitHub, release, and related-repo routing belong in
  `docs/project-routing.md`.
- Tool commands, auth source names, permissions, and known limits belong in
  `docs/tools.md`.
- Stable behavior belongs in `AGENTS.md`.
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
- Do not let two sessions edit the same file unless one session sequences the
  work.
- Finished sessions report changed files, verification, residual risk, and ship
  status.
- Use separate threads or subagents for noisy exploration, logs, broad search,
  long tests, and independent review so the main thread stays focused.

## Review Loop

- Inspect the diff before calling work done.
- Run the narrowest proof that can fail for the change.
- For user-facing behavior, dogfood the changed path through the closest real
  runtime, browser, UI, or CLI loop when feasible.
- For UI work, capture or inspect the actual screen when possible.
- For bugs, prefer a reproducer or regression test before the fix.
- For high-risk changes, use a fresh review context so the reviewer is not
  anchored to the implementation path.

## Adversarial Done Gate

Use this gate for `/goal` runs, long-running plans, multi-step edits,
security-sensitive changes, or any task where "done" depends on more than one
obvious check. For tiny, obvious edits, a direct self-review can satisfy the
gate.

Before marking a task or plan item done:

1. Restate the success criteria and evidence gathered.
2. Ask a fresh reviewer, preferably a subagent or separate thread, to attack the
   completion claim using only the task brief, relevant diff or artifacts, and
   verification output.
3. Have the reviewer return `pass`, `gap`, or `blocker`, with the smallest
   evidence needed.
4. If a material gap appears, do not mark the task done. Fix it, reroute to a
   different tool or check when the path is wrong, or record the blocker and
   next decision.
5. When the gate passes, include the review result in the finish packet.

Prompt shape:

```text
Adversarial review:
Goal:
Done claim:
Evidence:
Changed files:
Look for: missed requirements, unverified assumptions, regressions, overbuilt changes.
Return: pass, gap, or blocker; include file/line or command evidence when possible.
```

## Publish Path

- Start with `git status --short --branch`.
- Confirm branch and origin before publishing.
- Confirm the active GitHub repo/account before commenting, opening PRs,
  pushing, or releasing.
- Preserve user and other-agent changes; do not revert unrelated work.
- Commit and push only verified repo-visible work.
- Prefer focused commits; group files only when they are inseparable.
- Keep private, scratch, partial, failing, and unverified work out of commits.
- Destructive git operations require explicit user instruction.

## Decision Discipline

- Ask only when ambiguity changes scope, data exposure, architecture, or publish
  behavior.
- Prefer the simplest complete change.
- Add regression coverage when a bug was observed and the check is cheap.
- Do not edit adjacent code, docs, formatting, or config unless the request
  requires it.

## Finish Packet

Report:

- changed files;
- verification run and result;
- residual risk or unverified area;
- commit, push, PR, or local-only state.
