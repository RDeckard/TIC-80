# .agents-memory Structure

Last updated: 2026-03-02
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
├── tasks/
│   ├── active/
│   │   ├── README.md             # In-progress tasks
│   │   └── TASK-20260302-quickwins-attack-order.md # Ordered execution plan
│   ├── done/
│   │   └── README.md             # Completed tasks
│   ├── blocked/
│   │   └── README.md             # Blocked tasks
│   └── templates/
│       ├── task-template.md      # Task file template
│       └── decision-template.md  # Technical decision template
├── decisions/
│   ├── README.md                 # Decision log rules/index
│   └── DEC-20260302-quickwin-selection-and-contributor-constraints.md # Quick-win decision record
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

## End-of-Session Checklist
- [ ] New tasks exist in `tasks/active/` and are referenced in `backlog.md`.
- [ ] Finished/blocked tasks were moved to the right folder.
- [ ] Non-trivial decisions were logged.
- [ ] Session summary was added in `sessions/`.
- [ ] `structure.md` remains accurate.
