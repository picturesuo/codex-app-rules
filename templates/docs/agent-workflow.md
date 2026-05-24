# Agent Workflow

## Codex App Loop

1. Read AGENTS.md, then this file.
2. Check docs/queue.md for the next task and docs/knowledge.md for durable facts.
3. Define success criteria before editing.
4. Make the smallest coherent change.
5. Run the proof that matches the risk.
6. Update status, changed files, verification, and next action.

## Workflow Packaging

- Use docs/workflow-packaging-audit.md before creating a new skill, subagent,
  automation, or recurring workflow asset.
- Reuse or extend existing skills, docs, scripts, and automations before adding
  another artifact.
- Create only high-confidence missing items with stable inputs, a repeatable
  procedure, and a clear stopping condition.

## Context Reset

- Treat about 80% context used as the reset point.
- Before compacting or starting a fresh Codex app thread, update current status.
- Keep current task state outside AGENTS.md.
- Keep durable reusable knowledge in docs/knowledge.md.

## Ship Path

- Follow the repo-local AGENTS.md.
- Publish mode is auto unless the user explicitly asks for local-only work.
- Commit and push only verified repo-visible work.
- Prefer focused commits; use one commit per finished file when practical.
- Keep private, scratch, partial, failing, and unverified work out of the publish path.
