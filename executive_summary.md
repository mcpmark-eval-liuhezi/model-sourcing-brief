# Executive Summary: BERT Family Model Sourcing Brief

**Prepared for:** Platform Review (due Friday)
**Source of team Hugging Face access:** @lhz7891444 (Hugging Face account ID: 68805cebc41d25c21ef2183e, user-type account, personal access token with write role)

## Incumbent Model

- **Model:** google-bert/bert-base-uncased
- **Downloads (as returned right now):** 3,292.5M (~3.29B all-time downloads)
- **Likes:** 3,067
- **Verification query result:** row count of 4 in the warehouse table (1 incumbent + 3 candidates)

## Candidate Shortlist (other BERT-family models on the Hub)

| Model Identifier | Downloads | Likes |
|---|---|---|
| google-bert/bert-base-cased | 334.6M | 398 |
| google-bert/bert-base-multilingual-cased | 263.1M | 623 |
| google-bert/bert-base-multilingual-uncased | 124.1M | 177 |

## Deliverables

1. **Word brief:** `model_sourcing_brief.docx` (saved at /tmp/mcp_ws/model_sourcing_brief.docx)
   - Title: "Model Sourcing Brief"
   - Sections: Incumbent Model (with the statement "Our current production model is google-bert/bert-base-uncased."), Candidate Shortlist (with a 3-row table of identifier/downloads/likes), Warehouse Record, and Next Steps (3 bullets)
2. **Snowflake warehouse record:** fully qualified table path `BERT_MODEL_SOURCING.eval.bert_model_shortlist`
   - Columns: model_id, downloads, likes, role, loaded_at
   - 4 rows loaded (verified via SELECT COUNT(*) → 4), one per shortlisted model plus one for the incumbent

## Recommendation

The three google-bert family candidates all have strong Hub traction. bert-base-cased leads on downloads (334.6M) and is a drop-in case-sensitive alternative; bert-base-multilingual-cased has the highest like count (623) and broadest language coverage. Recommend validating them against our search stack latency/quality benchmarks before committing.

---
*Posted as executive summary for the platform review. Original brief: model_sourcing_brief.docx | Warehouse table: BERT_MODEL_SOURCING.eval.bert_model_shortlist | HF account: @lhz7891444*
