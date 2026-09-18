# Coastal Construction Style Reference

Typography, color, footer, and scrollbar system used in `index.html` and `sitemap.html`, adapted from the Roar Media visual-sitemap template (accent color swapped to Coastal Construction's blue).

## Global Colors

- Page background: `#F4F1EA`
- Footer background: `#DCD5C5`
- Footer/socket text: `#1C1E2E`
- Primary dark text: `#1B2A41`
- Secondary muted text: `rgba(27, 42, 65, 0.5)`
- Accent (tag / hover / active): `#2364b0` (brand blue, sampled from the logo)
- Brand green (icon only, not used elsewhere in the UI): `#529636`
- Sitemap scrollbar thumb: `#1C1E2E`
- Sitemap scrollbar track: `rgba(28, 30, 46, 0.12)`

```css
:root {
  --page-bg: #F4F1EA;
  --footer-bg: #DCD5C5;
  --footer-text: #1C1E2E;
}
```

## Fonts

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link
  href="https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;600&family=Instrument+Serif:ital@0;1&family=Newsreader:opsz,wght@6..72,500&family=Hanken+Grotesk:wght@400;500;600;700&display=swap"
  rel="stylesheet">
```

- `Instrument Serif` — editorial headings (hub title, sitemap H1).
- `Instrument Sans` — supporting text, nav labels, legend, footer copy.
- `Newsreader` — root node wordmark on the sitemap tree.
- `Hanken Grotesk` — body font.

## Sitemap Branch Colors

Seven branches, one color theme each (`c-red`, `c-orange`, `c-gold`, `c-green`, `c-teal`, `c-blue`, `c-navy`):

| Branch | Theme |
|---|---|
| Our Company | `c-red` |
| Portfolio | `c-orange` |
| What We Do | `c-gold` |
| Our Commitments | `c-green` |
| Our People & Partners | `c-teal` |
| Contact Us | `c-blue` |
| Footer Utility | `c-navy` |

## Node Types

- `.page-node` (solid border) — a real, primary page.
- `.page-node.sub-page` (dashed border) — a real interior/sub-page reached from the parent page. Only two exist in this sitemap: **Our History/Legacy + Leaders** and **News + Media Kit**, both under Our Company.
- `.section-leaf` — a section that lives on its parent page (not a separate URL), including "— Tabber" modules (in-page tabbed content, e.g. Services, Coastal Way, Join Us).
- `.section-leaf.sub-item` — nested content revealed inside a Tabber section (e.g. the region list under "Where We Are — Tabber").

## Footer System

Same footer treatment across `index.html` and `sitemap.html`:

```html
<footer class="site-footer">
  <div class="site-footer-inner">
    <img class="site-footer-logo" src="./images/rm-logo.svg" alt="Roar Media Logo">
    <p class="site-footer-copy">2026 ROAR MEDIA · ALL RIGHTS RESERVED</p>
  </div>
</footer>
```

- Top padding above logo: `64px`
- Gap between logo and socket text: `30px`
- Bottom padding below socket text: `40px`

## Horizontal Scrollbar (`sitemap.html`)

```css
.scroll-container::-webkit-scrollbar { height: 12px; }
.scroll-container::-webkit-scrollbar-track { background: rgba(28, 30, 46, 0.12); border-radius: 999px; }
.scroll-container::-webkit-scrollbar-thumb { background: #1C1E2E; border-radius: 999px; }
.scroll-container { scrollbar-color: #1C1E2E rgba(28, 30, 46, 0.12); }
```

## Logo Assets

Derived from the client-supplied logo file (`Coastal Construction logo.webp`, white wordmark + color wave icon on transparent background):

- `images/coastal-logo-full.png` — full lockup (icon + white wordmark). Only legible on a dark background, so it's used inside the sitemap's navy `.root-box` chip.
- `images/coastal-icon.png` — icon cropped out on its own (color wave mark, no wordmark). Used in `index.html`'s hub, paired with a navy text wordmark, since the hub sits directly on the light page background.

## Source

Content structure sourced from the client deck "Coastal Construction" (Google Slides, slide titled "Proposed Sitemap V2 — Future State").
