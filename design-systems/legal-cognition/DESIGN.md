# Legal Cognition

> Category: Brand
> Imported from a Claude Design export (LC7 codebase). German legal-tech
> platform — AI Assistant, Vault, CLM, Data Rooms, semantic search over
> German law, TipTap notes editor. Use for any Legal Cognition surface;
> works generally as a warm-paper monochrome system with one strong accent.

## Bundled Assets
The system ships with the real LC files alongside this `DESIGN.md`. Reference
them with paths relative to the design-system root.

- `colors_and_type.css` — drop-in stylesheet. All `--lc-*` CSS variables
  plus semantic element styles (`html`, `body`, `h1`–`h4`, `p`, `a`, `hr`).
  Link it once and bare HTML already looks like Legal Cognition:
  `<link rel="stylesheet" href="colors_and_type.css" />`
- `fonts/Hikasami-Regular.woff2` (400) · `Hikasami-Medium.woff2` (500) ·
  `Hikasami-SemiBold.woff2` (600) · `Hikasami-Bold.woff2` (700) ·
  `Hikasami-VF.woff2` (variable, axis 100–900). Already wired up via
  `@font-face` inside `colors_and_type.css`.
- `assets/LC7x.png` — primary wordmark / logo (light surfaces).
- `assets/logo_weiss.png` — wordmark for dark surfaces.
- `assets/madeinger_black.png` / `madeinger_white.png` — Made-in-Germany
  badges. Required when the surface mentions data residency or trust.
- `assets/Icon_free.svg` · `Icon_professional.svg` · `Icon_business.svg` ·
  `Icon_team.svg` · `Icon_enterprise.svg` — bespoke botanical plan icons
  (seed → sprout → canopy → network → stack). **Pricing page only —
  do not reuse elsewhere.**
- `assets/models/claude.svg` · `gemini.svg` · `mistral.svg` ·
  `openai.svg` · `scrivener.svg` — model avatars. Use only when naming
  the corresponding model in an AI-assistant surface.
- `assets/connectors/Dropbox.png` · `SharePoint.png` · `Notion.png` ·
  `GoogleDrive.png` · `OneDrive.png` · `Confluence.svg` — third-party
  integration logos. Use on connector / integrations surfaces only;
  always next to the connector name.

Hikasami is a proprietary brand typeface — do not redistribute these
woff2 files outside this project. The system stack fallback in
`--lc-font-sans` keeps the design legible if the fonts are removed.

## 1. Visual Theme & Atmosphere

Lawyer-calm. Warm paper, deep ink, a single burgundy CTA. Monochrome
ink-on-paper with no ornament. Trust signals (DSGVO, BRAO, ISO 27001,
Made in Germany) are part of the visual rhythm. The whole system is
designed to read like the print of a serious legal periodical that
happens to ship product chrome — not a SaaS landing page.

**Key Characteristics**
- Warm paper background `#FAF9F5` instead of pure white — the entire
  system is warm-shifted toward off-white parchment.
- Deep slate-navy ink `#213547` instead of pure black — softer, more
  literate, less screen-glare.
- One brand accent: burgundy `#66023C`, reserved exclusively for the
  primary CTA. No second accent ever competes with it.
- Hikasami brand sans at weight 400 carries every display surface;
  size, not weight, drives hierarchy. 600 only appears on plan prices.
- 1px borders earn elevation; cards never use box-shadow.
- Sticky header with `backdrop-filter: blur(10px)` over a 90% paper
  fill creates the only "glass" moment in the system.
- Footer is the system's tonal opposite: pure black surface with a
  type-animating tagline **"Recht bekommen."** + Made-in-Germany badge.
- Trust copy and statute citations (§ 43e BRAO, DSGVO, ISO 27001,
  XTS-AES-256, TLS, EWR) are visual elements, not decoration.

## 2. Color Palette & Roles

### Light mode (default — "paper")

| Role | Token | Value | Use |
|---|---|---|---|
| Page background | `--lc-bg` | `#FAF9F5` | Page canvas, header fill at 90% alpha |
| Surface | `--lc-bg-alt` | `#FFFFFF` | Cards, form containers |
| Sunken surface | `--lc-bg-sunken` | `#E8E6E1` | Feature stage backdrops, sections behind cards |
| Lawyer backdrop | `--lc-bg-lawyer` | `#D4D1CB` | Hero portrait / image backdrop |
| Ink (primary text) | `--lc-ink` | `#213547` | Body, headings — deep slate-navy |
| Ink @ 70% | `--lc-ink-2` | `rgba(33, 53, 71, 0.70)` | Secondary text, subtitles |
| Ink @ 50% | `--lc-ink-3` | `rgba(33, 53, 71, 0.50)` | Nav inactive, captions |
| Ink @ 15% | `--lc-ink-4` | `rgba(33, 53, 71, 0.15)` | Dividers on ink surfaces |
| Border | `--lc-border` | `rgba(0, 0, 0, 0.08)` | Cards |
| Border strong | `--lc-border-strong` | `rgba(0, 0, 0, 0.15)` | Inputs, secondary buttons |
| Hairline | `--lc-border-hairline` | `rgba(0, 0, 0, 0.06)` | Header divider |
| Divider | `--lc-divider` | `rgba(0, 0, 0, 0.10)` | Accordion / `hr` |

### Brand & semantic

| Role | Token | Value | Use |
|---|---|---|---|
| Accent | `--lc-burgundy` | `#66023C` | **Primary CTA only** |
| Accent hover | `--lc-burgundy-hover` | `#4F022E` | CTA hover state |
| Accent fg | `--lc-burgundy-fg` | `#FFFFFF` | Label on burgundy fill |
| Success | `--lc-success` | `hsl(147, 99%, 41%)` | Form success, status pill |
| Warn | `--lc-warning` | `hsl(52, 100%, 41%)` | Caution, draft status |
| Danger | `--lc-danger` | `hsl(7, 100%, 54%)` | Destructive |
| Danger soft | `--lc-danger-soft` | `#EF4444` | Form errors |

### Dark mode (`<html data-theme="dark">`)

| Role | Value |
|---|---|
| Background | `#1A1A1A` |
| Surface (alt) | `#000000` |
| Sunken | `#111111` |
| Ink | `#FFFFFF` |
| Ink @ 70% | `rgba(255, 255, 255, 0.70)` |
| Border | `rgba(255, 255, 255, 0.10)` |
| Border strong | `rgba(255, 255, 255, 0.15)` |

### Reserved / scoped

- **Editor-only legacy violet** (`--tt-brand-50` … `--tt-brand-900`,
  canonical `#6229FF`): lives **inside TipTap surfaces only**. Do not
  leak into product chrome, marketing, or decks.
- **Neutral gray scale** (`--lc-gray-50` … `--lc-gray-900`, e.g.
  `rgb(125,127,130)` at 500): used for non-brand UI scaffolding when
  ink-on-paper isn't appropriate (e.g. raw data tables). Prefer ink
  alphas before reaching for grays.

**Rules.** One accent, ever. Burgundy carries the primary CTA and
nothing else. No gradients. No ornamental color. Never pure black on
pure white — the warmth is the brand.

## 3. Typography Rules

### Font stacks

| Role | Token | Stack |
|---|---|---|
| Brand sans | `--lc-font-sans` | `'Hikasami', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif` |
| Display | `--lc-font-display` | `'Hikasami VF', 'Hikasami', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif` (variable cut, axis 100–900) |
| Serif | `--lc-font-serif` | `'New York', ui-serif, Georgia, Cambria, 'Times New Roman', Times, serif` |
| Mono | `--lc-font-mono` | `ui-monospace, SFMono-Regular, 'SF Mono', Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace` |

Hikasami is bundled (Regular 400, Medium 500, SemiBold 600, Bold 700,
plus a variable cut). System stack is the fallback so bare HTML still
reads correctly.

### Size scale

| Token | Size | Use |
|---|---|---|
| `--lc-text-xs` | 13px (`0.8125rem`) | Nav buttons, privacy copy |
| `--lc-text-sm` | 14px (`0.875rem`) | Dropdown titles |
| `--lc-text-base` | 15px (`0.9375rem`) | Body default |
| `--lc-text-md` | 16px (`1rem`) | Nav links |
| `--lc-text-lg` | 18px (`1.125rem`) | Feature / FAQ question |
| `--lc-text-xl` | 24px (`1.5rem`) | Plan name |
| `--lc-text-2xl` | 32px (`2rem`) | Plan price |
| `--lc-text-3xl` | 36px (`2.25rem`) | Section headline |
| `--lc-text-4xl` | 56px (`3.5rem`) | Hero headline |

### Hierarchy

| Role | Font | Size | Weight | Line-height | Tracking | Notes |
|---|---|---|---|---|---|---|
| Hero | display | 56px | 400 | 1.20 | `-0.01em` | Hero statements |
| Section H2 | display | 36px | 400 | 1.25 | `-0.01em` | Centered, `margin: 0 0 1rem` |
| H3 | sans | 24px | 500 | 1.30 | `0` | Card heading, plan name |
| H4 | sans | 18px | 500 | 1.4 | `0` | List heading |
| Plan price | sans | 32px | 600 | 1.2 | `0` | **Only place 600 is allowed** |
| Body | sans | 15px | 400 | 1.6 | `0` | Default at ink-2 (70%) |
| Subtitle | sans | 16px | 400 | 1.6 | `0` | Hero subline at ink-2 |
| Caption | sans | 13px | 400 | 1.5 | `-0.005em` | Footer, metadata, ink-3 |
| Nav link | sans | 16px | 400–500 | 1.0 | `0` | Header desktop |
| Button label | sans | 14–15px | 500 | 1.0 | `0` | Primary + secondary |
| Footer tagline | display | 56–96px | 400 | 1.0 | `-0.01em` | "Recht bekommen." — type-animated |

### Tracking scale

Tighter at display, neutral at body. Map letter-spacing to size, never
the other way around.

| Size | Tracking |
|---|---|
| ≥ 32px | `-0.01em` (`--lc-tracking-tight`) |
| 24–31px | `-0.005em` (`--lc-tracking-snug`) |
| ≤ 18px | `0` (`--lc-tracking-normal`) |

### Weight scale

`400` (regular) · `500` (medium) · `600` (semibold) · `700` (bold,
**banned in product**). The product is almost entirely 400/500. 600
appears only on plan prices. 700 is reserved for `<strong>` inside
running prose.

### Principles

- **Size carries hierarchy**, weight does not. A 56/400 hero next to
  a 36/400 section is the canonical look.
- **No italic**, no all-caps headlines, no display weights ≥ 700.
- **`line-height: 1.6` on body**, `1.2–1.25` on headings — generous
  paragraph rag, tight display rag.
- Code/inline mono uses `0.9em` of the surrounding text.

## 4. Component Stylings

### Buttons

| Variant | Fill | Label | Border | Radius | Padding | Notes |
|---|---|---|---|---|---|---|
| Primary | `#66023C` | `#FFFFFF` | none | 6px (`--lc-radius-sm`) | 10/14px | Burgundy CTA, exactly one per screen |
| Secondary | transparent | ink | `1px solid rgba(0,0,0,0.15)` | 6px | 10/14px | Outline; hover fill `rgba(0,0,0,0.05)` |
| Ghost | transparent | ink @ 70% | none | 6px | 6/12px | Tertiary actions, dismiss |
| Auth pill | `#FFFFFF` | ink | `1px solid rgba(0,0,0,0.15)` | 20px | 6/14px | **Landing only** — only allowed pill |

### Cards

- Background: `#FFFFFF` (`--lc-bg-alt`).
- Border: `1px solid rgba(0,0,0,0.08)` (`--lc-border`).
- Radius: 16px (`--lc-radius-xl`).
- Padding: `2.5rem 2rem`.
- **No shadow.** Elevation comes from the border alone.

### Inputs

- Border: `1px solid rgba(0,0,0,0.15)` (`--lc-border-strong`).
- Radius: 8px (`--lc-radius-md`).
- Padding: 10px vertical.
- Focus ring: ink at full alpha (not burgundy).
- Error state: `--lc-danger-soft` border, message in `--lc-danger`.

### Dropdowns / menus

- Surface inside: 12px radius (`--lc-radius-lg`).
- Panel: 16px radius (`--lc-radius-xl`).
- Shadow: `--lc-shadow-dropdown` = `0 20px 60px rgba(0,0,0,0.08)`.
- Backdrop blur: `--lc-backdrop-menu` = `blur(20px)`.

### Header

- Position: `sticky; top: 0`.
- Background: `--lc-header-bg` = `rgba(250,249,245,0.90)`.
- Backdrop: `--lc-backdrop-header` = `blur(10px)`.
- Bottom border: `--lc-header-border` = `rgba(0,0,0,0.06)`.
- Wordmark left, nav center, primary CTA right.

### Footer

- Surface: pure black (`#000000`).
- Tagline: **"Recht bekommen."** rendered in display font at 56–96px,
  type-animating one character at a time.
- Made-in-Germany badge: `assets/madeinger_white.png`.
- Wordmark: `assets/logo_weiss.png`.

### Links

- Color: ink (`--lc-ink`).
- Decoration: `underline`, 2px offset, 1px thickness.
- Hover: color → `--lc-burgundy`.
- Transition: `--lc-t-default` ease.

### Icons

- **Generic UI:** `lucide-react` at 2px stroke, sizes 14 / 16 / 24px.
  Inherit `currentColor`, never hard-coded.
- **Plan icons:** the bespoke botanical SVG set
  (`assets/Icon_free|professional|business|team|enterprise.svg`).
  Pricing only.
- **Model avatars:** `assets/models/<provider>.svg` only when the
  surface names that model in the AI-assistant context.
- **Connector logos:** `assets/connectors/*.png|svg`, always paired
  with the connector name on integration surfaces.

### Distinctive components

- **Plan card with botanical icon.** White card, 16px radius,
  bordered. Top: botanical SVG (~80×80px). Then plan name (24/500).
  Then plan price (32/600). Then feature list using `✓` plain
  characters. Primary CTA at bottom.
- **AI assistant chat row.** 32×32px model avatar SVG at the left,
  message bubble in `--lc-bg-sunken` with 12px radius, 15/400 body
  in ink. Streaming indicator uses ink @ 50%.
- **Connector grid item.** 1fr column inside a 3–4-column grid, 16px
  radius card. Connector logo at top (centered, ~48×48px), connector
  name (16/500) below, status (13/400 at ink-3) below that.
- **Trust strip.** Single horizontal row in a sunken section,
  separator-spaced text only: `DSGVO  ·  ISO 27001  ·  § 43e BRAO  ·
  XTS-AES-256  ·  Made in Germany`. 13/500 in ink @ 70%.
- **Type-animated footer tagline.** `Recht bekommen.` rendered
  character-by-character with the long transition (`0.3s`) per
  character, ending on the period.

## 5. Layout Principles

### Spacing scale

Base unit `0.25rem` (4px). Hero and section rhythm use rem units.

| Token | Value | Use |
|---|---|---|
| `0.25rem` | 4px | Icon-text micro alignment |
| `0.5rem` | 8px | Inline gap |
| `0.75rem` | 12px | Tight stack inside cards |
| `1rem` | 16px | Default stack |
| `1.5rem` | 24px | Stack between paragraph and CTA |
| `2rem` | 32px | Card horizontal padding, hero column gap base |
| `2.5rem` | 40px | Card vertical padding |
| `4rem` | 64px | Hero column gap |
| `6rem` | 96px | Section vertical rhythm (desktop) |
| `8rem` | 128px | Hero top padding |
| `12rem` | 192px | Hero bottom padding |

### Grid & container

- Max content width: **1280–1400px**.
- Hero: `grid-template-columns: 1fr 1fr; gap: 4rem`.
- Section vertical rhythm: 6rem desktop / 4rem tablet / 3rem phone.
- Hero padding: `8rem 2rem 12rem` desktop.
- Plan grid: 4–5 columns at desktop, 2 at tablet, 1 at phone.

### Border-radius scale

| Token | Value | Use |
|---|---|---|
| `--lc-radius-xxs` | 2px | Fine detail |
| `--lc-radius-xs` | 4px | Inline badges, small chips |
| `--lc-radius-sm` | 6px | **Buttons** (primary + secondary) |
| `--lc-radius-md` | 8px | **Inputs**, plan buttons |
| `--lc-radius-lg` | 12px | Surfaces inside dropdowns |
| `--lc-radius-xl` | 16px | **Cards**, form panels, menu panels |
| (auth pill) | 20px | Landing auth toggle — only fully-rounded element |

No 9999px / full pills. The 20px auth pill is a single named exception.

### Whitespace philosophy

- Whitespace is the dominant separator. Use `hr` only between
  unrelated top-level sections.
- Generous outer margin, dense inner stacks. The page should feel
  spacious; the card should feel composed.
- Section variation comes from background tone shifts (`--lc-bg` →
  `--lc-bg-sunken` → `--lc-bg`), never from harsh dividers.
- The feature video is allowed to break the grid (`width: 183%`).
  Reserved trick — do not reuse for static media.

## 6. Depth & Elevation

| Level | Treatment | Use |
|---|---|---|
| **0 — Flat** | no border, no shadow | Page background, body text |
| **1 — Border** | `1px solid rgba(0,0,0,0.08)` | Default card, plan card, connector tile |
| **1b — Border strong** | `1px solid rgba(0,0,0,0.15)` | Input, secondary button, table rule |
| **2 — Soft small** | `--lc-shadow-sm` = `0 1px 2px rgba(17,24,39,0.04)` | Subtle pop for nested chips |
| **2 — Hover lift (CTA)** | `--lc-shadow-hover` = `0 8px 20px rgba(33,53,71,0.15)` + `translateY(-2px)` | Primary CTA hover only |
| **3 — Dropdown** | `--lc-shadow-dropdown` = `0 20px 60px rgba(0,0,0,0.08)` | Menus, popovers |
| **3 — Modal** | `--lc-shadow-md` (layered ink) | Dialogs, command palettes |

**Philosophy.** Elevation is earned by border, not by shadow. The
only place a shadow is "felt" in the static UI is on the dropdown
menu and on a CTA hover lift — both cases where the surface needs
to read as floating *because the user just summoned it*. Cards do
not float.

No neumorphism. No glassmorphism (the header backdrop blur is the
single sanctioned exception).

## 7. Interaction & Motion

### Hover states

- **Primary CTA:** `opacity: 0.9` + `translateY(-2px)` +
  `box-shadow: --lc-shadow-hover`. Transition `--lc-t-default`.
- **Secondary button:** fill `rgba(0,0,0,0.05)`. Border unchanged.
- **Link:** color → `--lc-burgundy`. Underline persists.
- **Card (interactive):** no shadow change; border darkens to
  `rgba(0,0,0,0.15)` (`--lc-border-strong`).
- **Plan card (selected):** border swaps to `--lc-burgundy` at 1px,
  no fill change.

### Focus states

- Inputs: ring is the ink color, not burgundy. `outline: 2px solid
  --lc-ink` with 2px offset.
- Buttons: same ink outline at 2px offset; primary CTA keeps its
  burgundy fill underneath.
- Never use a cool blue browser-default focus ring — it clashes with
  the warm-paper canvas.

### Transitions

| Token | Duration | Use |
|---|---|---|
| `--lc-t-short` | 0.1s | Tooltip in/out, micro hovers |
| `--lc-t-default` | 0.2s | Color/background hover, button states |
| `--lc-t-long` | 0.3s | Theme toggle (`background-color`, `color`), card border darken |
| `--lc-t-slow` | 0.64s | Type-animated footer tagline per character |

### Easing

- `--lc-ease` = `cubic-bezier(0.46, 0.03, 0.52, 0.96)` — default in/out,
  used for hover and color transitions.
- `--lc-ease-out` = `cubic-bezier(0.65, 0.05, 0.36, 1)` — used for
  enter-from-edge animations (dropdown open, modal lift).

### Motion principles

- No bounce, no spring, no overshoot.
- No staggered choreographed entrance for landing sections — sections
  appear when scrolled into view, but each fades in at the same
  duration with the default ease.
- Theme transitions on `background-color` and `color` use
  `--lc-t-long`, applied to `html` and `body` only — children
  inherit, no per-component fades.

## 8. Voice & Copy

- **German first**, bilingual DE/EN where the brief asks for it.
- Address users **Sie** in product, **du** in landing privacy copy.
- Gender-inclusive colon form: **Kund:innen**, **Dienstleister:innen**.
- Cite statutes literally: **§ 43e BRAO**, **§ 203 StGB**, **DSGVO**,
  **ISO 27001**, **XTS-AES-256**, **TLS**, **EWR**.
- Primary CTA: **"Legal Cognition ausprobieren"**. Secondary: **"Demo
  buchen"**.
- Trust copy is a feature — any surface that touches data must include
  at least one of `DSGVO`, `ISO 27001`, `§ 43e BRAO`, `TLS`,
  `XTS-AES-256`, `EWR`, or `Made in Germany`.
- Short, verb-led, no adjectives. End hero lines with a period.
- Footer tagline is fixed: **"Recht bekommen."** Never localize, never
  rephrase.

## 9. Do's and Don'ts

- ✅ Let whitespace do the work.
- ✅ One accent element per screen — burgundy on the primary CTA, nowhere else.
- ✅ Sentence-case headings.
- ✅ Cards earn elevation from a 1px border, not a shadow.
- ✅ Trust strip on any data-touching surface.
- ❌ No gradients. No textures. No illustrated SaaS characters.
- ❌ No emoji in product UI (internal docs only). The `+` FAQ toggle
  and `✓` pricing check are plain characters, not icons.
- ❌ No headline weights ≥ 700 in product, no italic display, no
  all-caps headlines.
- ❌ No fully-rounded buttons (the 20px landing auth pill is the only
  exception).
- ❌ No second accent color. Burgundy stands alone.
- ❌ No hype copy ("revolutionize", "unleash", "10x"). Lawyer-calm.
- ❌ No cool-blue focus rings. Focus is ink-colored.
- ❌ No reuse of botanical plan icons outside pricing.

## 10. Responsive Behavior

| Breakpoint | Width | Hero | Sections | Type-scale |
|---|---|---|---|---|
| Phone | < 640px | Stacks, padding `4rem 1.5rem 6rem` | 3rem vertical | Hero 56→40px, H2 36→28px |
| Tablet | 640–1023px | Stacks, padding `6rem 2rem 8rem` | 4rem vertical | Hero 56→48px, H2 36→32px |
| Desktop | ≥ 1024px | `1fr 1fr` grid, `gap: 4rem`, padding `8rem 2rem 12rem` | 6rem vertical | Full scale |

### Collapsing strategy

- Header nav: horizontal links at desktop → hamburger at phone; CTA
  collapses to icon-only.
- Plan grid: 4–5 cols → 2 cols → 1 col stacked.
- Connector grid: 4 cols → 3 → 2 → 1.
- Hero `1fr 1fr` becomes single-column with copy on top, image below.
- Footer tagline scales 96 → 72 → 56 → 40px while keeping the
  type-animation timing constant.
- Trust strip wraps onto two lines on phone with the same separator
  rhythm.

## 11. Agent Prompt Guide

### Quick color reference

| Need | Value |
|---|---|
| Page background | `#FAF9F5` (light) / `#1A1A1A` (dark) |
| Card surface | `#FFFFFF` / `#000000` |
| Sunken section | `#E8E6E1` / `#111111` |
| Ink (primary text) | `#213547` / `#FFFFFF` |
| Secondary text | `rgba(33, 53, 71, 0.70)` / `rgba(255,255,255,0.70)` |
| Subtle text / nav inactive | `rgba(33, 53, 71, 0.50)` |
| Card border | `rgba(0, 0, 0, 0.08)` / `rgba(255,255,255,0.10)` |
| Primary CTA fill | `#66023C` |
| Primary CTA hover | `#4F022E` |
| Form error | `#EF4444` |

### Mandatory openers for every artifact

1. Link the drop-in stylesheet **first**:
   `<link rel="stylesheet" href="colors_and_type.css" />`. That alone
   loads every token, the Hikasami `@font-face` rules, and the
   semantic element defaults.
2. Default to light mode. Add `<html data-theme="dark">` only when the
   brief explicitly asks for dark.
3. Reference logos and icons by their bundled paths
   (`assets/LC7x.png`, `assets/Icon_business.svg`, `assets/models/claude.svg`).
   Don't substitute lucide or generic icons for the bespoke
   botanical plan icons.
4. **Never invent hex values.** If the request needs a token outside
   the palette, surface a warning comment in the artifact and use
   the closest existing token.

### Example component prompts

These are the canonical patterns. When the brief asks for one of
these surfaces, mirror these prompts; don't freestyle.

- **Hero (marketing landing).** "Sticky header with `backdrop-filter:
  blur(10px)` over `rgba(250,249,245,0.90)` and a 1px hairline at
  `rgba(0,0,0,0.06)`. Below: `1fr 1fr` grid hero with `gap: 4rem`,
  padding `8rem 2rem 12rem`. Left column: H1 in display font at
  56/400, `letter-spacing: -0.01em`, ink color, ending in a period.
  Subline at 16/400 in ink @ 70%. Two buttons: primary burgundy
  `#66023C` at 6px radius with white label *Legal Cognition
  ausprobieren*, secondary outline at 6px with ink label *Demo
  buchen*. Right column: hero image on `#D4D1CB` backdrop."
- **Plan card with botanical (pricing).** "White card on `#FFFFFF`,
  border `1px solid rgba(0,0,0,0.08)`, 16px radius, padding `2.5rem
  2rem`. Top: `assets/Icon_business.svg` at 80×80px, centered. Plan
  name *Business* in 24/500. Price *€49 / Monat* in 32/600 (the only
  600 in the system). Feature list using plain `✓` characters at
  15/400 in ink @ 70%. Primary CTA fills the bottom: full-width
  burgundy at 6px radius, label *Plan wählen*. **No shadow** — the
  border carries elevation."
- **AI assistant chat row.** "Two-column flex row, gap 12px. Left:
  32×32px `assets/models/claude.svg`. Right: bubble with background
  `#E8E6E1` (`--lc-bg-sunken`), 12px radius, padding `0.75rem 1rem`,
  message at 15/400 in ink. Streaming indicator: three 4px dots at
  `rgba(33,53,71,0.50)` with `--lc-t-default` opacity transition."
- **Connector grid item (integrations page).** "4-column grid at
  desktop. Each tile: white card, 16px radius, `1px solid
  rgba(0,0,0,0.08)`, padding 24px. Connector logo at 48×48px
  centered (e.g. `assets/connectors/Notion.png`). Connector name at
  16/500. Status pill below at 13/400 in ink @ 50% — *Verbunden*
  with a 4px green dot or *Nicht verbunden* with no dot."
- **Trust strip.** "Single horizontal row inside a 3rem-padded
  sunken section (`#E8E6E1`). Six labels separated by middle dots
  with 1.5rem of horizontal space: *DSGVO  ·  ISO 27001  ·  § 43e
  BRAO  ·  XTS-AES-256  ·  TLS  ·  Made in Germany*. All at 13/500
  in ink @ 70%. Centered. No icons — text is the icon."
- **Footer.** "Black surface (`#000000`), full-bleed. Padding 6rem
  vertical. Center: tagline *Recht bekommen.* in display font at
  96/400 white, `letter-spacing: -0.01em`. Animate the characters
  in one by one over `--lc-t-slow` (`0.64s`) per character. Below
  tagline: small row with `assets/logo_weiss.png` left and
  `assets/madeinger_white.png` right. Legal links at 13/400 in
  white @ 70%, separator dots."

### Iteration checklist

1. Did I link `colors_and_type.css`? (No inline `:root` token blocks.)
2. Is there exactly **one** burgundy element on the screen?
3. Are weights 400 / 500 only — except plan price (600)?
4. Are all radii from the scale (2 / 4 / 6 / 8 / 12 / 16 / [20])?
5. Did I default to size-driven hierarchy, not weight?
6. Did I include at least one trust signal on any surface that
   touches data?
7. Is the primary CTA copy German (*Legal Cognition ausprobieren* /
   *Demo buchen*) unless the brief explicitly says otherwise?
8. Do my cards rely on a 1px border for elevation, not a shadow?
9. Did I avoid emoji and pure black/white?
10. If I used a botanical or model SVG, am I in the right context
    (pricing / AI assistant only)?

### Surface-specific guidance

- **Marketing landing.** Model the layout on the LC landing: sticky
  blurred header, hero `1fr 1fr` with one burgundy CTA + outline
  secondary, section H2 centered at 36/400, cards with 16px radius
  and a 1px border (no shadow), trust strip mid-page, black footer
  with *Recht bekommen.*
- **Product chrome (Vault, CLM, Data Rooms, AI Assistant).** Same
  palette, raise density: 14–15px body, 8px input radius, lucide
  icons at 16px, sidebar nav with `--lc-divider` separators, table
  rules at `rgba(0,0,0,0.10)`.
- **Pricing.** Botanical plan card pattern, 4–5 across at desktop,
  trust strip directly below the grid.
- **Decks / pitch.** Hero patterns translate directly to title slides
  (56–72/400 with `-0.01em`, single burgundy accent on a CTA-style
  closing slide). No deck-mode chrome or page numbers — strip down.
