# Core Loader

## Always-Load Set
1. `../structure.md`
2. this file
3. `../backlog.md`
4. all files in `../tasks/active/` (except optional `README.md`)

## Cold Context Access
Use indexes before opening cold files:
1. `../indexes/wave-index.md`
2. `../indexes/cold-manifest.md`

## Stable Rules
- Keep all `.agents-memory/*.md` in English.
- Keep memory notes concise and actionable.
- A wave closes when its tasks are `done|blocked` and related PR(s) are open/ready, unless an explicit user override says otherwise.
- PR status refresh on 2026-06-11: RDeckard PRs `#2894` through `#2903` tracked in memory are merged; `#2916` is the only tracked upstream PR still open.
- Follow-up issue `#2940` is linked to merged PR `#2901` / issue `#2330` and should be treated as a follow-up to our tab-aware code editor mouse mapping work if revisited.
- Branch workflow: `codex` is the private memory branch. For upstream work, investigate from `codex`, then create a clean branch from `main`, port only PR-worthy changes, commit there, push to the user's fork when requested, do not open upstream PR unless explicitly asked, then return to `codex` and update memory.
- Prefer a separate git worktree for clean upstream PR branches so `.agents-memory/` changes on `codex` stay isolated from PR-worthy code changes. Before creating one, run `git worktree list` and reuse an existing worktree if the branch is already checked out.
- Use deterministic PR worktree names based on the branch name, so returning to an existing branch makes the existing worktree easy to find.
- After a PR branch has been pushed and memory has been updated back on `codex`, keep recent PR worktrees instead of deleting them immediately. As hygiene, retain the five most recent PR worktrees and remove only older inactive ones after confirming they are not the main repo worktree and do not contain unpushed or useful active work.
- Before pushing updates to an already-open, non-draft upstream PR, even when pushing only to the user's fork branch, stop after local changes/verification and ask the user to manually review the local diff before push.
- Do not spend time trying to run full local builds by default: upstream GitHub CI validates builds on draft PRs before review. Prefer lightweight local checks when available; rely on CI for full build coverage unless the user explicitly asks for local builds or a local build is necessary to debug a failure.
- Keep `.agents-memory/` and private process files out of clean upstream PR branches.
- Completed implementation task files should end with a reusable `# PR Description` section containing concise maintainer-facing `## Why`, `## What`, and optional `## Impact` text for the user to paste into the upstream PR.
