# TASK-20260302-quickwins-attack-order

## Metadata
- ID: TASK-20260302-quickwins-attack-order
- Status: active
- Priority: high
- Created: 2026-03-02
- Updated: 2026-06-12
- Links (issue/PR/commit):
  - TODO source: https://github.com/users/nesbox/projects/2

## Context
Prepare a practical sequence for future contribution iterations on TIC-80 project 1.2 TODO items.

## Objective
Define a low-risk, high-throughput order of execution for quick wins, while respecting external contributor permissions.

## Assumptions/Constraints
- We do not have rights to edit `nesbox` project board columns/cards.
- We can contribute via fork + PR workflow.
- Each issue should be handled in a focused conversation.
- PR status refresh (2026-06-11): tracked RDeckard PRs `#2894` through `#2903` are merged; only `#2916` remains open and has comments to address in a separate follow-up.
- Follow-up issue `#2940` is linked to merged PR `#2901` / issue `#2330`.

## Plan
1. Start with documentation and narrow editor bugs.
2. Continue with Android input fixes.
3. Move to medium enhancement scope.

## In-Progress Board Quick Complexity Scan (2026-03-04)
Source: `https://github.com/users/nesbox/projects/2` (`In progress` lane).

Inference used to mirror the lane quickly via API: `project:"nesbox/2" is:open assignee:*` (10 items).

### Per-item pre-opinion
- `#2447` (HTML export + MoonScript loading): `M/L` complexity, medium-to-high debug risk.
- `#2876` (third-party license notices/compliance): `M/L` complexity, legal/process-heavy.
- `#2437` (music preview mute channel mismatch): completed; PR `#2899` merged 2026-03-12.
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

## Execution
- [x] Wave 1A: `#2478` Document `map` remap callback differences across language bindings. See `../done/TASK-20260302-2478-remap-docs-cross-surface.md`.
- [x] Wave 1B: `#2480` Fix Caps Lock handling for A-F volume/hex input in music editor. See `../done/TASK-20260303-2480-capslock-music-hex.md`.
- [x] Wave 2: `#2439` Fix Android `Ctrl+S` adding extra `s`. See `../done/TASK-20260303-2439-android-ctrl-shortcut-text-guard.md`.
- [x] Wave 3: `#2292` Fix Android arrow keys from external/Bluetooth keyboard. See `../done/TASK-20260303-2292-android-arrow-keys-routing.md`.
- [x] Wave 4: `#2392` Add language/runtime version info to `help version`. See `../done/TASK-20260303-2392-help-version-language-runtimes.md` (PR `#2898` merged 2026-03-12).
- [x] Wave 5: `#2437` Fix music editor note preview mute channel mismatch. See `../done/TASK-20260303-2437-music-preview-mute-channel.md` (PR `#2899` merged 2026-03-12).
- [ ] Wave 6: `#2388` Website "play" page alphabetic sorting adjustment. Blocked in `../blocked/TASK-20260303-2388-website-play-alphabetic-sorting.md` (website source not present in this repo).
- [ ] Wave 7: `#2301` `ttri` issue in `export html alone=1`. Blocked in `../blocked/TASK-20260303-2301-ttri-export-html-alone1.md` (low-confidence fix path after investigation).
- [x] Wave 8: `#2614` Keys getting stuck when grabbing the window. See `../done/TASK-20260304-2614-sdl-stuck-keys-window-grab.md` (PR `#2900` merged 2026-03-12).
- [x] Wave 9: `#2330` Fix tab-aware mouse cursor/selection alignment in code editor. See `../done/TASK-20260304-2330-code-mouse-tab-alignment.md` (PR `#2901` merged 2026-05-04; follow-up `#2940` open).
- [x] Wave 10: `#2615` Mitigate stale native export template risk via local-template fallback. See `../done/TASK-20260304-2615-native-export-local-template-fallback.md` (PR `#2916` open; comments to address later).
- [x] Wave 11: `#2855` Fix macOS horizontal scroll direction by scoping `scrollx` inversion to non-macOS builds. See `../done/TASK-20260304-2855-macos-horizontal-scroll-direction.md` (PR `#2903` merged 2026-05-04).
- [x] Wave 12: `#2940` Fix tab width handling after horizontal scroll in the code editor. See `../done/TASK-20260612-2940-code-tab-scroll-mapping.md` (PR `#2957` open from branch `fix/2940-code-tab-scroll-mapping`).

## Verification
- Tests run:
  - To be filled per issue implementation.
- Results:
  - To be filled per issue implementation.

## Result
Execution order prepared and linked to backlog records.

## Follow-up
- Track progress per wave in this file.
- Create focused implementation tasks if parallel work starts.
- If maintainers grant project permissions later, revisit board hygiene item (`#2584`) directly.
