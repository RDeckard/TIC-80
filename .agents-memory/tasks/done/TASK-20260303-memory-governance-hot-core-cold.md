# TASK-20260303-memory-governance-hot-core-cold

## Metadata
- ID: TASK-20260303-memory-governance-hot-core-cold
- Status: done
- Priority: high
- Wave: process
- Created: 2026-03-03
- Updated: 2026-03-03
- Links (issue/PR/commit):
  - Plan conversation: memory governance refinement (hot/core/cold)
  - Depends-On: none

## Context
The memory workspace needed a deterministic default-load model to avoid context overload while preserving full history access.

## Objective
Implement a concise hot/core/cold memory policy, plus indexes for cold retrieval.

## Assumptions/Constraints
- Keep all `.agents-memory/*.md` in English.
- Keep docs concise.
- No automatic physical compaction of cold folders.

## Plan
1. Add core/index directories and files.
2. Update policy docs (`AGENTS.md`, `structure.md`, READMEs, templates).
3. Register the change in backlog and tracking logs.

## Execution
- [x] Create `core/` and `indexes/` files.
- [x] Update policy and structure docs.
- [x] Finalize tracking records and close task.

## Verification
- Tests run:
  - Manual file integrity and link checks.
- Results:
  - Policy files, indexes, and tracking records are aligned.

## Result
Completed.

## Follow-up
- Keep `indexes/wave-index.md` and `indexes/cold-manifest.md` updated when waves close.
