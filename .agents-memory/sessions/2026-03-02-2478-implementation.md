# Session - #2478 Implementation - 2026-03-02

## Context
Implement issue `#2478` by documenting `map(..., remap=...)` callback differences across bindings while preserving existing documentation style in each scope.

## Actions Performed
- Added complete binding-specific `remap` documentation to `map` help text in `src/api.h`.
- Added a concise runtime-doc pointer in `README.md` under Contributing.
- Added short language-specific remap notes to `demos/luademo.lua`, `demos/jsdemo.js`, and `demos/pythondemo.py`.
- Updated backlog and quick-win execution tracking.
- Logged scope/style decision and recorded this session.

## Decisions
- Canonical detail lives in API help (`src/api.h`).
- Non-API surfaces remain concise and discoverability-oriented.
- Documentation follows existing per-file style and avoids unnecessary expansion.

## Next Steps
- Open PR for `#2478`.
- Start Wave 1B issue `#2480`.
