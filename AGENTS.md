# AGENTS

## General Goal
This repository is used to keep TIC-80 moving forward through practical, testable, and well-tracked contributions (code, docs, triage, and issue follow-up).

## Available Tools
- Local shell (read/edit files, build, test, git).
- Local git (branches, commits, diffs, history).
- GitHub MCP (issues, PRs, labels, comments, search).
- Web/curl when external verification is needed.

## Persistent Project Memory
The [`.agents-memory/`](./.agents-memory/) directory is the persistent working memory across conversations.

Mandatory reference file:
- [`.agents-memory/structure.md`](./.agents-memory/structure.md)

It defines the current layout, each file/directory purpose, and maintenance rules.

## Code Style and Comment Policy
When editing source files:
1. Follow the existing code style in the touched file (formatting, naming, patterns).
2. Follow the existing comment style and tone in that file.
3. Do not introduce a new style when the file already has a clear one.
4. Keep comments concise and useful; avoid noisy or redundant comments.

## Mandatory Maintenance Rules
1. Always read `.agents-memory/structure.md` at the start of work.
2. Any create/delete/rename/move inside `.agents-memory/` must be reflected in `structure.md` in the same change.
3. Every new task must be tracked in:
- `backlog.md`
- a task file under `tasks/active/`
4. Any non-trivial technical decision must be logged under `decisions/`.
5. Any important conversation/work session must leave a concise trace in `sessions/`.
6. `.agents-memory/` is a living workspace and may be amended, corrected, expanded, and reorganized over time.
7. Never store secrets, tokens, credentials, or sensitive data in `.agents-memory/`.

### Tracking Scope Guardrails
- Do not create task/backlog/session records for routine administrative actions that do not advance the project directly.
- Examples of actions to skip: simple status checks, folder/file listing, reading existing memory to decide next steps, and informal checkpoint replies.
- Create tracking records only when there is concrete project progress (code/doc changes, actionable triage, issue/PR follow-up, or non-trivial technical decisions).

## Tracking Workflow
1. Review backlog and active tasks.
2. Create/update the active task file (scope, plan, status, links).
3. Execute work and log important decisions.
4. At the end:
- move task to `done/` or `blocked/`
- update backlog
- add a session summary in `sessions/`
- verify `structure.md` is accurate.

## PR Description Format
When asked to write a PR description, keep it brief and use exactly these sections:
- `Why`
- `What`
- `Impact` (only if there is a meaningful impact to call out)
