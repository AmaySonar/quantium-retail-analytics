# Quantium Retail Analytics — Chip Category Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Tableau](https://img.shields.io/badge/Tableau-Public-orange?logo=tableau)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Programme](https://img.shields.io/badge/Quantium-Virtual%20Experience-purple)
![University](https://img.shields.io/badge/University%20of%20Birmingham-MSc-blue)

> **A full end-to-end retail analytics project simulating a professional 
> data consultancy engagement for Quantium — one of Australia's leading 
> analytics firms.**

---

## Live Dashboard

[![Tableau Dashboard](https://img.shields.io/badge/View%20Live%20Dashboard-Tableau%20Public-orange)](https://www.linkedin.com/in/amaysonar/)

---

## Project Overview

This project was completed as part of the **Quantium Data Analytics 
Virtual Experience Programme** during my MSc at the 
**University of Birmingham**, where I led a team of 7 members through 
a full retail analytics workflow — from raw data ingestion to strategic 
client recommendation.

The analysis covers **264,836 transaction records** across **271 stores**, 
**71,287 customers** and **20 chip brands** over the financial year 
July 2018 to June 2019.

---

## Business Context

The Category Manager for chips at a major Australian supermarket chain 
needed to:

- Understand which customer segments were driving chip sales
- Identify what was driving spend within each segment
- Assess whether a new in-store chip layout trial was effective
- Receive a data-driven recommendation for the next half-year 
  category strategy

---

## Project Structure

| Notebook | Description | Key outputs |
|---|---|---|
| [01 — Data Cleaning](notebooks/01_data_cleaning.ipynb) | Load, validate and clean raw transaction and customer data | Clean merged dataset, audit log |
| [02 — Customer Analysis](notebooks/02_customer_analysis.ipynb) | Segment metrics, visualisations, brand and pack size analysis | 8 charts, segment summary CSV |
| [03 — Trial Store Analysis](notebooks/03_trial_store_analysis.ipynb) | Control store selection, uplift testing, statistical significance | Trial results CSV, recommendation |

---

## Key Findings

### Customer Segments
- **Older Families — Budget** is the highest revenue segment 
  at **$156,864 (8.7% of total)**
- **Mainstream Young Singles/Couples** pay the highest unit price 
  at **$4.07** — a classic impulse buying profile
- Mainstream Young Singles/Couples are **23% more likely** to purchase 
  Tyrrells chips vs the broader population
- Family segments drive revenue through **frequency** (4.4–4.7 trips/year) 
  while singles drive it through **unit price**

### Brand & Pack Size
- **Kettle** dominates with **$390,240** — 21% of total category revenue
- **175g** is the #1 pack size at **$485,000** — 26% of all chip sales
- Bottom 6 brands contribute less than 6% combined — 
  ranging review recommended

### Trial Store Results

| Store | Control | Sales Uplift | Customer Uplift | Significant | Verdict |
|---|---|---|---|---|---|
| 77 | 233 | +27.8% | +25.2% | No (p=0.13) | Extend trial |
| 86 | 155 | +11.6% | +12.7% | **Yes (p=0.012)** | **Roll out** |
| 88 | 91  | +8.6%  | +7.2%  | No (p=0.24) | Re-trial |

> The new layout consistently drives **more customers** into the chip 
> category — not more spend per visit.

---

## Strategic Recommendation

Four prioritised actions for the Category Manager:

1. **Off-locate Tyrrells and small packs** in discretionary space near 
   Young Singles/Couples zones — capitalise on impulse buying behaviour
2. **Roll out the new layout** to stores similar to Store 86 — 
   the only statistically confirmed trial success
3. **Protect Kettle and 175g shelf space** — together they represent 
   the backbone of category revenue
4. **Target Older Families** with volume promotions — highest frequency, 
   highest total spend segment

---

## Visualisations

| Chart | Preview |
|---|---|
| Segment sales heatmap | ![heatmap](outputs/charts/chart1_sales_heatmap.png) |
| Monthly sales trend | ![trend](outputs/charts/chart5_monthly_trend.png) |
| Brand revenue ranking | ![brands](outputs/charts/chart6_brand_sales.png) |
| Trial store uplift | ![uplift](outputs/charts/uplift_summary.png) |

---

## Tools & Methods

| Category | Tools used |
|---|---|
| Language | Python 3.10 |
| Data manipulation | pandas, numpy |
| Visualisation | matplotlib, seaborn |
| Statistical testing | scipy.stats (Pearson correlation, t-test) |
| Notebook environment | Google Colab |
| Dashboard | Tableau Public |
| Presentation | PowerPoint (PptxGenJS) |
| Version control | Git / GitHub |

---

## Analytical Methods

- **Data cleaning** — outlier removal, date format correction, 
  regex feature extraction
- **Feature engineering** — brand name and pack size derived from 
  product name string
- **Customer segmentation** — 21 segments across lifestage × premium tier
- **Metric definition** — total sales, avg spend per customer, purchase 
  frequency, avg unit price
- **Control store selection** — Pearson correlation + normalised 
  magnitude distance scoring
- **Uplift testing** — scaled control comparison + independent samples 
  t-test
- **Executive reporting** — Pyramid Principle framework

---

## Data Audit Log

Full data transformation log available in 
[docs/data_audit_log.md](docs/data_audit_log.md)

| Phase | Action | Rows before | Rows after |
|---|---|---|---|
| Raw load | Transaction file loaded | — | 264,836 |
| Phase 2 | Non-chip products removed | 264,836 | 264,834 |
| Phase 2 | Outlier customer removed | 264,834 | 246,740 |
| Phase 4 | Merged with customer data | 246,740 | 246,739 |
| Phase 4 | Unmatched row dropped | 246,739 | 246,739 |

---

## How to Run

### Option 1 — Google Colab (recommended)

1. Open each notebook link above
2. Click **Open in Colab**
3. Upload the data files when prompted
4. Run all cells in order

### Option 2 — Local environment

```bash
# Clone the repository
git clone https://github.com/YOURUSERNAME/quantium-retail-analytics.git
cd quantium-retail-analytics

# Install dependencies
pip install -r requirements.txt

# Open notebooks
jupyter notebook notebooks/
```

---

## Project Context

| Detail | Information |
|---|---|
| Programme | Quantium Data Analytics Virtual Experience |
| Institution | University of Birmingham — MSc |
| Team size | 7 members |
| Role | Project Lead & Technical Lead |
| Timeline | 2026 |
| Status | Complete |

---

## Repository Structure

```
quantium-retail-analytics/
│
├── data/
│   ├── README.md
│   └── sample/
│       └── sample_transactions.csv
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_customer_analysis.ipynb
│   └── 03_trial_store_analysis.ipynb
│
├── outputs/
│   ├── charts/
│   │   ├── chart1_sales_heatmap.png
│   │   ├── chart2_sales_by_segment.png
│   │   ├── chart3_avg_spend.png
│   │   ├── chart4_purchase_frequency.png
│   │   ├── chart5_monthly_trend.png
│   │   ├── chart6_brand_sales.png
│   │   ├── chart7_pack_size_sales.png
│   │   ├── chart8_avg_unit_price.png
│   │   ├── uplift_summary.png
│   │   └── final_recommendation_chart.png
│   │
│   ├── report/
│   │   └── Quantium_Chip_Category_Report.pdf
│   │
│   └── data/
│       ├── quantium_segment_summary.csv
│       └── quantium_trial_results.csv
│
├── docs/
│   ├── data_audit_log.md
│   └── pyramid_principle_report.md
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Author
** Amay Sonar** <br>
MSc Student — University of Birmingham <br>
[LinkedIn](https://www.linkedin.com/in/amaysonar/) | 
[Tableau Public](https://public.tableau.com/app/profile/amay1318/vizzes) |
[Email](mailto:amaysonar@gmail.com)

---

*This project was completed as part of the Quantium Virtual Experience 
Programme. Raw data files are not included in this repository in 
accordance with Quantium's data usage terms. A 50-row sample is 
available in the data/sample/ folder for reference.*
