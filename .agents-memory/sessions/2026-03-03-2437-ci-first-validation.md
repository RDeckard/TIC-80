# Session: 2026-03-03 - #2437 CI-first validation policy

## Context
While implementing issue `#2437`, local build execution was stopped on user request due to workstation performance cost.

## Actions performed
- Implemented localized fix in `src/studio/editors/music.c` (`playNote()` channel selection by active tab).
- Stopped local build-heavy validation flow.
- Recorded a CI-first validation policy decision for this environment.
- Updated active task verification notes to reflect local-skip and CI dependency.

## Decisions made
- Do not run local full builds by default on this workstation.
- Use static/local reasoning checks and rely on CI for full compile/test validation.

## Next steps
- Open/refresh PR for `#2437`.
- Use CI result as authoritative validation signal.
