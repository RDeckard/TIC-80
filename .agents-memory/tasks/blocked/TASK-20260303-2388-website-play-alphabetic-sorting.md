# TASK-20260303-2388-website-play-alphabetic-sorting

## Metadata
- ID: TASK-20260303-2388-website-play-alphabetic-sorting
- Status: blocked
- Priority: medium
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2388
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`
  - Decision: `../../decisions/DEC-20260303-post-2392-next-quickwin-order.md`

## Context
Wave 5 (`#2437`) is complete and in PR review with green CI, so the next queued quick win is `#2388`: add practical alphabetic sorting support for the website "play" listing workflow.

## Objective
Implement a focused, low-risk alphabetic sorting adjustment for the website play-page cart list behavior, without broadening into full search/filter redesign.

## Assumptions/Constraints
- Keep scope aligned with issue intent: alphabetic sorting first.
- Avoid unrelated website sorting/filter refactors.
- Preserve existing default behavior when no new sort mode is selected.
- This repository does not contain `tic80.com/play` website source code.

## Plan
1. Locate where play-page sort options and ordering logic are defined.
2. Add/adjust alphabetic sort option and wire it through the relevant request/UI path.
3. Verify behavior with targeted checks and document results.

## Execution
- [x] Gather issue context and constraints from `#2388`.
- [x] Locate implementation points in repo code.
- [ ] Implement localized sorting adjustment.
- [ ] Run verification and document outcome.

## Verification
- Tests run:
  - Repository scan for play-page/website source and SURF data path.
- Results:
  - `tic80.com/play` website source is not present in this repository.
  - Only SURF client-side listing code (`src/studio/screens/surf.c`, `src/studio/fs.c`) is available.

## Result
Blocked for issue-complete implementation in this repository due to missing website source code.

## Follow-up
- Moved to `../blocked/` for now.
- Continue queue with `#2301`.
