# DEC-20260304-2855-macos-scrollx-platform-scope

## Context
Issue `#2855` reports that horizontal trackpad scroll direction is inverted on macOS while vertical direction is already correct.
The current code path in `src/studio/studio.c` applies `scrollx *= -1` unconditionally for studio input processing.

## Decision
- Scope: `wave`
- Promote-to-core: `no`

Apply a platform-scoped fix:
1. Keep `scrollx` inversion for non-macOS builds.
2. Disable this inversion on macOS (`__TIC_MACOSX__`).
3. Keep SDL event collection and wheel handling unchanged.

## Rationale
- Localized change with minimal regression surface.
- Directly targets the platform where mismatch was reported.
- Avoids broad input normalization changes without cross-platform validation.

## Alternatives Considered
1. Remove inversion globally on all platforms.
2. Rework wheel-direction handling in SDL runtime using event direction metadata.

## Consequences
- Short term:
  - macOS horizontal scroll behavior aligns with expected system direction.
  - non-macOS behavior remains unchanged.
- Long term:
  - if further platform inconsistencies are reported, revisit with a cross-platform input normalization policy.

## Links
- Issue: https://github.com/nesbox/TIC-80/issues/2855
- Task: `../tasks/done/TASK-20260304-2855-macos-horizontal-scroll-direction.md`
- Parent plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`
