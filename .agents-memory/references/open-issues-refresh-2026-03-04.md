# Open Issues Refresh - 2026-03-04

## Scope
Snapshot of issue intelligence collected during the latest triage/research pass.
No additional fetch was performed after this refresh request.

## Confirmed Current State
- `#2614` remains open; draft PR `#2900` exists (pending checks state at read time).
- `#2330` remains open; draft PR `#2901` exists (pending checks state at read time).
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
