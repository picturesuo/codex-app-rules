---
summary: Repo-local and user-local tools Codex may need.
read_when:
  - You need a command that is not obvious from package scripts.
  - You are using a tool with auth, permissions, rate limits, or sharp edges.
  - A previous session wasted time choosing the wrong tool.
---

# Tools

Catalog only tools that prevent repeated mistakes. Keep entries short,
verifiable, and safe to publish.

## Rules

- Prefer repo scripts and documented package-manager commands.
- Verify non-obvious tools with `command -v`, `--help`, or repo docs.
- Name auth sources by kind only: browser profile, 1Password item name, or env
  var name. Never include secret values.
- Record limits, permissions, and fallbacks only when they affect work.

## Ladder

1. Repo scripts and package-manager commands.
2. Purpose-built CLIs: `gh`, deploy CLIs, test runners, log tools.
3. MCP servers/connectors for live external context or actions.
4. Browser or computer-use tools for UI inspection or operation.
5. Skills for repeated tool workflows.
6. Automations for stable scheduled work.

## GitHub

- Tool: `gh`
- Use for: issues, PRs, CI, releases, comments, repo identity.
- First checks: `gh auth status`; `gh repo view --json nameWithOwner`
- Note: use `--body-file` for public text containing shell, env vars, quotes, or
  user-provided content.

## Visual Or Runtime Proof

- For UI or behavior bugs, prefer screenshots, browser inspection, logs, and
  local runtime checks.
- Record stable dev server command, port, browser profile, and login-safe test
  account here.
- Use the in-app browser for unauthenticated local web routes.
- Use computer use only when lower-context tools cannot inspect the needed GUI
  or signed-in state.

## Entry

```text
Name:
Use for:
Install check:
Commands:
Auth/permissions:
Limits:
Fallback:
```
