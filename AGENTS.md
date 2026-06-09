# AGENTS.md

## Purpose

Publish a compact, reusable Codex app rules pack.

## Read First

- `README.md` for install and contract.
- `docs/codex-app-workflow.md` for file roles.
- `docs/agent-workflow.md` for the working loop.
- `docs/workflow-packaging-audit.md` before packaging repeated work.
- `docs/source-inspirations.md` when changing rules or templates.

## Rules

- Templates must be public-safe: no secrets, private data, account paths,
  tokens, credentials, or PR-body surprises.
- Put common reusable rules in `templates/`; put rationale in `docs/`.
- Keep each Markdown file to one job; link instead of duplicating.
- Do not overwrite a target repo's existing instructions.
- When editing a target repo, read that repo's `AGENTS.md` first.
- State assumptions when they affect scope, architecture, data, UX, or proof.
- Use the simplest complete change; add no speculative features or refactors.
- Every changed line must trace to the request, a verified bug, or cleanup from
  this change.
- For nontrivial work, define success and proof before editing, then use the
  adversarial gate in `docs/agent-workflow.md`.
- Preserve user and other-agent work. No destructive git without explicit
  instruction.
- Publish mode is automatic unless the user asks for local-only work: status,
  verify, commit, push.

## Verification

- Template install: `tmp=$(mktemp -d); bin/install-codex-rules "$tmp"; find "$tmp" -maxdepth 3 -type f | sort`
- Markdown and whitespace: `git diff --check`
