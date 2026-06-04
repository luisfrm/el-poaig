# AGENTS.md — EL POAIG Landing

## Quick start
```powershell
python3 -m http.server 8090
# http://localhost:8090/index.html     — English
# http://localhost:8090/jp/            — Japanese
# http://localhost:8090/es/            — Spanish
```

## Project structure
Static single-file HTML landing page — **no build step, no dependencies, no CI**.
- `index.html` — English (canonical, latest copy)
- `jp/index.html` — Japanese
- `es/index.html` — Spanish
- Images, videos, logos in project root; SVG icons in `icons/`
- `HANDOFF.md` — full handoff doc (design system, effects, brand intel)
- `requirements/` — spec trackers and status per date

## CRITICAL: Versioning rule
**Never edit an active HTML file in place.** Copy to a new version first:
```powershell
cp index.html index-v{N}.html   # then edit index-v{N}.html
```
Every historical version is kept for rollback. Active files are renamed to plain `index.html` / `jp/index.html` / `es/index.html` after review.

## Language parity
EN → ES/JP copies are **out of sync**. After EN copy changes (25–27 May 2026 spec updates), replicate them in `es/index.html` and `jp/index.html`. Always edit both JP and ES alongside EN unless told otherwise.

## HTML is self-contained
All CSS (custom properties in `:root`) and JS inline. Google Fonts loaded from CDN. No frameworks.

## Video quirks (touch with care)
- **Hero video**: freezes on last frame via `timeupdate` (do NOT use `ended` event — unreliable across browsers).
- **Cinematic video**: JS-driven opacity fade in/out loop.
- Avoid seeking into video with `currentTime` — pre-cut clips with ffmpeg instead.

## CSS filter gotcha
`.cinematic-wrapper` has `filter: ...` which creates a new containing block. Any `position: fixed` elements **inside** it behave like `position: absolute`. Fixed overlays (cursor, grain, vignette, progress bar, loader) are correctly placed **outside** the wrapper — keep them there.

## Available skills
- `.agents/skills/frontend-design/` — for visual/UI/aesthetic work
- `.agents/skills/interface-design/` — for dashboards/tools (mostly not relevant here)

## Key reference
Read `HANDOFF.md` first for design system (colors, typography, effects), brand intel, known issues, and copy rationale.

## Copy conventions
- Olive age range: `1,000 to 3,000 years` (not absolute "3,000")
- Replace "Millennial" → "Millenary" where applicable
- No price visible on page (only on Shopify)
- No green tones — palette is gold, charcoal, cream, warm-white only
