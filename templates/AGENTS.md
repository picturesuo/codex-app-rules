# AGENTS.md

## Purpose

This repo is worked by Codex app sessions using repo-local Markdown rules.

## Read First

- README.md when present.
- docs/agent-workflow.md
- docs/workflow-packaging-audit.md
- docs/queue.md
- docs/knowledge.md

## Hard Rules

- Follow the user's latest request.
- Keep current-task state in the shared context or current thread summary.
- Keep durable project facts in docs/knowledge.md.
- Keep the next small task in docs/queue.md.
- Do not store secrets in repo docs, profiles, .codex config, commits, or PR bodies.

## Think Before Coding

- State assumptions before implementation when they affect the path.
- Do not hide confusion. If multiple interpretations exist, name them.
- If a simpler approach exists, say so and use it unless there is a concrete reason not to.
- Push back when the request implies unnecessary scope, risky data exposure, or brittle architecture.

## Simplicity First

- Write the minimum code that solves the problem.
- No features beyond what was asked.
- No abstractions or configurability for single-use code.
- If a change feels overbuilt, make it smaller before handoff.

## Surgical Changes

- Touch only files required by the current request.
- Match existing style.
- Do not refactor adjacent code unless the current change requires it.
- Every changed line must trace to the request, a verified bug, or cleanup caused by this change.

## Goal-Driven Execution

- Convert vague tasks into verifiable success criteria before editing.
- For bugs, prefer a check that reproduces the failure before fixing it.
- Run the narrowest useful proof before committing or pushing.

## Publish Path

- Publish mode is auto unless the user explicitly asks for local-only work.
- Start with `git status --short --branch`.
- Preserve user or other-agent changes; do not revert unrelated work.
- Commit and push each finished repo-visible change after verification.
- Prefer focused commits; use one commit per finished file when practical, and group files only when inseparable.
- Keep private, scratch, partial, failing, and unverified work out of commits.
