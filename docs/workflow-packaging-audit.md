---
summary: Audit repeated work and package only the smallest useful Codex asset.
read_when:
  - The user asks what should become a skill, subagent, or automation.
  - You are turning sessions, Memories, or Chronicle evidence into reusable workflow assets.
---

# Workflow Packaging Audit

## Goal

Find repeated manual work worth packaging for Codex, then create only the
high-confidence missing asset. The default outcome can be "skip" when evidence
is thin, sensitive, too broad, or already covered.

## Evidence Order

Use the strongest available evidence first:

1. Recent Codex sessions, task summaries, shared context files, and repo docs.
2. Codex Memories and rollout summaries for patterns repeated across sessions.
3. Chronicle, when enabled, for discovery only. Confirm important details in
   the source system before acting.
4. Existing skills, custom subagents, automations, project docs, and scripts.

Do not use screenshots, Chronicle notes, Memories, or session summaries as a
source of truth for sensitive facts. Treat them as leads and verify in the
repo, tracker, document, calendar, or CLI that owns the work.

## Candidate Test

Package a workflow only when it passes all of these checks:

- It happened at least twice, or is clearly likely to recur and costly to repeat.
- It has stable inputs, a repeatable procedure, and a clear output or stopping
  condition.
- It improves speed, quality, consistency, or reliability enough to justify the
  extra artifact.
- Existing skills, subagents, automations, docs, or scripts do not already cover
  it well.

Skip work that is one-off, ambiguous, secret-heavy, too personal to encode,
poorly evidenced, or better handled by a normal prompt.

## Smallest Useful Form

- Skill: reusable method, playbook, or tool workflow.
- Custom subagent: bounded specialist investigation or review role.
- Automation: scheduled or recurring check, report, reminder, or monitor.
- Extend existing: small improvement to a current skill, doc, script,
  automation, or agent instruction.
- Skip: not worth packaging yet.

Prefer extension over duplication. Prefer a short doc or script over a skill
when the workflow belongs only to one repo. Prefer an automation only after the
interactive prompt shape has worked at least once and the output is easy to
review.

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

Include "skip" decisions in the shortlist so future sessions can see what was
considered and why it was not packaged.

## Creation Rules

Create only high-confidence missing items. Keep each created asset narrow:

- expected inputs;
- exact procedure or delegation boundary;
- output and stopping condition;
- verification step;
- source systems it may consult;
- privacy limits.

Do not create speculative, overlapping, or broad assets. If the candidate needs
more evidence, write the missing evidence requirement instead.

## Finish Format

```text
Created or extended:
Deliberately skipped:
Needs more evidence:
Verification:
```
