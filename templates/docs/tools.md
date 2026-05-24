# Tools

Catalog repo-local and user-local tools that Codex may need. Keep entries short,
verifiable, and safe to publish.

## Rules

- Prefer repo scripts and documented package-manager commands before ad hoc
  shell.
- Verify a tool exists with `command -v`, `--help`, or the repo docs before
  using it.
- Document auth sources by kind only, such as browser profile, 1Password item
  name, or environment variable name. Never include secret values.
- Include known limits, required permissions, and fallback commands when they
  prevent repeated mistakes.

## GitHub

- Tool: `gh`
- Use for: issues, PRs, CI runs, releases, comments, and repo identity.
- First checks: `gh auth status`; `gh repo view --json nameWithOwner`
- Notes: use `--body-file` for public issue, PR, or release bodies when text
  contains shell, env vars, quotes, or user-provided content.

## Tool Entry Template

```text
Name:
Use for:
Location or install check:
Common commands:
Auth or permissions:
Known limits:
Fallback:
```
