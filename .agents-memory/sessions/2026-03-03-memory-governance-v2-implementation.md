# Session: 2026-03-03 memory governance v2 implementation

## Context
Implemented the approved memory governance plan to reduce default context load.

## Actions performed
- Added `core/` and `indexes/` directories.
- Added `core/loader.md` for default load contract.
- Added `indexes/wave-index.md` and `indexes/cold-manifest.md` for cold retrieval.
- Updated `AGENTS.md`, `structure.md`, README files, and templates.
- Added tracking artifacts (task/backlog/decision/session).

## Decisions made
- Use hot/core/cold memory layers.
- Keep cold history intact (no auto-compaction).
- Keep all memory markdown in English and concise.

## Next steps
- Continue implementation work using hot/core default loading.
- Update indexes at each wave closure.
