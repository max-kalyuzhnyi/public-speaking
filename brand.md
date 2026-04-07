# Brand guide — public speaking (AI-native decks)

Machine-readable tokens: [`brand.json`](brand.json). Use the same values in CSS (`brand.css`), Slidev/Marp themes, and Pencil variables.

## Base (personal)

| Token | Value | Usage |
|-------|-------|--------|
| Background | `#ffffff` | Slide / page background |
| Text | `#1a1f16` | Body copy |
| Accent (personal) | `#1a2744` | Navy — links, emphasis when **no** client overlay |
| Muted | `#6b7280` | Captions, secondary |
| Border | `#e2e8df` | Dividers, cards |

## Typography — Gilroy

Fonts live in [`Gilroy/`](Gilroy/) (six weights). In CSS we expose:

- `--font-gilroy` with weights 300–800 mapped to Light → Extrabold.

**Headings (sections):** ALL CAPS, Bold or Extrabold, generous size.  
**Subheadings:** Sentence case, Semibold.

## Semantic colors (fixed across clients)

| Role | Hex | Meaning |
|------|-----|---------|
| danger | `#d94040` | Cost, complexity, risk |
| success | `#0d8a3e` | Growth, positive signal |
| warning | `#e5a000` | Caution |

## Client overlay

Only two things change per client:

1. **Accent** — replaces navy for UI chrome (progress bar, links, tags) when `data-client` is set on `<html>` or root.
2. **Logo** — optional path under `clients/` (add SVG/PNG yourself; paths in `brand.json` are placeholders).

Clients defined in `brand.json`: `sber`, `vtb`, `skolkovo`, `default` (personal navy).

## Imagery

Mix: real screenshots for cases; AI or icons for concepts. Keep one idea per slide; whitespace first.

## Editor: paste images into Markdown

Copy [`recommended-vscode-settings.json`](recommended-vscode-settings.json) into `.vscode/settings.json` (workspace) or merge into Cursor **User** settings. Then paste/drop images while editing a `.md` file — files go to `lecture_assets/` **next to that file** (`${documentDir}/lecture_assets/`).

## Consumption

- **HTML:** [`brand.css`](brand.css) — `:root` + `[data-client="…"]` overrides.
- **Markdown:** content only; images in `lecture_assets/` next to the `.md` file.
- **Tools:** import `brand.json` in build scripts or paste tokens into Slidev theme.
