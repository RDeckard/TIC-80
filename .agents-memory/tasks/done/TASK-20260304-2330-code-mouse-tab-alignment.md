# TASK-20260304-2330-code-mouse-tab-alignment

## Metadata
- ID: TASK-20260304-2330-code-mouse-tab-alignment
- Status: done
- Priority: high
- Wave: 9
- Created: 2026-03-04
- Updated: 2026-06-11
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2330
  - PR: https://github.com/nesbox/TIC-80/pull/2901 (merged 2026-05-04)
  - Follow-up issue: https://github.com/nesbox/TIC-80/issues/2940
  - Parent plan: `TASK-20260302-quickwins-attack-order.md`

## Context
Issue `#2330` reports that mouse cursor placement/selection in the code editor is visually misaligned when tab size is greater than 1.

## Objective
Apply a low-risk, localized fix that aligns mouse click/drag cursor mapping with visual tab width, without changing keyboard navigation behavior.

## Assumptions/Constraints
- Scope is limited to mouse mapping in `src/studio/editors/code.c`.
- Tab hit policy inside expanded tab width is nearest boundary; tie goes to the right boundary.
- Do not change line/column keyboard movement behavior.

## Plan
1. Add visual-column helpers for tab-aware mouse mapping.
2. Route mouse cursor placement through the new visual mapping helper.
3. Validate with configure/build and keep manual repro checks pending.

## Execution
- [x] Locate current mouse-to-cursor mapping path in code editor.
- [x] Implement tab-aware visual mapping helpers.
- [x] Wire `processMouse()` to use visual mapping for click/drag selection.
- [x] Run configure/build validation.
- [x] Close locally per user directive (manual in-app validation deferred unless user revisits).

## Verification
- Tests run:
  - `cmake -S . -B /tmp/tic80-2330-check -DBUILD_SDLGPU=On -DBUILD_WITH_ALL=On`
  - `cmake --build /tmp/tic80-2330-check --target tic80 --parallel 4`
- Results:
  - Configure succeeded.
  - Build succeeded (`tic80` target built successfully).
  - Manual reproduction validation deferred by choice; local closure requested by user.

## Result
Done.
Implementation and build validation are complete.
PR `#2901` merged upstream on 2026-05-04 and closed `#2330`.
Follow-up issue `#2940` reports a horizontal-scroll edge case in this tab-aware mouse mapping.

## Follow-up
- Treat `#2940` as the active follow-up if this area is revisited.
