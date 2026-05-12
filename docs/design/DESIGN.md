# DESIGN.md · Mhordu

> Design tokens — dual register (A · Modern Thai Mystical / B · Y2K Mystic Pop).
> All values in OKLCH. Thai-first typography. LINE-native sizing.

---

## Shared system

These cross both registers.

### Logo
- **Mark:** abstract lotus + planet glyph, monoline, single weight
- **Source files** (to be commissioned in build-mode step 1):
  - `assets/logo/mhordu-mark.svg` — symbol only
  - `assets/logo/mhordu-wordmark-th.svg` — หมอดู wordmark, Pridi-derived custom letterforms
  - `assets/logo/mhordu-lockup.svg` — mark + wordmark, horizontal
- **Clearspace:** = mark height on all sides
- **Minimum size:** 24px on screen, 8mm in print

### Thai font stack
All fonts free / open-source. Loaded via Google Fonts and LINE's font CDN.

| Role | Font | Weights | Source |
|---|---|---|---|
| **Display serif** (both registers) | **Pridi** | 200, 300, 400, 500, 600, 700 | Google Fonts (Cadson Demak) |
| **Display rounded** (B only) | **Mali** | 200, 300, 400, 500, 600, 700 | Google Fonts (Cadson Demak) |
| **Body sans** (A) | **Sarabun** | 300, 400, 500, 600, 700 | Google Fonts (Cadson Demak) |
| **Body sans** (B) | **IBM Plex Sans Thai** | 300, 400, 500, 600 | Google Fonts (IBM) |
| **UI sans** (both) | **LINE Seed Sans Thai** | 400, 700, 900 | line-superapp/line-seed-sans-thai (GitHub, OFL) |
| **Numerals (latin)** | **JetBrains Mono** | 400, 500 | Google Fonts — for prices / data only |

### Type rules (Thai-specific)

- **Body line-height ≥ 1.8** (Thai vowel marks need vertical room). Latin default 1.5 will break Thai.
- **No tracking** on Thai body. Tracking breaks vowel-mark positioning.
- **Headlines: line-height 1.3–1.5**, weight 600+.
- **Thai numerals** (๐–๙) only in mystical / spiritual content. Arabic (0–9) for prices, dates, data.
- **Max headline length: 35 Thai characters** (Thai is denser than Latin — overflow at LINE thumbnail).

### Spacing scale
Base unit `4px`. Geometric, not linear.

```
xxs   4   px
xs    8   px
sm   12   px
md   16   px
base 24   px   ← default content gap
lg   32   px
xl   48   px
2xl  72   px
3xl 108   px
4xl 156   px
```

### Border radius
- `xs` 6 (chips)
- `sm` 12 (inputs)
- `md` 20 (cards register A)
- `lg` 32 (cards register B — softer)
- `pill` 999

### Motion
- **Easing default:** `cubic-bezier(0.22, 1, 0.36, 1)` (ease-out-quart)
- **Hover:** 180ms
- **State change:** 240ms
- **Page transition:** 360ms
- **Never animate** width / height / margin (use transform / opacity)
- **No bounce, no elastic** (per impeccable's motion law)
- A register: restrained, single-property fades
- B register: small parallax, gentle wobble (1–2°) on mascot only

---

## Register A · Modern Thai Mystical

**Surfaces:** mhordu.ai landing, pricing, cultural authority, paywall, ฤกษ์ B2B, premium-tier UI.

**Scene sentence:** *32yo Thai woman on BTS, single-glance read, forwards to mom on LINE. Authority, calm, premium.*

### Palette (Committed strategy — one signature color carries 30–60% of surface)

| Token | OKLCH | Hex (approx) | Role |
|---|---|---|---|
| `--a-paper` | `oklch(95% 0.02 80)` | `#F4EFE6` | Background, dominant |
| `--a-paper-warm` | `oklch(93% 0.025 75)` | `#EEE7DA` | Surface variant |
| `--a-ink` | `oklch(22% 0.06 270)` | `#1B1F3A` | Text + logo + signature color |
| `--a-ink-soft` | `oklch(38% 0.055 270)` | `#3A3F5C` | Secondary text |
| `--a-gold` | `oklch(72% 0.13 80)` | `#C9A24D` | Accent ≤10%, ฤกษ์ markers, emphasis |
| `--a-stone` | `oklch(80% 0.01 80)` | `#C8C2B6` | Dividers, subtle UI |
| `--a-blush` | `oklch(88% 0.04 25)` | `#E8D2C9` | Soft warmth, only on portrait sections |

**Forbidden:** pure `#000`, pure `#fff`, any neutral that isn't tinted toward the brand hue 270 or 80.

### Typography (A)

```css
--a-display: 'Pridi', 'Noto Serif Thai', serif;
--a-body:    'Sarabun', 'LINE Seed Sans Thai', sans-serif;
--a-ui:      'LINE Seed Sans Thai', system-ui, sans-serif;
--a-num:     'JetBrains Mono', monospace;
```

Type scale (line-height shown):
| Step | Size | Weight | LH | Use |
|---|---|---|---|---|
| display-xl | 80px | 600 | 1.05 | Hero headline |
| display-lg | 56px | 600 | 1.1 | Section headlines |
| display-md | 40px | 500 | 1.2 | Card titles |
| h1 | 32px | 600 | 1.3 | Page H1 |
| h2 | 24px | 600 | 1.35 | Section H2 |
| body-lg | 19px | 400 | 1.85 | Lead paragraph |
| body | 17px | 400 | 1.85 | Body Thai |
| caption | 14px | 500 | 1.6 | Labels |

### Layout grammar (A)
- Generous whitespace (24–72px gaps)
- Editorial column widths (max ~65 Thai characters)
- Single-column or asymmetric 2-column (no card grids)
- Subtle horizontal rules (1px `--a-stone`), never colored bars
- Type-led hierarchy, no decorative icons

---

## Register B · Y2K Mystic Pop

**Surfaces:** daily horoscope card, ดวงคู่, lucky color tile, sticker pack, all share-optimized.

**Scene sentence:** *19yo uni student screenshots her daily card, drops emoji caption, posts to IG Story before lunch. Playful, viral, daylight-bright.*

### Palette (Full palette strategy — 3–4 named roles, each deliberate)

| Token | OKLCH | Hex (approx) | Role |
|---|---|---|---|
| `--b-butter` | `oklch(92% 0.10 95)` | `#F5E7A8` | Hero background, dominant warm |
| `--b-lavender` | `oklch(82% 0.08 290)` | `#C2B3E2` | Secondary background, cool counterweight |
| `--b-mint` | `oklch(88% 0.09 165)` | `#A8E2C5` | Tertiary background, mood variant |
| `--b-blush` | `oklch(85% 0.10 25)` | `#F0BFB0` | Tertiary background, mood variant |
| `--b-ink` | `oklch(20% 0.005 270)` | `#28282E` | Body text, soft black |
| `--b-ink-soft` | `oklch(45% 0.04 285)` | `#5E5A75` | Secondary text |
| `--b-holo-1` | `oklch(85% 0.10 95)` | — | Gradient stop 1 (holographic gold accent) |
| `--b-holo-2` | `oklch(85% 0.10 195)` | — | Gradient stop 2 |
| `--b-holo-3` | `oklch(85% 0.10 320)` | — | Gradient stop 3 |
| `--b-mark-line` | `oklch(35% 0.06 270)` | `#3A3858` | Mascot line color |

**Holographic gold gradient** (signature element, B-only):
```css
background: conic-gradient(from 220deg at 50% 50%,
  var(--b-holo-1),
  var(--b-holo-2),
  var(--b-holo-3),
  var(--b-holo-1));
```

### Typography (B)

```css
--b-display: 'Mali', 'Pridi', sans-serif;
--b-display-serif: 'Pridi', serif;
--b-body:    'IBM Plex Sans Thai', 'LINE Seed Sans Thai', sans-serif;
--b-ui:      'LINE Seed Sans Thai', system-ui, sans-serif;
```

Type scale:
| Step | Size | Weight | LH | Use |
|---|---|---|---|---|
| story-xl | 120px | 700 | 1.0 | IG Story hero word |
| story-lg | 80px | 600 | 1.1 | IG Story subhead |
| card-lg | 56px | 600 | 1.15 | Card title |
| card-md | 40px | 600 | 1.25 | Card subtitle |
| body-lg | 22px | 500 | 1.8 | Reading text |
| body | 18px | 400 | 1.85 | Card body |
| label | 14px | 700 | 1.5 | UPPERCASE chip labels |

### Mascot — abstract geometry placeholder

The Y2K register includes a mascot system, but **v1 uses abstract geometry**, not figurative drawing (huashu-design honest-placeholder rule). Future revision will commission a real mascot.

Geometric mascot v1:
- **Crescent moon** (60% body)
- **Star sparkle** (orbits around)
- **Single dot** (the "eye" — single circle, no face)
- **Holographic fill** on the crescent
- Optional gentle wobble animation (1–2°, 4s loop)

### Layout grammar (B)
- Larger curves (32px radius default, pill chips)
- Off-grid placement OK (rotated 2–4° elements)
- Color-led mood: same composition, different `--b-*` background = different daily mood
- Type-shaped (Mali rounded headlines feel "warm" — pairs with Thai phonetics)
- IG-Story-shaped artifacts (1080×1920) and LINE-timeline (1080×1080) — both ratios must work

---

## LINE-specific dimensions

| Artifact | Size | Ratio |
|---|---|---|
| Rich menu | 2500 × 1686 px | 1.483 |
| Rich menu (square) | 2500 × 843 px | half height |
| Carousel card image | 1024 × 1024 px (max 1.51:1) | 1:1 typical |
| Image map | 1040 × 1040 px | 1:1 |
| Stickers | 370 × 320 px each | — |
| **Daily share card (IG Story)** | 1080 × 1920 px | 9:16 |
| **Daily share card (LINE timeline)** | 1080 × 1080 px | 1:1 |
| **Daily share card (LINE chat thumb)** | 240 × 240 px equiv | 1:1 thumb test |

All B-register share artifacts MUST render readably at LINE chat thumbnail (240px) and IG Story screen (375pt iPhone).

---

## Accessibility

- Thai text contrast ratio ≥ 4.5:1 against background (WCAG AA)
- Minimum tap target: 44×44pt (iOS / LINE WebView)
- No color-only meaning (lucky color = colored chip + Thai label)
- All emoji replaced with SVG glyphs in shipped cards (LINE / Apple / Google emoji render inconsistently)
- Numbers in pricing: Arabic + Thai both (e.g., `99 บาท / เก้าสิบเก้าบาท`) — Thai for spiritual, Arabic for data

---

## Forbidden across both registers (impeccable's absolute bans)

- ❌ Side-stripe borders (border-left/right >1px as colored accent)
- ❌ Gradient text (`background-clip: text` on gradient)
- ❌ Glassmorphism as default
- ❌ Hero-metric template (big number + label + supporting stats)
- ❌ Identical card grids (icon + heading + text repeated)
- ❌ Modal as first thought (use inline / progressive alternatives)
- ❌ Em dashes in copy
