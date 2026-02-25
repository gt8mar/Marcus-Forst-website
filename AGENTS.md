# Repository Guidelines

## Project Structure & Module Organization
This is an Astro 2 site for `marcusforst.com`, deployed on Netlify.

- `src/pages/`: route-based pages (for example `src/pages/research/index.astro` -> `/research`)
- `src/components/`: shared UI (`layout.astro`, `nav.astro`, `footer.astro`, `hero.astro`, `project-card.astro`)
- `public/`: static assets (images, fonts, favicon, `docs/Marcus_Forst_CV.pdf`, `global.css`)
- `netlify/`: Netlify-specific resources (including functions when used)
- `dist/`: production output from build (generated)

## Build, Test, and Development Commands
- `npm install`: install dependencies
- `npm run dev`: run Astro dev server
- `npm run build`: create production build in `dist/`
- `npm run preview`: preview built output locally
- `netlify dev`: run with Netlify features (forms/functions) for realistic local behavior

Netlify deployment uses `netlify.toml` with `npm run build` and publish directory `dist`.

## Coding Style & Naming Conventions
- Formatting is controlled by Prettier (`.prettierrc`): 2-space indentation, no tabs.
- Keep Astro pages/components in lowercase kebab-case (for example `project-card.astro`).
- Prefer reusable components in `src/components/` over duplicating markup in pages.
- Keep global tokens and shared visual rules in `public/global.css`; keep page-specific styles scoped inside each `.astro` file.

## Testing Guidelines
There is currently no automated test suite in this repository. Before opening a PR:

- Run `npm run build` to catch compile/runtime issues.
- Smoke-test core routes: `/`, `/about`, `/research`, `/publications`, `/contact`.
- If editing the contact form, verify Netlify form flow and `/contact/success` using `netlify dev`.
- Validate responsive behavior on mobile and desktop for any UI changes.

## Commit & Pull Request Guidelines
Recent history uses concise, imperative commit messages (for example: `Add live IVF tool link for Theo project`, `Restore standard top nav...`).

- Use one focused change per commit.
- Write commit subjects in imperative mood, ~50-72 chars when possible.
- PRs should include: purpose summary, affected routes/components, manual test notes, and screenshots/GIFs for visual changes.
- Link related issues/tasks when available and call out Netlify/config changes explicitly.
