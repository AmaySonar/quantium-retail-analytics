# Data Audit Log
## Quantium Retail Analytics Project

**Project:** Quantium Chip Category Analysis  
**Analyst:** [Your Name]  
**Institution:** University of Birmingham — MSc  
**Date:** April 2026  

---

## Phase 1 — Data Loading

| Check | Finding |
|---|---|
| Transaction file | QVI_transaction_data.xlsx |
| Customer file | QVI_purchase_behaviour.xlsx |
| Raw transaction rows | 264,836 |
| Raw customer rows | 72,637 |
| Transaction columns | DATE, STORE_NBR, LYLTY_CARD_NBR, TXN_ID, PROD_NBR, PROD_NAME, PROD_QTY, TOT_SALES |
| Nulls found | None in either file |
| DATE format issue | Excel serial integer — required conversion |

---

## Phase 2 — Transaction Cleaning

| Check | Finding | Action |
|---|---|---|
| DATE column | Excel serial format | Converted to datetime |
| Non-chip products | Salsa rows present | Removed |
| PROD_QTY outlier | Customer buying 200 units | Removed — non-retail |
| Rows removed | 2 | — |
| Rows remaining | 246,740 | — |
| PROD_QTY after cleaning | Min 1, Max 5, Mean 1.91 | Normal retail range |
| UNIT_PRICE range | $1.32 – $6.50 | No anomalies |
| Duplicates | None | — |

---

## Phase 3 — Feature Engineering

| Feature | Method | Result |
|---|---|---|
| PACK_SIZE | Regex extract (\d+)[gG] | 20 distinct sizes, 70g–380g |
| BRAND | First word of PROD_NAME | 28 raw → 20 after standardisation |
| Brand standardisation | Two-pass mapping dictionary | RRD/Red→Red Rock Deli, GrnWves→Grain Waves etc |
| Unique products | Spot check | 105 unique products verified |

---

## Phase 4 — Customer Merge

| Check | Finding |
|---|---|
| Join key | LYLTY_CARD_NBR |
| Join type | Left join |
| Rows before merge | 246,740 |
| Rows after merge | 246,739 |
| Unmatched transactions | 0 |
| Duplicate dropped in merge | 1 |
| Final columns | 13 |
| Total sales | $1,805,171.70 |

---

## Phase 5 — Metrics

| Metric | Top segment | Value |
|---|---|---|
| Total sales | Older Families — Budget | $156,863.75 |
| Avg spend per customer | Older Families — Mainstream | $34.58 |
| Purchase frequency | Older Families — Mainstream | 4.71 txns |
| Highest avg unit price | Young Singles/Couples — Mainstream | $4.07 |

---

## Phase 6 — Trial Store Analysis

| Trial store | Control store | Match score | Sales uplift | p-value | Verdict |
|---|---|---|---|---|---|
| 77 | 233 | 0.7576 | +27.8% | 0.13 | Extend trial |
| 86 | 155 | 0.7458 | +11.6% | 0.13 | Roll out |
| 88 | 91  | 0.5010 | +8.6%  | 0.09 | Re-trial |