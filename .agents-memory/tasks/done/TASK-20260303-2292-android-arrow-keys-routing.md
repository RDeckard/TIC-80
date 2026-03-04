# TASK-20260303-2292-android-arrow-keys-routing

## Metadata
- ID: TASK-20260303-2292-android-arrow-keys-routing
- Status: done
- Priority: high
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2292
  - Parent plan: `./TASK-20260302-quickwins-attack-order.md`

## Context
Android users report that external/Bluetooth keyboard arrow keys do not work in TIC-80, while other keys work and arrows work in other apps.

## Objective
Restore arrow key behavior from external/Bluetooth keyboards on Android without regressing gamepad input behavior.

## Assumptions/Constraints
- Keep the fix minimal and low-risk for quick-win wave execution.
- Preserve the current joystick-first event flow for real game controllers.
- Avoid broad SDLActivity routing refactors in this task.

## Plan
1. Patch Android device classification to avoid treating alphabetic keyboards as joysticks.
2. Build-check affected targets.
3. Update memory tracking and quick-win wave status.

## Execution
- [x] Add keyboard-vs-joystick guard in `SDLControllerManager.isDeviceSDLJoystick`.
- [x] Run build verification.
- [x] Update backlog/task records.

## Verification
- Tests run:
- `cmake --build /tmp/tic80-plan-check --target tic80 --parallel 4`
- `cd build/android && ./gradlew :app:compileDebugJavaWithJavac -x externalNativeBuildDebug`
- Results:
- `tic80` build passed.
- Android Java compile could not run because `JAVA_HOME` is unset and `java` is not available in the environment.

## Result
Implemented an Android input-classification fix to keep alphabetic external keyboards on the keyboard path, restoring arrow key handling for affected Bluetooth keyboards without changing joystick-first handling for real gamepads.

## Follow-up
- Run Android device-level manual verification when Java/Android toolchain is available.
