# TASK-20260303-2301-ttri-export-html-alone1

## Metadata
- ID: TASK-20260303-2301-ttri-export-html-alone1
- Status: active
- Priority: medium
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2301
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`
  - Decision: `../../decisions/DEC-20260303-post-2392-next-quickwin-order.md`

## Context
Wave 6 (`#2388`) is currently blocked in this repository because `tic80.com/play` website source is not present here. The next actionable queued issue is Wave 7 `#2301`: `ttri` draws nothing in pages generated via `export html alone=1`.

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
- [ ] Locate implementation points in repo code.
- [ ] Reproduce or reason through failure path in standalone export runtime.
- [ ] Implement localized fix.
- [ ] Run verification and document outcome.

## Verification
- Tests run:
  - Pending.
- Results:
  - Pending.

## Result
In progress.

## Follow-up
- If completed, move this file to `../done/`.
