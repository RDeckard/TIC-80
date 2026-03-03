# Session: 2026-03-03 - Issue #2292 implementation

## Context
Implement quick-win Wave 3 issue `#2292`: Android external/Bluetooth keyboard arrow keys not working.

## Actions performed
- Inspected Android key routing in `SDLActivity` and device classification in `SDLControllerManager`.
- Identified keyboard devices exposing both `SOURCE_KEYBOARD` and `SOURCE_DPAD` as likely root cause.
- Implemented a classification guard in `SDLControllerManager.isDeviceSDLJoystick` to keep alphabetic keyboards on keyboard path.
- Ran `tic80` build verification.
- Updated task/backlog/wave tracking and recorded the technical decision.

## Decisions made
- Use classification guard in `isDeviceSDLJoystick` rather than reordering global key routing in `SDLActivity`.
- Keep scope narrow for quick-win execution and lower regression risk.

## Verification
- Command: `cmake --build /tmp/tic80-plan-check --target tic80 --parallel 4`
- Result: success, target `tic80` built and linked.
- Command: `cd build/android && ./gradlew :app:compileDebugJavaWithJavac -x externalNativeBuildDebug`
- Result: could not run in current environment (`JAVA_HOME` unset and `java` unavailable).

## Next steps
- Run Android manual verification on device with external/Bluetooth keyboard arrows.
- Continue quick-win sequence with Wave 4 (`#2392`).
