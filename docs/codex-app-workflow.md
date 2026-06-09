---
summary: Why the common Codex app files exist.
read_when:
  - You are installing or changing the shared rules.
  - You are deciding what belongs in the common template set.
---

# Codex App Workflow

## Goal

Make any repo easy for Codex to enter, understand, verify, and ship from.

The common files should do only durable work:

- tell Codex how to behave;
- name the working loop;
- preserve stable project knowledge;
- preserve durable architectural decisions and invariants;
- preserve long-run execution shape when a task needs to survive compaction,
  review, or handoff;
- make GitHub, publish, related-project, and local-tool routing explicit without
  storing secrets;
- keep the next task visible;
- define when repeated work deserves packaging;
- set repo-scoped Codex defaults.

## File Roles

| File | Role | Update When |
| --- | --- | --- |
| `AGENTS.md` | Behavior contract and hard rules. | A rule should apply across many sessions. |
| `docs/agent-workflow.md` | Read, edit, verify, and publish loop. | The working loop changes. |
| `docs/execution-packet.md` | Lightweight packet for long, multi-step, or `/goal` work. | A long-run task needs a reusable packet shape. |
| `docs/startup-agent-workflow.md` | Founder workflow for product bets, shipping loops, and durable decisions. | The repo is used to build a startup or product. |
| `docs/project-routing.md` | Repo, GitHub, release, and related-project routing. | Codex has to ask the same routing question twice. |
| `docs/tools.md` | Tool commands, auth source names, limits, and fallbacks. | A local tool has a stable command or gotcha. |
| `docs/workflow-packaging-audit.md` | Decision test for skills, subagents, automations, docs, and scripts. | Repeated work needs packaging discipline. |
| `docs/adr/0000-template.md` | Compact template for architectural decisions and invariants. | A decision must guide future sessions or code paths. |
| `docs/queue.md` | Current task baton and small backlog. | Work is paused, resumed, blocked, or handed off. |
| `docs/knowledge.md` | Durable facts and user preferences. | A fact will help future sessions. |
| `.codex/config.toml` | Repo-scoped Codex defaults. | The repo needs a stable Codex default. |

These files are common across projects. Project-specific commands, ports,
architecture notes, tool paths, GitHub accounts, and release rules belong in the
target repo after install.

## Read And Write Paths

- Read path: `AGENTS.md` -> workflow -> routing/tools -> queue/knowledge ->
  ADRs when architecture matters -> source code.
- Write path: code and tests first, then update queue, knowledge, routing, or
  tools only when the work produced durable context. Add an ADR when the work
  creates or depends on a decision future sessions must preserve. Use an
  execution packet for long work that needs a stable target through compaction
  or handoff.
- Keep the shared package small. If a detail is true for one repo, install the
  templates there and write it there.

## Workflow Shape

The templates encode a few patterns that kept recurring across strong public
agent workflows:

- brief like a GitHub issue: goal, context, constraints, and done condition;
- align before risky work by having the main thread read relevant code and docs,
  present a few options, ask only questions that change the design, and keep the
  chosen reasoning in context;
- explore and plan before large edits, but skip ceremony for obvious changes;
- keep context lean by sending noisy search, logs, and review into separate
  threads or subagents;
- preserve durable architecture choices in short ADRs with invariants,
  consequences, and file references;
- use execution packets for long goal runs so plan, proof, dogfood path, and
  risks stay visible across compaction or handoff;
- add an adversarial done gate for long `/goal` runs so a fresh reviewer
  challenges completion before plan items are marked done;
- prefer measurable loops: run proof, inspect output, keep the change only when
  it improves the target without needless complexity;
- dogfood user-facing work through the closest real runtime or UI loop before
  handoff when feasible;
- choose proof from a ladder: static checks, focused tests, integration/build,
  runtime smoke, then browser/computer-use or end-to-end dogfood;
- use tools deliberately: repo scripts first, CLIs before broad integrations,
  MCP/browser/computer-use only when they close a real feedback loop;
- run the `docs/workflow-packaging-audit.md` routine-design loop before turning
  repeated work into a skill, subagent, automation, doc, or script;
- write retrospectives back into docs, skills, scripts, or automations only
  after repeated friction.

## Operating Loop

1. Open Codex on the target checkout.
2. Read `AGENTS.md`.
3. Read `docs/agent-workflow.md`.
4. Check `docs/project-routing.md` before cross-repo, GitHub, release, or
   publish work.
5. Check `docs/tools.md` before using repo-specific or user-local tools.
6. Check `docs/queue.md` and `docs/knowledge.md`.
7. Check `docs/adr/` when architecture, invariants, or service boundaries
   matter.
8. Check or create an execution packet for long, multi-step, or `/goal` work.
9. Define success criteria.
10. Make the smallest coherent change.
11. Verify.
12. Commit and push finished repo-visible work unless the user asks for
   local-only work.

## Parallel Work

- Use one Codex thread per coherent unit of work.
- Split only when ownership is clear.
- Keep architecture-forming context in the main thread until decisions settle.
- Use subagents for bounded research, tests, triage, archaeology, or fresh
  review.
- Use isolated worktrees or equivalent workspaces for parallel write-heavy work.
- Report changed files, verification, residual risk, and ship status before
  handoff.

## Design Standard

Every common rule must earn its place by preventing a likely mistake across many
repos. If a rule only fits one project, put it in that project's docs.
