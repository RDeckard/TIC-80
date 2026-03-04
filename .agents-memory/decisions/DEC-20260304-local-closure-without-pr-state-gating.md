# DEC-20260304-local-closure-without-pr-state-gating

## Context
Two implementation waves (`#2614`, `#2330`) were functionally completed locally (code changes + build validation), while related PRs remained open in draft state.
User requested to stop tracking draft/open PR state as a blocker for these tasks unless manually revisited later.

## Decision
- Scope: `core`
- Promote-to-core: `yes`

For `#2614` and `#2330` in local memory tracking:
1. Mark tasks/waves as done immediately.
2. Do not block closure on draft/open PR state.
3. Reopen only on explicit user request.

## Rationale
- Matches explicit user workflow preference for this repository memory.
- Avoids repeated churn on already-implemented work.
- Keeps focus on the next actionable issues.

## Alternatives Considered
1. Keep default policy (wait for PR open/ready status gates).
2. Keep tasks in active state until manual validation + PR state transition.

## Consequences
- Short term:
  - Waves 8 and 9 are closed locally.
  - Backlog and active-task surface become cleaner for next issue selection.
- Long term:
  - If policy changes, reopen is explicit and traceable.

## Links
- Parent plan: `../tasks/active/TASK-20260302-quickwins-attack-order.md`
- Done task: `../tasks/done/TASK-20260304-2614-sdl-stuck-keys-window-grab.md`
- Done task: `../tasks/done/TASK-20260304-2330-code-mouse-tab-alignment.md`
