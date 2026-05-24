# AGENTS.md

## Purpose

This repo packages reusable Codex app rules and templates for other repos.

## Read First

- `README.md`: install and usage.
- `docs/codex-app-workflow.md`: Codex-app-first operating model.
- `docs/agent-workflow.md`: session loop and publish path.
- `docs/workflow-packaging-audit.md`: skill, subagent, automation, extension, or skip audit.
- `docs/source-inspirations.md`: external patterns adapted here.

## Hard Rules

- Keep templates safe to publish.
- No secrets in docs, templates, configs, commits, or PR bodies.
- Keep `AGENTS.md` durable and terse; put workflow explanation in `docs/*.md`.
- Prefer repo-local Markdown and `.codex/config.toml` over terminal-specific automation.
- If editing a target project using these rules, read that project's own `AGENTS.md` first.

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

## Verification

- Markdown/templates: `git diff --check`
- Repo state: `git status --short --branch`

## Git

- Work on `main` unless the user asks for another branch.
- Use focused commits with conventional prefixes when practical.
- Destructive git operations require explicit user instruction.
