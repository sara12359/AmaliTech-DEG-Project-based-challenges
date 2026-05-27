# The "Last Mile" Logistics Auditor — Veridi Logistics

---

## A. Executive Summary

An audit of 99,441 orders from the Olist Brazilian E-Commerce Dataset revealed that Veridi Logistics has a **7.9% late delivery rate**, with the problem heavily concentrated in Brazil's Northeast region. States like **Alagoas (AL) at 24%** and **Maranhão (MA) at 20%** suffer disproportionately high late delivery rates compared to southeastern states like São Paulo (5.5%), confirming the issue is **regional, not nationwide**. Analysis of customer reviews proves a direct link between delivery delays and negative sentiment — orders delivered very late average only **1.72 stars** compared to **4.15 stars** for on-time deliveries. The root cause is a combination of inaccurate estimated delivery dates and insufficient logistics infrastructure in remote northeastern states far from the main distribution centers.

---

## B. Project Links

- **Notebook:** [Google Colab](https://colab.research.google.com/drive/1yQj9oAulWp03vZ7gOJuFu7oVY10sa5wX?usp=sharing)
- **Dashboard:** [Tableau Public](https://public.tableau.com/app/profile/sara.salah5077/viz/Book1_17707382813860/Dashboard1)
- **Presentation:** [Google Slides](https://docs.google.com/presentation/d/1yA8eE2QDj-kQwhZ_ru7TFFBO42hZCsk0Udbvd810wSo/edit?usp=sharing)

---

## C. Technical Explanation

### Data Cleaning
- Loaded 6 CSV files from the Olist dataset and joined them into a single master DataFrame (114,092 rows × 33 columns) using `order_id`, `customer_id`, and `product_id` as join keys.
- Checked for duplicate rows after all joins — **0 duplicates found**.
- Converted date columns to `datetime` format for accurate delay calculations.
- Excluded cancelled and unavailable orders, keeping only `delivered` orders (110,840 rows) for delay analysis.
- Handled missing values in `review_score` and `Days_Difference` by dropping null rows before sentiment analysis.
- Translated Portuguese product category names to English using the `product_category_name_translation.csv` file.

### Candidate's Choice: Monthly Late Delivery Trend
I added a **Monthly Late Delivery Rate Over Time** line chart as the Candidate's Choice feature. This analysis tracks the percentage of late orders month by month from September 2016 to August 2018. This feature adds direct business value because it reveals **seasonal spikes** — notably in November 2017 and March 2018 — which likely correspond to holiday season demand surges. By monitoring this KPI monthly, the operations team can proactively scale logistics capacity before high-demand periods rather than reacting after negative reviews have already accumulated. This transforms the audit from a one-time report into an ongoing monitoring tool.

---

## Dataset

- **Source:** [Kaggle - Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Note:** Raw CSV files are not included in this repository. Download from Kaggle and place in the same folder as the notebook.

---

*Project submitted as part of the AmaliTech Data Engineering Graduate Program — May 2026*
