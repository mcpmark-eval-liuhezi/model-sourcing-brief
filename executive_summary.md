# Executive Summary: BERT-Family Model Sourcing Brief

## Hub Account
Our team's Hugging Face access is tied to the account **@lhz7891444** (user account, write-role personal access token). All stats below were pulled live from the Hugging Face Hub on the date of this brief.

## Incumbent Model
- **Model:** google-bert/bert-base-uncased
- **Downloads (all-time):** 3,291.4M (~3.29 billion)
- **Likes:** 3,066

## Candidate Shortlist (3 most-downloaded BERT-family models, excluding the incumbent)
1. **google-bert/bert-base-cased** — 334.5M downloads, 398 likes
2. **google-bert/bert-base-multilingual-cased** — 263.0M downloads, 623 likes
3. **google-bert/bert-base-multilingual-uncased** — 124.1M downloads, 177 likes

All three candidates are official google-bert community models (fill-mask, BERT architecture, Apache-2.0 license).

## Deliverables
- **Written brief:** model_sourcing_brief.docx (saved in the team workspace, /tmp/mcp_ws/)
- **Snowflake warehouse table:** MODEL_SOURCING_DB.EVALUATION.MODEL_SHORTLIST
  - Columns: MODEL_ID, DOWNLOADS, LIKES, AS_OF
  - Loaded rows: 4 (incumbent + 3 candidates)
  - Verification query returned ROW_COUNT = 4 — confirmed.

## Next Steps
- Evaluate the three candidates against launch requirements and select a replacement or complement for google-bert/bert-base-uncased before the platform review deadline.
- Refresh the Snowflake table (MODEL_SOURCING_DB.EVALUATION.MODEL_SHORTLIST) on a weekly cadence to keep downloads/likes current with the Hub.
- Circulate this brief and model_sourcing_brief.docx to the platform review committee, crediting @lhz7891444 for source attribution.