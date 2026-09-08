# Stakeholder-Insights-and-Performance-Dashboard
Interactive Tableau dashboard analysing insurance stakeholder premium trends, profitability &amp; shareholding structure — built end-to-end with BRD, testing &amp; documentation.
# 📊 Stakeholder Insights and Performance Dashboard

**An interactive Tableau dashboard for insurance/BFSI stakeholder analytics — premium trends, profitability, shareholding structure, and asset distribution.**

![Tableau](https://img.shields.io/badge/Tableau-Public-262D79?style=flat-square&logo=tableau)
![Excel](https://img.shields.io/badge/Data-Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-2E7D32?style=flat-square)
![Type](https://img.shields.io/badge/Type-Portfolio%20Project-262D79?style=flat-square)

---

## 🖼️ Dashboard Preview

![Dashboard Preview](https://github.com/mahesh735-ai/Stakeholder-Insights-and-Performance-Dashboard/blob/main/Dashboard.png)

> 📄 A static PDF export is also included: [`Stakeholder_Insights_and_Performance_Dashboard.pdf`](https://github.com/mahesh735-ai/Stakeholder-Insights-and-Performance-Dashboard/blob/main/User_Guide.docx)
---

##  Overview

This project simulates a **real-world BI project lifecycle** end-to-end — not just building charts, but following the same Requirement → Data → Build → Test → Document workflow used on client engagements:

`Business Requirement Document (BRD) → Data Understanding → Dashboard Development in Tableau → Unit Testing → User Guide`

**Why this project exists:** my primary BI tool is **Power BI**, but several companies expect Tableau as well — this project keeps that skill active and demonstrates it with a complete, documented, portfolio-ready build.

---

## 🎯 Business Context (Simulated)

A fictional insurance company needs one consolidated view of premium performance, profitability, and shareholding/stakeholder structure to support leadership decisions — the full requirement is documented in [`Refined_BRD.docx`](https://github.com/mahesh735-ai/Stakeholder-Insights-and-Performance-Dashboard/blob/main/BRD.docx).

---

## 🗂️ Dataset

| Detail | Value |
|---|---|
| Source file | `Finance_record.xlsx` (single sheet: *Finance Sheet*) |
| Size | ~2,000+ records, spanning 2014–2024 |
| Fields | ID, Stakeholder, Insurer, Value Created, Shareholding Pattern, City, Brokers, Premium, Date, Profitability, Cost Ratio, Assets Under Management, Education, Policy Tenure, Gender, Age |
| Cleaning required | Minimal — data was pre-validated (checked via filter for blanks/nulls) |

---

## ✅ What the Dashboard Includes

**4 KPI cards**
| KPI | Value | Logic |
|---|---|---|
| Total Premium | 245.9B | `SUM([Premium])` |
| Average Age of Stakeholder | 34.45 | `AVG([Age])` |
| Equity Value Created | 230.8B | `IF [Assets under management]='Equity' THEN [Value Created] ELSE 0 END` |
| Highest Value Created by Insurer | 49.17M | `MAX([Value Created])` |

**6 chart views**
- Total Value Created by Insurer (bar)
- Premium Over Time, 2014–2024 (stacked bar by premium type)
- Shareholding Distribution — Retail / DII / FII / Promoters (**donut chart**, built via Tableau's dual-axis trick since Tableau has no native donut)
- Cost Ratio vs. Profitability (side-by-side bar)
- Profitability by City and Tenure (colour-shaded crosstab / heatmap)
- Assets Under Management by Stakeholder (bar, split by Equity/Debt)

**7 filters** — City, Stakeholder, Assets Under Management, Profitability, Premium, Gender, Month/Year of Date — all applied at the **data-source level**, so one selection updates every chart and KPI simultaneously.

**1 PDF export button** — built using Tableau's native Download object.

---

## 🛠️ Tools & Techniques Used

- **Tableau Desktop / Public** (2026.2)
- Calculated fields (`IF` logic, helper field for donut chart)
- Dual-axis chart merging (for the donut chart)
- Horizontal/Vertical containers with "Distribute Contents Evenly" for a clean, responsive layout
- Data-source-level filter scoping
- Manual Unit Testing (dashboard KPI values cross-checked against raw Excel aggregates)

---

## 📁 Repository Structure

```
stakeholder-insights-tableau-dashboard/
│
├── README.md                                          ← you are here
├── Tableau_Dashboard_project.twb                       ← Tableau workbook (source file)
├── Finance_record.xlsx                                 ← source dataset
│
├── docs/
│   ├── Refined_BRD.docx                                ← Business Requirement Document
│   ├── Refined_User_Guide.docx                         ← User Guide
│   └── Tableau_Project_Revision_Notes.pdf              ← build notes / self-revision doc
│
├── exports/
│   └── Stakeholder_Insights_and_Performance_Dashboard_downloaded.pdf   ← static PDF export
│
└── assets/
    └── dashboard-preview.png                           ← dashboard screenshot for this README
```

---

##  How to Explore

1. **View the workbook interactively:** open `Tableau_Dashboard_project.twb` in [Tableau Desktop](https://www.tableau.com/products/desktop) or [Tableau Public](https://public.tableau.com/) (free).
2. **View a static snapshot:** open the PDF in `exports/`.
3. **Read the process:** see `docs/Refined_BRD.docx` (requirements) and `docs/Refined_User_Guide.docx` (how to use it).

---

## 🧠 Skills Demonstrated

`Tableau` · `Calculated Fields` · `Dual-Axis Charts` · `Dashboard Design (Containers/Layout)` · `Data Cleaning` · `KPI Design` · `BI Requirement Gathering (BRD)` · `Unit Testing` · `Technical Documentation`

---

## 👤 Author

**Mahesh** — Final-year B.Tech CSE student | Data Analyst (Power BI, SQL, Python) | building Tableau alongside Power BI for a broader BI tool stack.

---

## 📄 License

This project uses a synthetic/illustrative dataset for practice purposes only and is shared for portfolio and learning use.
