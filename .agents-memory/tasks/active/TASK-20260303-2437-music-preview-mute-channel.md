# TASK-20260303-2437-music-preview-mute-channel

## Metadata
- ID: TASK-20260303-2437-music-preview-mute-channel
- Status: active
- Priority: high
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2437
  - Decision: `../../decisions/DEC-20260303-post-2392-next-quickwin-order.md`
  - Decision: `../../decisions/DEC-20260303-2437-validation-policy-ci-first.md`

## Context
After completing the previously planned quick-win waves up to `#2392`, the next best low-risk/high-throughput issue is `#2437` (music editor note preview mute channel mismatch).

## Objective
Implement and validate a focused fix for `#2437` without expanding scope to unrelated audio/editor behavior.

## Assumptions/Constraints
- External contributor workflow only (fork + PR).
- Keep change localized to music preview/mute routing behavior.
- Preserve existing behavior outside the targeted bug.
- No local full build/check by default on this workstation (performance constraint); rely on CI for full validation.

## Plan
1. Locate current note preview + mute channel selection logic in music editor code.
2. Apply a minimal fix that routes preview mute to the intended channel.
3. Verify with targeted reproduction and available local checks.

## Execution
- [ ] Reproduce issue behavior from `#2437`.
- [x] Implement localized code fix.
- [x] Run verification and document outcome.

## Verification
- Tests run:
  - Local full build intentionally skipped (performance policy, CI-first validation).
- Results:
  - Static validation completed on changed code path.
  - Full compile/test confirmation pending CI.

## Result
Code fix prepared for `playNote()` channel routing:
- Tracker tab preview now uses tracker-selected channel.
- Piano tab preview keeps using piano-selected channel.
- Final pass/fail signal delegated to CI.

## Follow-up
- If completed, move this file to `../done/`.
- Then continue queue with `#2388` and `#2301`.
