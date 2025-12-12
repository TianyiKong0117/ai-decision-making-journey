# Project Outline - AI-assisted Crown Prediction (Movie Ratings)
## 1. Research Question
Which method predicts movie ratings more accurately?
- Individual humans
- Crowd average
- Offline LLM prediction
- Hybrid (crowd + LLM weighted)

## 2. Target Platform for Ground Truth
Douban

## 3. Movie List
- Successor (2024)
- G for Gap (2024)
- Johnny Keep Walking! (2023)
- Twilight of the Warriors: Walled In (2024)
- Fly me to the moon (2024)
- 18x2 Beyond Youthful Days (2024)
- Evacuate from the 21st Century (2024)
- Wonka (2023)
- Look Back (2024)
- What Goes Around Comes Around (2024)
- Picnic (2023)

## 4. Human Prediction Plan
- Recruit: aim for 15 participants
- Each participant receives English-only info package:
  - English title
  - Year
  - Short English summary
  - Genre
  - Actor
  - Country
- Each participant will provide:
  - Predicted rating (1-10, one decimal）
  - Confidence level (1-10)

## 5. LLM Prediction Plan
Prediction model: qwen3:8b running via Ollama (Mac local, offline / no internet)

For each movie, the LLM receives:
- English title
- Year
- Country/Region
- Short English summary

The LLM outputs:
- A single predicted rating (1-10, one decimal)

LLM Prompt:
Your task:
Estimate what rating a movie would receive on Douban, using ONLY the information I provide.

Output rules:
Output ONE number only.
The number must be between 1.0 and 5.0.
Use exactly ONE decimal place (e.g., 3.3, 4.0).
No text, no explanation, no JSON.

Restrictions:
Do NOT search for external information.
Do NOT recall or reference known Douban ratings.
Do NOT mention training data.
Use only the information given.

Movie information:
Title: {English title}
Year: {Year}
Genre: {Genre}
Actors: {Actor}
Country/Region: {Country}
Summary: {1–2 sentence summary}


Please output only one number (1-10, one decimal).
For example: 4.6

## 6. Aggregation Method
Accuracy Metric：
- Mean Absolute Error (MAE)
Method Compared:
- Individual Human Prediction
- Crowd Average
- Offline LLM Prediction
- Hybrid Aggregation (learned weights)
  - fit a simple linear regression model
  - The coefficients represent the optimal weights
  - Final prediction = weighted combination learned from regression
  
