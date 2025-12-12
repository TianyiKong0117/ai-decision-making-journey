This document records the evolution of the project — ideas, pivots, design upgrades, and lessons learned.

# 2025-12-11 - Major Methodological Upgrade
## 1. Standardize All Movie Inputs to English
To ensure fairness between human participants and AI:
- English title
- English summary
- Actors
- Year, region unified
- Rating scale standardized (1-5, one decimal)

Reason
- Multilingual titles may bias LLM predictions
- Humans only receive English → AI should match that

## 2. Switch to Offline / No-Internet LLM
New rule for AI predictions:
- Must use a purely local/offline model
- No browsing capability
- No external retrieval
- Must rely solely on the given movie info

## 3. New Standardized GPT Input Template
GPT receives exactly:
- Title (English)
- Year
- Country/Region
- Short Summary (English)
And outputs:
A single predicted rating (1-5, one decimal)

## 4. New To-do Items Generated
- Rewrite human survey with standardized English format
- Prepare offline model prediction for all movies
- Create a CSV dataset for storing:
  - human predictions
  - AI predictions
- Plan linear regression for hybrid weighting

# 2025-11-18 - Early Drafts & Explorations
## Progress
- Drafted human survey
- Drafted early GPT prompts
- Mixed-language movie titles still used
- GPT not restricted (risk of retrieving real ratings)
- Human vs AI input not standardized

## Key Issues Identified
- GPT might “know” real ratings
- Multilingual titles could introduce LLM bias
- Humans see only English titles but GPT has multilingual titles

# 2025-11-15 — Initial Project Outline Created
## What Was Defined
- First attempt to build an AI-assisted decision-making project
- Four prediction methods:
  - Individual human
  - Crowd average
  - GPT prediction
  - Hybrid (crowd + GPT)
- Ground truth: Douban ratings
- Accuracy metric: MAE
- Three-stage roadmap:
- Baseline comparison
- Hybrid linear regression
- Embedding-based exploration

## Status
- Project outline created
- Movie list created (initial version)



