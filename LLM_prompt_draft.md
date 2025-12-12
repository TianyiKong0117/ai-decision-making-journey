# Offline LLM Prediction Prompt – Draft (Updated)

## Goal
Generate a predicted Douban rating **(1-5, one decimal)** for each movie based *only* on the information provided.

The model is **offline / no-internet**, so the prompt must prevent use of memorized or retrieved real ratings.

The offline model used in this project is qwen3:8b, running locally through Ollama (Mac, no internet access).

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

You are an offline language model running locally on my machine via Ollama (no internet access).

Your task:
Estimate what rating a movie would receive on Douban, using ONLY the information I provide.

Output rules (very important):
- Output ONE number only.
- The number must be between 1.0 and 5.0 (inclusive).
- Use exactly ONE decimal place (e.g., 3.3, 4.0, 4.6).
- Do NOT output any text, explanation, JSON, or confidence score.
- No extra spaces, no units, no commentary. Just the number.

Restrictions:
- Do NOT search for external information.
- Do NOT recall or reference any known Douban ratings.
- Do NOT mention training data.
- Use only the information given below (title, year, genre, actors, country, summary).
- If you are uncertain, still make your best guess.

Movie information:
Title: {{title_en}}
Year: {{year}}
Genre: {{genre}}
Actors: {{actors}}
Country/Region: {{country_region}}
Short Summary (English): {{summary}}

Now output a single predicted rating (1–5, one decimal) and nothing else.

