# DEC-20260303-2392-help-version-runtime-mapping

## Context
Issue `#2392` asks for language/runtime versions in `help version` so users can identify matching documentation for embedded runtimes.

## Decision
Implement language/runtime version reporting with CMake-time extraction from vendored/runtime source files into a generated header (`runtime_versions.h`), consumed by a localized mapping table in `src/studio/screens/console.c`, without changing `tic_script` structure or runtime plugin ABI.

## Rationale
- The request is console-output oriented and can be satisfied without cross-module interface changes.
- Modifying `tic_script` would increase ABI risk for dynamic runtime loading (`dlsym`/`SCRIPT_CONFIG`).
- Extracting versions in CMake avoids manual hardcoded version drift while keeping runtime behavior simple and deterministic.
- A localized mapping in console output keeps the change minimal and low-risk for quick-win Wave 4.

## Alternatives Considered
1. Add a version callback field to `tic_script`: rejected due to ABI-change risk and broader implementation surface.
2. Query each runtime dynamically through VM calls: rejected for complexity and inconsistent support across runtimes.
3. Hardcode runtime versions in `console.c`: rejected because values drift whenever vendored runtimes are updated.
4. Add broad library inventory in `help version`: rejected for this task's scope (language/runtime versions only).

## Consequences
- Short term:
  - `help version` now includes useful per-language runtime version information.
- Long term:
  - Version strings track vendored/runtime source updates automatically at configure time.
  - New language backends still require adding one extraction rule and one mapping entry.

## Links
- Task: `../tasks/done/TASK-20260303-2392-help-version-language-runtimes.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2392
