# DEC-20260303-post-2392-next-quickwin-order

## Context
Quick-win waves planned in `DEC-20260302-quickwin-selection-and-contributor-constraints.md` were completed through `#2392`. We needed a concrete next execution order from the remaining TODO snapshot items.

## Decision
1. Set `#2437` as the next implementation target.
2. Keep `#2388` as the immediate follow-up after `#2437`.
3. Keep `#2301` after `#2388`, due to likely higher verification risk on HTML/export behavior.

## Rationale
- `#2437` is narrow, editor-localized, and aligns with recent music/input fixes.
- `#2388` appears low-risk and mostly isolated to website ordering behavior.
- `#2301` is potentially broader due to rendering/export surface and should follow smaller wins.

## Alternatives Considered
1. Start directly with `#2301`.
2. Start with a broader platform/theme item (`#2341`, `#2343`, `#2408`).

## Consequences
- Short term:
  - Maintains high-throughput contribution cadence with lower merge risk.
- Long term:
  - Preserves momentum while delaying a potentially deeper HTML/export investigation by one step.

## Links
- Execution plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`
- Next active task: `../tasks/active/TASK-20260303-2437-music-preview-mute-channel.md`
- TODO snapshot: `../references/project-1.2-view1-todo-snapshot-2026-03-02.md`
