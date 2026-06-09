---
summary: Startup-focused Codex workflow.
read_when:
  - You are building a startup, product, growth loop, or customer-facing system.
  - The task mixes product judgment, architecture, and shipping pressure.
---

# Startup Agent Workflow

## Goal

Move fast enough to learn from customers while preserving the few decisions that
would be expensive to rediscover or unwind.

Use three kinds of artifacts:

- Execution packet: the temporary source of truth for one substantial task.
- ADR: a durable decision record for architecture, product invariants, or
  service boundaries future sessions must preserve.
- Proof: the smallest real feedback loop that can disprove the work.

## How The Pieces Fit

- Conversation is for alignment: goal, options, tradeoffs, and questions.
- Execution packets are for work in motion: plan, scope, proof, risks, and
  handoff.
- ADRs are for decisions that should outlive the feature branch.
- Queue is for paused or resumed work.
- Knowledge is for stable facts and preferences that are not decisions.
- Tools docs are for exact commands, ports, auth source names, and limits.

## Startup Loop

1. Frame the bet.
   - Customer:
   - Pain:
   - Business outcome:
   - Product promise:
   - Fastest proof:

2. Align before coding.
   Ask Codex to read relevant code, docs, ADRs, metrics, and customer context.
   Have it return 2-3 approaches, one recommendation, and up to 5 questions
   that would change architecture, UX, data exposure, or go-to-market risk.

3. Decide what to preserve.
   Create or update an ADR only when the decision should constrain future work.
   Do not write ADRs for routine implementation choices.

4. Create the execution packet.
   Use it for long, multi-step, or /goal work. Keep the packet compact enough
   to reread before every major edit.

5. Build the smallest complete slice.
   Prefer one customer-observable path over broad infrastructure. Avoid
   speculative settings, abstractions, admin panels, dashboards, or future
   integrations unless they are required for the current proof.

6. Dogfood the changed path.
   Use the closest real loop: unit test, integration test, local runtime, CLI,
   browser, screenshot, computer use, or end-to-end flow. For product UI, proof
   should include what Codex actually saw or operated.

7. Review like an owner.
   Inspect the diff, run the proof ladder, and use a fresh review pass for
   security, billing, auth, data loss, payments, customer messaging, or
   migration risk.

8. Ship or stop.
   Commit and push verified repo-visible work. If the work does not improve the
   target, shrink it, revert only your own failed path, or record the blocker.

9. Feed the loop.
   If a mistake repeats, add the smallest durable guardrail: docs, ADR, tool
   command, test, script, skill, or automation.

## When To Use ADRs

Use an ADR when a future agent should not casually change the answer.

Good ADR candidates:

- billing ownership and enforcement;
- auth, tenant, permission, or data boundary;
- where customer-visible state is sourced from;
- event, job, or workflow ownership;
- pricing, plan, trial, or entitlement invariants;
- migration strategy for durable data;
- API/provider choice when switching is expensive;
- product invariant that shapes code, such as "users never talk to agents."

Skip ADRs for:

- local refactors;
- naming;
- one-off UI copy;
- routine library usage;
- implementation details already obvious from nearby code.

ADR prompt:

```text
Turn the decision we just aligned on into a compact ADR.
Include: decision, context, details, invariants, consequences, references, and
the proof that should fail if this decision is broken.
Keep it short enough that a future agent will actually read it.
```

## Default Prompts

Research and alignment:

```text
We need to build [feature].
Read the relevant code, docs, ADRs, and tests. Do not edit yet.
Return 2-3 viable approaches, your recommended approach, the simplest complete
slice, and up to 5 questions whose answers would materially change architecture,
UX, data exposure, business risk, or proof.
```

Execution:

```text
Create an execution packet for the chosen approach and execute it to completion.
Keep the packet updated when the plan materially changes. Dogfood the changed
path through the closest real runtime or UI loop, run the proof ladder, inspect
the diff, and use the adversarial done gate before shipping.
```

Fresh review:

```text
Review this work like a startup owner.
Look for missed customer promise, security/data exposure, billing/auth gaps,
behavior regressions, missing proof, overbuilt scope, and anything that slows
learning without reducing real risk.
Return pass, gap, or blocker with file/line or command evidence.
```

## Parallel Work

Keep product and architecture alignment in the main thread. Use subagents or
separate threads for bounded work that can return summarized evidence:

- code archaeology;
- log or test output analysis;
- competitor or API research;
- fresh review;
- independent implementation only when file ownership is clear.

Use an isolated worktree for parallel write-heavy work. Do not let two live
threads edit the same files without a sequencer.

## Weekly Founder Rhythm

- Monday: pick one customer-facing bet and one risk-reduction task.
- Daily: run one execution packet or one tight shipping loop.
- Before ship: dogfood and adversarial review.
- After ship: capture only repeated friction or durable decisions.
- Friday: prune docs and queue; package only workflows that repeated twice.
