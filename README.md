# VisionCable Supply — B2B Cable & Connector Website

A bilingual (English / Chinese) B2B website for sourcing industrial cables and connectors — MIPI CSI-2, M12, GMSL, industrial Ethernet — built for robotics, machine vision, and automation applications.

Built with [Astro](https://astro.build/), zero-JS by default, deployed as a static site.

## Features

- **B2B product catalog** — MIPI cables, M12 connectors, GMSL cables, custom assemblies
- **Detailed spec pages** — full technical parameters, selection guides, application notes
- **SEO blog** — 3 in-depth technical articles for content-driven lead generation
- **Bilingual (EN/ZH)** — client-side language switcher with localStorage persistence
- **Inquiry form** — contact form for quote requests
- **Responsive design** — works on mobile, tablet, and desktop
- **Zero runtime JS** — ships as pure HTML/CSS, only the i18n switcher adds ~2KB JS

## Tech Stack

| Tool | Purpose |
|------|---------|
| [Astro 5](https://astro.build/) | Static site generator |
| TypeScript | Type-safe config |
| Vanilla CSS | Styling (no UI framework) |
| Custom i18n | Client-side translation system |

## Project Structure

```
src/
├── components/
│   ├── Header.astro          # Navigation bar with language switcher
│   ├── Footer.astro          # Site footer
│   ├── ProductCard.astro     # Reusable product card component
│   └── LanguageSwitcher.astro # EN / 中文 toggle button
├── i18n/
│   └── translations.js       # All EN/ZH text translations
├── layouts/
│   ├── Layout.astro          # Base layout (Header + Footer + i18n script)
│   └── BlogLayout.astro      # Blog article layout with bilingual content
├── pages/
│   ├── index.astro           # Home page
│   ├── about.astro           # About / company story
│   ├── contact.astro         # Contact form + info
│   ├── products/
│   │   ├── index.astro                    # Product catalog
│   │   ├── mipi-csi2-cables.astro         # MIPI CSI-2 detail page
│   │   └── m12-industrial-connectors.astro # M12 connector detail page
│   └── blog/
│       ├── index.astro                          # Blog listing
│       ├── how-to-choose-mipi-cable.astro       # MIPI selection guide
│       ├── mipi-vs-gmsl-vs-fpd-link.astro       # Interface comparison
│       └── m12-connector-coding-guide.astro     # M12 coding reference
├── styles/
│   └── global.css            # Global styles, CSS variables, responsive rules
└── public/
    └── favicon.svg
```

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 18+ (tested on Node 24)
- npm

### Installation

```bash
# Clone the repo
git clone https://github.com/LehmanLM/we-connect-website-astro-project.git
cd we-connect-website-astro-project

# Install dependencies
npm install
```

### Development

```bash
# Start dev server (hot reload)
npm run dev

# Open http://localhost:4321/
```

### Build

```bash
# Build static site to dist/
npm run build

# Preview the production build
npm run preview
```

### Deploy

The `dist/` directory contains static HTML/CSS/JS that can be deployed to any static host:

- **Cloudflare Pages** (recommended) — free, unlimited requests, global CDN
- **Vercel** — free tier, 100GB/month bandwidth
- **GitHub Pages** — free, 100GB/month bandwidth

## How the i18n System Works

1. UI text is tagged with `data-i18n="translation.key"` attributes
2. Blog content uses `class="i18n-content" data-lang="en|zh"` wrappers
3. Translations are defined in `src/i18n/translations.js`
4. The i18n script in `Layout.astro` reads the saved language from `localStorage` and swaps text on page load
5. Language switcher buttons trigger real-time text replacement

To add a new translatable string:

```js
// 1. Add to translations.js
'en': { 'my.key': 'Hello' },
'zh': { 'my.key': '你好' },

// 2. Use in any .astro file
<p data-i18n="my.key">Hello</p>
```

## Cost

| Item | Cost |
|------|------|
| Domain (.com) | ~$1/month |
| Hosting (Cloudflare Pages) | Free |
| SSL | Free (auto) |
| Build tooling | Free (open source) |
| **Total** | **~$12/year** |

## License

This is a private commercial project. All rights reserved.

---

**Questions?** Contact: info@visioncablesupply.com
