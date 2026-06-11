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
- Keep `.agents-memory/` and private process files out of clean upstream PR branches.
