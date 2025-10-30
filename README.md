# 📦 Automated Box Reconciliation Dashboard – Power BI Integration for SAP and Local Excel Systems

This repository hosts the Power BI visualization project designed to automate the reconciliation of box records between **SAP query data** and **locally formatted Excel-based tracking sheets**.  
The system provides real-time variance analysis, trend monitoring, and integrity reporting across multiple data sources.

---

## 🎯 Project Overview

Traditional reconciliation between SAP and local operational records often involves manual checks that are time-consuming and error-prone.  
This Power BI solution bridges the two systems, **automating data comparison and variance tracking** through linked data models and Power Query transformations.

The **core objective** is to ensure data integrity by comparing:
- `BoxType_Clean` (from local Excel transformations)
- `BoxType_SAP_Clean` (from SAP query exports)
- Variances in the number of boxes and reconciliation status

---

## 🧩 Data Sources

| Source | Description | Format |
|--------|--------------|--------|
| **SAP Query Export** | Extracted transactional data from SAP Sales Orders | Excel (.xlsx) / CSV |
| **Formatted Excel Sheet** | Processed local file with Power Query transformations and calculated columns | Excel (.xlsx) |

The Power BI dashboard consumes both datasets and models them into unified relationships for live reconciliation.

---

## ⚙️ Power BI Components

### 1. **Power Query Editor**
- Handles all data transformations, merges, and column cleaning.
- Refreshes automatically when source data changes.

### 2. **Data Model**
- Establishes relationships between SAP and Local sources.
- Includes DAX measures for key indicators such as:
  - Total Boxes
  - Mismatch Count
  - Variance Percentage

### 3. **Visual Dashboard**
- Displays comparative insights using:
  - Variance Indicator Cards
  - Trend Line Charts
  - Box Type Distribution
  - Drop-off Point Comparison
  - Mismatch Heatmaps

---

## 📈 Key Performance Indicators (KPIs)

| Metric | Formula | Purpose |
|---------|----------|----------|
| **Total Records** | `COUNTROWS(Line_Compare)` | Number of records analyzed |
| **Mismatch Count** | `COUNTROWS(FILTER(Line_Compare, BoxType_Clean <> BoxType_SAP_Clean))` | Detects inconsistencies |
| **Variance %** | `DIVIDE([Mismatch Count], [Total Records], 0)` | Measures reconciliation accuracy |

---

## 🧮 Automation and Refresh Workflow

1. Data from both SAP and Excel sources are loaded into Power BI.
2. Power BI refreshes using:
   - **Power Query transformations** (for Excel formulas and cleaning)
   - **Scheduled refresh** (via Power BI Service or Power Automate)
3. The dashboard dynamically updates variance results after every refresh.

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|----------|
| **Microsoft Excel** | Data formatting, Power Query logic |
| **SAP Query Export** | Source transactional dataset |
| **Power BI Desktop / Service** | Visualization, DAX analytics, and automation |
| **GitHub** | Version control and project documentation |

---

## 🚀 How to Use

1. Clone or download this repository:
   ```bash
   git clone https://github.com/<your-username>/Automated-Box-Reconciliation-PowerBI.git
