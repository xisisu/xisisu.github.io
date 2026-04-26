# CLAUDE.md - xisisu.github.io

## Project Context
**Repository**: `xisisu.github.io` — Personal portfolio website for Sisu Xi
**Stack**: Hugo static site generator + PaperMod theme, deployed to GitHub Pages
**URL**: https://xisisu.github.io/

## Project Structure
| Directory | Contents |
|-----------|----------|
| `archetypes/` | Hugo content template (default front matter) |
| `assets/` | Custom CSS overriding PaperMod theme |
| `content/` | 3 pages: homepage, resume, publications |
| `data/` | Empty — Hugo data directory (unused) |
| `i18n/` | Empty — internationalization (unused) |
| `layouts/` | Custom template overrides for PaperMod |
| `static/` | Profile image and robots.txt |
| `themes/` | PaperMod theme (git submodule) |
| `.github/` | GitHub Actions workflow for Pages deployment |

**Generated (gitignored):** `public/`, `resources/`

## Configuration
- `hugo.yaml` — site config: PaperMod theme, profile mode, dark default, 6 profile buttons
- `.gitmodules` — PaperMod submodule from `adityatelange/hugo-PaperMod`
- Unsafe HTML rendering enabled (for Google Docs embeds in resume page)

## Development
```bash
hugo server -D          # Local dev server with drafts
hugo --gc --minify      # Production build
```

## Deployment
Automated via GitHub Actions (`.github/workflows/hugo.yaml`):
- Triggers on push to `main` or manual dispatch
- Hugo 0.159.1 extended, builds with `--gc --minify`
- Deploys to GitHub Pages

## Conventions
- Commit directly to `main` — no branches/PRs needed
- Content pages use `layout: "single"` with custom URLs
- Custom CSS goes in `assets/css/extended/custom.css` (PaperMod convention)
- Layout overrides mirror PaperMod's directory structure under `layouts/`
