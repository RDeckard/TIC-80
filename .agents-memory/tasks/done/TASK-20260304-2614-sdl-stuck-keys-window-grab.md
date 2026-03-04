# TASK-20260304-2614-sdl-stuck-keys-window-grab

## Metadata
- ID: TASK-20260304-2614-sdl-stuck-keys-window-grab
- Status: done
- Priority: high
- Created: 2026-03-04
- Updated: 2026-03-04
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2614
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`
  - Decision: `../../decisions/DEC-20260304-2614-focus-loss-key-reset-policy.md`
  - Closure policy: `../../decisions/DEC-20260304-local-closure-without-pr-state-gating.md`

## Context
After blocking Wave 7 (`#2301`) due to low-confidence standalone-export root-cause isolation, the next actionable issue is `#2614`: keyboard keys can stay logically pressed when a `KEYUP` event is missed during window-grab/focus transitions.

## Objective
Apply a focused SDL-side fix that prevents stuck keyboard state after focus loss/window grab, without broad input-pipeline refactors.

## Assumptions/Constraints
- Keep the change localized to SDL event handling (`src/system/sdl/main.c`).
- Do not alter non-SDL runtimes.
- Avoid behavior changes for normal in-focus key handling.

## Plan
1. Add a keyboard-state reset helper in SDL runtime code.
2. Trigger it on `SDL_WINDOWEVENT_FOCUS_LOST`.
3. Keep existing Linux focus-gain lock logic unchanged.
4. Run configure/build validation.

## Execution
- [x] Locate the SDL event-processing path and keyboard-state lifecycle.
- [x] Implement focus-loss keyboard-state reset.
- [x] Run configure/build verification and document outcome.

## Verification
- Tests run:
  - `cmake -S . -B /tmp/tic80-2614-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On`
  - `cmake --build /tmp/tic80-2614-check --target tic80 --parallel 4`
- Results:
  - Configure succeeded.
  - Build succeeded (`tic80` target linked successfully).
  - Manual in-app reproduction check remains pending by choice; local closure requested by user.

## Result
Done (local closure).
Implementation and build validation are complete.
By user directive, task closure is not blocked by draft/open PR state.

## Follow-up
- Reopen only if the user explicitly asks to revisit `#2614`.
