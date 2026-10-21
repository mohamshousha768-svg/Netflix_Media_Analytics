# 🎬 Netflix Media & Content Analytics

**Turning Media Catalog Data into Actionable Business Insights**

**Prepared by:** Mohamed Nabil  
**Project Type:** End-to-End Data Analytics  
**Tools:** Python (Pandas) · Power Query · Power BI & DAX  

---

## 📌 Project Overview

This project presents an end-to-end data analytics study on **8,807 Netflix titles** (Movies and TV Shows). The analytics pipeline combines Python-based ETL & automated data cleaning, Power Query schema transformation, and an interactive multi-page Power BI dashboard engineered with custom DAX calculations.

### 🎯 Business Problem

Content streaming platforms manage vast, complex catalogs with multi-value attributes (e.g., co-productions across multiple countries, shared cast, and multi-genre tags). 

Without proper data integrity governance:
- **Data Inflation:** Splitting delimited attributes causes row multiplication, distorting high-level executive KPIs.
- **Content Strategy Mismatch:** Lacking clear visibility on Movie vs. TV Show ratios and target audience ratings leads to suboptimal licensing investments.

This project addresses these challenges by delivering an accurate, audit-ready analytics workflow that reconciles multi-country title metrics while maintaining absolute data integrity.

---

## 📊 Key Results

| Metric | Result Value |
| :--- | :--- |
| **Total Catalog Records** | 8,807 Unique Titles |
| **Total Movies Count & Share** | 6,131 (~69.6%) |
| **Total TV Shows Count & Share** | 2,676 (~30.4%) |
| **Peak Content Output Year** | 2018 |
| **Data Integrity Metric Logic** | `DISTINCTCOUNT(Netflix_Titles[show_id])` |

> ⚠️ **Interpretation Note:** Multi-country titles were unpivoted/split to evaluate individual country outputs. Custom DAX measures were engineered to lock aggregate catalog metrics strictly at **8,807 unique titles** to prevent artificial record inflation.

---

## 🔄 Analytics Workflow

### 1. Data Preparation — Python
- Inspected raw dataset schema and evaluated missing value distributions across 8,807 records.
- Imputed missing categorical attributes in `Director`, `Cast`, and `Country` with `'Unknown'`.
- Cleaned string formatting, trimmed whitespace, and unified date structures (`date_added`).
- Feature-engineered parsed release years, months, and interval spans.

### 2. Data Modeling & DAX Engine — Power BI
- Built relational models for content categories, ratings, and release timelines.
- Applied DAX measures to maintain metric accuracy during multi-value filtering:
  ```dax
  Total Titles = DISTINCTCOUNT(Netflix_Titles[show_id])
🔍 Selected Findings1. Catalog Format BreakdownContent TypeTotal VolumePercentage ShareStrategic FunctionMovies6,13169.61%Quick Subscriber AcquisitionTV Shows2,67630.39%Multi-episode Viewer Engagement2. Rating & Audience DistributionRating ClassificationTarget DemographicCatalog ShareStrategic FocusTV-MA / RMature AdultsHighSubscription Drive & RetentionTV-14 / PG-13Teens & FamiliesHighMainstream EngagementTV-Y / GKids & ChildrenModerateLong-term Family Retention💡 Business RecommendationsValidate Reporting Metrics First: Enforce DISTINCTCOUNT logic in BI dashboards when working with unpivoted multi-country metadata to prevent reporting inflated counts to executive stakeholders.Optimize Content Acquisition Strategy: Balance high-volume Movie releases for quick subscriber attraction with long-form TV Show investments for sustained user engagement.Targeted Regional Investment: Focus content licensing budgets on high-growth regional hubs while monitoring cross-border co-production performance.Data Governance Standards: Standardize multi-value delimiter formatting (cast/country/director) at database entry points to streamline future ETL automation pipelines.🖥️ Dashboard ScreenshotsThe following visual figures document the technical workflow from initial dataset ingestion to the final interactive dashboard.Figure 1 — Dataset OverviewFigure 2 — Data QualityFigure 3 — Analytics WorkflowFigure 4 — Database VerificationFigure 5 — Landing PageFigure 6 — Overview Dashboard📁 Repository StructurePlaintextNetflix_Data_Analysis_Project/
├── Code/          <- Python Jupyter Notebooks (Data Cleaning & ETL)
├── Dashboard/     <- Power BI (.pbix) Interactive Dashboard
├── Data/          <- Raw & Cleaned Dataset CSV Files
└── Screenshots/   <- Visual Evidence (Figures 1 to 6)
⚠️ Data LimitationsSnapshot Dataset: Reflects catalog availability up to its extraction date and does not record real-time viewership or streaming minutes.Public Metadata Constraints: Financial budgets, content acquisition costs, and individual subscriber retention metrics were excluded from the public dataset.🛠️ Tools and Skills DemonstratedProgramming: Python, Pandas, NumPyETL & Data Cleansing: Missing Value Treatment, String Normalization, Feature EngineeringBusiness Intelligence & DAX: Power BI, Power Query, Data Integrity DAX Engineering (DISTINCTCOUNT)Data Analytics: Catalog Breakdown, Multi-country Slicing, KPI ReconciliationStrategic Communication: Technical Documentation, Business Reporting, Strategic Action Plans👤 AuthorMohamed NabilAI Student · Cybersecurity & Data Analytics Enthusiast
