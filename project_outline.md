# Project Outline - AI-assisted Crown Prediction (Movie Ratings)
## 1. Research Question
Which method predicts movie ratings more accurately?
- Individual humans
- Crowd average
- GPT prediction
- A simple aggregation of crowd + GPT

## 2. Target Platform for Ground Truth
Douban

## 3. Movie List
- 抓娃娃 (2024)
- 走走停停 (2024)
- 年会不能停 (2023)
- 九龍城寨之圍城 (2024)
- Fly me to the moon (2024)
- 青春18×2 君へと続く道 (2024)
- 从21世纪安全撤离 (2024)
- Wonka (2023)
-  ルックバック (2024)
- Maharaja (2024)
- 소풍 (2023)

## 4. Human Prediction Plan
- Recruit: aim for 15 participants
- Each person will provide:
  - Predicted rating (1-5）
  - Confidence level (1-5)

## 5. ChatGPT Prediction Plan
For each movie, ChatGPT will be given:
- Tittle
- Year
- Short plot summary
- Genre
- Actors

And ChatGPT will output:
- Predicting rating (1-5)
- Reasoning
- Confidence level (1-5)

## 6. Aggregation Method
- Accuracy Metrics
  - Mean Absolute Error (MAE)
- Hybrid Aggregation Method
  - Human crowd average
  - GPT predicted rating
  - Final prediction = (human_weighted + GPT_pred) / 2

## 7. Deliverables for Week 1
- One file defining this outline (this file) (completed)
- A draft of the human survey
- A draft of the GPT prompt
- A movie list (completed)

  
