# DEC-20260304-2614-focus-loss-key-reset-policy

## Context
Issue `#2614` reports stuck keys when a key is released while the TIC-80 window is being grabbed, implying missed `SDL_KEYUP` delivery and stale keyboard state.

## Decision
- Scope: `wave`
- Promote-to-core: `no`

Use a focused SDL mitigation:
1. Add a keyboard-state reset helper for focus-loss transitions.
2. Trigger it on `SDL_WINDOWEVENT_FOCUS_LOST` only.
3. Keep existing `SDL_WINDOWEVENT_FOCUS_GAINED` Linux lock-input workaround unchanged.

## Rationale
- The bug pattern aligns with focus-transition key event loss.
- Reset-on-focus-loss is low-risk and localized.
- Broader strategies (per-frame state sync or resize/move resets) increase behavior risk and complexity.

## Alternatives Considered
1. Reset keyboard state on focus loss plus move/resize events.
2. Rework key lifecycle around continuous `SDL_GetKeyboardState` synchronization.

## Consequences
- Short term:
  - Prevents stale stuck-key state after focus-lost transitions from window grabbing.
- Long term:
  - Leaves room for future broader input refactor only if additional evidence appears.

## Links
- Active task: `../tasks/active/TASK-20260304-2614-sdl-stuck-keys-window-grab.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2614
