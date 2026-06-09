# AGENTS.md

## Purpose

This repo is worked by Codex app sessions.

## Read First

- README.md when present.
- docs/agent-workflow.md
- docs/project-routing.md
- docs/tools.md
- docs/workflow-packaging-audit.md
- docs/adr/ when architecture decisions matter.
- docs/queue.md
- docs/knowledge.md

## Hard Rules

- Follow the user's latest request.
- Keep current task state in the active thread, shared context, or docs/queue.md.
- Keep durable facts in docs/knowledge.md.
- Keep durable architecture decisions and invariants in docs/adr/.
- Keep repo identity, publish routing, and tool catalogs in docs/project-routing.md
  or docs/tools.md.
- Keep each Markdown file focused on one job; prefer links and short maps over
  duplicated instruction blocks.
- Do not store secrets in docs, config, commits, issues, PRs, or logs.

## Think Before Coding

- State assumptions when they affect the path.
- Name ambiguity instead of guessing silently.
- Use the simpler complete approach unless there is a concrete reason not to.
- Push back on unnecessary scope, risky data exposure, or brittle architecture.

## Simplicity First

- Write the minimum code that solves the problem.
- Add no speculative features, abstractions, or configurability.
- If a change feels overbuilt, make it smaller before handoff.

## Surgical Changes

- Touch only files required by the current request.
- Match existing style.
- Do not refactor adjacent code unless the change requires it.
- Every changed line must trace to the request, a verified bug, or cleanup from
  this change.

## Goal-Driven Execution

- Convert vague tasks into verifiable success criteria before editing.
- For bugs, prefer a check that reproduces the failure before fixing it.
- Run the narrowest useful proof before committing or pushing.
- Before marking nontrivial work done, use the adversarial review gate in
  docs/agent-workflow.md: challenge the completion claim with a fresh subagent
  or thread when available, then fix or record any material gaps.

## Publish Path

- Publish mode is auto unless the user asks for local-only work.
- Start with `git status --short --branch`.
- Preserve user and other-agent changes; do not revert unrelated work.
- Commit and push each finished repo-visible change after verification.
- Prefer focused commits; group files only when they are inseparable.
- Keep private, scratch, partial, failing, and unverified work out of commits.
- Destructive git operations require explicit user instruction.
