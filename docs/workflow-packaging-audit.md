---
summary: Decide whether repeated work deserves a Codex asset.
read_when:
  - The user asks what should become a skill, subagent, or automation.
  - You are converting repeated work into reusable process.
---

# Workflow Packaging Audit

## Goal

Package only the durable part of repeated work. "Skip" is a valid outcome.

## Test

Create or extend an asset only when the workflow has:

- repetition or high-confidence recurrence;
- stable input, output, owner, and stop point;
- speed, quality, consistency, or reliability gain;
- easier review than the repeated prompt;
- no existing asset that already covers it.

Do not package one-off, ambiguous, sensitive, or poorly evidenced work.

## Evidence

Use source systems:

1. repo docs, recent sessions, task summaries, and shared context;
2. Codex Memories and rollout summaries;
3. Chronicle for discovery only;
4. existing skills, subagents, automations, docs, and scripts.

Confirm important details before writing durable instructions.

## Smallest Form

| Form | Use For |
| --- | --- |
| ADR | Architecture decision, invariant, data boundary, service ownership. |
| Execution packet | One long task needing plan, proof, and handoff. |
| Knowledge note | Stable fact, preference, caveat, retrospective. |
| Tool entry | Exact command, auth source name, port, limit, or fallback. |
| Script/check | Deterministic command-shaped work. |
| Skill | Repeatable method across repos with proof and stopping condition. |
| Subagent/thread | Noisy exploration, long logs, tests, or fresh review. |
| Automation | Stable scheduled work with reviewable output. |
| Skip | Evidence is thin or the prompt is already enough. |

Prefer extension over duplication, repo docs/scripts over skills for one-repo
work, and automation only after the manual loop is reliable.

## Shortlist

```text
Workflow:
Evidence:
Frequency/confidence:
Smallest form:
Already covered by:
Decision:
Reason:
```

## Creation Rules

Name inputs, procedure, output, stopping condition, proof, source systems, and
privacy limits. If the asset does not reduce steps, mistakes, or context load,
shrink it or skip it.

## Finish

```text
Created or extended:
Skipped:
Needs more evidence:
Verification:
```
