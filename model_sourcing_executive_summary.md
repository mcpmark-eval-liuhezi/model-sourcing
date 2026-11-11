# executable-src / Model Sourcing Brief — Executive Summary

**Hub account:** @lhz7891444 (user account, write-role token, no org memberships)
**Prepared for:** Platform review — BERT-family model sourcing decision

## Incumbent Model

- **Model:** google-bert/bert-base-uncased
- **Downloads:** 3,292.5M (3,292,500,000)
- **Likes:** 3,067
- **Notes:** 110.1M-parameter fill-mask encoder, apache-2.0 license, English, last updated 19 Feb 2024.

## Candidate Shortlist (3 most-downloaded BERT-family models, excluding incumbent)

| # | Model Identifier | Downloads | Likes |
|---|---|---|---|
| 1 | google-bert/bert-base-cased | 3.3M | 398 |
| 2 | google-bert/bert-base-multilingual-uncased | 2.0M | 177 |
| 3 | google-bert/bert-base-multilingual-cased | 1.5M | 623 |

All three are same-architecture (bert) variants from the google-bert org, so switching cost is low; the trade-off is cased vs. multilingual coverage.

## Where Things Live

- **Word brief:** model_sourcing_brief.docx (saved in /tmp/mcp_ws/)
- **Snowflake warehouse table:** BERT_EVALUATION.MODEL_EVALUATION.BERT_MODEL_SOURCING
  - One row per shortlisted model plus one row for the incumbent (4 rows total, verified via COUNT(*) = 4)
  - Columns: model_id, model_identifier, download_count, like_count, source, recorded_at

## Next Steps

1. Review the three shortlisted candidates against search stack requirements before the platform review.
2. Validate the BERT_EVALUATION.MODEL_EVALUATION.BERT_MODEL_SOURCING table in Snowflake and schedule periodic re-pulls of Hub download/like counts.
3. Decide whether to retain bert-base-uncased or migrate to a cased/multilingual variant based on language coverage and latency needs.
