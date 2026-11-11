# Executive Summary: Model Sourcing Brief — BERT-Family Search Stack Evaluation

**Prepared for:** Platform Review (due Friday)
**Hugging Face Account:** @lhz7891444 (user account, personal access token with write role; no org memberships visible)
**Brief location:** model_sourcing_brief.docx (Word deliverable, saved in the shared workspace)
**Warehouse table:** SEARCH_MODEL_SOURCING_DB.BERT_EVAL.MODEL_SHORTLIST (Snowflake) — 4 rows verified (incumbent + 3 candidates), each with model identifier, download count, and like count.

## Incumbent Model
- **Model:** google-bert/bert-base-uncased
- **Downloads:** ~3.29B (3,292.5M as reported on the Hub right now)
- **Likes:** 3,067
- **Status:** Our current production model. Apache-2.0 licensed, 110.1M parameters, fill-mask task, English, last updated 19 Feb 2024.
- Required sentence in brief: "Our current production model is google-bert/bert-base-uncased."

## Candidate Shortlist (most-downloaded BERT-family models on the Hub, excluding incumbent)
| Model Identifier | Downloads | Likes |
|---|---|---|
| google-bert/bert-base-cased | 334.6M | 398 |
| google-bert/bert-base-multilingual-cased | 263.1M | 623 |
| google-bert/bert-base-multilingual-uncased | 124.1M | 177 |

All three are Apache-2.0 licensed, ~110M parameters, fill-mask task, and suitable as drop-in alternatives. bert-base-cased is the strongest direct English replacement (cased text retention); the two multilingual variants add cross-lingual coverage at the cost of a smaller English-specific throughput edge.

## Warehouse Record
- **Fully qualified table path:** SEARCH_MODEL_SOURCING_DB.BERT_EVAL.MODEL_SHORTLIST
- **Schema:** BERT_EVAL (in database SEARCH_MODEL_SOURCING_DB)
- **Verification:** SELECT COUNT(*) returned **4 rows** with **4 distinct model identifiers** — one row per shortlisted model plus one row for the incumbent, with model identifier, download count, and like count loaded.

## Next Steps
1. Run live latency/quality benchmarks of the three candidates vs. the incumbent before any switchover.
2. Confirm @lhz7891444 Hub access is sufficient for our CI pipeline and schedule periodic re-pulls of download/like counts.
3. Reference model_sourcing_brief.docx and SEARCH_MODEL_SOURCING_DB.BERT_EVAL.MODEL_SHORTLIST in the platform review, and gate any model change on the 4-row verification query.
