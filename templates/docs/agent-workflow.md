---
summary: The common Codex app working loop.
read_when:
  - You are deciding whether to edit, verify, commit, or push.
  - You are resuming, compacting, reviewing, or handing off work.
---

# Agent Workflow

## Prime Directive

Move from request to verified change with the smallest useful context surface.

Keep three things explicit:

- target: the outcome that matters;
- boundary: what must not drift;
- proof: what would show the work is wrong.

## Brief

For nontrivial work, write or infer:

```text
Goal:
Context:
Constraints:
Proof:
```

If architecture, data exposure, UX, or publish behavior is unclear, align before
coding. Return 2-3 approaches, one recommendation, up to 5 questions that would
change the design, and the proof that should fail if the implementation is
wrong.

## Loop

1. Read `AGENTS.md`, then this file.
2. Check routing, tools, queue, knowledge, and ADRs only when relevant.
3. Define success and the narrowest proof.
4. Make the smallest coherent change.
5. Run the proof ladder as high as the risk requires.
6. Inspect the diff.
7. Use the adversarial done gate for nontrivial, long, or `/goal` work.
8. Record changed files, proof, risk, and next action.
9. Commit and push verified repo-visible work unless the user asked for
   local-only work.

## Artifacts

| Artifact | Use When | Keep It |
| --- | --- | --- |
| Thread | One-off context. | Conversation. |
| Execution packet | Long, multi-step, or `/goal` work. | Plan, scope, proof, risks, handoff. |
| ADR | Durable architecture/product invariant. | Short, numbered, referenced. |
| Queue | Paused or handed-off work. | Baton, not backlog. |
| Knowledge | Stable fact or preference. | Dated when likely to expire. |
| Tools | Command, auth name, port, limit, fallback. | Verifiable and secret-free. |

## Proof Ladder

1. Static checks, types, lint, or formatting.
2. Focused unit or regression tests.
3. Integration, build, migration, or API checks.
4. Runtime smoke through the changed route, CLI, job, or service.
5. Browser, screenshot, computer-use, or end-to-end dogfood when user
   experience is the claim.

Say what ran, what passed, and what was skipped.

## Delegation

- Main thread owns requirements, decisions, and proof.
- Split only when ownership is clear or scope is read-only.
- Use helpers for noisy exploration, logs, broad search, long tests, and fresh
  review.
- Parallel write-heavy work needs an isolated worktree or workspace.
- Workers return files touched, evidence, risk, and ship status.

## Done Gate

Use this for `/goal` runs, long plans, multi-step edits, security-sensitive
changes, or any task where done depends on more than one obvious check.

```text
Adversarial review:
Goal:
Done claim:
Evidence:
Changed files:
Look for: missed requirements, unverified assumptions, regressions, overbuilt changes.
Return: pass, gap, or blocker; include file/line or command evidence when possible.
```

Use a fresh reviewer or separate thread when available and authorized; otherwise
self-review against the same fields. Fix material gaps or record the blocker
before claiming done.

## Finish

Report changed files, proof, residual risk, and local-only, commit, push, or PR
state.
