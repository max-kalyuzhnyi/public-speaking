# Talks (site pages)

Each subdirectory is one **public deck** + assets. Root `index.html` links here.

## Layout

```
talks/
  sber-market-ai-2026/    # example: index.html = deck, content.md, lecture_assets/
  <future-talk>/          # add folder + link from repo root index.html
```

## Adding a new talk

1. Create `talks/<slug>/` with `index.html` (deck), optional `content.md`, `lecture_assets/`.
2. Link `../../brand.css` from `talks/<slug>/index.html`.
3. Add a list item to the root `index.html` hub.
4. Commit and push; GitHub Pages serves from repo root.
