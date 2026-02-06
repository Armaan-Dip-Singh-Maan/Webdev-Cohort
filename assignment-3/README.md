# Assignment 3 – Mintlify-inspired documentation site

A desktop-only, HTML and CSS documentation-style landing page inspired by [mintlify.com](https://mintlify.com). No JavaScript, Tailwind, or animations.

## Sections recreated

1. **Top navigation bar** – Header with logo, nav links (Resources, Company, Documentation, Customers, Blog, Pricing), and CTAs (Contact sales, Start for free).
2. **Hero section** – Headline “The Intelligent Knowledge Platform”, tagline, email input + “Start now” CTA, and hero illustration.
3. **Documentation preview** – Two-column layout: left sidebar (Get started, Organize, Customize, Create content with nested links) and right-hand content with card grid (Quickstart, CLI installation, Web editor, Components).
4. **Trusted by** – Section heading and horizontal row of company names (Anthropic, Coinbase, HubSpot, Zapier, AT&T).
5. **Feature highlights** – Alternating two-column blocks: “Built for the intelligence age”, “Built for both people and AI”, “Self-updating knowledge management”, “Intelligent assistance for your users”.
6. **Intelligent assistant / UI preview** – Section with heading, short description, and large mockup area.
7. **Enterprise features** – Title and intro, then two feature cards (Build with partnership, Compliance and access control).
8. **Case studies** – Card grid with image placeholder, title, excerpt, and “Read story” link (Perplexity, X, Vercel).
9. **Final call-to-action** – Heading “Make documentation your winning advantage” and two buttons (Get started for free, Get a demo).
10. **Footer** – Multi-column links (Product, Resources, Company, Legal) and copyright.

## Fonts and colors

- **Fonts:** [Inter](https://fonts.google.com/specimen/Inter) from Google Fonts for headings and body; fallback system sans-serif.
- **Colors:**
  - Background: `#ffffff`
  - Background subtle: `#f8fafb`
  - Primary text: `#1a1a2e`
  - Secondary text: `#64748b`
  - Accent (mint): `#00c2a8`
  - Border: `#e2e8f0`
  - Button primary: background `#00c2a8`, text white; secondary: transparent with dark border.

## Screenshots

See the `screenshots/` folder for final output captures (optional; add your own screenshots there).

## Live link

If you deploy this folder (e.g. GitHub Pages or Surge), add the live URL here.

## File structure

```
assignment-3/
├── index.html
├── style.css
├── README.md
├── screenshots/
└── assets/
    ├── logo.svg
    └── hero.svg
```

## Running locally

Open `index.html` in a browser, or serve the folder with any static server (e.g. `npx serve .`).
