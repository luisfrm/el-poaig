# EL POAIG — Landing Page Handoff

Premium landing page for **El Mil del Poaig**, the world's first organic extra virgin olive oil from millennial olive trees (1,000–3,000 years old). Limited edition: 615 handmade porcelain olieras per season, 500ml, Farga variety, €265.

---

## Quick start

```bash
cd <project-folder>
python3 -m http.server 8090
# Then open:
# http://localhost:8090/index.html        — English
# http://localhost:8090/index-jp.html     — Japanese
```

The page is fully self-contained: HTML + CSS + JS inline in a single file. No build step, no dependencies except Google Fonts (loaded from CDN).

---

## File inventory

### HTML
- `index.html` — English version (latest stable, was index-v31.html)
- `index-jp.html` — Japanese version (latest stable, was index-v31-jp.html)

### Videos
- `video-hero-clip.mp4` (~585KB) — 6-second clip used in the hero section, plays at 0.75x speed and freezes on the last frame
- `video-cinematic-30s.mp4` (~7.3MB) — 30-second clip used in the cinematic section, loops with fade in/out

Both clips were extracted from a longer source video using ffmpeg. The originals are not in the handoff bundle; if you need them ask the client.

### Client photos (gallery and floating images)
- `IMG_6036.webp` — Millennial olive grove of the Maestrat (gallery col 1)
- `2020-10-17_16.02.12_554bea07-41f5-4d7a-a864-122a44915d81.webp` — Traditional harvest (gallery col 2)
- `E84A9270-1_copia_b584fe40-0f49-4b38-b1d6-42c21b720209.webp` — Olives + oil (gallery col 3)
- `EL_MIL1.webp`, `EL_MIL2.webp`, `EL_MIL5.webp` — Product shots (oliera)
- `IMG_0432.webp`, `IMG_0434.webp` — Landscape and harvest details

### Press logos
`logos/*-white.png` — 14 publication logos converted to cream-on-transparent PNGs:
- TIME, The Times, The Independent, Wallpaper*, El Mundo, Food & Wine
- Luhho, Delicatessen, Chic & Tendance, Setrill, Via Gourmet, Sibaritisimo, Delicate, Monkey Zen

The originals were sourced from Wikimedia Commons (the big 6) and from El Poaig's own press page (`elpoaig.com/pages/prensa`) for the niche ones. They were then processed with PIL to recolour dark pixels to cream `#F7F1E6`.

---

## Page structure (top to bottom)

1. **Loader** — Pre-render screen with logo and animated gold line. Fades after `window.load`.
2. **Scroll progress bar** — Thin gold line at the top growing with scroll.
3. **Cursor** — Custom gold circle + dot (desktop only).
4. **Grain overlay** — SVG noise texture for film effect.
5. **Vignette** — Radial darkening at the edges (cinematic).
6. **Nav** — Fixed, transparent over hero, opaque on scroll. Logo centered.
7. **Hero** — `video-hero-clip.mp4` background + 3-line title + bottom badge with edition info + tagline + primary CTA.
8. **Press carousel** — Infinite horizontal marquee with the 14 publication logos. Pauses on hover. Each card hover: scale up + background flips to cream + logo darkens.
9. **Marquee divider** — Gold horizontal text marquee (Millennial Trees · Limited Edition · …).
10. **Philosophy** — Light section with a big editorial headline + subtitle and floating images with parallax. Background SVG topographic pattern.
11. **Gallery** — Three-column grid with the client's own photos. Curtain reveal on scroll, hover zoom + caption.
12. **Origin** — Mirror of philosophy with the Maestrat story.
13. **Cinematic video** — `video-cinematic-30s.mp4` with overlay quote. Fade in/out loop controlled by JS.
14. **Counters** — 4 monumental numbers (3000 · 615 · 500 · 1) animating from 0 on scroll.
15. **Product** — Two-column grid: porcelain oliera with gold corner frame and animated halo glow + spec sheet + buy button.
16. **Process** — Three-step explanation (pruning, harvest, extraction) with engraved giant numerals.
17. **Reviews** — Three customer review cards on dark background.
18. **CTA** — Final call-to-action with big shimmering price.
19. **Footer** — Olive branch SVG ornament + logo + links.

---

## Design system

### Colour palette (CSS custom properties)
| Token | Hex | Use |
|---|---|---|
| `--gold` | `#C4A265` | Accents, labels, borders |
| `--gold-light` | `#D4B878` | Shimmer gradient |
| `--charcoal` | `#1A1A14` | Dark backgrounds |
| `--cream` | `#F7F1E6` | Text on dark, light overlays |
| `--warm-white` | `#FAF8F3` | Light section backgrounds |
| `--olive-dark` | `#3A3A2A` | Intermediate backgrounds (CTA) |
| `--olive-green` | `#6B7B3A` | Italic accents in light sections |

### Typography
- **Playfair Display** (serif, 900) — Headlines, large numbers, logo
- **IBM Plex Mono** (300/400/500) — Labels, buttons, nav, functional text
- **Cormorant Garamond** (300/400) — Body paragraphs, quotes (italic)
- **Noto Serif/Sans JP** — Loaded only in `index-jp.html` for Japanese

### Cinematic filter
A `.cinematic-wrapper` div wraps the entire body content (excluding cursor, grain, vignette and loader) with:
```css
filter: contrast(1.05) saturate(0.88) sepia(0.06) brightness(0.98);
```
plus a fixed radial vignette overlay. This gives the whole site a subtle warm filmic grade.

### Effects already implemented
- Custom gold cursor with hover expansion (desktop only)
- SVG noise grain overlay
- Scroll-triggered reveals (`IntersectionObserver`, `.reveal`, `.reveal-left`, `.reveal-right`)
- Hero word-by-word stagger animation
- Shimmer gradient on key gold text
- Parallax for floating images and the cinematic video
- Gallery curtain reveal (scaleX)
- Counter ease-out-quart animation
- Press carousel infinite marquee with edge fade
- Animated gold halo glow behind the product image
- Olive-branch SVG dividers between sections

---

## Video JS — important context

Both versions have **two videos**, each controlled by a tiny JS block at the bottom of the file. **Touch with care** — the user spent a lot of time getting these to work.

### Hero video (`video-hero-clip.mp4`)
The clip is already pre-cut to the desired range, so the JS only needs to:
1. Slow it to `0.75x`
2. Pause exactly on the last frame using `timeupdate`:
```js
heroVideo.addEventListener('timeupdate', () => {
    if (heroVideo.duration - heroVideo.currentTime < 0.15) {
        heroVideo.pause();
    }
});
```

**History/lessons learned:**
- Earlier versions tried to seek into the full source video to a specific timestamp (`currentTime = 168`). This proved unreliable across browser cache states (worked uncached, raced with `autoplay` when cached). The current solution pre-cuts the clip with ffmpeg so no seeking is needed.
- Do **NOT** use the `ended` event to freeze the frame — some browsers reset `currentTime` to 0 before you can pause. Use `timeupdate` with a small threshold instead.

### Cinematic video (`video-cinematic-30s.mp4`)
JS-driven loop with fade in/out at the boundaries:
```js
cinVideo.addEventListener('timeupdate', () => {
    const t = cinVideo.currentTime;
    if (t < 1.5) cinVideo.style.opacity = Math.min(t / 1.5, 1);
    else if (cinVideo.duration - t < 1.5) cinVideo.style.opacity = Math.max((cinVideo.duration - t) / 1.5, 0);
    else cinVideo.style.opacity = '1';
});
cinVideo.addEventListener('ended', () => {
    cinVideo.currentTime = 0;
    cinVideo.play();
});
```
The opacity transition is set inline on the element: `style="transition: opacity 1.5s ease;"`.

---

## Versioning rule (CRITICAL)

Per the user's repeated and very firm instruction: **never edit the active HTML file in place.** Always copy to a new version first:

```bash
cp index.html index-v32.html   # then edit index-v32.html
```

The handoff bundle contains the latest version renamed to `index.html` / `index-jp.html` for clarity, but in the working folder the user keeps every historical version (`index-v2.html` … `index-v31.html`) so they can compare and roll back. Continue this convention.

---

## Copy notes (from marketing analysis)

The copy was rewritten using frameworks from the user's marketing library skill (Hormozi, Godin, Cialdini, StoryBrand, Dunford). Key principles applied:

- **Hero**: Identity-based positioning à la Godin's *People like us do things like this*. The chosen line is *"You Don't Buy / This Oil. / You're Chosen."* — frames the buyer as the hero, not the product.
- **Press carousel**: Authority signal early in the page (Cialdini principle 4). Uses the actual TIME / The Times / The Independent / Wallpaper* / El Mundo / Food & Wine / + 8 niche food publications that have actually featured the brand.
- **Product section**: Real differentiator is *"the world's first organic EVOO from millennial trees"* + the 11–14% extraction yield (vs industry 20%). Both are surfaced explicitly.
- **CTA**: Has scarcity (615 olieras), urgency ("Few units remaining"), and identity framing ("For those who know that the authentic is never mass-produced").

The Japanese copy is a faithful adaptation, not a literal translation. Niche publication names stay in the Latin alphabet; only the quotes and structural copy were translated.

---

## Brand intelligence

- **Company**: EL POAIG SL, founded 2008 by Joaquim Solano and Manuel Arnau, Valencia, Spain.
- **Revenue**: < €2M/year, 10–49 employees. Small artisan operation.
- **Production**: ~2,000 bottles/year total across 3 products. *El Mil del Poaig* runs 615 units this season (was 223 last season).
- **Real awards (use these — they're verifiable)**: TIME Magazine "100 Best Inventions of the Year" (2008), Flos Olei top 20 oils worldwide. Served by Quique Dacosta (3 Michelin stars), and Michelin-starred restaurants in Tokyo, Hong Kong, Madrid.
- **Digital footprint**: Minimal. ~739 Instagram followers, 46 Facebook likes. Their current Shopify site uses a stock theme. This landing is by far the most premium digital asset they've ever had.
- **Shop URL**: `https://www.elpoaig.com/products/el-mil-02-olive-oil`
- **Price**: €265 (or €290 with personalized olive-wood label)

---

## Known issues and TODOs

- The video-hero-clip + freeze-on-last-frame approach is reliable but the very last frame can flicker for a split second on some browsers when the page first loads from cache. A possible improvement is to fall back to a static `.jpg` poster of the last frame. Not done because of the user's preference to keep the handoff stable.
- The press carousel uses raster PNG logos rather than SVG. The 4 from Wikimedia (TIME, The Times, Wallpaper*, El Mundo) have SVG sources available — if you want razor-sharp logos at any zoom, swap those four `<img>` tags to use the SVGs and recolour the cream via `filter: brightness(0) invert(...)` instead of pre-baking the colour into a PNG.
- The CSS `filter` on `.cinematic-wrapper` creates a new containing block. If you ever add `position: fixed` elements **inside** that wrapper, they'll behave like `position: absolute`. The current fixed elements (cursor, grain, vignette, scroll progress, loader) are correctly placed **outside** the wrapper.
- Mobile (< 900px) is functional but never thoroughly QA'd. It hides the custom cursor, the floating images, the gold corner frames around the product, and the press quote text in the carousel.

---

## How to continue from here

1. Start the Python server (`python3 -m http.server 8090`) and open both versions.
2. Read this document and the original `CLAUDE.md` (if you have it).
3. Before any change: copy `index.html` to `index-v32.html` (or higher), then edit the new file. Same for the JP version.
4. When the user says "make X bigger / change Y / move Z" — they invariably mean *both* the EN and JP files. Do them in parallel.
5. The user values speed, decisiveness and getting it right the first time. They are very vocal when something is broken or sloppy.

Good luck.
