---
summary: Repo identity, GitHub, publish, and related-project routing.
read_when:
  - You are about to read or write GitHub state.
  - You are about to publish, release, deploy, or switch repos.
  - The task mentions another checkout, fork, account, or organization.
---

# Project Routing

Store repo routing that should survive Codex sessions. No tokens, passwords,
API keys, private customer data, or other secrets.

## Identity

- GitHub repo:
- Default branch:
- Primary checkout:
- Related checkouts:
- Runtime/package manager:

## Publish

- Derive repo identity with `gh repo view` or `git remote get-url origin`.
- Run `gh auth status` when the active GitHub account matters.
- Ask before writing if account, fork, organization, branch, or release target
  is ambiguous.
- Record stable release, deploy, changelog, or CI rules here.

## Checks

```bash
git status --short --branch
git remote -v
gh repo view --json nameWithOwner --jq .nameWithOwner
gh auth status
```

## Surfaces

- Local thread: real checkout, local tools, browser/screenshots, user steering.
- Worktree or cloud thread: independent work with clear setup and branch.
- Automation: stable recurring checks, summaries, triage, or reports.

When moving work, record branch, task URL or thread name, proof gathered, and
next decision.

## Related Projects

Stay in this checkout unless the user asks for another repo or this file names a
required related project. For cross-repo work, record repo, branch, ownership,
and proof for each repo.
