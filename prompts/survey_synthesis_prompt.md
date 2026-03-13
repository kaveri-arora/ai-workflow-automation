# Prompt: Survey Synthesis (NPS / CSP Performance)

## Use Case
Synthesising pre/post conference survey data on CSP ratings and NPS scores into a ranked executive summary.

## Prompt Template

```
You are an analyst summarising survey results for a senior leadership presentation.

I'm going to give you survey responses from [N] respondents rating their experience
with Customer Success Partners (CSPs) across two dimensions:
- Customer Effort Score (CES): how easy it was to work with their CSP (scale 1–7)
- Overall CSP Rating: general quality of service (scale 1–5)

For each CSP, calculate:
1. Average CES score
2. Average Overall Rating
3. Overall rank (1 = highest rated)
4. One-sentence summary of key themes from open-ended comments

Format the output as:
- A ranked table with columns: Rank | CSP Name | Avg CES | Avg Rating | Key Theme
- A 3-bullet executive summary highlighting: top performers, bottom performers,
  and any notable patterns across regions or event types

If response count per CSP is below 5, flag as "low sample size".

Data:
[paste survey export here]
```

## Tips
- Works best in NotebookLM when uploaded as part of a larger document corpus
- For Claude: paste data directly after the prompt
- Always validate averages against raw data before presenting to leadership
