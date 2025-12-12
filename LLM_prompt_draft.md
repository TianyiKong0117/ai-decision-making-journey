# Offline LLM Prediction Prompt – Draft (Updated)

## Goal
Generate a predicted Douban rating **(1-5, one decimal)** for each movie based *only* on the information provided.

The model is **offline / no-internet**, so the prompt must prevent use of memorized or retrieved real ratings.

## Output Requirements
The LLM must output **one single number** only:
Example:
4.6

Rules:
- Output must be **1-5**, with **one decimal place** (e.g., 3.3, 4.0).
- **No text, no JSON, no explanations**, no confidence score.
- No commentary before or after the number.

---

## Restrictions

To ensure fairness between human and AI predictions:

- Do **NOT** search for external information.
- Do **NOT** recall or reference known Douban ratings.
- Do **NOT** reference training data.
- Use **only** the information given (title, year, country, summary).

If uncertain, the model must still make its **best guess**.

---

## Standardized Input Template

You will be given basic information about a movie.

Using *only* this information, estimate what rating this movie would receive on Douban (1-5 scale, one decimal).

Do **not** search externally, and do **not** recall actual Douban ratings.

Movie Information:
- **Title:** {{title_en}}
- **Year:** {{year}}
- **Genre:** {{genre}}
- **Actors:** {{actor}}
- **Country:** {{country}}
- **Short Summary (English):** {{summary}}

Now output **a single predicted rating (1-5, one decimal)** and nothing else.

