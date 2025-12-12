**This project is being actively updated — see timeline.md for latest methodological changes.**

# AI-assisted Crowd Prediction - Movie Rating Project

Goal: Build my first AI-assisted decision-making mini project.

I am starting from a fundamental level in coding and applied AI work.  
This repository will record every step of the process, **including failures and ugly drafts**.

## Project Idea
Use both human crowd predictions and LLM predictions to estimate movie ratings on Douban, then compare:

- Single individual predictions  
- Simple crowd average  
- LLM's prediction  
- A simple aggregation of crowd + LLM  

to see which method is closest to the actual rating.

This is my first attempt to move from *understanding papers* to **building something that actually runs**.

---

## Roadmap (Initial Plan)

This project will expand in three major stages:

### 1. Baseline Evaluation
- Collect human predictions  
- Generate LLM predictions
  - LLM used for prediction: qwen3:8b via Ollama (runs fully offline on Mac).
- Compare crowd vs LLM accuracy using MAE  

### 2. Hybrid Weight Learning
Use a simple linear regression model to learn the optimal combination of:
- crowd prediction  
- LLM prediction  

This will show which source is more reliable and what weight combination produces the lowest error.

### 3. Embedding-based Analysis
Generate embeddings from each movie’s title/year/summary/counrty/region/genre/actors.  
Use them to:
- visualize patterns (PCA)  
- explore what features high-rated movies share  
- build a small regression model (embedding → predicted rating)

---

More steps will be added as the project evolves.
