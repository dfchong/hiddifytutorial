# AGENTS.md

This file provides guidance to agents when working with code in this repository.

## Non-obvious Project Details

- Tailwind v4 uses `@tailwindcss/cli` package, not traditional PostCSS config or `tailwind.config.js`
- [`src/input.css`](src/input.css) contains only `@import "tailwindcss"` — no custom config file exists
- [`src/index.html`](src/index.html) and [`references/video.html`](references/video.html) are empty (0 bytes) files — need creation from scratch
- Build script uses Unix-specific `rm -rf` and `mkdir -p` commands (not cross-platform)
- Video.js v7+ files are pre-downloaded to [`js/`](js/) directory (not from CDN or npm)
- Video.js CSS path: [`js/video-js.min.css`](js/video-js.min.css) (non-standard, outside `node_modules`)
- The dev command is `npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch` (uses `@tailwindcss/cli`, not `npx tailwindcss`)
- Build outputs: dev → [`src/output.css`](src/output.css) (gitignored), production → `dist/output.css`
- The project is a Hiddify VPN video tutorial + software download landing page
