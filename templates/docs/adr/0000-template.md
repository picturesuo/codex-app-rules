---
summary: Template for durable architectural decisions.
read_when:
  - You are making or following an architectural decision.
  - A feature depends on invariants future sessions must preserve.
---

# ADR 0000: Title

- Status: Proposed
- Date: YYYY-MM-DD

## Decision

State the decision in one sentence.

## Context

Why this decision exists. Include the problem, constraints, and rejected
pressure that could pull future work off course.

## Details

Explain the chosen shape only as much as a future session needs to implement or
preserve it.

## Invariants

- List conditions that must stay true for the decision to hold.

## Consequences

- Name the tradeoff or failure mode this decision accepts.
- Name the problem this decision prevents.

## References

- Link files, services, tests, docs, issues, or PRs future sessions should read.

## Verification

- Name the proof that should fail when the decision is broken.
