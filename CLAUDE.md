# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for Marcus Forst (marcusforst.com), built on Astro 2 with Preact for interactive components. Originally forked from the Netlify Feature Tour template. Deployed on Netlify.

## Commands

- `npm run dev` — Start local dev server (or `netlify dev` for full Netlify feature support including serverless functions and forms)
- `npm run build` — Production build to `/dist`
- `npm run preview` — Preview the production build locally
- Formatting: Prettier (2-space indent, no tabs — see `.prettierrc`)

## Architecture

**Astro file-based routing**: Pages in `src/pages/` auto-generate routes. Each page imports the shared `Layout` component from `src/components/layout.astro`.

**Interactive components**: Preact (`.jsx`) used for client-side interactivity, hydrated via Astro's `client:visible` directive. See `src/components/function-tester.jsx`.

**Styling**: Design tokens from `@netlify/netlify-marketing-tokens` defined as CSS custom properties in `public/global.css`. Pages use Astro scoped `<style>` blocks. Fonts: Pacaembu (headings) and Mulish (body) loaded from `public/fonts/`.

**Serverless functions**: Located in `netlify/functions/`. Requires `netlify dev` (not plain `npm run dev`) to test locally.

**Forms**: Netlify Forms integration — forms with `netlify` attribute are handled server-side without custom backend code. Success redirect goes to `/success`.
