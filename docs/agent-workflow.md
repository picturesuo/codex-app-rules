---
summary: The common Codex app working loop.
read_when:
  - You are deciding whether to edit, verify, commit, or push.
  - You are tightening the shared workflow templates.
---

# Agent Workflow

## Prime Directive

Move from request to verified change with the smallest useful context surface.

Keep three things clear:

- target: what outcome matters;
- boundary: what must not drift;
- proof: what would show the work is wrong.

## Task Brief

For nontrivial work, start with:

```text
Goal:
Context:
Constraints:
Done when:
```

If architecture, data exposure, UX, or publish behavior is unclear, pause for
alignment before coding.

## Alignment

For product-shaped, risky, or architecture-changing work, the main thread reads
the relevant code, docs, ADRs, and tests before implementation. Use helpers only
for noisy search, long logs, or independent review until the decision is clear.

Return:

- 2-3 viable approaches when the design is not obvious;
- one recommendation and why it fits the repo;
- up to 5 questions that would change the design, risk, or proof;
- the proof that should fail if the implementation is wrong.

Write an ADR only when the decision should constrain future work.

## Artifacts

| Artifact | Use When | Keep It |
| --- | --- | --- |
| Thread | One-off task context. | In the conversation. |
| Execution packet | Long, multi-step, or `/goal` work. | Current, compact, discardable. |
| ADR | Durable architecture/product invariant. | Short, numbered, referenced. |
| Queue | Paused or handed-off work. | Small baton, not backlog. |
| Knowledge | Stable facts and preferences. | Dated when likely to expire. |
| Tools | Exact commands, auth names, ports, limits. | Verifiable and secret-free. |

Execution packets carry plan, scope, proof ladder, dogfood path, risks, and
handoff. ADRs carry decisions that should survive the branch.

## Loop

1. Read `AGENTS.md`, then this file.
2. Check queue, knowledge, tools, routing, and ADRs only when relevant.
3. Define success criteria and the narrowest proof.
4. Make the smallest coherent change.
5. Run the proof ladder as high as the risk requires.
6. Inspect the diff.
7. Use the adversarial done gate for nontrivial, long, or `/goal` work.
8. Record status and next action.
9. Commit and push verified repo-visible work unless the user asked for
   local-only work.

## Proof Ladder

1. Static checks, types, lint, or formatting.
2. Focused unit or regression tests.
3. Integration, build, migration, or API checks.
4. Runtime smoke through the changed route, CLI, job, or service.
5. Browser, screenshot, computer-use, or end-to-end dogfood when user
   experience is the claim.

Record what ran, what passed, and what was skipped.

## Parallel Work

- Keep architecture-forming reads and decisions in the main thread until the
  approach is settled.
- Split only when tasks have clear ownership or read-only scope.
- Use separate threads or subagents for noisy exploration, logs, broad search,
  long tests, and independent review.
- Use worktrees or another isolated workspace for parallel write-heavy work.
- Finished workers report changed files, verification, residual risk, and ship
  status.

## Adversarial Done Gate

Use this for `/goal` runs, long plans, multi-step edits, security-sensitive
changes, or any task where "done" depends on more than one obvious check.

Before calling the work done:

1. Restate success criteria and evidence.
2. Ask a fresh reviewer, subagent, or separate thread to attack the done claim.
3. Have the reviewer return `pass`, `gap`, or `blocker`.
4. Fix material gaps or record the blocker.
5. Include the review result in the finish packet.

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

## Publish

- Start with `git status --short --branch`.
- Preserve user and other-agent changes.
- Commit and push only verified repo-visible work.
- Keep private, scratch, partial, failing, and unverified work out of commits.
- Destructive git operations require explicit user instruction.

## Finish Packet

Report changed files, proof, residual risk, and commit/push/PR or local-only
state.
