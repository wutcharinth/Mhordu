# brand-spec.md · Mhordu

> Asset registry per huashu-design's "core asset protocol."
> v0 state: Mhordu is a new brand. Logo + mascot + photography do not exist yet.
> This file declares what assets WILL exist, where they live, and what serves as
> v0 placeholder until they're commissioned.

---

## Asset completeness — v0 (current)

| Asset | Status | Path / placeholder |
|---|---|---|
| **Logo · mark** | 🟡 PLACEHOLDER | CSS-rendered abstract mark (lotus + planet) in each design file. To commission month 1. |
| **Logo · wordmark TH** | 🟡 PLACEHOLDER | "มหรดู" typeset in Pridi 600 with manual letter-spacing tweaks. To commission. |
| **Logo · lockup** | 🟡 PLACEHOLDER | Composed inline. To commission. |
| **Mascot (B register)** | 🟢 v1 INTENTIONAL | Abstract geometric crescent + sparkle + dot (per "honest placeholder" rule). Real mascot deferred to month 6+. |
| **Product / UI imagery** | 🟢 N/A | This IS the UI. No external product to photograph. |
| **Founder / team photos** | 🔴 MISSING | Solo founder. To add when team grows. Not on v1 surfaces. |
| **Iconography** | 🟡 INLINE SVG | Custom Thai-mystical iconography (ฤกษ์ wheel, planet glyphs, lotus) — drawn inline in design files. |
| **Photography** | 🔴 NOT USED v1 | Brand intentionally avoids stock photography (AI slop trap). |
| **Color tokens** | 🟢 DOCUMENTED | `DESIGN.md` — all OKLCH-defined |
| **Type stack** | 🟢 DOCUMENTED | `DESIGN.md` — Pridi / Mali / Sarabun / IBM Plex Thai / LINE Seed Sans TH |

🟢 = ready · 🟡 = placeholder, plan to commission · 🔴 = intentionally absent v1

---

## Logo specification

### Mark — concept

**Form:** lotus blossom abstracted into 5 monoline petals, with a circle (planet / cosmic body) overlapping the center-top petal. Single-weight line, no fill.

**Construction grid:** 24×24 unit. Stroke 2 units. Circle Ø 8 units.

**Why this mark:**
- Lotus = Thai cultural anchor, Buddhist resonance without depicting Buddha
- Planet glyph = astrology / cosmic / fortune
- Monoline = works on both registers (premium A reads "refined," playful B reads "kawaii")
- Symmetric, no character = easy to recolor / scale

**v0 inline implementation** (CSS / SVG, present in every design file):
```svg
<svg viewBox="0 0 48 48" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
  <!-- 5 lotus petals -->
  <path d="M24 8 C20 16 20 22 24 26 C28 22 28 16 24 8 Z"/>
  <path d="M10 14 C14 20 18 24 24 26 C20 22 16 16 10 14 Z"/>
  <path d="M38 14 C34 20 30 24 24 26 C28 22 32 16 38 14 Z"/>
  <path d="M6 26 C12 28 18 28 24 26 C18 28 12 32 6 26 Z"/>
  <path d="M42 26 C36 28 30 28 24 26 C30 28 36 32 42 26 Z"/>
  <!-- planet glyph above -->
  <circle cx="24" cy="7" r="3.5"/>
</svg>
```

### Wordmark — "มหรดู"

- Set in **Pridi 600** (display), tracking adjusted manually per glyph pair
- Custom ligature consideration: หร kerning, ดู mai-han-akat stacking
- v1 uses live-typeset Pridi; real custom-drawn wordmark in build-mode month 1

### Lockup

```
[mark]   มหรดู
         mhordu.com
```

Mark height = wordmark cap-height × 1.6. Gap = 0.6 × mark height.

---

## Mascot — abstract geometric placeholder

Per huashu-design's honest-placeholder rule, v1 deliberately uses abstract geometry rather than figurative drawing. Real mascot commissioned month 6 (when first hire = part-time content / design lead).

### Geometric form

```
       ✦  (small star, off-axis)
   ╭───╮
   │  •│   (crescent body + single dot eye)
   ╰───╯
       *   (sparkle accent)
```

- Crescent moon — 60% of mark
- Single circle dot — the "eye," no other facial features
- Star sparkle (orbital element)
- Sparkle accent (mood marker)

### Rendering

- Holographic gradient fill on the crescent (B register only)
- Solid `--b-mark-line` outline on the moon
- Gentle wobble animation (rotate ±2°, 4s ease-in-out infinite) on hero placements only — never on share artifacts (must be static for screenshots)

### Naming
Internal codename: "ดูดู" (doo-doo, short for หมอดู). NOT a public-facing name yet. Real mascot naming is part of month-6 commission brief.

---

## Iconography library

Custom inline SVGs, drawn to match register. All single-stroke (A) or single-fill (B).

| Icon | Use | Approx form |
|---|---|---|
| **ฤกษ์ wheel** | ฤกษ์ดี calendar markers | 8-spoke circle, single-stroke |
| **Planet ☉☽♂♀♃♄** | Thai planetary days | 7 traditional glyphs, monoline |
| **Lotus petal** | Section dividers | Single petal silhouette |
| **Compass star** | Directions (มหาทักษา 8 directions) | 8-point star, single stroke |
| **Day-pip** | Day-of-week markers | 7 colored dots (สีมงคล) |
| **Sparkle ✦** | Mood emphasis (B only) | 4-point star |

All icons live in `assets/icons/*.svg` (when built). v1 inline in design files.

---

## สีมงคล day-of-week color palette

This is **canonical Thai astrology** — must be accurate. Used as colored chips in cards, not as brand colors.

| Day | Thai | Color (canonical) | Hex |
|---|---|---|---|
| อาทิตย์ (Sun) | วันอาทิตย์ | แดง (red) | `#D04545` |
| จันทร์ (Mon) | วันจันทร์ | เหลือง (yellow) | `#F2C94C` |
| อังคาร (Tue) | วันอังคาร | ชมพู (pink) | `#F08AAB` |
| พุธ (Wed กลางวัน) | วันพุธกลางวัน | เขียว (green) | `#5BAE6E` |
| พุธ (Wed กลางคืน) | วันพุธกลางคืน | เทา (gray) | `#8C8C8C` |
| พฤหัสบดี (Thu) | วันพฤหัสบดี | ส้ม (orange) | `#E08545` |
| ศุกร์ (Fri) | วันศุกร์ | ฟ้า (sky blue) | `#5BA8D6` |
| เสาร์ (Sat) | วันเสาร์ | ม่วง (purple) | `#7C5BAE` |

Brand palette **avoids** strong red / yellow / green at saturated levels to prevent visual collision with these meaningful colors when rendered together in a card.

---

## Photography / illustration approach

**v1: no photography.** Anti-slop. No stock photos, no AI-generated lifestyle imagery in v1.

**Imagery uses:**
- Inline SVG iconography (above)
- CSS-rendered illustrations (gradients, geometric forms)
- Mascot (abstract geometric)
- Type as image (large Thai display type as visual element)

**v2 (year 1 month 9+):** commission Thai illustrator for:
- Header artwork on web (mhordu.com about / cultural authority page)
- Sticker pack illustrations
- Mascot final character design

**Never use:**
- Stock astrology imagery (Western zodiac, crystals, candles)
- AI-generated faces (figurative AI slop)
- Generic "mystical hands" stock photos

---

## Font sourcing checklist (build-mode action)

| Font | Source | License | Self-host path |
|---|---|---|---|
| Pridi | https://fonts.google.com/specimen/Pridi | OFL | `assets/fonts/pridi/*.woff2` |
| Mali | https://fonts.google.com/specimen/Mali | OFL | `assets/fonts/mali/*.woff2` |
| Sarabun | https://fonts.google.com/specimen/Sarabun | OFL | `assets/fonts/sarabun/*.woff2` |
| IBM Plex Sans Thai | https://fonts.google.com/specimen/IBM+Plex+Sans+Thai | OFL | `assets/fonts/plex-thai/*.woff2` |
| LINE Seed Sans Thai | https://github.com/line/LINE-Seed-sans-thai | OFL | `assets/fonts/line-seed-th/*.woff2` |
| JetBrains Mono | https://fonts.google.com/specimen/JetBrains+Mono | OFL | `assets/fonts/jetbrains/*.woff2` (numbers only — small subset) |

All OFL licensed. Self-host in production; use Google Fonts CDN in v1 prototypes for speed.
