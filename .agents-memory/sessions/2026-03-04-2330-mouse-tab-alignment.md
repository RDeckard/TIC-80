# Session: 2026-03-04 - #2330 mouse tab alignment

## Context
After complexity triage of the project board `In progress` lane, issue `#2330` was selected as a low-risk external-contributor target.

## Actions performed
- Inspected `src/studio/editors/code.c` to identify where mouse click/drag maps to cursor position.
- Implemented tab-aware visual mapping helpers for mouse cursor placement.
- Updated `processMouse()` to use visual mapping for click/drag selection.
- Kept keyboard navigation code paths unchanged.
- Ran configure/build validation for `tic80` target.

## Decisions made
- Adopt mouse-only scope for this fix.
- Use nearest-boundary tab policy for click inside tab visual width (tie to right boundary).

## Verification
- `cmake -S . -B /tmp/tic80-2330-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On` -> success
- `cmake --build /tmp/tic80-2330-check --target tic80 --parallel 4` -> success

## Next steps
- Perform manual in-editor validation for tab-size scenarios.
- Prepare PR handoff once manual behavior checks are confirmed.
