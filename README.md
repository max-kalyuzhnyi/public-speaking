# public-speaking

Brand tokens, Gilroy, and a static web deck for talks. Published with **GitHub Pages**.

## Live site

After Pages is enabled: `https://max-kalyuzhnyi.github.io/public-speaking/`

Entry point redirects to the latest deck under `2026/СБЕР/`.

## Repo layout

| Path | Purpose |
|------|---------|
| `brand.json`, `brand.schema.json`, `brand.md`, `brand.css` | Design tokens + CSS |
| `Gilroy/*.otf` | Font files referenced by `brand.css` |
| `market-analysis-skill.md` | AI-agent skill (workflow + prompts) |
| `market-analysis-checklist.md` | Human checklist |
| `recommended-vscode-settings.json` | Optional VS Code/Cursor paste-to-markdown helper |
| `2026/СБЕР/*` | Lecture content + `lecture_assets/` |

## GitHub Pages setup

1. Repo **Settings → Pages → Build and deployment**
2. **Source:** Deploy from a branch
3. **Branch:** `main`, folder **`/` (root)**
4. Save. The site will be available in ~1–2 minutes at the URL above.

## Local preview

Open `index.html` or the deck HTML in a browser from a local checkout (relative paths assume repo root).
