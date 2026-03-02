# .agents-memory Structure

Last updated: 2026-03-03
Owner: agent

## Role of This File
`structure.md` is the master index of `.agents-memory/`.
It must always reflect the actual directory structure exactly.

## Tree and Roles
```text
.agents-memory/
├── structure.md                  # Master index (mandatory, always up to date)
├── backlog.md                    # Short view of prioritized topics/tasks
├── sessions/
│   ├── README.md                 # Session logging rules
│   └── 2026-03-02-bootstrap.md   # Bootstrap session note
│   └── 2026-03-02-todo-and-quickwins-planning.md # TODO/quick-win planning update
│   └── 2026-03-02-2478-implementation.md # #2478 implementation session log
│   └── 2026-03-02-pr-description-format-guideline.md # PR description format guideline session log
│   └── 2026-03-03-2480-implementation.md # #2480 implementation session log
├── tasks/
│   ├── active/
│   │   ├── README.md             # In-progress tasks
│   │   └── TASK-20260302-quickwins-attack-order.md # Ordered execution plan
│   ├── done/
│   │   ├── README.md             # Completed tasks
│   │   └── TASK-20260302-2478-remap-docs-cross-surface.md # Completed #2478 doc task
│   │   └── TASK-20260302-pr-description-format-guideline.md # Completed PR description format task
│   │   └── TASK-20260303-2480-capslock-music-hex.md # Completed #2480 music editor fix
│   ├── blocked/
│   │   └── README.md             # Blocked tasks
│   └── templates/
│       ├── task-template.md      # Task file template
│       └── decision-template.md  # Technical decision template
├── decisions/
│   ├── README.md                 # Decision log rules/index
│   └── DEC-20260302-quickwin-selection-and-contributor-constraints.md # Quick-win decision record
│   └── DEC-20260302-2478-documentation-scope-and-style.md # #2478 doc surface and style decision
│   └── DEC-20260303-2480-localized-music-hex-fix.md # #2480 localized fix decision
└── references/
    ├── README.md                 # Useful links/docs/context
    └── project-1.2-view1-todo-snapshot-2026-03-02.md # Snapshot of 24 TODO items
```

## Naming Conventions
- Tasks: `tasks/<state>/TASK-YYYYMMDD-slug.md`
- Decisions: `decisions/DEC-YYYYMMDD-slug.md`
- Sessions: `sessions/YYYY-MM-DD-note.md`

## Maintenance Contract (Mandatory)
1. Read this file before structural changes.
2. If any file/folder is added/removed/renamed/moved, update this tree and relevant sections immediately.
3. If a convention changes, document the new convention here.
4. Do not leave any mismatch between filesystem reality and this document.

## Tracking Scope
- `.agents-memory/` should capture concrete project progress, not routine administrative navigation.
- Do not add task/backlog/session entries for simple status checks, directory/file listing, or reading memory to decide what to do next.
- Add records when there is material advancement (implementation, documentation changes, actionable triage/follow-up, or non-trivial decision making).

## End-of-Session Checklist
- [ ] New tasks exist in `tasks/active/` and are referenced in `backlog.md`.
- [ ] Finished/blocked tasks were moved to the right folder.
- [ ] Non-trivial decisions were logged.
- [ ] Session summary was added in `sessions/`.
- [ ] `structure.md` remains accurate.
