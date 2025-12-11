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
  - Country
  - Short English summary
- Each participant will provide:
  - Predicted rating (1-5）
  - Confidence level (1-5)

## 5. LLM Prediction Plan
Prediction model: Offline / no-internet LLM (to avoid retrieval of true ratings)

For each movie, the LLM receives:
- English title
- Year
- Country/Region
- Short English summary

The LLM outputs:
- A single predicted rating (1-5)

LLM Prompt:
You will estimate the expected Douban rating of a movie.
Please do NOT search for real data and do NOT base your answer on memorized rating numbers.
Only use the information below.

---
Title: {English title}
Year: {Year}
Country/Region: {Country}
Summary: {1–2 sentence summary}
---

Please output only one number (1-5).
For example: 4

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
  
