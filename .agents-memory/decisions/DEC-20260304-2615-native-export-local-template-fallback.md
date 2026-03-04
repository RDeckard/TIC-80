# DEC-20260304-2615-native-export-local-template-fallback

## Context
Issue `#2615` indicates PCM is silent in exported native builds. Maintainer feedback attributes this to stale server-side export binaries.

## Decision
- Scope: wave
- Promote-to-core: no

## Rationale
Prefer local executable template for same-platform native export targets (`win`, `linux`, `mac`) before falling back to server templates. This reduces dependency on server freshness for same-platform exports while preserving current behavior for cross-platform exports.

## Alternatives Considered
1. Keep current server-only export flow.
2. Block native export when server binaries are suspected stale.

## Consequences
- Short term:
  - Same-platform native exports are more likely to include current runtime fixes (including PCM behavior).
  - Cross-platform export path remains unchanged.
- Long term:
  - Reduces impact of intermittent server pipeline lag.
  - Does not replace the need for proper server-side artifact refresh.

## Links
- Issue: https://github.com/nesbox/TIC-80/issues/2615
- Task: ../tasks/done/TASK-20260304-2615-native-export-local-template-fallback.md
- Code: ../../src/studio/screens/console.c
