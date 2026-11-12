# Executive Summary: Model Sourcing Brief — BERT Family Evaluation

**Prepared for:** Platform Review (due Friday)
**Hugging Face account:** @lhz7891444 (user account, write-role personal access token; Account ID: 68805cebc41d25c21ef2183e)

## Incumbent Model

Our current production model is google-bert/bert-base-uncased. Current Hugging Face Hub stats as of this writing: approximately **3,292.5M downloads** and **3,068 likes**, making it the most-downloaded BERT-family model on the Hub (~110.1M parameters, fill-mask task, Apache-2.0 license).

## Candidate Shortlist (top 3 most-downloaded BERT-family models, excluding incumbent)

| Model Identifier | Downloads | Likes |
|---|---|---|
| google-bert/bert-base-cased | 334.6M | 398 |
| google-bert/bert-base-multilingual-cased | 263.1M | 623 |
| google-bert/bert-base-multilingual-uncased | 124.1M | 177 |

All three candidates are from the google-bert organization, are fill-mask tasks, ~109M parameters, and licensed under Apache-2.0 — the same ecosystem and license as our incumbent, minimizing migration risk. bert-base-cased offers case-preserving tokenization; the multilingual variants support non-English search queries.

## Deliverables Location

- **Written brief:** `model_sourcing_brief.docx` (saved at `/tmp/mcp_ws/model_sourcing_brief.docx`; contains sections: Incumbent Model, Candidate Shortlist (with identifier/downloads/likes table), Warehouse Record, and Next Steps with 3 bullets)
- **Snowflake warehouse table:** `BERT_SEARCH_STACK_SOURCING.SOURCING.MODEL_SHORTLIST`
  - Columns: MODEL_ID (TEXT), DOWNLOADS (NUMBER), LIKES (NUMBER)
  - One row per shortlisted model plus one row for the incumbent (4 rows total)
  - Verification query (SELECT COUNT(*)) returned a verified row count of **4**

## Recommended Next Steps

1. Present this brief and the executive summary at the platform review and confirm whether to retain google-bert/bert-base-uncased or evaluate the three shortlisted BERT-family models for production use.
2. Refresh Hub stats in `BERT_SEARCH_STACK_SOURCING.SOURCING.MODEL_SHORTLIST` on a scheduled basis (e.g., weekly) to keep download and like counts current.
3. Expand the shortlist to include domain-specific and multilingual fine-tunes (e.g., nlpaueb/legal-bert-base-uncased, dslim/bert-base-NER) once language and domain requirements are confirmed.

*Source: Hugging Face Hub (retrieved live via HF API at time of writing for this brief); Snowflake warehouse (BERT_SEARCH_STACK_SOURCING.SOURCING.MODEL_SHORTLIST). Note: this executive summary is hosted as `executive_summary.md` in the `mcpmark-eval-liuhezi/model-sourcing-brief` repository because the personal access token in use does not have gist-creation scope.*
