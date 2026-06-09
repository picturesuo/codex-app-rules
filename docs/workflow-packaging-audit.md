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

Create or extend an asset only when the workflow:

- repeated or is clearly about to repeat;
- has stable inputs, output, owner, and stopping point;
- improves speed, quality, consistency, or reliability;
- is easier to review than the repeated prompt;
- is not already covered.

Do not package one-off, ambiguous, sensitive, or poorly evidenced work.

## Evidence

Use source systems, not vibes:

1. repo docs, recent sessions, task summaries, and shared context;
2. Codex Memories and rollout summaries;
3. Chronicle for discovery only;
4. existing skills, subagents, automations, docs, and scripts.

Confirm important details before writing durable instructions.

## Smallest Form

| Form | Use For |
| --- | --- |
| ADR | Architecture decision, invariant, data boundary, service ownership. |
| Execution packet | One long task that needs stable plan, proof, and handoff. |
| Knowledge note | Stable fact, preference, caveat, or retrospective. |
| Tool entry | Exact command, auth source name, port, limit, or fallback. |
| Script/check | Deterministic command-shaped work. |
| Skill | Repeatable method across repos with proof and stopping condition. |
| Subagent/thread | Noisy exploration, long logs, tests, or fresh review. |
| Automation | Stable scheduled work with reviewable output. |
| Skip | Evidence is thin or the prompt is already enough. |

Prefer extension over duplication. Prefer repo docs or scripts over skills when
the workflow belongs to one project. Prefer automation only after the manual
loop is reliable.

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
privacy limits. Dry-run manually when possible. If the new asset does not reduce
steps, mistakes, or context load, shrink it or skip it.

## Finish

```text
Created or extended:
Skipped:
Needs more evidence:
Verification:
```
