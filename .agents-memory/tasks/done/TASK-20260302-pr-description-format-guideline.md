# TASK-20260302-pr-description-format-guideline

## Metadata
- ID: TASK-20260302-pr-description-format-guideline
- Status: done
- Priority: low
- Created: 2026-03-02
- Updated: 2026-03-02
- Links (issue/PR/commit):
  - Scope file: `../../../AGENTS.md`

## Context
User requested a standard format for PR descriptions with sections `Why`, `What`, and optional `Impact`.

## Objective
Add a clear repository-level instruction in `AGENTS.md` to keep PR descriptions short and consistent.

## Assumptions/Constraints
- Keep the new guidance concise.
- Follow the existing writing style of `AGENTS.md`.

## Plan
1. Add a dedicated section to `AGENTS.md`.
2. Keep section names explicit and brief.
3. Avoid adding unrelated process rules.

## Execution
- [x] Added `PR Description Format` section in `AGENTS.md`.

## Verification
- Tests run:
  - `sed -n '1,260p' AGENTS.md`
- Results:
  - New format guidance is present and unambiguous.

## Result
`AGENTS.md` now documents the expected PR description structure for future requests.

## Follow-up
- Apply this format in upcoming PR descriptions by default.
