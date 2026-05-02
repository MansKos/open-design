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

## Visual Theme & Atmosphere
Lawyer-calm. Warm paper, deep ink, a single burgundy CTA. Monochrome
ink-on-paper with no ornament. Trust signals (DSGVO, BRAO, ISO 27001,
Made in Germany) are part of the visual rhythm. No gradients, no
illustrated SaaS characters, no hype.

## Color Palette & Roles
Light mode (default — "paper"):
- **Background:** `#FAF9F5` (warm off-white)
- **Surface:** `#FFFFFF` (cards, form containers)
- **Sunken surface:** `#E8E6E1` (feature stage backdrops)
- **Foreground / ink:** `#213547` (deep slate-navy, never pure black)
- **Muted (ink @ 70%):** `rgba(33, 53, 71, 0.70)` — secondary text
- **Subtle (ink @ 50%):** `rgba(33, 53, 71, 0.50)` — nav inactive, captions
- **Border:** `rgba(0, 0, 0, 0.08)` — cards
- **Border strong:** `rgba(0, 0, 0, 0.15)` — inputs, secondary buttons
- **Hairline:** `rgba(0, 0, 0, 0.06)` — header divider
- **Accent (burgundy):** `#66023C` — primary CTA only
- **Accent hover:** `#4F022E`
- **Accent fg:** `#FFFFFF`
- **Success:** `hsl(147, 99%, 41%)`, **Warn:** `hsl(52, 100%, 41%)`,
  **Danger:** `hsl(7, 100%, 54%)`

Dark mode (`<html data-theme="dark">`):
- **Background:** `#1A1A1A`, **Surface (alt):** `#000000`,
  **Sunken:** `#111111`
- **Ink:** `#FFFFFF`, muted `rgba(255,255,255,0.70)`
- **Border:** `rgba(255, 255, 255, 0.10)`

Rules: **one** accent. Burgundy is reserved for the primary CTA.
No gradients. No ornamental color. Editor-only legacy violet
(`#6229FF`, `--tt-brand-500`) lives inside TipTap surfaces and must
not leak into product chrome.

## Typography Rules
- **Brand sans:** `'Hikasami', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif`
- **Display:** `'Hikasami VF', 'Hikasami', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif` (variable cut, weight axis 100–900)
- **Serif fallback:** `'New York', ui-serif, Georgia, Cambria, serif`
- **Mono:** `ui-monospace, SFMono-Regular, 'SF Mono', Menlo, Consolas, monospace`
- Hikasami is bundled (Regular 400, Medium 500, SemiBold 600, Bold 700,
  plus a variable cut). System stack is the fallback so bare HTML
  still looks correct.
- Scale (px): 13 · 14 · 15 (body default) · 16 · 18 · 24 · 32 · 36 · 56
- **Hero headline:** 56px / weight 400 / `letter-spacing: -0.01em` / `line-height: 1.2`
- **Section H2:** 36px / weight 400 / centered / `line-height: 1.25`
- **H3:** 24px / weight 500
- **Body:** 15px / `line-height: 1.6` at ink-2 (70% ink)
- Weights stay at **400 / 500 / 600**. 600 only on plan prices. 700+ banned.
- No italic. No all-caps headlines. Size carries hierarchy, weight does not.

## Component Stylings
- **Buttons (primary):** burgundy fill, white label, **6px radius**,
  hover = `opacity: 0.9` + `translateY(-2px)` + `box-shadow: 0 8px 20px rgba(33,53,71,0.15)`.
- **Buttons (secondary):** transparent fill, `1px solid rgba(0,0,0,0.15)` border,
  hover = `rgba(0,0,0,0.05)` fill. Same 6px radius.
- **Buttons (auth pill — landing only):** 20px radius — only allowed pill in the system.
- **Cards:** `background: #FFF`, `border: 1px solid rgba(0,0,0,0.08)`,
  `border-radius: 16px`, padding `2.5rem 2rem`. **No shadow** —
  elevation comes from the border.
- **Inputs:** 1px border `rgba(0,0,0,0.15)`, **8px radius**, 10px
  vertical padding, focus ring uses ink (not burgundy).
- **Dropdowns / menus:** 12px radius surface inside, panel at 16px,
  `box-shadow: 0 20px 60px rgba(0,0,0,0.08)`.
- **Links:** ink color, `text-decoration: underline`, 2px offset, 1px
  thickness; hover swaps to burgundy.
- **Header:** sticky, `backdrop-filter: blur(10px)` over `rgba(250,249,245,0.90)`.
- **Footer:** black background, type-animating tagline **"Recht bekommen."**,
  Made-in-Germany badge.
- **Icons:** `lucide-react` at 2px stroke, sizes 14 / 16 / 24 px,
  inherit `currentColor`. **Plan icons** are the bespoke botanical
  SVG set (seed/sprout/canopy/network/stack) — pricing only.

## Layout Principles
- Max content width **1280–1400px**.
- Section vertical rhythm: **6rem** desktop.
- Hero padding: **`8rem 2rem 12rem`**.
- Landing hero: `1fr 1fr` grid, `gap: 4rem`.
- Generous whitespace is the main separator; dividers (`hr`) only
  between unrelated top-level sections.
- Feature video may deliberately break the grid (`width: 183%`) —
  reserved trick, do not reuse for static media.

## Depth & Elevation
- Cards: **flat**, border-only.
- Hover lift on primary CTA: 2px y-offset + soft ink-tinted shadow.
- Dropdowns / menus: `0 20px 60px rgba(0,0,0,0.08)` (light) /
  `0 20px 60px rgba(0,0,0,0.30)` (dark).
- No neumorphism, no glassmorphism (except header backdrop blur).

## Motion
- Durations: `0.1s` (short), `0.2s` (default), `0.3s` (long), `0.64s` (slow).
- Default ease: `cubic-bezier(0.46, 0.03, 0.52, 0.96)`.
- Ease-out: `cubic-bezier(0.65, 0.05, 0.36, 1)`.
- Theme transitions on `background-color` and `color` use the long
  duration. No bounce. No spring. No staggered entrance choreography.

## Voice & Copy
- **German first**, bilingual DE/EN where the brief asks for it.
- Address users **Sie** in product, **du** in landing privacy copy.
- Gender-inclusive colon form: **Kund:innen**, **Dienstleister:innen**.
- Cite statutes literally: **§ 43e BRAO**, **§ 203 StGB**, **DSGVO**, **ISO 27001**.
- Primary CTA: **"Legal Cognition ausprobieren"**. Secondary: **"Demo buchen"**.
- Trust copy is a feature — any surface that touches data must include
  at least one of `DSGVO`, `ISO 27001`, `§ 43e BRAO`, `TLS`,
  `XTS-AES-256`, `EWR`, or `Made in Germany`.
- Short, verb-led, no adjectives. End hero lines with a period.

## Do's and Don'ts
- ✅ Let whitespace do the work.
- ✅ One accent element per screen — burgundy on the primary CTA, nowhere else.
- ✅ Sentence-case headings.
- ✅ Cards earn elevation from a 1px border, not a shadow.
- ❌ No gradients. No textures. No illustrated SaaS characters.
- ❌ No emoji in product UI (internal docs only). The `+` FAQ toggle and `✓`
  pricing check are plain characters, not icons.
- ❌ No headline weights ≥ 700, no italic display, no all-caps headlines.
- ❌ No fully rounded buttons (the 20px landing auth pill is the only exception).
- ❌ No second accent color. Burgundy stands alone.
- ❌ No hype copy ("revolutionize", "unleash", "10x"). Lawyer-calm.

## Responsive Behavior
- Desktop ≥ 1024px: full `1fr 1fr` hero, 1280–1400px cap, 6rem section spacing.
- Tablet 640–1023px: hero stacks, sections 4rem.
- Phone < 640px: hero stacks, sections 3rem, hero font scales 56→40px,
  section H2 36→28px.

## Agent Prompt Guide
- **Start every artifact** by linking the drop-in stylesheet:
  `<link rel="stylesheet" href="colors_and_type.css" />`. That gets you
  the full token set, the `@font-face` declarations for Hikasami, and
  the semantic element styles in one line — never re-author them inline.
- Pull every color and font value from this file. **Never invent hexes.**
  Burgundy is `#66023C`; paper is `#FAF9F5`; ink is `#213547`. If the
  request needs a token outside the palette, surface a warning comment
  in the artifact and use the closest existing one.
- Reference logos and icons by their bundled paths (`assets/LC7x.png`,
  `assets/Icon_business.svg`, etc.). Don't substitute lucide or other
  generic icons for the bespoke botanical plan icons.
- Default to light mode. Add `<html data-theme="dark">` only when the
  brief explicitly asks for dark.
- For marketing surfaces, model the layout on the LC landing: sticky
  blurred header, hero `1fr 1fr` with one burgundy CTA + outline
  secondary, section H2 centered at 36px/400, cards with 16px radius
  and a 1px border (no shadow), black footer with "Recht bekommen."
- For product chrome (Vault, CLM, Data Rooms, AI Assistant), keep the
  same palette but raise density: 14–15px body, 8px input radius,
  lucide icons at 16px.
- Always emit at least one trust signal where the surface handles data.
- Default copy is German. If the brief is in English, mirror with a
  short German subline on hero and CTAs.
