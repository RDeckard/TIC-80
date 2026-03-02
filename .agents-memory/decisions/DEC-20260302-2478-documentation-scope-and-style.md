# DEC-20260302-2478-documentation-scope-and-style

## Context
While preparing implementation for issue `#2478`, we needed to decide how far to document `map(..., remap=...)` differences across bindings and where to place that documentation.

## Decision
1. Keep `src/api.h` as the canonical and complete source for binding-specific `remap` behavior.
2. Add concise non-API documentation in `README.md` and in Lua/JS/Python demo comments.
3. Keep additions minimal and style-aligned in each file scope, with no behavior changes.

## Rationale
- `src/api.h` powers `help map`, which is the most direct runtime documentation path.
- A short README pointer improves discoverability without duplicating a full matrix.
- Demo-level notes provide practical entry points for common bindings with minimal maintenance cost.

## Alternatives Considered
1. Document only in `src/api.h` and skip other surfaces.
2. Create a dedicated long-form markdown reference page.

## Consequences
- Short term:
  - Issue `#2478` is addressed with complete canonical coverage and lightweight discoverability improvements.
- Long term:
  - Lower risk of documentation drift by keeping detail centralized in API help text.

## Links
- Issue: https://github.com/nesbox/TIC-80/issues/2478
- Task: `../tasks/done/TASK-20260302-2478-remap-docs-cross-surface.md`
- Parent plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`
