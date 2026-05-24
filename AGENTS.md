# AGENTS.md

## Purpose

This repo packages reusable Codex app rules for other repos.

## Read First

- `README.md`: install and contract.
- `docs/codex-app-workflow.md`: why these files exist.
- `docs/agent-workflow.md`: the working loop.
- `docs/workflow-packaging-audit.md`: when to package repeated work.
- `docs/source-inspirations.md`: source patterns.

## Hard Rules

- Keep templates safe to publish.
- No secrets in docs, templates, config, commits, or PR bodies.
- Keep common project rules in `templates/`; keep explanation in `docs/`.
- Keep each Markdown file focused on one job; prefer links and short maps over
  duplicated instruction blocks.
- Do not overwrite a target repo's existing instructions.
- When editing a target repo, read that repo's `AGENTS.md` first.

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

## Publish Path

- Publish mode is auto unless the user asks for local-only work.
- Start with `git status --short --branch`.
- Preserve user and other-agent changes; do not revert unrelated work.
- Commit and push each finished repo-visible change after verification.
- Prefer focused commits; group files only when they are inseparable.
- Keep private, scratch, partial, failing, and unverified work out of commits.

## Verification

- Template install: `tmp=$(mktemp -d); bin/install-codex-rules "$tmp"; find "$tmp" -maxdepth 3 -type f | sort`
- Markdown and whitespace: `git diff --check`

## Git

- Work on `main` unless the user asks otherwise.
- Use focused conventional commits when practical.
- Destructive git operations require explicit user instruction.
