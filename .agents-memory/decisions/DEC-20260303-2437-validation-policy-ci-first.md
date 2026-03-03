# DEC-20260303-2437-validation-policy-ci-first

## Context
During issue `#2437` implementation, local full build/checks were started but user requested to stop because local builds are too expensive for this machine.

## Decision
1. Do not run local full builds for this repository by default on this workstation.
2. Prefer targeted static inspection and minimal code diffs locally.
3. Delegate full validation to CI for PR checks.

## Rationale
- Local full builds have high performance cost on this environment.
- CI provides a reproducible and complete validation path for integration.
- For narrow quick-win fixes, constrained local validation plus CI keeps throughput acceptable.

## Alternatives Considered
1. Continue full local builds for every change.
2. Build only selected targets locally on every change.

## Consequences
- Short term:
  - Faster local iteration and lower machine load.
  - Higher dependence on CI turnaround for compile/test confirmation.
- Long term:
  - Requires clear PR notes about what was or was not verified locally.

## Links
- Task: `../tasks/active/TASK-20260303-2437-music-preview-mute-channel.md`
- Issue: https://github.com/nesbox/TIC-80/issues/2437
