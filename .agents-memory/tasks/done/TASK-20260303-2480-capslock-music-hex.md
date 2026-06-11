# TASK-20260303-2480-capslock-music-hex

## Metadata
- ID: TASK-20260303-2480-capslock-music-hex
- Status: done
- Priority: high
- Created: 2026-03-03
- Updated: 2026-06-11
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2480
  - PR: https://github.com/nesbox/TIC-80/pull/2895 (merged 2026-03-12)
  - Parent plan: `./TASK-20260302-quickwins-attack-order.md`

## Context
Issue `#2480` reports that typing hex values `A-F` in the music editor fails when Caps Lock is enabled.

## Objective
Fix hex keyboard input in the music editor so both lowercase and uppercase letters are accepted for hex fields.

## Assumptions/Constraints
- Keep scope focused to the music editor implementation (`src/studio/editors/music.c`).
- Keep behavior unchanged for decimal fields and non-hex keys.
- CI will validate build after PR submission.

## Plan
1. Patch `sym2hex` in music editor to accept `A-F` and `a-f`.
2. Check all music editor call sites using `sym2hex`.
3. Update memory artifacts (backlog, wave tracker).

## Execution
- [x] Implement `music.c` fix for uppercase hex input.
- [x] Verify call sites and regression surface by static inspection.
- [x] Record tracking updates and move task to done.

## Verification
- Tests run:
  - Static inspection of affected call sites in tracker and piano editors.
  - Build not run locally (CI expected to validate).
- Results:
  - `sym2hex` now accepts both uppercase and lowercase hex letters.
  - Tracker `ColumnParameter1/2` and piano `PianoXYColumn` continue to use `sym2hex`.
  - No additional `a-f` only hex parsing was found in `src/`.

## Result
Issue `#2480` fixed with a localized and low-risk change in `src/studio/editors/music.c`.

## Follow-up
- PR `#2895` merged upstream on 2026-03-12.
