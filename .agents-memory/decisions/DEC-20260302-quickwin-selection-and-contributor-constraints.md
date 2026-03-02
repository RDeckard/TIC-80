# DEC-20260302-quickwin-selection-and-contributor-constraints

## Context
We reviewed the 24 TODO items from `nesbox` project `#2`, view `1`, and needed a realistic contribution plan for future sessions.

## Decision
1. Work in **external contributor mode** only:
- Propose changes through PRs from our fork.
- Do not assume board-level project permissions.
2. Treat `#2584` as a board hygiene mismatch, not an executable coding task:
- `#2584` is closed but still appears in TODO.
- We cannot move board cards directly.
3. Prioritize quick wins by low implementation risk + high merge likelihood:
- `#2478` (documentation)
- `#2480` (music editor Caps Lock hex input)
- `#2439` (Android Ctrl+S inserts `s`)
- `#2292` (Android arrow keys)
- `#2392` (enhancement: language/runtime versions in `help version`)
4. Run work in waves:
- Wave 1: `#2478`, `#2480`
- Wave 2: `#2439`
- Wave 3: `#2292`
- Wave 4: `#2392`

## Rationale
- Documentation and narrowly scoped input bugs are fast to validate and easier to review.
- Android input issues likely share nearby code paths and can be tackled sequentially.
- `#2392` is useful but slightly broader (API/version reporting design).
- Closed-card mismatch is informational unless maintainers act on the board.

## Alternatives Considered
1. Start from complex rendering/export issues (`#2301`, `#1948`) first.
2. Start from policy/legal item (`#2876`) first.

## Consequences
- Short term:
  - Faster cycle time and earlier upstream trust-building.
  - More predictable PR review outcomes.
- Long term:
  - Better foundation to tackle medium/complex TODO items afterward.

## Links
- TODO snapshot: `../references/project-1.2-view1-todo-snapshot-2026-03-02.md`
- Execution plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`

