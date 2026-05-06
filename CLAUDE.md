# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website/blog hosted at `github.tinywan.com` on GitHub Pages. The site contains multiple HTML pages covering different topics including PHP, Chinese calligraphy practice (麦川千字诵), Webman framework, AI prompts, and a Gomoku game.

## Build System

The project uses **Gulp** for asset compilation and **Jekyll** for GitHub Pages.

### Common Commands

```bash
# Install dependencies
npm install

# Build CSS from SCSS (compressCSS task)
npx gulp compressCSS

# Start browser-sync dev server with file watching
npx gulp

# Default task - builds CSS, starts server, watches for changes
npx gulp default
```

### Gulp Tasks (gulpfile.js)
- `compressCSS` - Compiles SCSS files in `src/css/*.scss`, adds autoprefixes, minifies, saves to `dist/css/`
- `browser-sync` - Starts local dev server on port 3000
- `watch` - Watches SCSS files and recompiles on change
- `default` - Runs compressCSS, browser-sync, and watch

## Architecture

- **Site generator**: Jekyll with `jekyll-theme-cayman` theme (configured in `_config.yml`)
- **Custom CSS**: SCSS source in `src/css/` (fontello.scss, print.scss, style.scss) compiles to `dist/css/`
- **Modern pages**: Some pages (index.html) use Tailwind CSS via CDN with GSAP animations and Lenis smooth scroll
- **CNAME**: Configured for `github.tinywan.com`

### Page Structure
| File | Description |
|------|-------------|
| `index.html` | Main landing page - "PHP 2025 - 语言重生" |
| `mai.html`, `mai2.html`, `maichuan.html` | 麦川千字诵 calligraphy practice pages |
| `webman.html` | Webman framework related content |
| `prompt.html` | AI prompts collection |
| `gomoku.html` | Gomoku (five-in-a-row) game |

## Notes

- No test framework is configured
- The SCSS pipeline is legacy Gulp 3.x style (synchronous API)
- Tailwind CSS is loaded via CDN for newer pages rather than through the build pipeline
