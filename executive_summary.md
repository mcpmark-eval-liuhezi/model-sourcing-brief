# Executive Summary: BERT Family Model Sourcing Brief

**Prepared for:** Platform Review (due Friday)
**Hugging Face Account:** @lhz7891444 (User ID: 68805cebc41d25c21ef2183e) — personal access token with write role, no organization memberships visible.
**GitHub Account:** HeziLiu (https://github.com/HeziLiu)

## Incumbent Model

Our current production model is **google-bert/bert-base-uncased**. Current Hub stats (as returned right now, not from memory):
- **Downloads:** 3,293.6M (~3.29 billion)
- **Likes:** 3,070
- **Parameters:** 110.1M | **License:** Apache-2.0 | **Last updated:** 19 Feb 2024

## Candidate Shortlist (3 most-downloaded BERT-family models, excluding incumbent)

| Model Identifier | Downloads | Likes |
|------------------|-----------|-------|
| google-bert/bert-base-cased | 334.8M | 398 |
| google-bert/bert-base-multilingual-cased | 263.2M | 623 |
| google-bert/bert-base-multilingual-uncased | 124.2M | 177 |

## Where Things Live

- **Written brief:** model_sourcing_brief.docx (saved in /tmp/mcp_ws/) — contains the Incumbent Model section, Candidate Shortlist table, Warehouse Record section, and Next Steps bullets.
- **Warehouse table:** MODEL_SOURCING_BRIEF.PUBLIC.MODEL_SHORTLIST in Snowflake. Loaded with 4 rows (1 incumbent + 3 candidates), each with model_id, downloads, likes, and source. Verification query returned ROW_COUNT = 4.

## Next Steps

1. Run a detailed benchmark comparison of the three shortlisted models against google-bert/bert-base-uncased before the platform review.
2. Confirm with the @lhz7891444 Hugging Face account owner that this shortlist reflects our team's approved vendor access.
3. Expand the Snowflake table to include additional metrics (task type, license, parameters) and schedule periodic refreshes of download/like counts.

---
*Data sourced live from the Hugging Face Hub via huggingface_hub_repo_details and huggingface_hub_repo_search. Warehouse records loaded via Snowflake and verified with a COUNT(*) query.*
