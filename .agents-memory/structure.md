# .agents-memory Structure

Last updated: 2026-03-04
Owner: agent

## Role of This File
`structure.md` is the master index of `.agents-memory/`.
It defines what is loaded by default and where cold history lives.

## Load Contract
Default load order:
1. `structure.md`
2. `core/loader.md`
3. `backlog.md`
4. all files in `tasks/active/` (except optional `README.md`)

Do not auto-load:
- `tasks/done/`
- `decisions/`
- `sessions/`
- `references/`

Use `indexes/wave-index.md` and `indexes/cold-manifest.md` to fetch cold context on demand.

## Tree and Roles
```text
.agents-memory/
├── structure.md                  # Master index and load contract
├── backlog.md                    # Prioritized topics/tasks
├── core/
│   ├── README.md                 # Rules for transverse memory
│   └── loader.md                 # Always-loaded core facts and pointers
├── indexes/
│   ├── wave-index.md             # Wave -> issue -> file map
│   └── cold-manifest.md          # Inventory of cold files
├── tasks/
│   ├── active/                   # Current execution context (hot)
│   ├── done/                     # Completed tasks (cold)
│   ├── blocked/                  # Blocked tasks (cold)
│   └── templates/                # Task/decision templates
├── decisions/                    # Non-trivial decisions (cold)
├── sessions/                     # Session logs (cold)
└── references/                   # External/source snapshots (cold)
```

## Naming Conventions
- Tasks: `tasks/<state>/TASK-YYYYMMDD-slug.md`
- Decisions: `decisions/DEC-YYYYMMDD-slug.md`
- Sessions: `sessions/YYYY-MM-DD-note.md`

## Maintenance Contract (Mandatory)
1. Read this file before structural changes.
2. If any file/folder is added/removed/renamed/moved, update this file in the same change.
3. Keep this file concise; use indexes for cold-file details.
4. Keep `.agents-memory/*.md` content in English.
5. Do not leave mismatches between filesystem and this file.

## Tracking Scope
- Track concrete project progress.
- Skip routine administrative checks.
- Record only material advancement (implementation, docs, triage/follow-up, non-trivial decisions).

## End-of-Session Checklist
- [ ] New task tracked in `tasks/active/` and `backlog.md`.
- [ ] Finished/blocked tasks moved to the right folder.
- [ ] Non-trivial decisions logged.
- [ ] Session summary added.
- [ ] `structure.md` and indexes are accurate.

## Recent Additions (2026-03-04)
- Task record moved to done: `tasks/done/TASK-20260304-2614-sdl-stuck-keys-window-grab.md`
- Task record moved to done: `tasks/done/TASK-20260304-2330-code-mouse-tab-alignment.md`
- Decision record: `decisions/DEC-20260304-local-closure-without-pr-state-gating.md`
- Session record: `sessions/2026-03-04-memory-refresh-local-closure-and-issue-scan.md`
- Reference snapshot: `references/open-issues-refresh-2026-03-04.md`
