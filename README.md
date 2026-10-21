# 🎬 Netflix Media & Content Analytics

**Turning Data Catalog into Actionable Streaming & Business Insights**

**Prepared by:** Mohamed Nabil  
**Project Type:** End-to-End Data Analytics  
**Tools:** Python (Pandas) · Power Query · Power BI & DAX  

---

## 📌 Project Overview & Business Problem

### Overview
This project presents an end-to-end data analytics study on **8,807 Netflix titles** (Movies and TV Shows). The analytics pipeline combines Python-based ETL & automated data cleaning, Power Query schema transformation, and an interactive multi-page Power BI dashboard engineered with custom DAX calculations.

### Business Problem
Streaming platforms manage massive, complex catalogs featuring multi-value attributes (e.g., co-productions across multiple countries, shared casts, and multiple genre tags). Without strict data governance:
- **Data Inflation:** Unpivoting delimited attributes causes artificial row multiplication, which distorts executive-level KPIs.
- **Content Strategy Mismatch:** Lacking clear visibility into Movie-to-TV Show ratios and target audience ratings leads to suboptimal licensing investments.

This project resolves these challenges by delivering an audit-ready analytics workflow that accurately reconciles multi-country title metrics while maintaining absolute data integrity.

---

## 📊 Key Results & Core Metrics

- **Total Catalog Records:** 8,807 Unique Titles
- **Total Movies Count & Share:** 6,131 (~69.6%)
- **Total TV Shows Count & Share:** 2,676 (~30.4%)
- **Peak Content Output Year:** 2018
- **Data Integrity Metric Logic:** `DISTINCTCOUNT(Netflix_Titles[show_id])`

> ⚠️ **Interpretation Note:** Multi-country titles were split/unpivoted to properly evaluate individual country outputs. Custom DAX measures were engineered to lock aggregate catalog metrics strictly at **8,807 unique titles** to prevent artificial record inflation.

---

## 🔄 Analytics Workflow & Technical Pipeline

### 1. Data Preparation & Cleaning (Python)
- Inspected raw dataset schemas and evaluated missing value distributions across all 8,807 records.
- Imputed missing categorical attributes in `Director`, `Cast`, and `Country` with `'Unknown'`.
- Cleaned string formatting, trimmed whitespace, and unified date structures (`date_added`).
- Feature-engineered parsed release years, months, and interval spans.

### 2. Data Modeling & DAX Engine (Power BI)
- Built robust relational models connecting content categories, ratings, and release timelines.
- Applied custom DAX measures to maintain absolute metric accuracy during complex multi-value filtering:
  `Total Titles = DISTINCTCOUNT(Netflix_Titles[show_id])`

---

## 🔍 Selected Findings & Visual Evidence

### Part 1: Dataset & Data Quality Structure
*The following figures validate the initial data ingestion, missing value treatment, and database verification.*

* **Figure 1 — Dataset Overview**  
  ![Figure 1 Dataset Overview](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201024.png)
* **Figure 2 — Data Quality Validation**  
  ![Figure 2 Data Quality](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201159.png)
* **Figure 3 — Analytics Pipeline Workflow**  
  ![Figure 3 Analytics Workflow](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201219.png)
* **Figure 4 — Database Schema Verification**  
  ![Figure 4 Database Verification](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201229.png)

---

### Part 2: Catalog Breakdown & Audience Distribution
*The following interactive dashboard pages illustrate content format performance and target demographics.*

- **Movies (6,131 Titles / 69.61% Share):** Drives quick subscriber acquisition across global markets.
- **TV Shows (2,676 Titles / 30.39% Share):** Drives long-form, multi-episode viewer engagement and retention.
- **Rating Breakdown:** High volume concentrated in **TV-MA / R** (mature content acquisition) and **TV-14 / PG-13** (mainstream family engagement).

* **Figure 5 — Dashboard Landing Page**  
  ![Figure 5 Landing Page](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201249.png)
* **Figure 6 — High-Level Overview Dashboard**  
  ![Figure 6 Overview Dashboard](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201258.png)
* **Figure 7 — Content Analysis View**  
  ![Figure 7 Content Analysis View](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201304.png)

---

### Part 3: Regional Trends & Advanced Insights
*Geographic performance, cross-border co-production metrics, and advanced trend analyses.*

* **Figure 8 — Geographic & Trend Breakdown**  
  ![Figure 8 Geographic Breakdown](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201311.png)
* **Figure 9 — Advanced Analytics & Insights**  
  ![Figure 9 Advanced Insights](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20215452.png)

---

## 💡 Strategic Business Recommendations

1. **Validate Reporting Metrics First:** Enforce `DISTINCTCOUNT` logic in BI dashboards when working with unpivoted multi-country metadata to prevent reporting inflated numbers to executive stakeholders.
2. **Optimize Content Acquisition Strategy:** Balance high-volume Movie releases for quick subscriber attraction with long-form TV Show investments for sustained user retention.
3. **Targeted Regional Investment:** Focus content licensing budgets on high-growth regional hubs while monitoring cross-border co-production performance.
4. **Data Governance Standards:** Standardize multi-value delimiter formatting (cast/country/director) at database entry points to streamline future ETL automation pipelines.

---

## 📁 Repository Structure

- **Code/** — Python Jupyter Notebooks (Data Cleaning & ETL)
- **Dashboard/** — Power BI (.pbix) Interactive Dashboard
- **Data/** — Raw & Cleaned Dataset CSV Files
- **Screenshots/** — Visual Evidence (Figures 1 to 9)

---

## ⚠️ Data Limitations

- **Snapshot Dataset:** Reflects catalog availability up to its extraction date and does not record real-time streaming minutes or live viewership.
- **Public Metadata Constraints:** Financial budgets, exact licensing acquisition costs, and individual subscriber churn metrics were excluded from the public dataset.

---

## 🛠️ Tools & Skills Demonstrated

- **Programming:** Python, Pandas, NumPy
- **ETL & Data Cleansing:** Missing Value Treatment, String Normalization, Feature Engineering
- **Business Intelligence & DAX:** Power BI, Power Query, Data Integrity DAX Engineering (`DISTINCTCOUNT`)
- **Data Analytics:** Catalog Breakdown, Multi-country Slicing, KPI Reconciliation
- **Strategic Communication:** Technical Documentation, Business Reporting, Strategic Action Plans

---

## 👤 Author

**Mohamed Nabil**  
*AI Student · Cybersecurity & Data Analytics Enthusiast*
