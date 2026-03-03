# DEC-20260303-memory-governance-hot-core-cold

## Context
Memory usage had to avoid default overloading while preserving access to historical records.

## Decision
- Scope: core
- Promote-to-core: yes

Adopt a three-layer memory model:
1. hot: `backlog` + `tasks/active`
2. core: always-loaded transverse rules under `core/`
3. cold: `tasks/done`, `decisions`, `sessions`, `references` via indexes only

Additional rules:
- No automatic cold compaction.
- All `.agents-memory/*.md` stay in English and concise.
- Wave closure = tasks `done|blocked` + PR open/ready.

## Rationale
This gives deterministic low-context startup and explicit cold retrieval.

## Alternatives Considered
1. Full exhaustive loading each conversation.
2. Time-window loading (e.g., last 14/30 days).

## Consequences
- Short term:
  - Smaller default context and faster startup.
- Long term:
  - Better scalability without losing history.

## Links
- `../core/loader.md`
- `../indexes/wave-index.md`
- `../indexes/cold-manifest.md`
