# TASK-20260303-2392-help-version-language-runtimes

## Metadata
- ID: TASK-20260303-2392-help-version-language-runtimes
- Status: done
- Priority: medium
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2392
  - Parent plan: `../active/TASK-20260302-quickwins-attack-order.md`

## Context
Issue `#2392` requests language/runtime version information in the `help version` console command so users can identify the correct language documentation for embedded runtimes.

## Objective
Extend `help version` to show TIC-80 version plus per-language runtime versions for currently available script runtimes.

## Assumptions/Constraints
- Scope is limited to language/runtime versions (no broad third-party library inventory).
- Avoid ABI changes to `tic_script` to preserve dynamic runtime loading compatibility.
- Keep changes localized to console output behavior.

## Plan
1. Add CMake-time runtime version extraction and generated header wiring.
2. Add `help version` output expansion in `src/studio/screens/console.c`.
3. Build-check the project target.
4. Update memory records and Wave 4 tracking.

## Execution
- [x] Implement runtime-version extraction in `cmake/runtime_versions.cmake` and generate `runtime_versions.h` from `cmake/runtime_versions.h.in`.
- [x] Wire runtime-version generation into top-level `CMakeLists.txt`.
- [x] Update `onHelp_version` to print TIC-80 version + `language runtimes` listing for loaded scripts.
- [x] Build-check `tic80` target.
- [x] Update backlog and quick-win tracking files.

## Verification
- Tests run:
- `cmake -S . -B /tmp/tic80-plan-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On`
- `cmake --build /tmp/tic80-plan-check --target tic80 --parallel 4`
- Results:
- Configuration succeeded.
- Build succeeded (`tic80` target linked successfully).

## Result
`help version` now provides runtime-version context for supported scripting languages in the current build, with versions sourced dynamically from vendored/runtime headers during CMake configuration.
