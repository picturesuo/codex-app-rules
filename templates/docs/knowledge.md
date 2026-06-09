---
summary: Durable project facts and user preferences.
read_when:
  - You need stable context from prior sessions.
  - You learned something future Codex sessions should not rediscover.
---

# Knowledge

## User Guidance

- Capture durable user preferences and constraints.

## Project Facts

- Capture stable project facts, decisions, and summaries worth reusing.
- Move architecture decisions, invariants, and service-boundary rules to
  docs/adr/ when future sessions must preserve them.

## Retrieval

- Search this file and nearby repo docs with `rg` before broader search.
- Label notes by source when useful: `user`, `repo`, or `external`.
- Prefer dated notes for facts that may expire.
- Remove or revise stale notes when source truth changes.

## Retrospectives

When Codex makes the same mistake twice, add a short note:

```text
Date:
Source:
Observed mistake:
Preferred behavior:
Verification:
```

If the note is really a command, move it to `docs/tools.md`. If it is really a
publish or repo-routing rule, move it to `docs/project-routing.md`.
