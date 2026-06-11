# TASK-20260303-2439-android-ctrl-shortcut-text-guard

## Metadata
- ID: TASK-20260303-2439-android-ctrl-shortcut-text-guard
- Status: done
- Priority: high
- Created: 2026-03-03
- Updated: 2026-06-11
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2439
  - PR: https://github.com/nesbox/TIC-80/pull/2896 (merged 2026-03-12)
  - Parent plan: `./TASK-20260302-quickwins-attack-order.md`

## Context
Android users reported that pressing `Ctrl+S` saves but also inserts an unwanted `s` in the code editor.

## Objective
Prevent text character injection during `Ctrl` shortcuts while preserving normal text entry behavior.

## Assumptions/Constraints
- Shortcut behavior should remain unchanged (save still triggers).
- `Ctrl+Alt` combinations should remain available for keyboard layouts that rely on AltGr-like behavior.
- Keep fix minimal and centered in shared studio keyboard text path.

## Plan
1. Add a `Ctrl` text-input guard in `getKeyboardText`.
2. Keep behavior backend-agnostic by fixing in studio-level text path.
3. Build `tic80` to validate no compilation regression.

## Execution
- [x] Add guard to block printable text when `Ctrl` is active without `Alt`.
- [x] Run build verification for `tic80`.
- [x] Update quick-win tracking and close this task.

## Verification
- Tests run:
  - `cmake --build /tmp/tic80-plan-check --target tic80 --parallel 4`
- Results:
  - Build passed, `tic80` target linked successfully.

## Result
Implemented a studio-level guard in `getKeyboardText` so `Ctrl` shortcuts no longer inject printable characters.

## Follow-up
- PR `#2896` merged upstream on 2026-03-12.
