# TASK-20260302-quickwins-attack-order

## Metadata
- ID: TASK-20260302-quickwins-attack-order
- Status: active
- Priority: high
- Created: 2026-03-02
- Updated: 2026-03-04
- Links (issue/PR/commit):
  - TODO source: https://github.com/users/nesbox/projects/2/views/1
  - Decision: `../../decisions/DEC-20260302-quickwin-selection-and-contributor-constraints.md`

## Context
Prepare a practical sequence for future contribution sessions on TIC-80 project 1.2 TODO items.

## Objective
Define a low-risk, high-throughput order of execution for quick wins, while respecting external contributor permissions.

## Assumptions/Constraints
- We do not have rights to edit `nesbox` project board columns/cards.
- We can contribute via fork + PR workflow.
- Each issue should be handled in a focused conversation/session.
- User-directed override (2026-03-04): treat `#2614` and `#2330` as locally done even if related PRs remain draft/open; revisit only on explicit user request.

## Plan
1. Start with documentation and narrow editor bugs.
2. Continue with Android input fixes.
3. Move to medium enhancement scope.

## In-Progress Board Quick Complexity Scan (2026-03-04)
Source: `https://github.com/users/nesbox/projects/2/views/1` (`In progress` lane).

Inference used to mirror the lane quickly via API: `project:"nesbox/2" is:open assignee:*` (10 items).

### Per-item pre-opinion
- `#2447` (HTML export + MoonScript loading): `M/L` complexity, medium-to-high debug risk.
- `#2876` (third-party license notices/compliance): `M/L` complexity, legal/process-heavy.
- `#2437` (music preview mute channel mismatch): `S/M` complexity; open draft PR exists.
- `#2430` (Raspberry Pi network behavior): `L` complexity, hardware/environment-sensitive.
- `#2157` (how to build on iOS): `M` if doc-only, `L` if implementation.
- `#1948` (Wren `textri` regression): `M/L` complexity, language runtime/API surface.
- `#2257` (shared plugins for languages): `XL` complexity, architecture-scale change.
- `#2325` (`blit` + `ttri` interaction bug): `M/L` complexity, graphics pipeline risk.
- `#2330` (tab-size cursor/selection misalignment): `S/M` complexity, likely localized editor fix.
- `#780` (Sokol renderer migration): `XL` complexity, renderer migration project.

### Practical Fit For External Contributors
- Good near-term candidates: `#2157` (doc-only), `#2325` (only if fast local repro).
- Medium-risk optional: `#1948`, `#2447`.
- Avoid for now (too large/high-risk): `#2257`, `#780`, `#2430`, `#2876`.

## Issue Intelligence Refresh (2026-03-04, no new fetch after scan)
Sources:
- GitHub issue/PR reads done during the same session.
- Local repository checks: `README.md`, `src/studio/studio.c`, `build/html/export.html`.
- Snapshot file: `../../references/open-issues-refresh-2026-03-04.md`.

Actionable candidates confirmed open:
- `#2858` (Arch build docs correction): README lines still show `pacman -S cmake ruby mesa libglvnd glu` without `--needed` and without `ruby-rake`.
- `#2868` (HTML export blur filter): export HTML template in this repo is present and can be changed locally.
- `#2855` (macOS horizontal scroll direction): current code still applies `scrollx *= -1` in `src/studio/studio.c`.
- `#2861` (JS `print(0.5)` crash): open with concrete repro and code pointer.
- `#2742` (Linux install misses language libraries): open with clear build/install repro.

Additional context collected:
- `#2821` is open (Android wireless keyboard arrow behavior).
- Android storage policy cluster remains open (`#2470`, `#2843`, `#2873`) and likely needs broader platform handling.
- Existing wave blockers remain unchanged: `#2388` (website repo absent), `#2301` (low-confidence localized fix path).
- Draft PRs exist for `#2614` (`#2900`) and `#2330` (`#2901`), but local tracking now treats both waves as done unless user revisits.

## Execution
- [x] Wave 1A: `#2478` Document `map` remap callback differences across language bindings. See `../done/TASK-20260302-2478-remap-docs-cross-surface.md`.
- [x] Wave 1B: `#2480` Fix Caps Lock handling for A-F volume/hex input in music editor. See `../done/TASK-20260303-2480-capslock-music-hex.md`.
- [x] Wave 2: `#2439` Fix Android `Ctrl+S` adding extra `s`. See `../done/TASK-20260303-2439-android-ctrl-shortcut-text-guard.md`.
- [x] Wave 3: `#2292` Fix Android arrow keys from external/Bluetooth keyboard. See `../done/TASK-20260303-2292-android-arrow-keys-routing.md`.
- [x] Wave 4: `#2392` Add language/runtime version info to `help version`. See `../done/TASK-20260303-2392-help-version-language-runtimes.md`.
- [x] Wave 5: `#2437` Fix music editor note preview mute channel mismatch. See `../done/TASK-20260303-2437-music-preview-mute-channel.md`.
- [ ] Wave 6: `#2388` Website "play" page alphabetic sorting adjustment. Blocked in `../blocked/TASK-20260303-2388-website-play-alphabetic-sorting.md` (website source not present in this repo).
- [ ] Wave 7: `#2301` `ttri` issue in `export html alone=1`. Blocked in `../blocked/TASK-20260303-2301-ttri-export-html-alone1.md` (low-confidence fix path after investigation).
- [x] Wave 8: `#2614` Keys getting stuck when grabbing the window. See `../done/TASK-20260304-2614-sdl-stuck-keys-window-grab.md` (closed locally by user directive).
- [x] Wave 9: `#2330` Fix tab-aware mouse cursor/selection alignment in code editor. See `../done/TASK-20260304-2330-code-mouse-tab-alignment.md` (closed locally by user directive).

## Verification
- Tests run:
  - To be filled per issue implementation session.
- Results:
  - To be filled per issue implementation session.

## Result
Execution order prepared and linked to backlog/decision records.

## Follow-up
- Track progress per wave in this file.
- Create focused implementation tasks if parallel work starts.
- If maintainers grant project permissions later, revisit board hygiene item (`#2584`) directly.
