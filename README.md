# 📊 TechNova Electronics — B2B Sales Analytics

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Tool-Power%20Query-2E75B6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-B2B%20Sales%20Analytics-orange?style=for-the-badge)

---

## 🏢 Project Overview

End-to-end **Business Intelligence project** simulating a real Junior BI Analyst role at **TechNova Electronics** — a B2B electronics distributor operating across 4 regions of India.

The raw data was exported from **Salesforce CRM**, **SAP ERP**, and **manual Excel reports** — exactly like real companies — and intentionally contained real-world data quality issues. The task was to clean the data, perform full analysis, compute business KPIs, and build an interactive executive dashboard.

---

## 🎯 Business Problem

Management needed a **single source of truth** for sales performance. Every regional manager was sending different Excel files with conflicting numbers. The MD wanted one clean, interactive dashboard showing:

- How is the company performing against targets?
- Which regions, products, and managers are driving growth?
- Where are the hidden business problems?

---

## 📁 Project Files

> **All files available on Google Drive — click below to access:**
>
> 🔗 **[Access All Project Files — Google Drive](https://drive.google.com/drive/folders/1RbMZ8jTjSlzH8J-W9cf0rECV1_vpM_hp?usp=drive_link)**

| File | Description |
|------|-------------|
| `BI_Case_Study_Raw_Dataset.xlsx` | Raw messy dataset — 67,000 rows across 4 sheets |
| `TechNova_Sales_Dashboard_Sahil_v1.xlsx` | Cleaned data + Interactive Executive Dashboard |
| `TechNova_BI_Project_Summary_Sahil.docx` | Complete project summary report |
| `BRD_Sales_Analytics_Case_Study.docx` | Business Requirement Document |

---

## 📊 Dataset Details

| Attribute | Details |
|-----------|---------|
| Rows | ~67,000 orders |
| Sheets | 4 — Sales Transactions, Customer Master, Product Master, Sales Target |
| Columns | 25 columns per transaction |
| Time Period | January 2023 — December 2025 |
| Data Sources | Salesforce CRM + SAP ERP + Manual Excel |
| Business Domain | B2B Electronics Distribution |

---

## 🔍 Phase 1 — Data Audit

Before touching anything — audited the raw dataset and identified:

- Mixed date formats across one column — DD/MM/YYYY, D-Mon-YY, YYYY-MM-DD, Excel serial numbers
- Inconsistent text values — `north`, `NORTH`, `North `, ` NORTH`
- Blank values in critical columns — Customer Name, Region, Sales Manager
- Duplicate order records from CRM + ERP export overlap
- Wrong calculated columns — Gross Sales, Net Sales, Profit

---

## 🧹 Phase 2 — Data Cleaning

**12 data quality issues found, documented, and resolved:**

| # | Issue | Column | Rows Affected | Resolution |
|---|-------|--------|---------------|------------|
| 1 | Mixed case text | Region | ~3,000 | TRIM(PROPER()) formula |
| 2 | Mixed case text | Customer_Name | All rows | TRIM(PROPER()) formula |
| 3 | Mixed case text | Customer_Type | All rows | TRIM(PROPER()) formula |
| 4 | Mixed date formats | Order_Date | All rows | Power Query Date conversion |
| 5 | Exact duplicate rows | All columns | 1,001 removed | Remove Duplicates tool |
| 6 | Duplicate Order_ID | Order_ID | 1,898 flagged | COUNTIF flag column |
| 7 | Missing Customer_Name | Customer_Name | ~630 rows | VLOOKUP from Customer Master |
| 8 | Missing Region / Manager | Region, Manager | ~3,000 rows | Replaced with Unknown |
| 9 | Wrong calculations | Gross/Net/Profit | 4,507 / 3,652 / 63,466 | Recalculated with correct formulas |
| 10 | Negative Quantity | Quantity | 1,316 rows | Flagged as returns |
| 11 | Missing Customer_ID | Customer_ID | 630 rows | Assigned placeholder C0000 |
| 12 | Missing Order_Date | Order_Date | 1,359 rows | Flagged and excluded from trends |

---

## 📈 Phase 3 — Analysis (14 Pivot Tables)

### Sales Analysis
- Monthly Revenue Trend — FY 2023 to 2025
- Region wise Performance — Revenue, Profit, Margin %
- Sales Manager Ranking — 10 managers compared
- Year-over-Year Growth
- Sales Channel Mix

### Customer Analysis
- Top 10 Customers by Revenue
- Customer Segment Breakdown — Enterprise, Mid-Market, SMB, Government
- New vs Existing Customer Trend

### Product Analysis
- Top 10 Products by Revenue and Profit
- Category Revenue Contribution
- Category Profitability Matrix

### Discount Analysis
- Average Discount by Category
- Discount by Sales Manager
- High Discount Customers

---

## 💡 Key Business Insights Discovered

> These insights were discovered independently by analysing the data — not given upfront.

**1. Revenue Declined in 2024 then Recovered**
Revenue dropped **-5.21%** in 2024 vs 2023, then partially recovered **+3.31%** in 2025. Business is stabilising but not yet back to 2023 peak.

**2. North vs South — The Revenue-Margin Paradox**
North generates highest revenue (₹137 Cr) but South has the highest profit margin (36.85%). North is winning deals through competitive pricing while sacrificing margin.

**3. Mobile Category — Structural Margin Problem**
Mobile is #2 by revenue (₹144 Cr) but has the **worst profit margin at 21.34%** across all 11 categories. Discount analysis confirmed this is NOT caused by heavy discounting — it is a supplier cost structure problem.

**4. Desktop is the Star Category**
Desktop is #1 by revenue (₹150 Cr) AND has a strong profit margin (39%). Only category combining high volume with good margin — deserves more sales focus.

**5. Discount Policy is Healthy**
Discount analysis across all categories and managers showed a uniform ~11% discount rate. Margin differences are driven entirely by **product mix**, not discount behaviour.

---

## 📊 Executive Dashboard

Built a fully interactive single-screen dashboard in Excel:

| Component | Details |
|-----------|---------|
| KPI Cards | Total Revenue, Total Profit, Profit Margin %, Total Orders, YoY Growth, Top Region |
| Line Chart | Monthly Revenue Trend — 36 months across FY 2023–2025 |
| Bar Chart | Region wise Revenue and Profit comparison |
| Donut Chart | Product Category Revenue Mix — 11 categories |
| Bar Chart | Top 10 Customers ranked by Revenue |
| Timeline Slicer | Interactive year/month filter |
| Region Slicer | Filter all visuals by North/South/East/West |
| Category Slicer | Filter by Product Category |
| Manager Slicer | Filter by Sales Manager |
| Status Slicer | Filter by Order Status |

---

## 🛠️ Skills Demonstrated

| Skill Area | Tools and Techniques |
|------------|---------------------|
| Data Cleaning | Power Query, TRIM(PROPER()), VLOOKUP, COUNTIF, Find & Replace |
| Data Analysis | 14 Pivot Tables, Calculated Fields, Grouping, Sorting, Filtering |
| Data Validation | Formula verification — Gross Sales, Net Sales, Profit cross-checks |
| Dashboard Design | KPI Cards, Line, Bar, Donut charts, Slicers, Timeline |
| Documentation | Data Quality Report, Business Requirement Document |
| Business Skills | Insight generation, Data storytelling, Executive presentation |

---

## 📚 Key Learnings

- Real-world data is never clean — even a single column can have 7+ variants of the same value
- Data cleaning takes 60–70% of total project time in a real BI role
- Always verify calculated columns — 63,466 rows had wrong Profit values
- Never clean on raw data — always work on a copy and document every change
- Insights come from asking the right questions — Mobile margin problem was about supplier costs, not discounts
- A good dashboard tells a story — not just charts, but insights that drive decisions

---

---

## 👤 About

**Sahil**
B.Tech Computer Science Engineering — GTB4CEC, GGSIPU (Batch 2022–26)
Business Analytics Intern — Polycab India Limited

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](www.linkedin.com/in/sahil-lakra-5349b12b4)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/SahilLakra08)

---

*This project was completed as part of a self-directed BI Analyst training program using a realistic case study dataset.*
