---
summary: Decide whether repeated work deserves a Codex asset.
read_when:
  - The user asks what should become a skill, subagent, or automation.
  - You are converting repeated work into reusable process.
---

# Workflow Packaging Audit

## Goal

Find repeated manual work worth packaging, then create only the smallest
high-confidence missing asset. "Skip" is a valid outcome.

## Evidence Order

1. Recent Codex sessions, task summaries, shared context, and repo docs.
2. Codex Memories and rollout summaries.
3. Chronicle, if enabled, for discovery only.
4. Existing skills, subagents, automations, docs, and scripts.

Confirm important details in the source system before acting. Memories,
Chronicle, screenshots, and summaries are leads, not source of truth.

## Candidate Test

Package work only when it:

- happened at least twice, or is clearly likely to recur and costly to repeat;
- has stable inputs, a repeatable procedure, and a clear stopping condition;
- improves speed, quality, consistency, or reliability;
- is not already covered well enough.

Skip work that is one-off, ambiguous, sensitive, poorly evidenced, or better
handled by a normal prompt.

## Smallest Useful Form

- Skill: reusable method or tool workflow.
- Subagent: bounded specialist investigation or review.
- Automation: scheduled check, report, reminder, or monitor.
- Extend existing: improve a current skill, doc, script, automation, or rule.
- Skip: not worth packaging yet.

Prefer extension over duplication. Prefer a repo doc or script over a skill when
the workflow belongs only to one repo. Prefer automation only after the prompt
shape has worked and the output is easy to review.

## Shortlist

```text
Workflow:
Evidence and dates:
Frequency/confidence:
Recommended form:
Already covered by:
Decision:
Reason:
```

## Creation Rules

Create only high-confidence missing items. Name:

- inputs;
- procedure or delegation boundary;
- output;
- stopping condition;
- verification;
- source systems;
- privacy limits.

Do not create speculative, overlapping, or broad assets. If evidence is missing,
say what evidence is needed.

## Finish

```text
Created or extended:
Skipped:
Needs more evidence:
Verification:
```
