# Presentation engine (this deck)


| Engine          | Status   | Notes                                                                                                                                                      |
| --------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Static HTML** | In use   | Open `Сбер_оценка_рынка_lecture.html` in a browser. Uses `../../brand.css` and `data-client="sber"`.                                                       |
| **Slidev**      | Optional | `npm init slidev@latest` in a subfolder; add a theme that maps CSS variables from `brand.css`; split `Сбер_оценка_рынка_content.md` on `---` slide breaks. |
| **Marp**        | Optional | VS Code Marp extension + custom CSS `@import` of `brand.css` (trim to Marp-compatible rules).                                                              |


Metadata: `[deck.meta.json](deck.meta.json)`.