# TASK-20260302-2478-remap-docs-cross-surface

## Metadata
- ID: TASK-20260302-2478-remap-docs-cross-surface
- Status: done
- Priority: high
- Created: 2026-03-02
- Updated: 2026-03-02
- Links (issue/PR/commit):
  - Issue: https://github.com/nesbox/TIC-80/issues/2478
  - Parent execution plan: `TASK-20260302-quickwins-attack-order.md`
  - Decision: `../../decisions/DEC-20260302-2478-documentation-scope-and-style.md`

## Context
Issue `#2478` asks to document `map(..., remap=...)` callback differences across language bindings.

## Objective
Document binding-specific `remap` behavior in canonical API help and keep project-level docs aligned without over-documenting.

## Assumptions/Constraints
- Keep runtime behavior unchanged.
- Follow the style already present in each documentation scope.
- Keep additions concise and practical.

## Plan
1. Update canonical `map` help text in `src/api.h`.
2. Add a short pointer in `README.md`.
3. Add compact binding-specific reminders in Lua/JS/Python demos.

## Execution
- [x] Add complete binding matrix in `src/api.h` map help text.
- [x] Add concise project-level pointer in `README.md`.
- [x] Add short language-specific remap notes in `demos/luademo.lua`, `demos/jsdemo.js`, and `demos/pythondemo.py`.
- [x] Update backlog, decision log, and session notes.

## Verification
- Tests run:
  - `git diff -- src/api.h README.md demos/luademo.lua demos/jsdemo.js demos/pythondemo.py`
- Results:
  - Documentation-only changes are present in the expected files and match binding implementations.

## Result
`#2478` documentation is implemented across API help and minimal non-API surfaces with style consistency per file scope.

## Follow-up
- Open a PR for review.
- Continue Wave 1 with `#2480`.
