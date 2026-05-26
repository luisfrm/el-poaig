# EL POAIG — Design System

## Brand Overview
Premium landing page for **El Mil del Poaig**, world's first organic EVOO from millennial olive trees (1,000–3,000 years old). Limited edition: 615 handmade porcelain olieras, 500ml, €265.

---

## Color Palette

| Token | Hex | Use |
|---|---|---|
| `--gold` | `#C4A265` | Accents, labels, borders, CTAs |
| `--gold-light` | `#D4B878` | Shimmer gradients |
| `--charcoal` | `#1A1A14` | Dark backgrounds |
| `--cream` | `#F7F1E6` | Text on dark, light overlays |
| `--warm-white` | `#FAF8F3` | Light section backgrounds |
| `--olive-dark` | `#3A3A2A` | Intermediate backgrounds (CTA section) |

---

## Typography

### Font Families
- **Playfair Display** (serif, 400/700/900) — Headlines, large numbers, logo
- **IBM Plex Mono** (300/400/500) — Labels, buttons, nav, functional text
- **Cormorant Garamond** (300/400) — Body paragraphs, quotes (italic)
- **Noto Serif/Sans JP** — Loaded only in `index-jp.html` for Japanese

### Type Scale
- Nav links: `10px`, `letter-spacing: 3px`, `text-transform: uppercase`
- Nav logo text: `22px`, `letter-spacing: 6px`
- Nav logo sub: `8px`, `letter-spacing: 6px`, `text-transform: uppercase`
- Hero titles: `clamp(44px, 7vw, 110px)`, Playfair Display 900
- Section headlines: `clamp(36px, 5vw, 64px)`, Playfair Display 900
- Body/quotes: `20-22px`, Cormorant Garamond 300, italic
- Labels: `8-9px`, `letter-spacing: 4-5px`, `text-transform: uppercase`

---

## Spacing & Layout

### Grid & Columns
- Desktop: 2-column product grid, 3-column process/gallery/reviews
- Mobile (< 900px): All grids collapse to 1 column

### Section Padding (desktop)
- Full sections: `220-240px` vertical padding
- Compact sections: `100-140px` vertical padding

### Section Padding (mobile)
- All sections: `120px` top/bottom, `24px` horizontal

---

## Navigation

### Desktop Structure
```
[Philosophy | The Oliera | Process]    EL POAIG    [Reviews | Shop | Store]
                    Millennial Olive Trees
```
- Fixed position, transparent over hero
- Logo centered absolutely
- Two nav-link groups flanking the logo
- On scroll: semi-transparent background with backdrop blur

### Desktop Scrolled State
- Background: `rgba(26, 26, 20, 0.92)`
- `backdrop-filter: blur(16px)`
- Border-bottom: `1px solid rgba(196, 162, 101, 0.08)`
- `min-height: 80px`

### Mobile Structure (CURRENT)
- Logo centered
- Nav links hidden (`display: none`)
- `min-height: 70px`
- `padding: 0 24px`

### Mobile Options (3 variants to test)

**Option A: Horizontal compact row below logo**
```
EL POAIG
Millennial Olive Trees
[Philosophy | Product | Process | Reviews]
```
- Font-size: `9px`
- `letter-spacing: 2px`
- Horizontal scroll if overflow
- All links in one row, centered

**Option B: Hamburger menu**
```
EL POAIG                              [≡]
Millennial Olive Trees
```
- 3-line hamburger icon on right
- Tapping opens full-screen overlay
- Links centered vertically in overlay
- Dark background matching site aesthetic
- Close button or tap outside to dismiss

**Option C: Essential links only**
```
EL POAIG
Millennial Olive Trees
[Philosophy | Product | Shop]
```
- Only 3 key links below logo
- Smaller, more subtle
- Non-essential links removed on mobile

---

## Buttons & CTAs

### Primary Button (`.btn-primary`)
- Background: `--gold`
- Color: `--charcoal`
- Padding: `20px 48px`
- Font: `10px`, `letter-spacing: 3px`, `text-transform: uppercase`, IBM Plex Mono 500
- Border-radius: `2px`
- Hover: background becomes `--cream`, `translateY(-3px)`, golden box-shadow
- Shimmer effect via `::before` pseudo-element

### Discover Link (`.discover-link`)
- Inline-flex with arrow
- Gold color, `10px`, `letter-spacing: 3px`
- Arrow widens on hover

---

## Effects & Atmosphere

### Cinematic Filter
- `.cinematic-wrapper` has CSS filter: `contrast(1.05) saturate(0.88) sepia(0.06) brightness(0.98)`
- Applied to all content except fixed overlays (cursor, grain, vignette)

### Grain Overlay
- Fixed SVG noise texture at `opacity: 0.035`
- Animated position shifts every 0.5s (`steps(1)`)
- Covers `200%` viewport to allow movement

### Vignette
- Fixed radial gradient: transparent center → dark edges
- `z-index: 9997`

### Scroll Progress Bar
- Fixed top, `2px` height, gold gradient
- `z-index: 10001`

### Custom Cursor (desktop only)
- Gold circle `12px` + gold dot `4px`
- Circle expands to `48px` on hover over interactive elements
- Lag-follow via `requestAnimationFrame` lerp (0.12)

---

## Animations

### Reveal on Scroll
- Classes: `.reveal`, `.reveal-left`, `.reveal-right`, `.reveal-scale`
- `IntersectionObserver` with `threshold: 0.15`
- `opacity: 0` + `translateY(50px)` → `opacity: 1` + `translateY(0)`

### Hero Word Stagger
- Each `.word` starts `translateY(120%)` with `opacity: 0`
- Staggered via `transition-delay: 0.4s + i * 0.12s`
- Triggers after loader fades

### Counter Animation
- `IntersectionObserver` at `threshold: 0.5`
- Ease-out-quart: `1 - (1 - progress)^4`
- Duration: 2000ms

### Press Carousel
- Infinite horizontal marquee, `50s` linear
- Pauses on hover
- Edge fade gradients mask the seamless loop

### Gallery Curtain Reveal
- `.img-reveal` scales `scaleX(1 → 0)` from left on scroll
- Uses `cubic-bezier(0.77, 0, 0.175, 1)`

### Shimmer Text
- Gold gradient animation, `4s ease-in-out infinite`
- Applied via `-webkit-background-clip: text`

---

## Components

### Hero Section
- Full viewport height (`100vh` desktop, `100svh` mobile)
- Background video with overlay gradient
- 3-line animated headline
- Badge: "World's First / Millennial EVOO"
- Tagline with CTA link
- Scroll indicator (hidden on mobile)

### Press Carousel
- 14 publication cards, duplicated for seamless loop
- Each card: logo, gold line, quote
- Hover: card scales up, background flips to cream, logo darkens

### Philosophy / Origin Sections
- Light background (`--warm-white`)
- Topographic SVG pattern at `opacity: 0.06`
- Editorial headline with italic gold accents
- Floating images with parallax effect (hidden on mobile)

### Gallery
- 3-column grid
- Image zoom + caption reveal on hover
- Curtain reveal animation on scroll
- `aspect-ratio: 4/3` desktop, `16/9` mobile

### Product Section
- 2-column: product image (left) + info (right)
- Gold corner frames, animated halo glow behind image
- Specification grid (Variety, Vessel, Acidity, Production)
- CTA button → Shopify checkout

### Process Section
- 3-step horizontal layout with connecting line
- Giant gradient numerals (01, 02, 03)
- Engraved/embossed aesthetic

### Counter Section
- 4 stats: 3000 years, 615 olieras, 500ml, 1 of a kind
- Large Playfair Display numerals in gold
- Animated count-up on scroll

### Reviews
- 3-column grid of review cards
- Large decorative quotation mark
- Author + badge below quote
- Hover: subtle lift + border glow

### CTA Section
- Dark olive background
- Shimmering price display
- Guarantee statement with border
- Primary CTA button

### Footer
- Olive branch SVG ornament
- Logo, nav links, copyright
- Compact single-row layout

---

## Responsive Breakpoints

Single breakpoint at **900px**.

### Mobile (< 900px) — What's Hidden
- Custom cursor
- Floating images (philosophy/origin)
- Gold corner frames (product)
- Scroll indicator
- Press quote text (card size reduced)
- Nav links (replaced by hamburger/compact row — pending)

### Mobile (< 900px) — What's Changed
- Nav: compact single-row layout, `min-height: 70px`
- Hero bottom: stacks vertically
- Product grid: 1 column
- Process steps: 1 column, connecting line hidden
- Gallery: 1 column, `aspect-ratio: 16/9`
- Counters: 2×2 grid
- Footer: stacked vertically, centered

---

## File Structure

```
landing-draft-v1/
├── index.html          # English version
├── index-jp.html       # Japanese version
├── requirements/
│   └── spec1.md        # Project specifications
├── logos/              # Press logos (PNG)
├── video-hero-clip.mp4
├── video-cinematic-30s.mp4
└── *.webp              # Client photos
```

Both HTML files share identical CSS structure and classes. Only text content differs by language.

---

## Technical Notes

- Single-file HTML with inline CSS and JS (no build step)
- Google Fonts via CDN
- CSS custom properties for design tokens
- IntersectionObserver for scroll animations
- `requestAnimationFrame` for cursor and counter animations
- Videos: hero freezes on last frame, cinematic loops with fade