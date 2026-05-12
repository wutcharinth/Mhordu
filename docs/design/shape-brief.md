# shape-brief.md · Mhordu — Phase 1 Design Brief

> One-page brief per impeccable's `shape` phase. Read this before any HTML.
> Confirms the brief that drives the seven Phase 1 surfaces.

---

## What we're shaping

**Phase 1 surface set (7 designs):**

1. `01-daily-card.html` — **HERO** · Daily horoscope share card · register B · 3 variations
2. `02-line-rich-menu.html` — LINE rich menu · register B
3. `03-onboarding.html` — Welcome + birth-info flow · register B
4. `04-duang-koo.html` — ดวงคู่ compatibility card · register B · invite mechanic visible
5. `05-paywall.html` — Subscription upsell · register B → A transition
6. `06-web-landing.html` — mhordu.ai landing · register A
7. `07-pricing.html` — Pricing page · register A
8. `index.html` — Gallery of all 7

---

## Goals

### Primary
Lock the dual-register visual system end-to-end on real Thai content, so subsequent build can extend confidently.

### Secondary
Validate Thai typography choices at the artifact sizes that matter (LINE thumbnail 240px, IG Story 1080×1920, BTS-glance 4-second read).

### Tertiary
Surface unknowns about Thai cultural-symbol density, สีมงคล collision, and พี่ voice tone consistency.

---

## Audience (per PRODUCT.md)

- **Primary:** พี่หนิง (22–38, urban Thai woman, BTS-glance reader, IG Story sharer)
- **Secondary:** พี่ตั้ม (35–55, SMB owner, ฤกษ์ business user, trust signal)
- **Tertiary:** น้องบีม (16–22, viral teen, ดวงคู่ engine)

Hero designs (1, 4, 5) optimized for พี่หนิง + น้องบีม. Brand designs (6, 7) optimized for พี่ตั้ม.

---

## The 8-second test

Three scene sentences from PRODUCT.md must pass:

1. ✅ 32yo Thai woman opens daily card on BTS, reads in 4s, screenshots to IG Story
2. ✅ 45yo shop owner lands on mhordu.ai, trusts it in 8s as "the real thing"
3. ✅ 19yo uni student sees ดวงคู่ card, taps "invite my crush" without hesitation

If a design fails any of these, redo.

---

## Constraints

### Hard
- Thai language only (no English in body copy)
- LINE-native dimensions (1080×1920 / 1080×1080 / 2500×1686 / 1024×1024)
- Mobile-first; web designs at 1280–1440 desktop max
- พี่ voice across all copy
- No stock photography (v1)
- No figurative mascot drawing — abstract geometry only
- No Buddha imagery, no monk imagery (year 2+ with advisory)

### Soft
- Should print readably at low DPI (LINE compression)
- Should work in LINE's dark mode where applicable
- Should screenshot well (no animation depended on)

---

## Color strategy commitments

- **Register A — Committed:** indigo `#1B1F3A` carries 30–60% of surface. Cream paper dominates. Gold accent ≤ 10%.
- **Register B — Full palette:** butter / lavender / mint / blush rotate as daily mood backgrounds. Soft black ink. Holographic gold gradient reserved as brand signature (not used everywhere).

---

## Type commitments

| Surface | Display | Body | UI |
|---|---|---|---|
| 01 daily card | Mali 700 | IBM Plex Thai 400 | LINE Seed Sans TH |
| 02 rich menu | Mali 600 | LINE Seed Sans TH 700 | LINE Seed Sans TH |
| 03 onboarding | Mali 600 | IBM Plex Thai 400 | LINE Seed Sans TH |
| 04 ดวงคู่ | Mali 700 | IBM Plex Thai 500 | LINE Seed Sans TH |
| 05 paywall | Mali 600 / Pridi 600 (transition) | IBM Plex Thai 400 | LINE Seed Sans TH |
| 06 web landing | Pridi 600 | Sarabun 400 | LINE Seed Sans TH |
| 07 pricing | Pridi 600 | Sarabun 400 | LINE Seed Sans TH |

All Thai body **line-height ≥ 1.8**.

---

## Motion commitments

- Static screenshots (cards) — no animation, captures must be pixel-static
- Web pages — single page-load orchestration (not per-element micro-animations), 360ms entry, ease-out-quart
- Mascot wobble (B register, web only) — ±2° rotate, 4s infinite, never on cards

---

## Anti-references (re-stated for the brief)

This brief explicitly avoids:
1. Co-Star purple-neon mystic (category default)
2. Generic SaaS hero + glass card grid
3. Sketchy Thai FB banner gradient text
4. ChatGPT-default Material UI
5. Western tarot dark / candle aesthetic
6. Hindu / Vedic / Sanskrit-leaning visuals
7. Casino / lottery gold-glitter
8. Side-stripe colored borders / glassmorphism / gradient text (impeccable absolute bans)

---

## What success looks like

After Phase 1 designs ship:
- A Thai astrology Facebook page admin sees daily card and DMs to ask "ทำเองหรือ?" ("did you make this yourself?") — they thought it was a real product
- A founder of a competing Thai horoscope app sees mhordu.ai and goes quiet for a week
- The Y2K register cards get screenshotted in Thai Twitter/X by users who don't know it's a brand yet — organic share before launch

---

## Out of scope (Phase 1)

- Real LINE bot implementation
- LLM prompt engineering
- Backend / payment integration
- SEO copywriting (placeholder Thai SEO content only)
- Final logo / mascot commission (placeholder v0)
- Photography / illustration (v1 has none)
- Email / push notification design
- Sticker pack (Phase 2 follow-on)

---

## Approval

✅ Direction A + B mix locked (user, 2026-05-12)
✅ พี่ voice locked (user, 2026-05-12)
✅ Full Phase 1 scope locked (user, 2026-05-13)
✅ Abstract geometric mascot locked (user, 2026-05-13)
✅ Location `/Users/oui/Mhordu/docs/design/` locked (user, 2026-05-13)

Build proceeds to craft.
