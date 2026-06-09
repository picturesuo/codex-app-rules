# AGENTS.md

## Purpose

This repo is a Codex app workspace.

## Read First

- README.md when present.
- docs/agent-workflow.md for edit, verify, and ship.
- docs/execution-packet.md for long, multi-step, or /goal work.
- docs/startup-agent-workflow.md for product, startup, or growth work.
- docs/project-routing.md for GitHub, release, deploy, or related repos.
- docs/tools.md for repo-local commands, auth names, and limits.
- docs/workflow-packaging-audit.md before creating durable workflow assets.
- docs/adr/ for architecture or product invariants.
- docs/queue.md and docs/knowledge.md when resuming or preserving context.

## Rules

- Follow the user's latest request.
- State assumptions that affect scope, architecture, data, UX, publish, or proof.
- Use the simplest complete change; add no speculative features or refactors.
- Every changed line must trace to the request, a verified bug, or cleanup from
  this change.
- Store context in the right file: task state in docs/queue.md, facts in
  docs/knowledge.md, decisions in docs/adr/, routing/tools in
  docs/project-routing.md or docs/tools.md, and long-run plans in the thread or
  docs/execution-packet.md.
- Keep each Markdown file to one job; link instead of duplicating.
- Do not store secrets in docs, config, commits, issues, PRs, or logs.

## Execution

- Convert vague tasks into success criteria before editing.
- For bugs, prefer a failing reproducer before the fix.
- Run the narrowest useful proof before committing or pushing.
- Use the adversarial gate in docs/agent-workflow.md before claiming nontrivial,
  long, or /goal work done.

## Publish

- Publish mode is auto unless the user asks for local-only work.
- Start with `git status --short --branch`.
- Preserve user and other-agent changes; do not revert unrelated work.
- Commit and push finished repo-visible changes after verification.
- Keep private, scratch, partial, failing, and unverified work out of commits.
- Destructive git operations require explicit user instruction.
