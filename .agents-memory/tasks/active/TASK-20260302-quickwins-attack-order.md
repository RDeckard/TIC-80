# TASK-20260302-quickwins-attack-order

## Metadata
- ID: TASK-20260302-quickwins-attack-order
- Status: active
- Priority: high
- Created: 2026-03-02
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - TODO source: https://github.com/users/nesbox/projects/2/views/1
  - Decision: `../../decisions/DEC-20260302-quickwin-selection-and-contributor-constraints.md`

## Context
Prepare a practical sequence for future contribution sessions on TIC-80 project 1.2 TODO items.

## Objective
Define a low-risk, high-throughput order of execution for quick wins, while respecting external contributor permissions.

## Assumptions/Constraints
- We do not have rights to edit `nesbox` project board columns/cards.
- We can contribute via fork + PR workflow.
- Each issue should be handled in a focused conversation/session.

## Plan
1. Start with documentation and narrow editor bugs.
2. Continue with Android input fixes.
3. Move to medium enhancement scope.

## Execution
- [x] Wave 1A: `#2478` Document `map` remap callback differences across language bindings. See `../done/TASK-20260302-2478-remap-docs-cross-surface.md`.
- [x] Wave 1B: `#2480` Fix Caps Lock handling for A-F volume/hex input in music editor. See `../done/TASK-20260303-2480-capslock-music-hex.md`.
- [x] Wave 2: `#2439` Fix Android `Ctrl+S` adding extra `s`. See `../done/TASK-20260303-2439-android-ctrl-shortcut-text-guard.md`.
- [x] Wave 3: `#2292` Fix Android arrow keys from external/Bluetooth keyboard. See `../done/TASK-20260303-2292-android-arrow-keys-routing.md`.
- [ ] Wave 4: `#2392` Add language/runtime version info to `help version`.

## Verification
- Tests run:
  - To be filled per issue implementation session.
- Results:
  - To be filled per issue implementation session.

## Result
Execution order prepared and linked to backlog/decision records.

## Follow-up
- Track progress per wave in this file.
- Create focused implementation tasks if parallel work starts.
- If maintainers grant project permissions later, revisit board hygiene item (`#2584`) directly.
