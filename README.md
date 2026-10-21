# 🎬 Netflix Media & Content Analytics

**Turning Raw Catalog Data into Actionable Streaming & Business Insights**

**Prepared by:** Mohamed Nabil  
**Project Type:** End-to-End Data Analytics  
**Tools:** Python (Pandas) · Power Query · Power BI & DAX  

---

## 📌 Project Overview & The Business Problem

### 1. Project Context
This project delivers an end-to-end data analytics study analyzing **8,807 Netflix titles** (Movies and TV Shows). It bridges the gap between raw data extraction, automated Python cleaning, relational data modeling, and executive-level Power BI reporting.

### 2. The Core Business Challenge
Streaming platforms manage massive, complex catalogs featuring multi-value attributes (e.g., titles co-produced across multiple countries, shared casts, and multi-genre tags). Without strict data governance:
- **Data Inflation:** Unpivoting delimited attributes causes artificial row multiplication, distorting high-level executive KPIs and total title counts.
- **Content Strategy Mismatch:** Lacking clear visibility into Movie-to-TV Show ratios and target audience ratings leads to suboptimal licensing investments.

This project resolves these challenges by establishing an audit-ready analytics workflow that maintains absolute data integrity.

---

## 🔄 Technical Workflow: From Raw Data to Relational Model (Python & Power Query)

To fix data quality issues and prepare the data for modeling, the pipeline starts with Python-based cleaning followed by Power Query schema structuring.

### Step 1: Data Ingestion & Quality Inspection
We first inspect the raw dataset schema, evaluate missing value distributions across all 8,807 records, and handle missing categorical attributes in `Director`, `Cast`, and `Country` by imputing them as `'Unknown'`.

* **Figure 1 — Raw Dataset Schema Overview**  
  ![Raw Dataset Schema Overview](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201024.png)

* **Figure 2 — Missing Value Treatment & Data Quality Report**  
  ![Missing Value Treatment](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201159.png)

### Step 2: Schema Transformation & Database Verification
After Python cleaning, Power Query handles unpivoting multi-value delimiters, standardizing date structures (`date_added`), and extracting release years and months. The final relational schema is then verified to ensure seamless table relationships.

* **Figure 3 — Power Query ETL & Unpivoting Workflow**  
  ![Power Query ETL Workflow](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201219.png)

* **Figure 4 — Relational Database Schema Verification**  
  ![Relational Database Schema](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201229.png)

---

## 📊 Core Metrics & Data Integrity Engine (Power BI & DAX)

To prevent data inflation caused by unpivoted multi-country relationships, custom DAX measures were engineered to lock aggregate catalog metrics strictly at **8,807 unique titles**.

### Key Results Summary
| Metric | Result Value |
| :--- | :--- |
| **Total Catalog Records** | 8,807 Unique Titles |
| **Total Movies Count & Share** | 6,131 (~69.6%) |
| **Total TV Shows Count & Share** | 2,676 (~30.4%) |
| **Peak Content Output Year** | 2018 |
| **Data Integrity Metric Logic** | `DISTINCTCOUNT(Netflix_Titles[show_id])` |

> ⚠️ **DAX Implementation Logic:** 
> ```dax
> Total Titles = DISTINCTCOUNT(Netflix_Titles[show_id])
> ```

---

## 🔍 Interactive Dashboard & Analytical Findings

The Power BI dashboard translates clean data into visual, multi-page executive insights.

### 1. Executive Navigation & High-Level Overview
The landing page sets up the analysis environment, leading directly into the high-level overview dashboard that tracks total catalog distribution across years and types.

* **Figure 5 — Executive Dashboard Landing Page**  
  ![Executive Dashboard Landing Page](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201249.png)

* **Figure 6 — High-Level Catalog Overview Dashboard**  
  ![High-Level Catalog Overview](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201258.png)

### 2. Content Format & Audience Demographics Analysis
A deeper dive into the catalog reveals distinct format strategies:
- **Movies (6,131 Titles / 69.61% Share):** Drives quick subscriber acquisition across global markets.
- **TV Shows (2,676 Titles / 30.39% Share):** Drives long-form, multi-episode viewer engagement and retention.
- **Audience Ratings:** High volume concentrated in **TV-MA / R** (mature content acquisition) and **TV-14 / PG-13** (mainstream family engagement).

* **Figure 7 — Content Format Breakdown (Movies vs. TV Shows)**  
  ![Content Format Breakdown](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201304.png)

* **Figure 8 — Rating Classification & Audience Demographics**  
  ![Rating Classification & Audience](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201311.png)

### 3. Regional Trends & Advanced Insights
Analyzing geographic distribution and release timelines highlights high-growth regional production hubs and historical content output peaks (notably in 2018).

* **Figure 9 — Geographic Co-Production & Advanced Trends**  
  ![Geographic Co-Production & Trends](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20215452.png)

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

## ⚠️ Data Limitations & Tools

### Data Limitations
- **Snapshot Dataset:** Reflects catalog availability up to its extraction date and does not record real-time streaming minutes or live viewership.
- **Public Metadata Constraints:** Financial budgets, exact licensing acquisition costs, and individual subscriber churn metrics were excluded from the public dataset.

### Tools & Skills Demonstrated
- **Programming & ETL:** Python, Pandas, NumPy, Missing Value Treatment, String Normalization, Feature Engineering
- **Business Intelligence & DAX:** Power BI, Power Query, Data Integrity DAX Engineering (`DISTINCTCOUNT`)
- **Strategic Communication:** Technical Documentation, Business Reporting, KPI Reconciliation

---

## 👤 Author

**Mohamed Nabil**  
*AI Student · Cybersecurity & Data Analytics Enthusiast*
