# DEC-20260303-2439-ctrl-shortcut-text-guard

## Context
Issue `#2439` reports that `Ctrl+S` on Android both saves and inserts an extra `s` character into editor text.

## Decision
Implement the fix in `getKeyboardText` at studio level by returning no character when `Ctrl` is active without `Alt`.

## Rationale
- `getKeyboardText` is the shared text-entry path used by code and other editor surfaces.
- Blocking text at this point avoids backend-specific drift and covers related paths consistently.
- Limiting the guard to `Ctrl && !Alt` keeps `Ctrl+Alt` combinations available for international keyboard layouts.

## Alternatives Considered
1. Android Java-only fix in `SDLActivity`: rejected because it is backend-specific and may miss other runtime paths.
2. Code-editor-only suppression: rejected because text injection behavior can surface in other studio views.

## Consequences
- Short term:
  - Fixes extra-character insertion for `Ctrl` shortcuts such as `Ctrl+S`.
- Long term:
  - Centralizes shortcut/text separation in a single studio entry point and reduces duplicated keyboard edge-case handling.

## Links
- Task: `../tasks/done/TASK-20260303-2439-android-ctrl-shortcut-text-guard.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2439
