---
summary: Startup-focused Codex workflow.
read_when:
  - You are building a startup, product, growth loop, or customer-facing system.
  - The task mixes product judgment, architecture, and shipping pressure.
---

# Startup Agent Workflow

## Principle

Ship fast loops, preserve durable decisions, and measure learning.

Peter-style: talk directly, keep blast radius small, dogfood the UI.
Karpathy-style: write the agent program, constrain the editable surface, run a
fixed-budget loop, keep wins, discard losses.

For a startup, combine them:

- conversation aligns taste and product judgment;
- execution packets drive one substantial task;
- ADRs preserve decisions future agents must not casually undo;
- proof loops decide whether work survives.

## Startup Loop

1. Frame the bet:

```text
Customer:
Pain:
Business outcome:
Product promise:
Fastest proof:
```

2. Align before coding.
   Ask Codex to read the relevant code, docs, ADRs, metrics, and customer
   context. It should return 2-3 approaches, one recommendation, and up to 5
   questions that would change architecture, UX, data exposure, business risk,
   or proof.

3. Preserve only real decisions.
   Create an ADR when the answer should constrain future work. Skip ADRs for
   routine implementation details.

4. Program the run.
   For long work, create an execution packet. For repeatable measurable loops,
   make it Karpathy-simple: editable surface, read-only surface, fixed budget,
   metric, log, keep/discard rule.

5. Build the smallest complete slice.
   Prefer one customer-observable path over broad infrastructure. Avoid
   speculative settings, abstractions, dashboards, and future integrations.

6. Dogfood.
   Use the closest real feedback loop: test, build, runtime smoke, browser,
   screenshot, computer use, or end-to-end path.

7. Review like an owner.
   Look for missed customer promise, security/data exposure, billing/auth gaps,
   regressions, missing proof, and overbuilt scope.

8. Ship or stop.
   Commit and push verified work. If the work does not improve the target,
   shrink it, discard your own failed path, or record the blocker.

9. Feed the loop.
   When a mistake repeats, add the smallest durable guardrail: test, command,
   doc, ADR, script, skill, or automation.

## ADRs

An ADR is a small decision receipt. It exists so future agents preserve the
reasoning, not just the code shape.

Write one for:

- billing ownership and enforcement;
- auth, tenant, permission, or data boundaries;
- customer-visible source of truth;
- event, job, or workflow ownership;
- pricing, plan, trial, or entitlement invariants;
- durable data migration strategy;
- expensive provider/API choices;
- product invariants such as "users never talk directly to agents."

Skip one for naming, routine refactors, one-off copy, obvious local code shape,
or anything already enforced by tests.

Prompt:

```text
Turn the decision we just aligned on into a compact ADR.
Include decision, context, details, invariants, consequences, references, and
the proof that should fail if this decision is broken.
Keep it short enough that a future agent will actually read it.
```

## Copy-Paste Prompts

Alignment:

```text
We need to build [feature].
Read the relevant code, docs, ADRs, tests, and customer context. Do not edit yet.
Return 2-3 viable approaches, your recommendation, the smallest complete slice,
and up to 5 questions that would materially change architecture, UX, data
exposure, business risk, or proof.
```

Execution:

```text
Create an execution packet for the chosen approach and execute it to completion.
Keep the packet updated only when the plan materially changes. Dogfood the
changed path, run the proof ladder, inspect the diff, and use the adversarial
done gate before shipping.
```

Measurable loop:

```text
Set up a Karpathy-style loop for [target].
Define editable files, read-only files, fixed budget, metric, log format, and
keep/discard rule. Run [N] iterations, keep only measured wins, and summarize
the result table.
```

Fresh review:

```text
Review this work like a startup owner.
Return pass, gap, or blocker. Focus on customer promise, data/security, billing
or auth, regressions, missing proof, and overbuilt scope.
```

## Parallel Work

Keep product and architecture alignment in the main thread. Split only bounded
work that can return evidence:

- code archaeology;
- log or test analysis;
- API or competitor research;
- fresh review;
- implementation with clear file ownership.

Use an isolated worktree for parallel write-heavy work.

## Weekly Rhythm

- Pick one customer-facing bet and one risk-reduction task.
- Run one execution packet or tight shipping loop each day.
- Dogfood and review before ship.
- Capture only repeated friction or durable decisions.
- Prune queue and docs weekly.
