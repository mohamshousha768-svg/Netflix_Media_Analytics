# 🎬 Netflix Media & Content Analytics

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Cleaning-150458?style=flat-square&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Executive%20Dashboards-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Integrity%20Modeling-00758F?style=flat-square)](https://docs.microsoft.com/dax/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

**Prepared by:** Mohamed Nabil  
**Project Type:** End-to-End Data Analytics Portfolio & Academic Assignment Project  

---

## 📌 Project Overview & The Business Problem

### 1. Project Context
Streaming platforms manage massive, multi-faceted content catalogs. This project presents an exhaustive end-to-end data analytics study on **8,807 Netflix titles** (Movies and TV Shows). It covers the complete data lifecycle: raw data ingestion, automated Python-based ETL and data cleaning, Power Query schema transformation, relational database modeling, and an interactive Power BI executive dashboard designed to meet rigorous academic submission and professional presentation standards.

### 2. The Core Business Challenge
Content catalogs frequently contain multi-value attributes (e.g., titles co-produced across multiple countries, shared casts, and multiple genre tags). Without strict data governance:
- **Data Inflation:** Unpivoting delimited attributes causes artificial row multiplication, which distorts executive-level KPIs and total title counts.
- **Content Strategy Mismatch:** Lacking clear visibility into Movie-to-TV Show ratios, target audience age ratings, and regional output leads to suboptimal licensing investments.

This project resolves these challenges by establishing an audit-ready analytics workflow that maintains absolute data integrity.

---

## 📊 Core Metrics & Key Results

| Metric | Result Value | Strategic Impact |
| :--- | :--- | :--- |
| **Total Catalog Records** | 8,807 Unique Titles | Locked aggregate baseline preventing record duplication |
| **Total Movies Volume** | 6,131 (~69.62%) | Primary driver for rapid global subscriber acquisition |
| **Total TV Shows Volume** | 2,676 (~30.38%) | Primary driver for long-form user engagement & retention |
| **Peak Content Output Year** | 2018 | Historical high-water mark for global content licensing |
| **Metric Reconciliation Logic** | `DISTINCTCOUNT(Netflix_Titles[show_id])` | DAX engine ensuring audit-ready KPI integrity |

> ⚠️ **Data Integrity Note:** Multi-country titles were unpivoted to evaluate regional performance. Custom DAX measures were engineered to lock aggregate catalog metrics strictly at **8,807 unique titles** to prevent artificial record inflation.

---

## 🛠️ Tech Stack

| Technology | Purpose | Role in Project |
| :--- | :--- | :--- |
| **Python / Pandas** | Data Engineering & ETL | Schema inspection, null imputation, string normalization, and date parsing |
| **Power Query** | Schema Transformation | Unpivoting multi-value delimiters and preparing relational tables |
| **Power BI** | Business Intelligence | Interactive multi-page executive dashboard design |
| **DAX** | Advanced Modeling | Custom aggregate measures (`DISTINCTCOUNT`) for KPI reconciliation |
| **Git / GitHub** | Version Control | Professional repository documentation and portfolio publishing |

---

## 🔄 Phase 1: Python Data Engineering & ETL Pipeline

The pipeline begins in Python, inspecting raw dataset schemas, handling missing values, standardizing string formats, and validating data types across all records.

### Step 1: Schema Inspection & Data Type Validation
We inspect raw dataset schemas, verify column data types across all 12 attributes, and evaluate datetime parsing structures.

- **Figure 1 — Dataset Schema & Data Type Inspection (`df.dtypes`)**  
  ![Figure 1 Schema Inspection](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201024.png)

- **Figure 2 — Dataset Descriptive Statistics (`df.describe()`)**  
  ![Figure 2 Descriptive Statistics](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201159.png)

---

### Step 2: Missing Value Audit & Data Cleansing
Missing values across `Director`, `Cast`, and `Country` are identified and imputed with `'Unknown'` to prevent null propagation during visual slicing. String columns undergo whitespace trimming and standardization.

- **Figure 3 — Null Value Audit & Categorical Imputation (`isnull().sum()`)**  
  ![Figure 3 Missing Value Audit](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201219.png)

- **Figure 4 — Genre Frequency & Distribution Breakdown**  
  ![Figure 4 Genre Distribution](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201229.png)

---

### Step 3: Data Preview & Sample Inspection
Evaluating cleaned dataset rows to verify schema consistency, string formatting, and date transformations prior to exporting into Power BI.

- **Figure 5 — Date Parsing & Schema Type Verification**  
  ![Figure 5 Date Parsing Verification](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201249.png)

- **Figure 6 — Cleaned Data Head Preview (`df.head()`)**  
  ![Figure 6 Cleaned Data Preview](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201258.png)

- **Figure 7 — Multi-Value Category Count Analysis**  
  ![Figure 7 Category Count Analysis](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201304.png)

- **Figure 8 — Primary Data Records Preview (`df.head(9)`)**  
  ![Figure 8 Primary Data Preview](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20201311.png)

---

## 📈 Phase 2: Power BI Executive Dashboard & Detailed Visual Breakdown

The processed dataset feeds into a fully interactive Power BI executive dashboard equipped with global slicers (`release_year`, `country`) to allow dynamic stakeholder filtering. Below is the granular breakdown of every visual component integrated into the dashboard:

### 1. Executive KPI Scorecards (Top Banner)
* **Total Titles (`8,808`):** Serves as the primary aggregate baseline for the entire catalog.
* **Total Movies (`6,131` / `69.62%`):** Highlights the heavy volume of cinematic content dedicated to rapid user acquisition.
* **Total TV Shows (`2,676` / `30.38%`):** Represents long-form episodic investments.
* **Peak Year (`2018`):** Identifies the historical high-water mark for content licensing velocity prior to increased streaming competition.

### 2. Production Growth Over Time (Line Chart)
* **Purpose:** Plots historical content additions spanning from 1920 to 2020.
* **Findings:** Illustrates a slow baseline growth for decades, followed by an exponential surge starting around 2014–2016 and peaking sharply in 2018 before stabilizing.

### 3. Content Distribution by Rating (Column Chart)
* **Purpose:** Evaluates the catalog across target audience maturity demographics.
* **Findings:** Reveals a massive concentration in mature (`TV-MA`, `R`) and teen/family (`TV-14`, `PG-13`) classifications, demonstrating a clear strategic focus on adult and young adult viewers.

### 4. Top 10 Production Countries (Horizontal Bar Chart)
* **Purpose:** Ranks the leading geographic production hubs.
* **Findings:** The United States leads by a wide margin (~2,800+ titles), followed by India (~970+ titles), United Kingdom, Japan, South Korea, Canada, Spain, France, Mexico, and Egypt.

### 5. Content Mix - Movies vs. TV Shows (Donut Chart)
* **Purpose:** Visually contrasts single-session media against episodic content.
* **Findings:** Reinforces the strategic 70/30 equilibrium (~69.62% Movies vs. ~30.38% TV Shows).

- **Figure 9 — Executive Power BI Analytics Dashboard**  
  ![Figure 9 Executive Dashboard](Netflix_Data_Analysis_Project/Screenshots/Screenshot%202026-10-21%20215452.png)

---

## 💡 Strategic Business Recommendations

1. **Enforce Governance in DAX:** Always apply `DISTINCTCOUNT` logic when dealing with unpivoted multi-value attributes (like co-production countries) to prevent reporting inflated catalog numbers to leadership.
2. **Balanced Licensing Portfolio:** Rebalance content acquisition budgets by leveraging Movies for initial user acquisition while investing in high-engagement TV Shows to improve subscriber retention.
3. **Regional Production Focus:** Capitalize on top production hubs (United States, India, United Kingdom) while expanding co-production deals in emerging regional markets.
4. **ETL Pipeline Automation:** Standardize delimiter inputs at data collection points to streamline automated Python cleaning workflows in future catalog updates.

---

## 📁 Repository Structure

```text
Netflix_Data_Analysis_Project/
├── Code/          <- Python Jupyter Notebooks (Data Cleaning & Inspection)
├── Dashboard/     <- Power BI (.pbix) Interactive Dashboard File
├── Data/          <- Raw & Cleaned CSV Datasets
└── Screenshots/   <- Visual Documentation (Figures 1 to 9)
```


