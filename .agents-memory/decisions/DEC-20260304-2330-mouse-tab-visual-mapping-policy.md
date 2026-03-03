# DEC-20260304-2330-mouse-tab-visual-mapping-policy

## Context
Issue `#2330` reports misaligned mouse cursor placement and selection in the code editor when tab width is greater than 1.

## Decision
- Scope: `wave`
- Promote-to-core: `no`

Use a focused editor-side fix:
1. Keep keyboard cursor movement logic unchanged.
2. Add tab-aware visual-column mapping for mouse click/drag only.
3. Use nearest boundary policy inside a tab visual span, with tie going to the right boundary.

## Rationale
- The bug is reported on mouse placement/selection, not keyboard navigation.
- A mouse-only fix is localized and lower-risk than refactoring line/column semantics globally.
- Nearest-boundary tab behavior matches user expectation while staying deterministic.

## Alternatives Considered
1. Broader cursor column refactor across keyboard and mouse paths.
2. Tab hit policy forced to tab-start only.
3. Tab hit policy forced to tab-end only.

## Consequences
- Short term:
  - Mouse click/drag selection should align with rendered tab width for `tabSize > 1`.
  - Keyboard behavior remains unchanged.
- Long term:
  - If broader column consistency issues appear, a dedicated follow-up refactor can be evaluated separately.

## Links
- Active task: `../tasks/active/TASK-20260304-2330-code-mouse-tab-alignment.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2330
