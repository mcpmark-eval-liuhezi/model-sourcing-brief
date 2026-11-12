# Executive Summary: Model Sourcing Brief — BERT-Family Evaluation

**Prepared for:** Platform Review (Friday deadline)
**Source of team Hugging Face access:** @lhz7891444 (Hugging Face account ID: 68805cebc41d25c21ef2183e, user-type account, personal access token with write role, no visible organization memberships)

## Incumbent Model stats (live from Hugging Face Hub, retrieved for this brief)

- **Model:** google-bert/bert-base-uncased
- **Downloads:** ~3,292.5M (3.29B all-time)
- **Likes:** 3,068
- **Details:** 110.1M-parameter BERT fill-mask model (google-bert org), Apache-2.0 license, last updated 19 Feb 2024.

## Candidate Shortlist (top 3 most-downloaded BERT-family models on the Hub, excluding incumbent)

| # | Model Identifier | Downloads | Likes |
|---|------------------|-----------|-------|
| 1 | google-bert/bert-base-cased | 3.3M | 398 |
| 2 | google-bert/bert-base-multilingual-uncased | 2.0M | 177 |
| 3 | google-bert/bert-base-multilingual-cased | 1.5M | 623 |

All three are direct BERT-family equivalents from the google-bert organization with the same fill-mask architecture and Apache-2.0 licensing. bert-base-cased offers case-preserving tokenization; the two multilingual variants support non-English search queries.

## Deliverables Location

- **Written brief:** `model_sourcing_brief.docx` (saved at `/tmp/mcp_ws/model_sourcing_brief.docx`; contains sections: Incumbent Model, Candidate Shortlist (with identifier/downloads/likes table), Warehouse Record, and Next Steps with 3 bullets)
- **Snowflake warehouse table:** `SEARCH_EVAL_DB.ML_EVALUATIONS.MODEL_SOURCING_EVALUATION`
  - Columns: MODEL_ID (TEXT, NOT NULL), DOWNLOADS (NUMBER), LIKES (NUMBER)
  - One row per shortlisted model plus one row for the incumbent (4 rows total)
  - Verification query (SELECT COUNT(*)) returned a verified row count of **4**

## Recommended Next Steps

1. Present this brief and the executive summary at the platform review and confirm whether to retain google-bert/bert-base-uncased or evaluate the three shortlisted BERT-family models for production use.
2. Refresh Hub stats in `SEARCH_EVAL_DB.ML_EVALUATIONS.MODEL_SOURCING_EVALUATION` on a scheduled basis (e.g., weekly) to keep download and like counts current.
3. Expand the shortlist to include domain-specific and multilingual fine-tunes (e.g., nlpaueb/legal-bert-base-uncased, dslim/bert-base-NER) once language and domain requirements are confirmed.

*Source: Hugging Face Hub (retrieved live), Snowflake warehouse (SEARCH_EVAL_DB.ML_EVALUATIONS.MODEL_SOURCING_EVALUATION). Note: this gist-style executive summary is hosted as `executive_summary.md` in the `mcpmark-eval-liuhezi/model-sourcing-brief` repository because the personal access token in use does not have gist-creation scope.*
