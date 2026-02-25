# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Long-form marketing/sales page for Digital ONION® (ONION®central.com). Pure HTML5/CSS3 with zero JavaScript dependencies. Deployed via GitHub Pages.

## Development

No build step required. Serve locally with:
```bash
python -m http.server 8000
# or
npx serve .
```

No package manager, test framework, or linting tools are configured.

## Architecture

This is a static site with four key files:

- **index.html** — Long-form scrollable marketing page with semantic HTML5, ARIA labels, and mobile-first responsive markup. Sections: hero, who-its-for, value-prop, testimonials, CTA bands, what-ONION®-is, how-it-works (5 layers), comparison, pricing, FAQ (native `<details>`/`<summary>` accordion), and final CTA.
- **styles.css** — All styling via CSS custom properties, grid layout, `clamp()` fluid typography, glass-morphism cards, sticky header with `backdrop-filter`, and responsive breakpoints at 900px/768px/480px/896px-landscape.
- **404.html** — Custom error page using `.page-centered` + `.glass-card` layout.
- **CNAME** — Custom domain mapping to `ONION®central.com`

## Page Structure

```
<header class="site-header">     — Sticky nav: brand + "How it works" link + primary CTA
<main>
  <section id="hero">             — Big headline, lead, 2 CTAs, tag pills, ONION® graphic
  <section id="who-its-for">      — Audience description + 3 check-mark bullets
  <section id="value-prop">       — "No need to stay stuck" + 4 red-X items
  <section id="testimonials">     — 7 blockquote cards in auto-fit grid
  <section id="cta-band-1">       — "Turn thinking into action" CTA button
  <section id="what-ONION®-is">    — Framework description + "What you get" list
  <section id="how-it-works">     — 5 layer cards (O-N-I-O-N)
  <section id="comparison">       — ChatGPT vs ONION®, 3 "designed for" cards
  <section id="pricing">          — $67/year card, 3-year lock-in, promo code note
  <section id="faq">              — 16 items using native <details>/<summary>
  <section id="final-cta">        — "Early Release — $67/year" + CTA button
</main>
<footer class="site-footer">      — Copyright, Privacy Policy, contact email
```

## CSS Conventions

Theme is defined through CSS custom properties on `:root`:
- `--bg` / `--ink` / `--muted` for base colors
- `--brand` (#7652B0) / `--brand-2` for the purple accent palette
- `--glass-bg` / `--glass-border` for glass-morphism effects
- `--radius`, `--shadow`, `--section-pad` for consistent UI treatment

Key layout classes:
- `.wrap` — max-width 1100px centered container
- `.section` / `.section--alt` / `.section--cta-band` — page sections with alternating backgrounds
- `.glass-card` — reusable glass-morphism card
- `.site-header` — sticky header with backdrop blur

Class naming follows a flat BEM-like pattern (`.btn`, `.btn.primary`, `.btn--lg`, `.layer-card`). Responsive breakpoints at 900px, 768px, 480px, and 896px landscape.

## Key URLs

- **CTA links** → `https://digital.onioncentral.com`
- **Contact email** → `support@onioncentral.com`
