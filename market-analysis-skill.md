# SKILL: AI Market Analysis

**Trigger:** User asks to estimate TAM/SAM/SOM, validate a market analysis, or assess market fit for a pitch or strategy.

---

## Step 1 — Collect framing from the user

Before any calculation, ask the user to confirm all of the following. Do not proceed until all are answered:

- Product / service
- Target customer segment
- Geography
- Time horizon (year / period)
- Calculation method: top-down / bottom-up / value theory / all three
- Goal: pitch / strategy / go-no-go decision

If any field is missing, ask for it explicitly. Do not fill gaps with assumptions.

---

## Step 2 — Run the market sizing prompt (Chain of Thought)

Use a web-search-enabled tool (Perplexity, ChatGPT Search, Gemini) — not raw LLM for finding numbers. Send:

```
Оцени рынок для: [продукт/сервис]
Клиент: [сегмент]
География: [страна/регион]
Период: [год]
Метод: [bottom-up / top-down / value theory]

Прежде чем считать:
1. Перечисли все ключевые допущения (минимум 5)
2. Укажи, что ты НЕ знаешь точно и откуда берёшь данные
3. Обозначь риски расчёта

Затем посчитай TAM, SAM, SOM.

Формат ответа — таблица:
| Уровень | Значение | Метод | Источник + год | Допущение |
| TAM | ... | ... | ... | ... |
| SAM | ... | ... | ... | ... |
| SOM | ... | ... | ... | ... |

Ниже — список рисков и слабых мест расчёта.
```

---

## Step 3 — Run adversarial review

Open a fresh context and send:

```
Вот анализ рынка:
[вставить результат шага 2]

Выступи в роли скептичного инвестора. Найди:
1. Три главных ошибки или слабых допущения
2. Цифры, которые выглядят как галлюцинации (нет источника / слишком круглые)
3. Что не учтено: конкуренция, регуляторика, сезонность, пост-2022 изменения рынка в РФ
4. Как бы ты пересчитал иначе?
```

---

## Step 4 — Run sanity checks

### A. Public company benchmark

Find a public company operating in this market with reported revenue. Send:

```
[Компания X] работает в этом рынке и показывает выручку = Y млрд/год.
По аналитике, её доля рынка = Z%.
Значит, рынок ≈ Y / Z * 100.
Сравни с нашим расчётом TAM.
```

For Russian market: Сбер, Ozon, Wildberries, HeadHunter, ЦИАН, VK, Яндекс, Fix Price, Магнит.

### B. Order-of-magnitude check

Do NOT answer these yourself. Ask the user to answer manually:

- "SOM реален при вашем размере команды и горизонте?"
- "Проникновение реалистично? (≤30% в год для нового рынка — уже агрессивно)"
- "Темп роста рынка объяснён реальным событием или AI просто экстраполировал?"

### C. Data freshness check

Verify all sources are from 2025–2026. If any source is from 2021–2022 for the Russian market, flag it explicitly before continuing.

---

## Step 5 — Strategic filter

Ask the user to provide their company's strategic priorities, then send:

```
Вот анализ рынка: [вставить]
Вот стратегические приоритеты/фокус компании: [вставить]

Ответь:
1. Три причины, почему этот рынок ПОДХОДИТ стратегии
2. Три причины, почему НЕ подходит
3. Какие активы (технология, клиентская база, бренд, команда) уже есть для входа?
4. Что нужно приобрести или построить?
```

Do not make a go/no-go recommendation. Return arguments only — the user decides.

---

## Step 6 — Auto-validate before presenting results

Check each item below. If triggered, flag it and ask the user to verify manually before finalizing:

- No source citations → likely hallucinated
- All numbers are round (100B, 50%, 10M) → no real data found
- "По данным отраслевых исследований" with no name → hallucination marker
- No specific competitors or players named → AI didn't find real data
- No uncertainty range → AI is faking precision
- Data from 2021–2022 for Russian market → post-sanctions world changed significantly
- SOM > 30% of SAM in year 1 → almost never realistic
- "Market grew 3× in one year" without explanation → extrapolation, not sourced data
- Citation to Statista / Grand View / MarketsandMarkets → AI cannot access paywalled data; numbers are fabricated

---

## Step 7 — Generate final report

Output in this exact format:

```markdown
## Оценка рынка: [название]

**Дата:** [дата]
**Методы:** [использованные]
**Горизонт данных:** [годы]

### Результаты

| Уровень | Значение | Метод | Источник + год |
|---------|----------|-------|----------------|
| TAM     | ...      | ...   | ...            |
| SAM     | ...      | ...   | ...            |
| SOM     | ...      | ...   | ...            |

### Ключевые допущения
1. ...
2. ...
3. ...

### Риски расчёта
- ...

### Sanity check
- Компания-ориентир: [X], выручка [Y], доля [Z%] → рынок ≈ [расчёт]
- Order-of-magnitude: [ответ пользователя]

### Стратегическое попадание
**За:** ...
**Против:** ...
**Вывод:** ...
```

---

## Tool selection


| Task                      | Tool                                               |
| ------------------------- | -------------------------------------------------- |
| Finding market numbers    | Perplexity or ChatGPT Search (web access required) |
| Deep synthesis            | Gemini Deep Research                               |
| Structuring / calculation | Claude, GPT-4o                                     |
| Adversarial review        | Claude (fresh context)                             |
| Russian market specifics  | Perplexity in Russian                              |


