---
summary: Repo identity, GitHub, publish, and related-project routing.
read_when:
  - You are about to read or write GitHub state.
  - You are about to publish, release, deploy, or switch repos.
  - The task mentions another checkout, fork, account, or organization.
---

# Project Routing

Use this file for repo-specific routing that should survive across Codex
sessions. Do not store tokens, passwords, API keys, private customer data, or
other secrets here.

## Project Identity

- GitHub repo:
- Default branch:
- Primary local checkout:
- Related local checkouts:
- Package manager/runtime:

## GitHub And Publish

- Derive the current repo from `gh repo view` or `git remote get-url origin`
  before reading, commenting, pushing, or opening PRs.
- Run `gh auth status` when the active GitHub account matters.
- If multiple GitHub accounts, remotes, forks, or orgs could apply, ask before
  publishing or commenting.
- Record release, deploy, changelog, or CI rules here only when they are stable
  for this repo.

## Quick Checks

```bash
git status --short --branch
git remote -v
gh repo view --json nameWithOwner --jq .nameWithOwner
gh auth status
```

Use read-only checks freely. Before write actions, confirm ambiguity around
account, fork, organization, branch, or release target.

## Work Surfaces

- Local app thread: best for changes that need the real checkout, local tools,
  browser inspection, screenshots, or active user steering.
- Cloud or background task: best for independent backlog work with clear setup,
  a clean branch, and no private local state.
- Automation: best for stable recurring checks, summaries, triage, or reports.
- Mobile or quick-capture task: best for parking a small idea that will be
  reviewed later on the main machine.

When moving work between surfaces, record the branch, task URL or thread name,
proof already gathered, and the next decision needed.

## Related Projects

- Stay in the current checkout unless the user asks for another repo or this
  file names a related project needed for the task.
- When work spans repos, record the source repo, target repo, branch, and proof
  needed for each one.

## Maintenance

- Update this file when the repo moves, the default branch changes, the publish
  path changes, or a repeated routing question comes up twice.
