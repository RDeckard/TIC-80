# DEC-20260303-2292-android-keyboard-vs-joystick-classification

## Context
Issue `#2292` reports that Android external/Bluetooth keyboard arrow keys are not recognized by TIC-80, while other keys work.

## Decision
Treat alphabetic keyboards as keyboard-only in `SDLControllerManager.isDeviceSDLJoystick`, even when they expose `SOURCE_DPAD`.

## Rationale
- Some Android external keyboards advertise `SOURCE_KEYBOARD` and `SOURCE_DPAD`.
- The joystick-first handling path can consume `KEYCODE_DPAD_*` before keyboard handling, causing arrow key loss.
- Excluding alphabetic keyboards from joystick classification restores arrow keys with a narrow, low-risk change.

## Alternatives Considered
1. Reorder `SDLActivity.handleKeyEvent` to handle keyboard first: rejected for this task because it broadens event-routing behavior and risk.
2. Combined patch (reorder + classification guard): rejected for quick-win scope due to larger change surface.

## Consequences
- Short term:
  - Restores external/Bluetooth keyboard arrow keys for affected Android setups.
- Long term:
  - Keeps joystick-first behavior for real controllers while avoiding keyboard misclassification.

## Links
- Task: `../tasks/done/TASK-20260303-2292-android-arrow-keys-routing.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2292
