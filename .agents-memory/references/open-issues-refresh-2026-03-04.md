# Open Issues Refresh - 2026-03-04

## Scope
Snapshot of issue intelligence collected during the latest triage/research pass.
No additional fetch was performed after this refresh request.

## PR Status Refresh - 2026-06-11
GitHub state was rechecked for RDeckard PRs referenced by memory:
- `#2894` (`#2478`) merged 2026-03-12.
- `#2895` (`#2480`) merged 2026-03-12.
- `#2896` (`#2439`) merged 2026-03-12.
- `#2897` (`#2292`) merged 2026-03-12.
- `#2898` (`#2392`) merged 2026-03-12.
- `#2899` (`#2437`) merged 2026-03-12.
- `#2900` (`#2614`) merged 2026-03-12.
- `#2901` (`#2330`) merged 2026-05-04.
- `#2903` (`#2855`) merged 2026-05-04.
- `#2916` (`#2615`) remains open; comments should be handled in a separate follow-up.
- `#2940` is a follow-up issue linked to merged PR `#2901` / issue `#2330`.

## Confirmed Current State
- Historical 2026-03-04 snapshot below is superseded by the 2026-06-11 PR refresh for PR status.
- `#2614` was open at this snapshot; PR `#2900` later merged on 2026-03-12.
- `#2330` was open at this snapshot; PR `#2901` later merged on 2026-05-04 and follow-up `#2940` is open.
- `#2388` remains open (website sorting request).
- `#2301` remains open (reopened state).

## Newly Captured Actionable Candidates
- `#2868` (HTML export blur filter)
  - HTML export templates are present in this repository under `build/html/`.
- `#2855` (macOS horizontal scroll direction)
  - Code path still applies `tic->ram->input.mouse.scrollx *= -1`.
- `#2861` (JS `print(0.5)` crash)
  - Open issue with minimal repro and concrete core code pointer.
- `#2742` (Linux install misses language libraries)
  - Open issue with reproducible install sequence and static-build workaround.

## Additional Context Gathered
- `#2821` is open (Android wireless keyboard arrows not recognized in editors/console).
- Android storage-policy cluster is active: `#2470`, `#2843`, `#2873`.
- Quick-win blockers unchanged in this repository context:
  - `#2388` (website source not in this repo)
  - `#2301` (no high-confidence localized fix path yet)

## Notes
This file is a memory artifact and not a recommendation lock.
Prioritization remains in `tasks/active/TASK-20260302-quickwins-attack-order.md` and `backlog.md`.
