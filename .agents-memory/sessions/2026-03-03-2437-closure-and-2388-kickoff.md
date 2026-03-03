# Session: 2026-03-03 - Close #2437 and start #2388

## Context
User confirmed issue `#2437` is in review and CI is green, and requested immediate transition to the next quick-win task.

## Actions performed
- Moved `TASK-20260303-2437-music-preview-mute-channel.md` from `tasks/active/` to `tasks/done/`.
- Updated `#2437` task metadata/execution/verification to reflect done state and green CI status.
- Updated backlog status (`BL-0007` to done; `BL-0008` to active).
- Updated quick-win wave tracker to mark Wave 5 done and point Wave 6 to a dedicated active task file.
- Created new active task file: `tasks/active/TASK-20260303-2388-website-play-alphabetic-sorting.md`.
- Synced `indexes/wave-index.md` and `indexes/cold-manifest.md`.
- Pulled issue `#2388` context/comments to scope Wave 6 implementation toward alphabetic sorting.

## Decisions made
- Keep Wave 6 scope tight on alphabetic sorting for the play page.
- Defer broader filter/search enhancements to separate issues (`#1575`, `#2415`) as already discussed in issue comments.

## Next steps
- Locate the play-page sorting implementation in the repository.
- Implement a localized alphabetic sorting adjustment.
- Run targeted verification and prepare PR handoff.
