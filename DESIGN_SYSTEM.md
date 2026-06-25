# neovie.dev — Design System

Extracted from `index.html` (homepage). Source of truth for any new page on the site.

---

## 1. Brand Foundation

### Colors

| Token | Value | Usage |
|-------|-------|-------|
| `--accent` | `#C9F23C` | Primary accent (lime). CTAs, active nav, highlights, callouts. |
| `--accent-deep` | `#B6E01F` | Deepened accent (computed via `shade(accent, -0.14)`). For filled badges, pill buttons on dark. |
| `--ink` | `#111511` | Primary text. Headlines, body emphasis. |
| Background | `#F4F5F2` | Page background (warm off-white). |
| Surface | `#FFFFFF` | Cards. |
| Surface-muted | `#F4F5F2` | Inner panels, secondary card surfaces. |
| Border | `#E6E8E2` / `#E2E4DE` | Card borders, dividers. |
| Text-muted | `#6E746E` | Body copy, descriptions. |
| Text-soft | `#8A908A` / `#9AA09A` | Subtitles, captions, "decorative" text. |
| Hero-dark | `#13182A → #0C1020 → #0A0D18` | Dark hero gradient (150°). |
| CTA-dark | `#0C0F18` | Black CTA card background. |

### Status Colors (used for risk/level badges)
- Green: `#22C55E` — positive / minimal risk
- Amber: `#F59E0B` — warning / limited risk
- Red: `#EF4444` — danger / high risk
- Black: `#111511` — blocked / forbidden

### Typography

- **Headings**: `Archivo` (Google Fonts) — weights 600, 700, 800, 900
- **Body**: `DM Sans` (Google Fonts) — weights 400, 500, 600, 700
- Always uppercase for H1/H2; tighter letter-spacing (-0.5 to -1.5px).

### Type Scale

| Element | Size (desktop) | Weight | Notes |
|---------|---------------|--------|-------|
| H1 (hero) | 72px | 900 | letter-spacing -1.5px, line-height 0.98 |
| H1 (subpages) | 56–60px | 900 | same as hero |
| H2 (section) | 34–36px | 800 | uppercase, -0.5px |
| H3 (card) | 21–29px | 700 | depends on card size |
| Lead (hero) | 17.5–18px | 400–500 | line-height 1.6, max-width 560–600px |
| Body | 14–15.5px | 400 | line-height 1.55–1.6 |
| Small / caption | 11–13px | 600 | uppercase, letter-spacing 0.5–1.5px |

---

## 2. Layout

- **Page max-width**: `1240px` centered, padding `18px 22px 60px`.
- **Sections**: vertical padding `30–70px` between sections.
- **Grid gap**: `18–22px` for card grids; `44–54px` for two-column content.
- **Border-radius**:
  - Hero / CTA card: `30px`
  - Big section cards: `24–26px`
  - Standard cards: `20px`
  - Small inner cards / badges: `12–16px`
  - Pill / button: `100px` (full radius)

---

## 3. Spacing Tokens (mental scale)

- `4` `8` `11` `14` `18` `22` `26` `30` `36` `44` `50` `60` `70`

---

## 4. Components

### Buttons
- **Primary (accent pill)**: `padding: 11–16px 22–30px`, `border-radius: 100px`, `background: var(--accent)`, `color: #111`, font `Archivo 700 14–15.5px`. Hover: `filter: brightness(1.05)`.
- **Secondary (dark pill)**: `background: rgba(255,255,255,0.08)`, `border: 1px solid rgba(255,255,255,0.22)`, `color: #fff`. Hover: `background: rgba(255,255,255,0.15)`.
- **Outline (light pill)**: `background: #F4F5F2`, `border: 1px solid #E2E4DE`, `color: #111511`. Hover: invert to dark with white text.
- **Text link with arrow**: `→` suffix, font-weight 600–700.

### Badges / Pills
- **Status dot**: 7px circle, pulse animation (`nvPulse`).
- **Section header pill**: `padding: 7px 15px`, `border: 1px solid rgba(201,242,60,0.35)`, `border-radius: 100px`, uppercase 12.5px tracking 1.5px, accent color.
- **Role pill** (in team cards): `padding: 5px 11px`, `border-radius: 100px`, `background: var(--accent)`, 12px uppercase.
- **Numbered step badge**: 42px circle, accent fill, dark text, `Archivo 800 18px`.
- **Risk dot**: 14px circle, color = status.

### Cards
- **Standard**: `background: #fff`, `border: 1px solid #E6E8E2`, `border-radius: 20–24px`, `padding: 28–36px`. Hover: `border-color: #111511; transform: translateY(-3px)`.
- **Numbered list item**: no card, only `border-top: 1px solid #E2E4DE` separator.
- **Highlighted (active/featured)**: `border: 2px solid var(--accent)` plus subtle accent-glow.
- **Dark card** (e.g. stat panel): `background: #13182A` or `#0C0F18`, `color: #fff`.

### Section Header
- H2 (Archivo 800 36px) + subtitle (`#8A908A` 15px) on a flex baseline row, 40–46px bottom margin.

### Icons
- **Inline SVG only**. No emoji, no icon fonts.
- Use **Lucide** (24x24 viewBox, `stroke-width="2"`, `stroke-linecap="round"`, `stroke-linejoin="round"`).
- Embed SVG paths directly in markup. Inherit color from `currentColor` via `stroke="currentColor"`.
- Standard icon container: 40–48px square, `border-radius: 12–14px`, `background: var(--accent)`, dark icon stroke (`#111`).

### Visual Decorations
- Dark hero: 60x60px grid pattern (`rgba(255,255,255,0.04)`), radial fade mask (75% 70% center), top-center green glow (radial-gradient `rgba(201,242,60,0.16)`).
- White cards: optional corner glow (top-right radial-gradient accent at low opacity).
- CTA card (dark): bottom-left green glow.

### Spinning CTA
- 138x138 rotating SVG circle with "GET STARTED · " textPath, center 62px accent circle with `↓` arrow. Spin 16s linear infinite.

### Quote Block
- 96px vertical padding, `max-width: 1000px`. Quote text `DM Sans 500 36px`, line-height 1.32, `text-wrap: balance`. Underneath: 38px accent-deep line + tagline 14px 600.

### Numbered Step Card
- 4-up grid on desktop. 42px accent circle with white number (top). H3 21px + body 14px. Min-height 210px.

### Team Card
- White, 24px radius. Top: 360px image area with colored background (`var(--accent)` or `#fd88b4`) + 20px dot-grid overlay. Bottom: name + role pill + bio + tag pills.

### Stack Card
- White, 26px radius, 50/46 padding. Two-column: title+desc / flex-wrap pills. Pills turn accent on hover.

### Footer (inside dark CTA)
- 4-col grid: brand+tagline / Leistungen / Unternehmen / Kontakt. Bottom row: copyright + tagline separated by top border.

---

## 5. Animations

```css
@keyframes nvSpin  { to { transform: rotate(360deg); } }     /* CTA rotation, 16s */
@keyframes nvPulse { 0%,100% { opacity: .5; } 50% { opacity: 1; } }  /* status dot, 2s */
```

Hover transforms are CSS-only (`transform: translateY(-3px)`, `filter: brightness(...)`).

---

## 6. Responsive

- **Tablet (≤980px)**: hide nav links, reduce H1 to 44–50px, stack 2-col grids, reduce padding.
- **Mobile (≤600px)**: H1 down to 30–34px, all grids 1-col, padding shrinks, border-radius 22px on hero.
- Touch targets ≥ 44x44px.

---

## 7. Iconography (Lucide subset used)

| Concept | Icon |
|---------|------|
| Inventory / list | `clipboard-list` |
| Target / risk classification | `target` |
| Search / gap analysis | `search` |
| Document / governance | `file-text` |
| Lab / fitness check | `flask-conical` |
| Implementation / hands | `handshake` |
| Money / sanctions | `euro` |
| Building / shutdown | `building-2` |
| Trophy / advantage | `trophy` |
| Chart / no surprises | `line-chart` |
| Puzzle / KMU | `puzzle` |
| Trust | `handshake` or `users` |
| Warning | `alert-triangle` |
| External link | `arrow-up-right` |
| Risk — minimal | `shield-check` |
| Risk — limited | `alert-circle` |
| Risk — high | `alert-triangle` |
| Risk — forbidden | `ban` |
| External source | `external-link` |

All Lucide icons: `viewBox="0 0 24 24"`, `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`, `stroke-linecap="round"`, `stroke-linejoin="round"`.

---

## 8. Do's and Don'ts

- ✅ Use the accent pill for primary CTAs.
- ✅ Use the dark card for "shell" sections (CTA, hero).
- ✅ Use the spinning CTA at the end of important flows.
- ✅ All cards on light bg: white surface + `#E6E8E2` border.
- ❌ No emoji as icons — always inline Lucide SVG.
- ❌ No blue/purple generic gradients.
- ❌ No drop-shadows that don't match the soft `0 24px 50px -24px rgba(0,0,0,0.4)` style.
- ❌ No system fonts; always Archivo + DM Sans.
- ❌ No emoji for "live" indicators — use a pulse dot.
