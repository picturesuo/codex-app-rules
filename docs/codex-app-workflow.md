---
summary: Why the common Codex app files exist.
read_when:
  - You are installing or changing the shared rules.
  - You are deciding what belongs in the common template set.
---

# Codex App Workflow

## Goal

Make a repo easy for Codex to enter, change, verify, and ship from.

The pack should read like a small agent program. Each common file earns its
place by preserving context Codex otherwise forgets or asks for twice.

## File Roles

| File | Role | Update When |
| --- | --- | --- |
| `AGENTS.md` | Always-on behavior and publish policy. | A rule should apply across sessions. |
| `docs/agent-workflow.md` | Main read/edit/verify/ship loop. | The loop changes. |
| `docs/execution-packet.md` | Active long-run task state. | Work needs durable plan/proof/handoff. |
| `docs/startup-agent-workflow.md` | Product/startup loop. | Startup/product judgment matters. |
| `docs/project-routing.md` | Repo, GitHub, release, related-project routing. | Routing was ambiguous twice. |
| `docs/tools.md` | Commands, auth names, limits, fallbacks. | A tool choice or gotcha repeats. |
| `docs/workflow-packaging-audit.md` | Durable-asset decision test. | Repeated work might become a guardrail. |
| `docs/adr/0000-template.md` | Architecture/product decision record. | A decision must constrain future work. |
| `docs/queue.md` | Baton and small backlog. | Work pauses or moves between threads. |
| `docs/knowledge.md` | Stable facts and preferences. | A future session should not rediscover it. |
| `.codex/config.toml` | Repo-scoped Codex defaults. | The repo needs stable model/config choices. |

Project-specific commands, ports, architecture notes, tool paths, accounts, and
release rules belong in the target repo after install.

## Read And Write Paths

- Read: `AGENTS.md` -> workflow -> routing/tools as needed -> queue/knowledge
  as needed -> ADRs when decisions matter -> source code.
- Write: code/tests first; docs only when the work creates durable context.
- If a detail is true for one repo, install the templates there and write it
  there.

## Design Standard

Every common rule must prevent a likely mistake across many repos. One-project
rules belong in that project's docs.
