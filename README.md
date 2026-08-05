# Landing Carlos Esteva

One-page sales landing for Carlos Esteva, an online fitness coach (12+ years of experience, natural bodybuilding pro cards). Target audience: Spanish-speaking men over 30 who want to lose fat with a personalized, contract-guaranteed coaching method. Primary conversion action: WhatsApp contact.

Live: https://fitleads-developers.github.io/landing-carlos-esteva/

## Pages

- `index.html` — the whole landing:
  - Top urgency bar + hero with WhatsApp CTA
  - Vimeo presentation video
  - Pain points ("¿Te suena algo de esto?") + reality band
  - Money-back guarantee section
  - Success-cases carousel (7 before/after photos, horizontal scroll-snap)
  - NO/SÍ qualification cards
  - 4-step process
  - About Carlos + stats
  - 6 five-star reviews
  - FAQ accordion (vanilla JS, one item open at a time)
  - Final CTA + footer + floating WhatsApp button
- `politica-de-privacidad.html` — privacy policy, same text as carlosesteva.es restyled to the landing design
- `aviso-legal.html` — legal notice, same text as carlosesteva.es restyled to the landing design
- `informacion-de-contacto.html` — contact information (name, phone, email, address) in the landing design

## Stack

Static HTML/CSS/JS, no build step. Fonts: Archivo Black + Barlow (Google Fonts). Self-contained (no dependency on the `webs` monorepo `shared/` assets). Deployed by `.github/workflows/deploy.yml` to GitHub Pages on push to `main`.

## Source

Converted from a Claude Design canvas (`Landing Carlos Esteva.dc.html`): the `sc-if`/`sc-for` template blocks and the DCLogic component state were flattened into static markup plus a small vanilla-JS FAQ accordion. Design props (`mostrarVideo`, `botonFlotante`) were baked in with their default value (`true`).

## Images

- `img/caso-1..7.webp` — before/after client photos, resized to 704×880 (2x of the 352×440 display size), WebP q80.
- `img/carlos-esteva.webp` — about-section portrait, 840×840, WebP q80 (sourced from carlosesteva.es).

## Pending

- [ ] Not yet verified in a real browser at 360/768/1280 px — layout is inline-styled with `clamp()`, flex-wrap and auto-fit grids from the design canvas, and media queries were reviewed statically, but do a visual pass after the first deploy.
- [ ] Presentation video stays on Vimeo (external embed, not committed — would bloat the repo).
- [ ] `aviso-legal.html` keeps the original placeholder fields verbatim ("[añadir tu número o CIF…]", "[tu email de contacto profesional]", "[tu dirección fiscal o profesional]") — the source page on carlosesteva.es was never filled in. Ask Carlos for the real data.
- [ ] No analytics/tracking pixel yet.
- [ ] Custom domain not configured (served from github.io).
