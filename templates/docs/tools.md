---
summary: Repo-local and user-local tools Codex may need.
read_when:
  - You need a command that is not obvious from package scripts.
  - You are using a tool with auth, permissions, rate limits, or sharp edges.
  - A previous session wasted time choosing the wrong tool.
---

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

## Tool Ladder

Prefer the lowest-context tool that can complete the job:

1. Repo scripts and package-manager commands.
2. Purpose-built CLIs such as `gh`, deploy CLIs, test runners, and log tools.
3. MCP servers or connectors when live external context or actions are needed.
4. Browser or computer-use tools when the task must inspect or operate UI.
5. Skills when the tool workflow repeats and needs instructions.
6. Automations when the workflow is stable, scheduled, and reviewable.

Do not wire in every possible tool. Add one when it removes a real manual loop,
reduces repeated mistakes, or gives Codex feedback it cannot get from files.

## Add Entries When

- a command is reused across tasks;
- the correct tool is not the obvious default;
- auth, rate limits, profiles, or environment setup matter;
- there is a safer fallback than guessing.

## GitHub

- Tool: `gh`
- Use for: issues, PRs, CI runs, releases, comments, and repo identity.
- First checks: `gh auth status`; `gh repo view --json nameWithOwner`
- Notes: use `--body-file` for public issue, PR, or release bodies when text
  contains shell, env vars, quotes, or user-provided content.

## Visual And Runtime Context

- Prefer screenshots, browser inspection, logs, and local runtime checks for UI
  or behavior bugs.
- Record the dev server command, port, browser profile, and any login-safe test
  account here when they are stable.
- For frontend work, proof should include what Codex actually saw, not only that
  the code compiled.

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
