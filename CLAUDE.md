# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Research and professional website for Marcus Forst (marcusforst.com) and Forst Laboratories LLC. Built on Astro 2 with Preact available for interactive components. Deployed on Netlify.

## Commands

- `npm run dev` — Start local dev server (or `netlify dev` for full Netlify feature support including serverless functions and forms)
- `npm run build` — Production build to `/dist`
- `npm run preview` — Preview the production build locally
- Formatting: Prettier (2-space indent, no tabs — see `.prettierrc`)

## Architecture

**Astro file-based routing**: Pages in `src/pages/` auto-generate routes. Each page imports the shared `Layout` component from `src/components/layout.astro`.

**Shared components** (`src/components/`):
- `layout.astro` — base HTML shell, meta tags (including Open Graph/Twitter Card), global styles
- `nav.astro` — fixed top nav bar with CSS-only mobile hamburger menu
- `footer.astro` — site footer with Email, GitHub, LinkedIn, Google Scholar, ORCID links
- `hero.astro` — hero section used on the homepage
- `project-card.astro` — reusable card with optional thumbnail image, title, description, collaborators, and link

**Pages**:
- `/` — homepage with hero + 4 project cards
- `/about` — bio, education table, awards
- `/research` — overview of Forst Labs projects, PhD work, and earlier research
- `/research/capillary-microscope`, `/research/lung-mural-cells`, `/research/uterine-atony`, `/research/ivf-prediction` — project detail pages
- `/publications` — journal articles (with DOI links), invited talks, conference presentations
- `/contact` — Netlify Forms contact form + sidebar with links
- `/contact/success` — form submission confirmation

**Styling**: Design tokens from `@netlify/netlify-marketing-tokens` defined as CSS custom properties in `public/global.css`. Pages use Astro scoped `<style>` blocks. Fonts: Pacaembu (headings) and Mulish (body) loaded from `public/fonts/`. Color scheme: `--primary` is `--blue-800` (#2036a1), `--highlight` is `--teal-400` (#05bdba), nav/footer background is `--blue-900` (#1b205b).

**Static assets** (`public/`):
- `images/` — research figures (capillary micrographs, ray diagram, MultiSero platereader)
- `docs/Marcus_Forst_CV.pdf` — downloadable CV (linked from nav)
- `fonts/` — Pacaembu and Mulish variable fonts

**Forms**: Netlify Forms integration — the contact form has the `netlify` attribute and redirects to `/contact/success` on submission.

**Serverless functions**: Located in `netlify/functions/`. Requires `netlify dev` (not plain `npm run dev`) to test locally. Currently unused.

## Key External Links

- Google Scholar: https://scholar.google.com/citations?user=J-QNTOIAAAAJ
- ORCID: https://orcid.org/0000-0002-2087-1255
- GitHub: https://github.com/gt8mar
