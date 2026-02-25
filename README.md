# Marcus Forst Website

Astro 2 site for `marcusforst.com`, deployed on Netlify.

## Stack

- Astro 2
- Netlify
- Static assets in `public/`

## Local Development

```bash
npm install
npm run dev
```

Open `http://localhost:4321`.

## Build

```bash
npm run build
npm run preview
```

Netlify build settings are defined in `netlify.toml`:

- Build command: `npm run build`
- Publish directory: `dist`

## Project Structure

- `src/pages/` route-based pages
- `src/components/` shared layout/components
- `public/` static files (images, fonts, CV PDF, global CSS)
- `netlify/` Netlify-specific resources
- `docs/` CV source and PDF

## Key Routes

- `/`
- `/about`
- `/research`
- `/publications`
- `/contact`
- `/where-in-the-world-is-marcus`
- `/archive/where-in-the-world-is-marcus-oklahoma`
