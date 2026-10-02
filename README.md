# Resonance Exhibition Website

A responsive Astro website for the **Resonance Exhibition**, based on the existing RMIT Design Studies Figma prototype.

> Development is currently focused on completing the landing/home page. The original Figma prototype is being treated as a visual reference and is not being modified.

## Tech Stack

- Astro
- TypeScript
- HTML
- CSS
- Node.js + npm
- Git
- GitHub (planned repository)
- Cloudflare Pages (planned hosting)

React, a database, and a separate backend are not currently required.

## Development Environment

Current environment:

- Ubuntu 24.04 LTS
- Visual Studio Code
- Node.js LTS/current installation
- npm
- Git

Recommended VS Code extensions:

- Astro
- Prettier - Code formatter
- ESLint
- GitLens (optional)

## Run Locally

From the project directory:

```bash
npm install
npm run dev
```

Open:

```text
http://localhost:4321/
```

The Astro development server provides live updates while editing.

## Current Project Structure

```text
Resonance/
├── public/
│   └── images/
│       └── landing/
│           ├── Logo.png
│           ├── Resonance_Logo.webp
│           └── student assets...
│
├── src/
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   └── StudentCard.astro
│   │
│   ├── layouts/
│   │   └── ExhibitionLayout.astro
│   │
│   ├── pages/
│   │   ├── index.astro
│   │   └── about.astro
│   │
│   └── styles/
│       └── global.css
│
├── package.json
├── package-lock.json
├── astro.config.mjs
└── tsconfig.json
```

Some components/routes are placeholders or reserved for later work.

## Architecture

### `ExhibitionLayout.astro`

Shared page shell:

```text
Header
  ↓
Page content (<slot />)
  ↓
Footer
```

### `Header.astro`

Currently contains:

- Resonance logo (`public/images/landing/Logo.png`)
- Instagram icon/link
- bottom border

The Instagram destination is still a placeholder.

### `Footer.astro`

Currently contains:

- Resonance / Exhibition
- RMIT SCD / Design Studies
- separator line

### `index.astro`

Current landing page contains:

- animated hero artwork (`Resonance_Logo.webp`)
- exhibition description
- Students heading
- About Us button
- 20 student wordmark assets

Student links are currently placeholders.

## Landing Page Assets

Located in:

```text
public/images/landing/
```

Current student assets include:

```text
AnhLe.png
AnhVu.png
Chau.png
Dat.png
Duc.png
Etel.png
Giang.png
HaNguyen.png
Lam.png
LyTruong.png
MaiDo.png
MaiNgo.png
Minh.png
Ngoc.png
NguyenDo.png
NguyenPham.png
Steve.png
Ton.png
Tony.png
TraPham.png
```

The student PNGs are currently exported at 4096 × 4096 with transparency.

The hero asset is an animated WebP:

```text
Resonance_Logo.webp
```

It is 2160 × 2880 and contains multiple animation frames. It is currently kept as the source asset and should be optimized before production deployment.

## Responsive Design

The project uses **one responsive website**, not separate mobile and desktop sites.

Current strategy:

```text
Mobile
  ↓
narrow exhibition layout
  ↓
2-column student grid

Desktop
  ↓
wider exhibition layout
  ↓
4-column student grid
```

CSS media queries handle layout changes.

## Current Hero Baseline

The landing-page hero currently uses a clipped container so the animated artwork can be positioned without altering the original source asset.

Mobile baseline:

```css
.logo-image {
  aspect-ratio: 0.9;
}

.logo-image img {
  transform: translateY(-12%);
}
```

Desktop baseline:

```css
@media (min-width: 1024px) {
  .logo-image {
    aspect-ratio: 1.06;
  }

  .logo-image img {
    transform: translateY(-19%);
  }
}
```

These values currently produce the desired hero positioning and should be treated as the working baseline.

## Content

Current exhibition description:

> Resonance Exhibition is organized by RMIT Hanoi's dedicated final-year students from the Design Studies program with the help of a lecture. Bringing together 20 distinct voices, Resonance is a space for our students, although different in their ideas and practices, to leave an impression on the audience through our echoing design.

## Planned Work

### Landing page

- [x] Astro project setup
- [x] Local development server
- [x] Shared exhibition layout
- [x] Header component
- [x] Footer component
- [x] Animated hero asset
- [x] Exhibition description
- [x] Student asset grid
- [x] Initial responsive behavior
- [ ] Final visual matching
- [ ] Final typography/font setup
- [ ] Final Instagram URL
- [ ] Production image optimization
- [ ] Final desktop art direction

### About page

- [x] Initial route
- [ ] Final visual implementation
- [ ] Final assets/content

### Student portfolio pages

Planned for a later stage.

The intended approach is one reusable student-page template backed by structured student data rather than 20 separately hand-coded pages.

## Performance

Before deployment:

- optimize the 4096 × 4096 student PNGs
- generate appropriately sized web images
- optimize the animated hero
- lazy-load below-the-fold student images where appropriate
- keep original source exports separate from production-optimized copies

## Deployment Plan

```text
Local Astro project
        ↓
Git
        ↓
GitHub
        ↓
Cloudflare Pages
        ↓
Public website
```

## Design Reference

The implementation is based on the Resonance Exhibition Figma prototype.

The Figma source should remain unchanged during development.

## Development Principles

- Keep mobile and desktop in one responsive project.
- Prefer reusable Astro components over duplicated markup.
- Keep shared styles in `src/styles/global.css`.
- Keep component-specific styles with their components.
- Preserve original design assets and create optimized production copies.
- Do not add a backend/database unless a real requirement appears.
- Finish the landing page before moving on to student portfolio pages.

## License / Ownership

Project-specific assets, text, logos, photography, artwork, and other creative material belong to their respective creators/owners unless otherwise specified. Add an explicit software/content license only when the project owner provides one.
