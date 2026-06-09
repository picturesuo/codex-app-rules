# Codex App Rules

A compact Markdown operating kit for Codex-ready repos.

It gives every checkout one durable agent surface: behavior rules, workflow,
state, routing, tools, decisions, knowledge, and repo-scoped Codex defaults.

## File Map

| File | Job |
| --- | --- |
| `AGENTS.md` | Hard rules and publish policy. |
| `docs/agent-workflow.md` | Read, edit, verify, ship. |
| `docs/execution-packet.md` | Long-run task state. |
| `docs/startup-agent-workflow.md` | Product/startup shipping loop. |
| `docs/project-routing.md` | Repo, GitHub, release, and related-project routing. |
| `docs/tools.md` | Commands, auth names, limits, and fallbacks. |
| `docs/workflow-packaging-audit.md` | Skill/subagent/automation/doc/script decision test. |
| `docs/adr/0000-template.md` | Durable decision record. |
| `docs/queue.md` | Current baton and small backlog. |
| `docs/knowledge.md` | Durable facts and preferences. |
| `.codex/config.toml` | Repo-scoped Codex defaults. |

## Install

From this repo:

```bash
bin/install-codex-rules /path/to/project
```

From a target repo:

```bash
/Users/bensuo/Desktop/codex-app-rules/bin/install-codex-rules
```

The installer copies only missing files. Merge existing project instructions by
hand.

## Contract

The contract is deliberately plain: think before coding, keep changes surgical,
verify before claiming done, preserve other people's work, and publish verified
repo-visible changes unless the user asks for local-only work.

Project-specific accounts, remotes, release rules, tool paths, ports, and
related repos belong in the installed target repo docs, never in this shared
package.

## Workflow Biases

- Prompt shape: goal, context, constraints, done.
- Alignment: options, recommendation, hard questions, proof.
- Artifacts: execution packets for active long work, ADRs for durable decisions.
- Feedback: tests, builds, runtime checks, browser/computer-use dogfood.
- Context: main thread owns decisions; helpers handle noise and review.
- Packaging: repeated friction becomes the smallest durable guardrail.

See `docs/source-inspirations.md` for sources and adaptations.
