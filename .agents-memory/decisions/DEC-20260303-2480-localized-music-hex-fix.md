# DEC-20260303-2480-localized-music-hex-fix

## Context
Issue `#2480` reports that the music editor does not accept hex letters `A-F` with Caps Lock enabled. We needed to decide whether to apply a narrow fix in `music.c` or introduce a broader shared helper refactor.

## Decision
1. Apply a localized fix in `src/studio/editors/music.c` by updating `sym2hex` to accept both `A-F` and `a-f`.
2. Do not introduce new cross-editor/shared hex helpers for this issue.
3. Keep behavior unchanged for non-hex input and decimal-only fields.

## Rationale
- The bug source is isolated to the local `sym2hex` implementation in the music editor.
- Other editor codepaths already use `isxdigit`/`toupper` patterns and are not impacted by this bug.
- A targeted patch minimizes review risk and keeps the PR focused on `#2480`.

## Alternatives Considered
1. Introduce a shared `sym2hex` helper in `studio.c/studio.h` and migrate call sites.
2. Perform a wider normalization refactor across multiple editors.

## Consequences
- Short term:
  - Fast, low-risk bug fix with minimal diff.
- Long term:
  - If more hex parsing inconsistencies appear later, a shared helper can be introduced with stronger justification.

## Links
- Issue: https://github.com/nesbox/TIC-80/issues/2480
- Task: `../tasks/done/TASK-20260303-2480-capslock-music-hex.md`
- Parent plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`
