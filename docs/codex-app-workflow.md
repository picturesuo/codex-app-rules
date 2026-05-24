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
- make GitHub, publish, related-project, and local-tool routing explicit without
  storing secrets;
- keep the next task visible;
- define when repeated work deserves packaging;
- set repo-scoped Codex defaults.

## Template Set

- `AGENTS.md`
- `docs/agent-workflow.md`
- `docs/project-routing.md`
- `docs/tools.md`
- `docs/workflow-packaging-audit.md`
- `docs/queue.md`
- `docs/knowledge.md`
- `.codex/config.toml`

These files are common across projects. Project-specific commands, ports,
architecture notes, tool paths, GitHub accounts, and release rules belong in the
target repo after install.

## Operating Loop

1. Open Codex on the target checkout.
2. Read `AGENTS.md`.
3. Read `docs/agent-workflow.md`.
4. Check `docs/project-routing.md` before cross-repo, GitHub, release, or
   publish work.
5. Check `docs/tools.md` before using repo-specific or user-local tools.
6. Check `docs/queue.md` and `docs/knowledge.md`.
7. Define success criteria.
8. Make the smallest coherent change.
9. Verify.
10. Commit and push finished repo-visible work unless the user asks for
   local-only work.

## Parallel Work

- Use one Codex thread per coherent unit of work.
- Split only when ownership is clear.
- Use subagents for bounded research, tests, triage, or archaeology.
- Report changed files, verification, residual risk, and ship status before
  handoff.

## Design Standard

Every common rule must earn its place by preventing a likely mistake across many
repos. If a rule only fits one project, put it in that project's docs.
