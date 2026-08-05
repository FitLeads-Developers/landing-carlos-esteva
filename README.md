# Landing Carlos Esteva

One-page sales landing for Carlos Esteva, an online fitness coach (12+ years of experience, bodybuilding pro cards). His coaching methodology is branded "Método E.S". Target audience: Spanish-speaking men over 30 who want to lose fat with a personalized, contract-guaranteed coaching method. Primary conversion action: WhatsApp contact.

Live: https://fitleads-developers.github.io/landing-carlos-esteva/

## Pages

- `index.html` — the whole landing:
  - Top urgency bar + hero with WhatsApp CTA and portrait photo
  - Vimeo presentation video
  - Pain points ("¿Te suena algo de esto?") + reality band
  - Money-back guarantee section
  - Success-cases carousels (3 rows: fat loss ×18, muscle gain ×7, women ×7; horizontal scroll-snap)
  - NO/SÍ qualification cards
  - 4-step process
  - "Día a día" media section: Método E.S vertical explainer video (phone frame, controls) + 4 muted autoplay loops (leg/biceps/shoulder training, cooking)
  - About Carlos + stats
  - Competition photo strip (Campeonato de España 2026, 6 photos)
  - 6 five-star reviews
  - FAQ accordion (vanilla JS, one item open at a time)
  - Final CTA + footer (with logo) + floating WhatsApp button
- `politica-de-privacidad.html` — privacy policy, same text as carlosesteva.es restyled to the landing design
- `aviso-legal.html` — legal notice, same text as carlosesteva.es restyled to the landing design
- `informacion-de-contacto.html` — contact information (name, phone, email, address) in the landing design

## Stack

Static HTML/CSS/JS, no build step. Fonts: Archivo Black + Barlow (Google Fonts). Self-contained (no dependency on the `webs` monorepo `shared/` assets). Deployed by `.github/workflows/deploy.yml` to GitHub Pages on push to `main`.

## Source

Converted from a Claude Design canvas (`Landing Carlos Esteva.dc.html`): the `sc-if`/`sc-for` template blocks and the DCLogic component state were flattened into static markup plus a small vanilla-JS FAQ accordion. Design props (`mostrarVideo`, `botonFlotante`) were baked in with their default value (`true`).

## Images & video

All optimized derivatives live in `img/` and `video/`; the raw source material the client provides (multi-GB `img/Recursos*`, `img/drive-download-*`, original `.MOV`s) is **gitignored** — only web-ready assets are committed.

- `img/caso-1..7.webp` (women), `img/caso-perdida-1..18.webp` (fat loss), `img/caso-masa-1..7.webp` (muscle gain) — before/after photos, 704×880 (2x of the 352×440 display size), WebP q80.
- `img/carlos-hero.webp` — hero portrait (from client resources), 840×840, WebP q82.
- `img/carlos-about.webp` — about-section photo, 840×840, WebP q82 (sourced from the carlosesteva.es CDN).
- `img/campeonato-1..6.webp` — Campeonato de España 2026 stage photos, 760px tall, WebP q78.
- `img/logo.webp` + `favicon.png` — the "Preparador Físico Carlos Esteva" logo (from client resources); favicon is the logo on a square canvas over the site background color.
- `video/entreno-{pierna,biceps,hombro}.mp4`, `video/nutricion-cocina.mp4` — 10s muted loops cut from the client's `.MOV`s, 720p H.264 CRF28, ~1-3 MB each, with WebP posters.
- `video/correccion-tecnica.mp4` — full "Método E.S" vertical explainer (2:33, with audio), 540×960 H.264 CRF30, ~15 MB, played with controls.

## Pending

- [ ] Not yet verified in a real browser at 360/768/1280 px — layout is inline-styled with `clamp()`, flex-wrap and auto-fit grids from the design canvas, and media queries were reviewed statically, but do a visual pass after the first deploy.
- [ ] Presentation video stays on Vimeo (external embed, not committed — would bloat the repo). The raw client videos (`img/Recursos*`, 100-455 MB `.MOV`s) are gitignored for the same reason; only the compressed cuts in `video/` ship.
- [ ] `aviso-legal.html` keeps the original placeholder fields verbatim ("[añadir tu número o CIF…]", "[tu email de contacto profesional]", "[tu dirección fiscal o profesional]") — the source page on carlosesteva.es was never filled in. Ask Carlos for the real data.
- [ ] No analytics/tracking pixel yet.
- [ ] Custom domain not configured (served from github.io).
