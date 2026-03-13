# 🤖 AI-Assisted Workflow Automation
**Redesigning Document-Heavy Analytics Workflows Using LLM Tools**

> Built during my role as Business Analyst at a global B2B events company. This repo demonstrates the workflow design methodology and prompt patterns using public/synthetic data.

---

## 🧩 Problem

A large portion of analyst time in sales operations goes to document-heavy tasks:
- Synthesising survey outputs (NPS, customer satisfaction scores) into executive narratives
- Extracting structured data from unstructured contract and account documents
- Converting raw analysis into stakeholder-ready presentation content

Done manually, each of these tasks took hours. During peak reporting cycles, this created a bottleneck that delayed decision-making — and left little time for higher-value analytical work.

---

## ✅ Solution

Redesigned recurring document review and synthesis workflows using AI tooling — specifically NotebookLM, Microsoft Copilot, and Claude — to handle first-pass extraction, synthesis, and narrative drafting.

### Workflow Before vs. After

| Step | Before (Manual) | After (AI-Assisted) |
|---|---|---|
| Survey synthesis | Read all responses, manually tag themes, write summary | Upload to NotebookLM, use structured prompts to extract themes and rankings |
| Contract/doc extraction | Ctrl+F and manual read-through of 20–50 page documents | Prompt-based extraction of specific fields (account name, value, terms) |
| Executive summary drafting | Write from scratch after completing analysis | AI-generated first draft from structured data, analyst edits and validates |
| Presentation narrative | Translate tables/charts into prose manually | LLM-drafted narrative from bullet-point inputs, refined by analyst |

**Time saved:** Multi-hour manual processes reduced to 30–60 minute AI-assisted workflows for first-pass output.

---

## 🛠️ Tools Used

| Tool | Primary Use |
|---|---|
| **NotebookLM** | Survey synthesis, knowledge base creation from large document sets |
| **Microsoft Copilot** | Presentation narrative drafting, document summarisation within M365 |
| **Claude** | Complex extraction tasks, structured data pull from unstructured docs |

---

## 📁 Repo Structure

```
ai-workflow-automation/
│
├── prompts/
│   ├── survey_synthesis_prompt.md         # NPS/satisfaction survey synthesis
│   ├── document_extraction_prompt.md      # Contract & account value extraction
│   ├── executive_summary_prompt.md        # Summary narrative generation
│   └── presentation_narrative_prompt.md   # Slide narrative drafting
│
├── notebooks/
│   └── demo_workflow.ipynb                # End-to-end demo using public survey data
│
├── output/
│   ├── sample_survey_synthesis.md         # Example synthesised survey output
│   └── sample_executive_summary.md        # Example executive summary output
│
└── README.md
```

---

## 🧠 Prompt Patterns

### 1. Survey Synthesis (NotebookLM / Claude)

**Use case:** Synthesising pre/post conference survey data on CSP ratings and NPS scores into a ranked executive summary.

```
You are an analyst summarising survey results for a senior leadership presentation.

I'm going to give you survey responses from [N] respondents rating their experience with 
Customer Success Partners (CSPs) across two dimensions:
- Customer Effort Score (CES): how easy it was to work with their CSP
- Overall CSP Rating: general quality of service

For each CSP, calculate:
1. Average CES score
2. Average Overall Rating
3. Overall rank (1 = highest rated)
4. 1-sentence summary of key themes from open-ended comments

Format the output as a ranked table followed by a 3-bullet executive summary highlighting:
- Top performers
- Bottom performers
- Any notable patterns across regions or event types

Data:
[paste survey export here]
```

---

### 2. Contract / Document Value Extraction (Claude)

**Use case:** Extracting account-level contract values and enterprise relationship data from large document sets.

```
You are a data extraction assistant. I will provide you with a document containing 
account and contract information.

Extract the following fields for each account mentioned:
- Account name
- Contract value (numeric, USD)
- Contract start date
- Contract end date
- Product/service type
- Account tier (Enterprise / Mid-Market / SMB if mentioned)

Return the output as a clean table with these exact column headers:
Account Name | Contract Value | Start Date | End Date | Product | Tier

If a field is not mentioned, return "N/A". Do not infer or estimate values 
not explicitly stated in the document.

Document:
[paste document content here]
```

---

### 3. Executive Summary Generation (Copilot / Claude)

**Use case:** Converting structured analysis (tables, metrics) into a narrative executive summary for leadership.

```
You are a business analyst writing an executive summary for a senior sales leader.

Below is structured data from a performance analysis. Write a 3-paragraph executive 
summary that:
- Opens with the key finding (1-2 sentences)
- Summarises performance across the top and bottom segments (1 paragraph)
- Closes with a clear recommendation or implication for the business (1 paragraph)

Tone: direct, data-driven, no jargon. Avoid phrases like "it is worth noting" or 
"it can be observed that". Write in active voice.

Data:
[paste analysis summary here]
```

---

### 4. Presentation Narrative (Copilot)

**Use case:** Converting raw bullet points and data into slide narrative for executive PowerPoint decks.

```
Convert the following bullet points into slide narrative text for a PowerPoint 
executive presentation.

Requirements:
- Each slide should have 1 headline sentence (bold, max 12 words)
- 2-3 supporting sentences below (plain text, conversational but professional)
- Do not use bullet points in the output — write in flowing prose
- Keep each slide's text under 60 words total

Slide topic: [topic]
Key points to cover:
- [bullet 1]
- [bullet 2]
- [bullet 3]
```

---

## 🔁 End-to-End Workflow Example

**Project: GLE Team Restructuring Proposal**

1. **Input:** Pre-conference survey (CSP Customer Effort Scores) + Post-conference survey (NPS ratings) across multiple events
2. **Step 1 — Upload to NotebookLM:** Created a structured knowledge base from both survey exports
3. **Step 2 — Extraction prompt:** Used the survey synthesis prompt above to generate ranked CSP performance table
4. **Step 3 — Narrative prompt:** Passed ranked table into executive summary prompt to generate leadership narrative
5. **Step 4 — Human review:** Validated figures against raw data, edited tone and context
6. **Output:** Executive slide deck with ranked CSP performance, NPS trends, and restructuring recommendation

**Time: ~1.5 hours (vs. estimated 5–6 hours manually)**

---

## 📈 Results

| Metric | Outcome |
|---|---|
| Workflows redesigned | Document review, survey synthesis, contract extraction, presentation drafting |
| Tools deployed | NotebookLM, Microsoft Copilot, Claude |
| Time reduction | Multi-hour manual reviews → 30–60 min AI-assisted workflows |
| Formal training | LLM Engineering certification (Gartner Udemy) |

---

## 💡 What I Learned

**Prompt specificity is everything.** Vague prompts produce vague outputs. The prompts that worked best specified the output format, the tone, what *not* to do, and how to handle missing data — before providing any content.

**AI as a first-pass, analyst as final pass.** The workflow that worked: AI generates the draft, analyst validates against source data and edits for context and judgement. Never distribute AI output without a human review step.

**Structured inputs produce structured outputs.** Unstructured document dumps produce unreliable extractions. Cleaning and structuring data before prompting (even basic reformatting) dramatically improved output quality.

---

## ⚠️ Note on Data

All documents and data referenced in this repository are **synthetic or publicly available**. No proprietary or confidential Gartner information is included. Prompt patterns are generalised from real workflows and designed to be reusable across similar business contexts.

---

*Part of my analytics portfolio — [LinkedIn](https://linkedin.com) | [Portfolio](https://github.com)*
