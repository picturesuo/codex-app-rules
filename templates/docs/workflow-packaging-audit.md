# Workflow Packaging Audit

## Goal

Look across recent Codex work and package only repeated manual workflows that
are stable, valuable, and not already covered.

## Evidence Order

1. Recent Codex sessions, task summaries, shared context files, and repo docs.
2. Codex Memories and rollout summaries for repeated patterns.
3. Chronicle, when enabled, for discovery only. Confirm important details in
   the source system before acting.
4. Existing skills, custom subagents, automations, project docs, and scripts.

Do not treat Memories, Chronicle, screenshots, or summaries as source-of-truth
for sensitive facts. Use them as leads and verify in the repo, tracker, doc,
calendar, or CLI that owns the work.

## Candidate Test

Package a workflow only when:

- it happened at least twice, or is clearly likely to recur and costly to repeat;
- it has stable inputs, a repeatable procedure, and a clear output or stopping condition;
- it materially improves speed, quality, consistency, or reliability;
- it is not already adequately covered.

## Smallest Useful Form

- Skill: reusable method, playbook, or tool workflow.
- Custom subagent: bounded specialist investigation or review role.
- Automation: scheduled or recurring check, report, reminder, or monitor.
- Extend existing: small improvement to a current skill, doc, script, automation, or agent instruction.
- Skip: one-off, ambiguous, sensitive, poorly evidenced, or better handled by a normal prompt.

## Shortlist Format

```text
Repeated workflow:
Evidence and dates:
Frequency/confidence:
Recommended form:
Worth creating because:
Already covered by:
Decision:
```

## Creation Rules

Create only high-confidence missing items. Keep each item narrow: expected
inputs, exact procedure or delegation boundary, output, stopping condition,
verification, source systems, and privacy limits.

Prefer extending existing assets over duplicating them. Prefer a repo doc or
script over a skill when the workflow belongs only to this repo. Prefer an
automation only after the interactive prompt shape has worked and the output is
easy to review.

## Finish Format

```text
Created or extended:
Deliberately skipped:
Needs more evidence:
Verification:
```
