# GPT Prediction Prompt – Draft

## Goal
Generate a predicted Douban rating (1–5) for each movie based only on the information provided, plus a confidence level and brief reasoning.

## Format Requirements
GPT must respond in the following JSON format:

{
  "predicted_rating": X,
  "confidence": X,
  "reasoning": "..."
}

- `predicted_rating`: an integer 1–5  
- `confidence`: an integer 1–5  
- `reasoning`: 1–2 sentences only  

## Restrictions
To ensure consistency and valid evaluation, GPT must follow these strict rules:

1. **Do NOT search for external information.**
2. **Do NOT recall or reference actual Douban ratings.**
3. **Do NOT output anything except the required JSON object.**
4. **Reasoning must be 1–2 sentences only** (no long explanations, no bullet points).
5. **Numbers must be integers between 1–5.**
6. **No extra text before or after the JSON block.**
7. **No commentary, disclaimers, or formatting outside of JSON.**
8. **If unsure, GPT must still output a forced best guess (no “cannot determine”).**

## Prompt Template

You will be given basic information about a movie.  
Using only this information, predict what rating this movie would receive on Douban (1–5) and provide a confidence score (1–5).

Do **not** search for external information or refer to real Douban records.

Here is the movie information:

Title: {{title}}  
Year: {{year}}  
Short plot summary: {{summary}}  
Genre: {{genre}}  
Actors: {{actors}}

Now output your prediction in the required JSON format.
