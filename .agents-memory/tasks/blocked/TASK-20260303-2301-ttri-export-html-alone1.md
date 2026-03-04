# TASK-20260303-2301-ttri-export-html-alone1

## Metadata
- ID: TASK-20260303-2301-ttri-export-html-alone1
- Status: blocked
- Priority: medium
- Created: 2026-03-03
- Updated: 2026-03-04
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2301
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`

## Context
Wave 6 (`#2388`) is blocked in this repository because `tic80.com/play` website source is not present here. Wave 7 (`#2301`) was then analyzed, but implementation confidence remained low without authoritative standalone export runtime parity.

## Objective
Reproduce and fix the `ttri` rendering regression specific to `export html alone=1` output, without broad changes to unrelated Web export/runtime behavior.

## Assumptions/Constraints
- Scope is limited to the `alone=1` export/runtime path.
- Keep native/runtime behavior unchanged where possible.
- Prefer a minimal fix validated with targeted reproduction.

## Plan
1. Locate the `export html` code path differences between `alone=0` and `alone=1`.
2. Reproduce/trace why `ttri` fails specifically in standalone exports.
3. Implement a focused fix and run targeted verification.

## Execution
- [x] Gather issue context/comments and repro hints from `#2301`.
- [x] Locate implementation points in repo code.
- [x] Reproduce or reason through failure path in standalone export runtime.
- [ ] Implement localized fix.
- [ ] Run verification and document outcome.

## Verification
- Tests run:
  - Static inspection of `export html` (`src/studio/screens/console.c`) and SDL/web runtime paths (`build/html/export.html`, `src/api/*`, `src/core/draw.c`).
  - Downloaded and decoded issue repro cart attachment to validate script/runtime context.
- Results:
  - Root cause remained ambiguous across remote standalone export/runtime differences.
  - No low-risk patch with high confidence was identified during this wave.

## Result
Blocked due to insufficient confidence for a safe localized fix in this repository context.

## Follow-up
- Moved to `../blocked/`.
- Continue with next actionable issue (`#2614`).
