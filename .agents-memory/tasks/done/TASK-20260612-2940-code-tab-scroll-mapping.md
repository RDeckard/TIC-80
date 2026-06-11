# TASK-20260612-2940-code-tab-scroll-mapping

## Metadata
- ID: TASK-20260612-2940-code-tab-scroll-mapping
- Status: done
- Priority: high
- Wave: 12
- Created: 2026-06-12
- Updated: 2026-06-12
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2940
  - Parent issue: https://github.com/nesbox/TIC-80/issues/2330
  - Parent PR: https://github.com/nesbox/TIC-80/pull/2901
  - Branch: `fix/2940-code-tab-scroll-mapping`
  - Commit: `47bb01ad` (`Fix code editor tab width after horizontal scroll`)
  - Fork branch: https://github.com/RDeckard/TIC-80/tree/fix/2940-code-tab-scroll-mapping

## Context
Issue `#2940` reports that the `#2901` tab-aware mouse mapping fix is incomplete when indentation tabs are hidden by horizontal scroll.

## Objective
Align code editor tab rendering and mouse-to-cursor mapping around one visual-column calculation so offscreen indentation tabs still advance by their full visual width.

## Assumptions/Constraints
- Keep the fix localized to `src/studio/editors/code.c`.
- Preserve the current nearest-boundary mouse hit policy inside expanded tabs.
- Use a clean branch from `main` for the upstream commit; keep memory on `codex`.

## Plan
1. Move tab advance calculation outside the visible-character drawing branch.
2. Make tab drawing consume a width derived from `getTabColumnWidth()`.
3. Port the code-only change to a clean branch from `main` and commit it there.
4. Return to `codex` and update memory with branch/commit details.

## Execution
- [x] Implemented local fix on `codex` for inspection.
- [x] Created clean branch `fix/2940-code-tab-scroll-mapping` from `main`.
- [x] Ported only `src/studio/editors/code.c` to the clean branch.
- [x] Committed code-only fix as `47bb01ad`.
- [x] Pushed branch to the user's fork.
- [x] Removed code change from `codex` and kept only memory updates there.

## Verification
- Tests run:
  - `git diff --check` on `codex` working diff.
  - `git diff --check` on clean branch before commit.
- Results:
  - Both whitespace checks passed.
  - Full build not run locally; CI/PR checks are expected to cover compilation.

## Result
Clean branch is pushed and ready for the user to open an upstream PR.
No upstream PR was opened by the agent.

## Follow-up
- User may open a PR from `RDeckard:fix/2940-code-tab-scroll-mapping` to `nesbox:main`.
- Suggested PR text can be generated on request.

# PR Description

## Why

Original issue: https://github.com/nesbox/TIC-80/issues/2940

Follow-up to https://github.com/nesbox/TIC-80/pull/2901.

The previous tab-aware mouse mapping fix handled visible tabs, but `#2940` shows a remaining mismatch after horizontal scrolling hides indentation tabs. In that case, hidden tabs could stop advancing the rendered x position by their full visual width, while mouse mapping still used visual tab columns.

## What

- Reuse the existing tab-column width calculation for code rendering.
- Compute a tab's x advance before the visibility check, so offscreen tabs still affect later character positions.
- Make `drawTab(...)` draw using the already computed visual width instead of recalculating from screen x.

## Impact

This should make rendering and mouse hit testing agree better when tabs are scrolled offscreen horizontally. I have not manually reproduced the exact video case, so reviewer confirmation on the `#2940` scenario would be useful.
