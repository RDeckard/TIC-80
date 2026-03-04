# Session: 2026-03-04 - #2855 macOS horizontal scroll direction

## Context
User requested implementation of the planned quick win for issue `#2855` (horizontal scroll direction inverted on macOS).

## Actions performed
- Implemented a localized fix in `src/studio/studio.c`:
  - `scrollx` inversion now applies only for non-macOS builds.
- Ran configure/build validation:
  - `cmake -S . -B /tmp/tic80-2855-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On`
  - `cmake --build /tmp/tic80-2855-check --target tic80 --parallel 4`
- Updated memory tracking artifacts (task/backlog/indexes/decision links).

## Decisions made
- Kept SDL wheel handling unchanged.
- Chose platform-scoped guard (`__TIC_MACOSX__`) over global behavior change.

## Next steps
- Validate runtime behavior on an actual macOS device/session.
- Open a PR from the branch with issue-linked description.
