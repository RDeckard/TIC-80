# TASK-20260304-2615-native-export-local-template-fallback

## Metadata
- ID: TASK-20260304-2615-native-export-local-template-fallback
- Status: active
- Priority: high
- Wave: 10
- Created: 2026-03-04
- Updated: 2026-03-04
- Links (issue/PR/commit):
 - Issue: https://github.com/nesbox/TIC-80/issues/2615
 - Depends-On: none

## Context
Issue `#2615` reports silent PCM channel in exported native builds. The maintainer confirmed stale export binaries on the server side.

## Objective
Reduce user impact from stale server export binaries by preferring the local executable as template when exporting for the same native platform.

## Assumptions/Constraints
- We are external contributors and cannot fix server deployment pipeline directly.
- Current export flow fetches platform templates from `/export/...` endpoint.
- Local fallback must not break existing cross-platform export behavior.

## Plan
1. Remove out-of-scope memory references from previous non-1.2 issue work.
2. Implement local-template native export fallback for same-platform targets.
3. Build `tic80` to verify compilation.

## Execution
- [x] Removed all `.agents-memory` references to the previously considered non-1.2 issue.
- [x] Added local-template fallback in `src/studio/screens/console.c`.
- [x] Ran `cmake -S . -B /tmp/tic80-build` and `cmake --build /tmp/tic80-build -j4`.

## Verification
- Tests run:
  - `cmake -S . -B /tmp/tic80-build`
  - `cmake --build /tmp/tic80-build -j4`
- Results:
  - Configure succeeded.
  - Build succeeded (`Built target tic80`).

## Result
Native export now first tries local executable template on matching platform (`win` on Windows, `linux` on Linux, `mac` on macOS). If local template cannot be used, existing server export path remains unchanged.

## Follow-up
- Validate runtime behavior manually by exporting and checking PCM playback on same-platform native export.
- Optionally add a user-visible note when fallback is used.
