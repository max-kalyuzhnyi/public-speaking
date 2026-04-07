# public-speaking

Brand assets, shared skills, and **static talk sites** — published with **GitHub Pages**.

## Single source of truth

- **Canonical repo:** this directory (`public-speaking` git root).
- **Local workspace:** `Выступления/2026/СБЕР` is a **symlink** → `talks/sber-market-ai-2026` (edit the deck there; same files).
- **Legacy files** (PDF, Key, старые деки) лежат в `Выступления/2026/СБЕР_archive` — не в репозитории.

## Site structure

| URL path | Content |
|----------|---------|
| `/` | Hub: список докладов (`index.html`) |
| `/talks/sber-market-ai-2026/` | Сбер 2026: `index.html` + `content.md` + `lecture_assets/` |
| `/brand.css`, `/brand.json`, … | Общий бренд |
| `/market-analysis-skill.md` | Skill для агента |
| `/market-analysis-checklist.md` | Чеклист для себя |

## Live site

`https://max-kalyuzhnyi.github.io/public-speaking/`

Entry point is the **hub**, not a single talk.

## GitHub Pages

Settings → Pages → branch **main**, folder **`/` (root)**.

## Local preview

Open `index.html` in the browser, or open `talks/sber-market-ai-2026/index.html` (paths assume repo root for `brand.css`).
