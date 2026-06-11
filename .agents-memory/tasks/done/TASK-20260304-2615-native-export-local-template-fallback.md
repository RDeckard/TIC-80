# TASK-20260304-2615-native-export-local-template-fallback

## Metadata
- ID: TASK-20260304-2615-native-export-local-template-fallback
- Status: done
- Priority: high
- Wave: 10
- Created: 2026-03-04
- Updated: 2026-06-12
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2615
  - PR: https://github.com/nesbox/TIC-80/pull/2916 (open)
  - Branch: `fix/2615-native-export-local-template-fallback`
  - Latest commit: `27c47b4f` (`Improve native export fallback handling`)
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
- [x] Addressed PR feedback by making the local-template path fall back to server export if embed/write fails, and by limiting the fallback message to same-platform exports.

## Verification
- Tests run:
  - `cmake -S . -B /tmp/tic80-build`
  - `cmake --build /tmp/tic80-build -j4`
  - `git diff --check` (2026-06-12 follow-up)
- Results:
  - Configure succeeded.
  - Build succeeded (`Built target tic80`).
  - Follow-up diff check passed. Local full build was not rerun; this environment did not provide `cmake`, `gcc`, or `clang`, and full build validation is expected from upstream CI on the PR branch.

## Result
Native export now first tries local executable template on matching platform (`win` on Windows, `linux` on Linux, `mac` on macOS). If local template cannot be used, existing server export path remains unchanged.
PR `#2916` remains open as of 2026-06-12 and was updated with commit `27c47b4f`.

## Follow-up
- Monitor PR `#2916` CI and maintainer feedback.
- Validate runtime behavior manually by exporting and checking PCM playback on same-platform native export.
- Optionally add a user-visible note when fallback is used.
- Follow-up comment posted: https://github.com/nesbox/TIC-80/pull/2916#issuecomment-4685885449

# Draft PR Comment
Updated the PR to make the local-template path best-effort only.

If embedding or writing the local executable template fails, export now falls back to the existing server template flow instead of reporting a local export failure. The fallback message is also only shown for same-platform exports, so cross-platform exports keep the previous behavior/noise level.

This is still intended as a narrow mitigation for stale same-platform server templates, not as a replacement for the server/template pipeline.
