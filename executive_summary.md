# Executive Summary: Model Sourcing Brief

## Incumbent Model
Our current production model is **google-bert/bert-base-uncased**. Current Hub stats: approximately **3,293.6M downloads** and **3,070 likes**. The incumbent is a 110.1M-parameter BERT encoder (fill-mask task, Apache-2.0 license).

## Team Hugging Face Account
Our team's access is tied to the Hugging Face account **@lhz7891444** (user account ID: 68805cebc41d25c21ef2183e). This is a personal user account (not an organization) with a personal access token bearing write role. No organization memberships are visible to the current authentication method.

## Candidate Shortlist (Top 3 BERT-family models by downloads, excluding incumbent)

| Model Identifier | Downloads | Likes |
|------------------|-----------|-------|
| google-bert/bert-base-cased | 3.3M | 398 |
| google-bert/bert-base-multilingual-uncased | 2.0M | 177 |
| google-bert/bert-base-multilingual-cased | 1.5M | 623 |

## Warehouse Record
The evaluation data has been loaded into Snowflake at the fully qualified table path: **BERT_MODEL_SHORTLIST.EVAL.MODEL_SOURCING**. The table contains one row per shortlisted model plus one row for the incumbent, each with model identifier, download count, and like count. A verification query returned a row count of **4**, confirming all records are successfully loaded.

## Deliverables
- **Word brief:** model_sourcing_brief.docx (contains Incumbent Model, Candidate Shortlist with table, Warehouse Record, and Next Steps sections)
- **Snowflake table:** BERT_MODEL_SHORTLIST.EVAL.MODEL_SOURCING (4 rows verified)
- **This file:** executive_summary.md (executive summary of the sourcing brief)

## Next Steps
- Request a code review on the shortlisted models to validate download volume and community adoption before committed procurement.
- Refresh the BERT_MODEL_SHORTLIST.EVAL.MODEL_SOURCING table monthly with updated download and like figures from the Hugging Face Hub.
- Present this brief at the upcoming platform review to decide whether to retain google-bert/bert-base-uncased or adopt one of the three candidates.
