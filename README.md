# 🎬 Netflix Media & Content Analytics

**Turning Media Catalog Data into Actionable Business Insights**

**Prepared by:** Mohamed Nabil  
**Project Type:** End-to-End Data Analytics  
**Tools:** Python (Pandas) · Power Query · Power BI & DAX  

---

## 📌 Project Overview

This project analyzes **8,807 Netflix titles** (Movies & TV Shows) to explore content production patterns, distribution mix, rating categories, and country contributions.

The workflow combines Python-based data cleaning & preprocessing, Power Query transformations, and an interactive Power BI dashboard featuring advanced DAX measures designed to handle multi-country catalog entries accurately.

---

## 📊 Key Results

| Metric | Result |
| :--- | :--- |
| **Total Unique Titles** | 8,807 |
| **Movies Count & Share** | 6,131 (~69.6%) |
| **TV Shows Count & Share** | 2,676 (~30.4%) |
| **Peak Content Output Year** | 2018 |
| **Data Integrity Logic** | `DISTINCTCOUNT(show_id)` |

> **Interpretation Note:** Multi-country titles were unpivoted/split to analyze geographical outputs. To prevent data inflation in primary metrics, custom DAX measures were engineered to lock total unique titles strictly at **8,807**.

---

## 🔄 Analytics Workflow

### 1. Data Preparation — Python
- Inspected raw dataset schema and identified missing fields.
- Imputed missing values (`Director`, `Cast`, and `Country`) with `'Unknown'`.
- Cleaned string formatting, trimmed whitespace, and unified date structures.
- Exported clean, structured datasets for BI analysis.

### 2. Power BI Dashboard & DAX Logic
Created interactive dashboard pages featuring:
- **Overview & Distribution:** Movies vs. TV Shows mix and release timelines.
- **Geographical Breakdown:** Country-level outputs without row multiplication.
- **DAX Measure Applied:**
  ```dax
  Total Titles = DISTINCTCOUNT(Netflix_Titles[show_id])
