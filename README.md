# Overton Forge — GitHub Pages site

Public-facing site for the Overton Forge umbrella brand. Plain HTML + CSS, no build step. Served by GitHub Pages as a User Site at `https://OvertonForge.github.io`.

## Files

- `index.html` — single landing page, anchored sections (hero, about, projects, philosophy, contact, footer)
- `styles.css` — full design system (color tokens, typography, layout, components, animations, responsive, reduced-motion)
- `README.md` — this file

## Source of truth

Content and design system come from the brand brief at `outputs/Overton_Forge/drafts/2026-05-09_OvertonForge_Brand_Brief_v1.md` in the Cowork workspace. If the brief changes, update the site to match.

## Local preview

No tooling required:

```bash
open index.html
```

Or a tiny static server (helpful if Google Fonts behaves oddly under `file://`):

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Deploy

This repo is a GitHub Pages **User Site**. Pages auto-detects User Sites and serves from `main` automatically — no Pages settings to flip. Push to `main`, site updates within ~30–60 seconds.

## Adding a project later

In `index.html`, find the `<!-- ChainKeeper -->` block in the Projects section. Copy a `<article class="project-card">` block, change:

- `data-tint="restore"` → `restore` / `signal` / `violet` (controls the card's accent color)
- The `mono-tag dim` text (e.g., `iOS APP`)
- The `status-chip` class (`status-active` / `status-planning` / `status-paused`) and label
- `project-name`, `project-desc`
- The `tag` chips in `project-tags`
- The link `href` and label

Commit + push.

## Updating brand colors

All design tokens live at the top of `styles.css` under `:root`. Change a single hex value and it propagates everywhere it's used.

## Custom domain (later)

When ready to point a custom domain (e.g., `overtonforge.com`):

1. Buy the domain.
2. Create a `CNAME` file at the root of this repo containing just the domain (no `https://`, no slashes).
3. In your DNS provider, point the apex (`@`) record at GitHub's IPs:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
   And the `www` CNAME at `OvertonForge.github.io.`
4. Repo Settings → Pages → Custom domain → enter the domain → enable HTTPS once the cert provisions.

## Tech notes

- No JavaScript. Pure HTML + CSS.
- Google Fonts loaded from CDN (Space Grotesk, Inter, IBM Plex Mono).
- Fully responsive down to 320px.
- `prefers-reduced-motion` respected.
- `:focus-visible` styles for keyboard navigation.
- Dark-mode first; no light-mode variant.

## Things deferred for v2

- Logo mark (currently text wordmark only)
- Per-project subpages
- Build log / Dispatches section
- OpenGraph image (no `og:image` set yet)
- Real contact email link
- Analytics (privacy-respecting if any)

---

*Built from Brand Brief v1, 2026-05-09.*
