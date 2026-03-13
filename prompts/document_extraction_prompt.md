# Prompt: Contract & Document Value Extraction

## Use Case
Extracting structured account-level data (contract values, terms, account details) from large unstructured documents.

## Prompt Template

```
You are a data extraction assistant. I will provide you with a document containing
account and contract information.

Extract the following fields for each account mentioned:
- Account name
- Contract value (numeric, USD)
- Contract start date
- Contract end date
- Product or service type
- Account tier (Enterprise / Mid-Market / SMB — if mentioned)

Return the output as a clean table with these exact column headers:
Account Name | Contract Value | Start Date | End Date | Product | Tier

Rules:
- If a field is not mentioned, return "N/A"
- Do not infer or estimate values not explicitly stated in the document
- If multiple contracts exist for the same account, list each as a separate row
- Flag any amended or superseded contracts with a note in a separate column called "Notes"

Document:
[paste document content here]
```

## Tips
- Run on one document at a time for best accuracy
- Always cross-check extracted values against the original document
- Pay special attention to the "Notes" column — amended contracts are easy to miss
