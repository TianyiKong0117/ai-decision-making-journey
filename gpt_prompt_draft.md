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
