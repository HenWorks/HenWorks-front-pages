---
name: HenWorks
colors:
  surface: '#000000'
  surface-dim: '#000000'
  surface-bright: '#111111'
  surface-container-lowest: '#000000'
  surface-container-low: '#0A0A0A'
  surface-container: '#0A0A0A'
  surface-container-high: '#111111'
  surface-container-highest: '#161616'
  on-surface: '#FFFFFF'
  on-surface-variant: '#888888'
  inverse-surface: '#FFFFFF'
  inverse-on-surface: '#000000'
  outline: '#666666'
  outline-variant: '#262626'
  surface-tint: '#C4212A'
  primary: '#C4212A'
  on-primary: '#FFFFFF'
  primary-container: '#E8333D'
  on-primary-container: '#FFFFFF'
  secondary: '#888888'
  on-secondary: '#000000'
  secondary-container: '#111111'
  on-secondary-container: '#FFFFFF'
  tertiary: '#444444'
  on-tertiary: '#FFFFFF'
  error: '#C4212A'
  on-error: '#FFFFFF'
  background: '#000000'
  on-background: '#FFFFFF'
typography:
  display-lg:
    fontFamily: Inter
    fontSize: 56px
    fontWeight: '600'
    lineHeight: 64px
    letterSpacing: -0.03em
  headline-md:
    fontFamily: Inter
    fontSize: 29px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  title-sm:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  body-base:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 27px
    letterSpacing: '0'
  body-bold:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 22px
    letterSpacing: '0'
  label-caps:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.08em
rounded:
  sm: 0px
  DEFAULT: 0px
  md: 6px
  lg: 8px
  xl: 28px
  full: 9999px
spacing:
  unit: 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 48px
  gutter: 16px
  margin-mobile: 24px
  margin-desktop: 48px
---

# Design System: HenWorks

The public site is a static multi-page site. The brand system lives in `index.html` as CSS custom properties on `:root`. Individual product pages reuse the same black canvas, Inter, and hairline rules, then tell that product’s story. This document is extracted from the homepage, which is the shared brand.

## 1. Visual Theme & Atmosphere

HenWorks presents itself as a night gallery: a pure black field, white type, and almost no color until a moment needs it. The mood is restrained craft rather than a startup gradient. Sections breathe. A product is introduced with a short uppercase label, a tight headline, and a quiet list — then a device frame carries the pictures.

Corners on controls are squared on purpose. The only large radii belong to the phone bezel and small dropdowns. Motion is slow and short: fades, a two-pixel lift on a button, a cross-fade inside a phone. Nothing bounces. The single saturated color, a deep signal red, is rare on the homepage itself; most actions invert to white-on-black. Red is reserved for emphasis, not for every link.

The site is dark by identity, not by a theme toggle. There is no light palette in the homepage tokens. Product pages (TVMate’s newsprint, vibe coding wand’s cyan) sometimes leave this system for a product-specific world. A new page that should feel like henworks.com stays inside these tokens.

## 2. Color Palette & Roles

### Primary Foundation

- **Ink Black** (`#000000`) — page background. The canvas is the brand.
- **Card Black** (`#0A0A0A`) — cards and the product column surface (`--bg-card`).
- **Elevated Black** (`#111111`) — dropdowns, phone chassis, hovered service tiles (`--bg-elevated`).
- **Hairline** (`rgba(255,255,255,0.08)`) — section rules and footer borders (`--border`).
- **Hairline Strong** (`rgba(255,255,255,0.15)`) — control outlines (`--border-strong`).
- **Overlay** (`rgba(255,255,255,0.04)` and `0.08`) — hover fills inside menus.

### Accent & Interactive

- **Signal Red** (`#C4212A`) — brand accent (`--accent`). Used sparingly.
- **Signal Red Hover** (`#E8333D`) — hover of that accent (`--accent-hover`).
- **Inverse Paper** (`#FFFFFF` on `#000000`) — the real primary action. Outlined buttons fill white and turn the label black.

Homepage buttons do not fill with red. Red is a token waiting for a moment that must be seen. Interactive borders must stay visible: a 15% white hairline fails non-text contrast, so controls that are only an outline should step up toward about `#8A8A8A` while decorative rules can stay faint.

### Typography & Text Hierarchy

- **Paper White** (`#FFFFFF`) — headlines and primary labels (`--text-primary`).
- **Ash** (`#888888`) — body, taglines, nav links at rest (`--text-secondary`). On black this clears body-text contrast.
- **Dim Ash** (`#666666`) — meta and footer (`--text-tertiary`). Too faint for small body copy; keep it for non-essential meta or lighten it.
- **Ember** (`#444444`) — large decorative numerals (`--text-light`).

### Functional States

The homepage does not define success, warning, or error tokens. Status is communicated with a five-pixel white dot and an uppercase label (“Now Available”, “Coming Soon”), not with a green pill. Do not invent a status green for HenWorks chrome.

## 3. Typography Rules

### Hierarchy & Weights

The voice is **Inter** for Latin, with **Noto Sans TC / JP / KR / Thai** behind it so CJK and Thai sit in the same line. A second token, `--font-en`, is Inter alone and is used for wordmarks, uppercase labels, and buttons so tracking stays even.

- **Display** — hero, `clamp(2rem, 5vw, 3.5rem)`, weight 600, line-height 1.15, tracking `-0.03em`. Not ultra-bold. The confidence is in the size and the black field.
- **Section title** — `clamp(1.5rem, 3vw, 2.2rem)`, weight 600, tracking `-0.02em`, line-height 1.25. Often breaks onto two lines.
- **Product name** — `clamp(1.3rem, 2.5vw, 1.8rem)`, weight 600, tracking `-0.02em`.
- **Body** — 13–14px, weight 400, line-height about 1.8–1.9. The site reads small and calm, not compact UI.
- **Label** — 10–12px, weight 400–500, uppercase, tracking `0.06em` to `0.1em`. Nav, badges, button text.

### Spacing Principles

Body line-height is generous on purpose. Headlines are tight. Labels are tracked out. Do not mix a third display face into the brand chrome. A product page may keep this scale and simply let the headline grow with `clamp()`.

## 4. Component Stylings

### Buttons

Primary and secondary actions share one shape: no radius, 1px strong hairline, uppercase 12px Inter, tracking `0.08em`, padding about `0.85rem 2rem`. Hover fills the button with white, turns the label black, and lifts it 2px over 0.3–0.4s. There is no filled-red default. A text link in the footer is 11px ash with a color shift on hover, no underline.

### Cards & Service Tiles

Service tiles are square, padding `2.5rem 2rem`, background Card Black, separated by 1px hairline gaps rather than shadows. Hover only lightens the tile to Elevated Black. Product copy sits in a column no wider than about 420px. Icons are 16px line icons inside a 36px square outline, not filled circles.

### Navigation

Fixed to the top. At rest it is transparent; after scroll it becomes `rgba(0,0,0,0.92)` with a 20px blur and a 1px bottom hairline. The wordmark is 14px, weight 600, tracking `0.1em`, uppercase. Links are 12px uppercase ash, turning white on hover. The product menu is a dropdown: Elevated Black, 8px radius, 1px hairline, a small diamond pointer, items with a 32px icon well and a two-line label (name plus 11px caption). Below 768px the bar collapses to a hamburger and a full-width stack. A language menu sits on the right (繁中, English, 日本語, 한국어, ภาษาไทย).

### Inputs & Forms

The homepage has no form controls. The only inputs in the system are language buttons. Treat any new control like a nav button: squared or slightly rounded (6px, as the language items are), hairline border, and a white focus outline. Do not introduce a rounded search pill.

### Product Showcase

The domain component. A two-column grid, copy left, device right, 4rem gap, stacking to one column under 768px with the device first. The phone is 332×520, radius 36px, Elevated Black chassis, deep shadow `0 30px 60px rgba(0,0,0,0.4)`. The screen cross-fades screenshots. A badge above the name is an uppercase outlined label with a 5px dot. Four feature rows use a 14px check icon and 13px ash text. The call to action is the square outline button.

## 5. Layout Principles

### Grid & Structure

Content width for the footer is 1000px. Product showcases run inside the section padding rather than a narrower blog column. The page is a single vertical sequence: hero, marquee, products, services, about, contact, footer. Dividers are inset horizontal rules, not full-bleed color bands.

### Whitespace Strategy

The rhythm is 4px-based but the steps are large: section padding is `8rem 3rem` on desktop and `5rem 1.5rem` under 768px. Gaps inside a product block are 4rem. The page prefers few things with room over a dense dashboard.

### Alignment & Visual Balance

The hero is centered. Product blocks are left-aligned copy beside a centered device. Section labels are small and uppercase above a left-aligned (or centered, for contact) title. Weight sits in the headline and the device, not in decoration.

### Responsive Behavior & Touch

The homepage is desktop-first in its media queries (`max-width: 768px`, then `480px`). New pages that must feel native on a phone should still land on the same breakpoints: one column, 24px side padding, hamburger nav, device scaled down (the homepage phone becomes 258×400). Hit targets for nav rows are the full row, not the glyph.

## 6. Design System Notes for Stitch Generation

### Language to Use

Night gallery, ink black canvas, paper-white type, ash secondary text, hairline borders, squared uppercase buttons that invert to white, slow fades, a phone bezel for product pictures, generous section padding, Inter with Noto for CJK and Thai. Signal red only when something must be found. No glassmorphism, no gradient meshes, no pill buttons on the brand chrome.

### Color References

- Ink Black (`#000000`) for the page background
- Card Black (`#0A0A0A`) for tiles
- Elevated Black (`#111111`) for menus and device frames
- Paper White (`#FFFFFF`) for headlines and the filled hover of a button
- Ash (`#888888`) for body copy
- Signal Red (`#C4212A`) for a rare accent, not for every button

### Component Prompts

- “Sticky navigation bar, transparent until scroll, then a blurred ink-black bar with a hairline. Left: uppercase HenWorks wordmark. Center: uppercase ash links and a product dropdown. Right: a language menu.”
- “Product showcase, two columns. Left: an outlined uppercase badge with a dot, a tight product name, a two-line ash tagline, four checked feature lines, and a squared outline button. Right: a tall phone bezel with a cross-fading screenshot.”
- “Footer, a hairline above, 11px ash, the copyright on the left and a short row of product links on the right.”

### Incremental Iteration

Change one band at a time. Keep the black field and the squared button. If a product’s own screenshots are colorful, let the screenshots carry that color; do not recolor the HenWorks chrome to match the app. Do not add ratings, prices, or store badges the source material does not support.
