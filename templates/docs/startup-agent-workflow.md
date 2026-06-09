---
summary: Startup-focused Codex workflow.
read_when:
  - You are building a startup, product, growth loop, or customer-facing system.
  - The task mixes product judgment, architecture, and shipping pressure.
---

# Startup Agent Workflow

## Principle

Ship fast loops, preserve durable decisions, and measure learning.

Startup use: talk directly, keep blast radius small, dogfood the UI, write the
agent program, constrain the editable surface, measure the loop, keep wins, and
discard losses.

## Startup Loop

1. Frame the bet:

```text
Customer:
Pain:
Business outcome:
Product promise:
Fastest proof:
```

2. Align before coding:
   read code, docs, ADRs, metrics, and customer context; return 2-3 approaches,
   one recommendation, up to 5 questions, and proof.

3. Preserve only real decisions:
   write an ADR only when future work must obey the answer.

4. Program the run:
   for long work, create an execution packet; for repeatable loops, name
   editable surface, read-only surface, budget, metric, log, keep/discard rule.

5. Build the smallest complete slice:
   prefer one customer-observable path over broad infrastructure.

6. Dogfood:
   test, build, runtime smoke, browser, screenshot, computer use, or end-to-end
   path.

7. Review like an owner:
   missed promise, data/security, billing/auth, regressions, missing proof,
   overbuilt scope.

8. Ship or stop:
   commit and push verified work; shrink, discard, or record the blocker if the
   target did not improve.

9. Feed the loop:
   repeated mistakes get the smallest guardrail: test, command, doc, ADR,
   script, skill, or automation.

## ADRs

An ADR is a small decision receipt.

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

ADR prompt:

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
- Run one execution packet or tight shipping loop daily.
- Dogfood and review before ship.
- Capture only repeated friction or durable decisions.
- Prune queue and docs weekly.
