# AGENTS

## General Goal
This repository is used to keep TIC-80 moving forward through practical, testable, and well-tracked contributions (code, docs, triage, and issue follow-up).

## Contributor Stance
- We are external contributors, not project owners.
- Prioritize small, testable, low-risk contributions over broad refactors.
- Avoid architecture-scale work unless maintainers explicitly ask for it.
- Communicate with humility: be explicit about assumptions and limits, avoid overclaiming expertise, and frame proposals for maintainer review.

## Available Tools
- Local shell (read/edit files, build, test, git).
- Local git (branches, commits, diffs, history).
- GitHub MCP (issues, PRs, labels, comments, search).
- Web/curl when external verification is needed.

## Priority Source of Truth (Project 1.2)
- Priority must follow the GitHub project board: `https://github.com/users/nesbox/projects/2`.
- Treat board columns `Todo` and `In progress` as the main queue for contribution selection.
- Use these GitHub MCP queries as the default operational proxy:
  - `project:"nesbox/2" is:open assignee:*` -> proxy for `In progress`
  - `project:"nesbox/2" is:open no:assignee` -> proxy for `Todo`
- Be explicit that this is an inference/proxy, because MCP issue search does not return board column data directly.
- Prefer tasks from this queue even if other open issues look simpler, unless the user asks for an exception.

## Persistent Project Memory
The [`.agents-memory/`](./.agents-memory/) directory is the persistent working memory across conversations.

Mandatory reference file:
- [`.agents-memory/structure.md`](./.agents-memory/structure.md)

It defines the current layout, each file/directory purpose, and maintenance rules.

### Memory Loading Policy (Hot/Core/Cold)
Default load at the start of each conversation:
1. `.agents-memory/structure.md`
2. `.agents-memory/core/loader.md`
3. `.agents-memory/backlog.md`
4. all files in `.agents-memory/tasks/active/` (except optional `README.md`)

Do not auto-load:
- `.agents-memory/tasks/done/`
- `.agents-memory/references/`

Load cold files only when linked from hot/core/index files.

### Memory Language and Style
- All `.md` files under `.agents-memory/` must be in English.
- Keep memory notes concise and actionable.

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
4. `.agents-memory/` is a living workspace and may be amended, corrected, expanded, and reorganized over time.
5. Never store secrets, tokens, credentials, or sensitive data in `.agents-memory/`.

### Tracking Scope Guardrails
- Do not create task/backlog records for routine administrative actions that do not advance the project directly.
- Examples of actions to skip: simple status checks, folder/file listing, reading existing memory to decide next steps, and informal checkpoint replies.
- Create tracking records only when there is concrete project progress (code/doc changes, actionable triage, or issue/PR follow-up).

## Tracking Workflow
1. Review backlog and active tasks.
2. Create/update the active task file (scope, plan, status, links).
3. Execute work.
4. At the end:
- move task to `done/` or `blocked/`
- update backlog
- verify `structure.md` is accurate.

## Branch and Commit Workflow
The `codex` branch is the private working/memory branch. Never use it as the base branch for upstream PR work.

For implementation work intended for `nesbox/TIC-80`:
1. Use `codex` for investigation and memory-aware planning.
2. When the fix is ready, switch to `main` and create a focused branch from `main`.
3. Port only the upstream-worthy code/docs changes onto that clean branch.
4. Commit on the clean branch, not on `codex`.
5. Push the clean branch to the user's fork when asked to push.
6. Do not open the upstream PR unless the user explicitly asks.
7. Return to `codex` after the commit/push and update `.agents-memory/` there with branch, commit, verification, and PR-status notes.

Keep `.agents-memory/` and other private process notes out of upstream PR branches.

### Wave Closure Rule
A wave is considered closed when:
1. all wave tasks are `done` or `blocked`
2. related PR(s) are open/ready

Do not wait for upstream merge to close a wave.

## PR Description Format
When asked to write a PR description, keep it brief and use exactly these sections:
- `Why`
- `What`
- `Impact` (only if there is a meaningful impact to call out)

Formatting preference:
- Leave one blank line after each section heading (`## Why`, `## What`, `## Impact`).
- In `Why`, include the original issue URL on its own line (e.g. `Original issue: https://github.com/nesbox/TIC-80/issues/2439`).

## PR Title Convention
When suggesting a PR title, use bracketed context tags and do not include the issue number.

Preferred pattern:
- `[Fix] [Android] short descriptive title`

## Post-Implementation Handoff
After finishing an implementation, proactively offer in the conversation:
- a suggested branch name
- a suggested PR title
- a suggested PR description (using the required `Why`/`What`/`Impact` format)

When the implementation includes a meaningful behavioral tradeoff, include a clear reviewer question in the PR description so maintainers can explicitly decide.

Do not include CI/check commands, verification summaries, or memory-tracking changes in the PR description draft.
