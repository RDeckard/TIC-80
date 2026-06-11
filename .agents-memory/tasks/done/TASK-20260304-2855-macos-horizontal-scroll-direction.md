# TASK-20260304-2855-macos-horizontal-scroll-direction

## Metadata
- ID: TASK-20260304-2855-macos-horizontal-scroll-direction
- Status: done
- Priority: high
- Wave: 11
- Created: 2026-03-04
- Updated: 2026-06-11
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2855
  - PR: https://github.com/nesbox/TIC-80/pull/2903 (merged 2026-05-04)
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`
  - Depends-On: none

## Context
Issue `#2855` reports that horizontal scroll direction is inverted on macOS while vertical scroll direction is already correct.

## Objective
Apply a low-risk, localized fix so horizontal scrolling follows expected macOS direction without changing non-macOS behavior.

## Assumptions/Constraints
- Keep the change localized to `src/studio/studio.c`.
- Do not refactor SDL wheel-direction handling.
- Preserve non-macOS behavior.

## Plan
1. Scope horizontal inversion to non-macOS builds only.
2. Build `tic80` to validate compilation.
3. Update memory tracking artifacts and close the wave.

## Execution
- [x] Scope `scrollx` inversion to non-macOS in `processMouseStates()`.
- [x] Run configure/build verification.
- [x] Finalize memory records and move task to `done/`.

## Verification
- Tests run:
  - `cmake -S . -B /tmp/tic80-2855-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On`
  - `cmake --build /tmp/tic80-2855-check --target tic80 --parallel 4`
- Results:
  - Configure succeeded.
  - Build succeeded (`Built target tic80`).

## Result
Done.
`scrollx` inversion now bypasses macOS builds while preserving existing non-macOS behavior.
PR `#2903` merged upstream on 2026-05-04.

## Follow-up
- Manual macOS behavior verification remains recommended when a macOS runtime is available.
