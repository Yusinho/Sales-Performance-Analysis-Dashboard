# 🛒 Keithston Grocery Store — Sales Performance Analysis Dashboard

### An Excel Pivot Table & Dashboard Analytics Project

---

## 📌 Table of Contents

1. [Project Overview](#-project-overview)
2. [Dataset Description](#-dataset-description)
3. [Data Cleaning & Preparation](#-data-cleaning--preparation)
4. [Calculated Fields](#-calculated-fields)
5. [Business Questions Addressed](#-business-questions-addressed)
6. [Dashboard Architecture](#-dashboard-architecture)
7. [Detailed Findings by Visual](#-detailed-findings-by-visual)
8. [Key Insights](#-key-insights)
9. [Data Limitations & Unanswerable Questions](#-data-limitations--unanswerable-questions)
10. [Recommendations](#-recommendations)
11. [Tools & Tech Stack](#-tools--tech-stack)
12. [How to Use This Repo](#-how-to-use-this-repo)
13. [Author](#-author)
14. [Disclaimer](#-disclaimer)

---

## 🎯 Project Overview

This project analyzes **800 sales transactions** from Keithston Grocery Store using Microsoft Excel Pivot Tables and dashboard visualization techniques. The goal was to move beyond a simple sales report and answer a structured set of business questions covering transaction behavior, customer demographics, product performance, regional trends, and profitability — turning raw transactional data into a single-page, slicer-driven decision-support tool for store management.

Where a requested analysis could not be reliably answered because the underlying dataset lacked the necessary structure (e.g., a field that wasn't captured), that limitation is explicitly documented rather than papered over — see [Data Limitations & Unanswerable Questions](#-data-limitations--unanswerable-questions).

---

## 🗂️ Dataset Description

The dataset contains **800 individual sales transactions**, capturing:

| Category | Fields |
|---|---|
| **Transaction Info** | Transaction ID, Transaction Date |
| **Customer Demographics** | Customer ID, Gender |
| **Product Details** | Product Name, Product Category, Unit Price, Cost Price |
| **Sales Metrics** | Quantity Sold, Sales Value |
| **People & Geography** | Salesperson, Region |

This structure supports **multidimensional analysis** — the dashboard can be sliced simultaneously by time, product, customer gender, salesperson, and region.

**Reference dimensions captured in the dashboard slicers:**
- **Regions (5):** Abuja, Ibadan, Kano, Lagos, Port Harcourt
- **Salespersons (8):** Ade, Bola, Chroma, Emeka, Fatima, John, Ngozi, Tunde
- **Product Categories (10):** Bakery, Beverages, Dairy, Grains, Household, Legumes, Protein, Roots, Snacks, Spread
- **Products (10):** Beans, Bread, Butter, Eggs, Milk, Plantain Chips, Rice, Soap, Soft Drink, Yam
- **Gender:** Female, Male

---

## 🧹 Data Cleaning & Preparation

Prior to analysis, the dataset was reviewed for completeness and analytical readiness:

- **Completeness check:** No missing values affecting the core metrics (Quantity Sold, Unit Price, Cost Price, Sales Value) were identified
- **Consistency check:** Product, category, region, and salesperson labels were validated for consistent spelling/formatting to prevent pivot table fragmentation (e.g., "Port Harcourt" vs. "PortHarcourt" being treated as separate categories)
- **Date validation:** Transaction dates were confirmed to fall within the analysis window used for the Q2 and daily trend visuals (April–June 2025)

---

## 🧮 Calculated Fields

Four calculated fields were built to enable the profitability analysis at the core of this dashboard:

| Field | Formula |
|---|---|
| **Total Sales / Revenue** | `Quantity Sold × Unit Price` |
| **Total Costs** | `Quantity Sold × Cost Price` |
| **Profit** | `Total Sales − Total Costs` |
| **Profit Margin (%)** | `(Profit ÷ Total Sales) × 100` |

These four fields form the backbone of every profitability-related pivot table and visual in the dashboard — from the headline Total Profit KPI down to the Top 3 Products by Profit Margin chart.

---

## ❓ Business Questions Addressed

| # | Question | Answered By |
|---|---|---|
| 1 | What is the overall sales and profit performance of the store? | Total Sales, Total Profit, Profit Margin (%) KPI cards |
| 2 | How many transactions were recorded? | Sales Count KPI card |
| 3 | Which regions generate the most sales? | "Sales By Region" chart |
| 4 | Who are the top-performing salespersons? | "Ranking Salespersons by Total Sales" chart |
| 5 | What is the gender composition of the customer base? | "Customers by Gender" donut chart |
| 6 | Which customers contribute the most revenue? | "Top-Notch Customers by Total Sales" chart |
| 7 | How did sales trend across Q2 2025? | "Total Sales for Q2" chart |
| 8 | Which products are most profitable? | "Top 10 Most Profitable Products" chart |
| 9 | Which product category sells best? | "Best Seller Product Category" chart |
| 10 | Which products yield the highest profit margins? | "Top 3 Products by Profit Margin (%)" chart |
| 11 | How does daily sales volume fluctuate? | "Daily Sales Trend" line chart |

---

## 🏗️ Dashboard Architecture

The dashboard is a **single interactive canvas** organized into four zones:

<img width="1375" height="732" alt="Sales Performance Analysis Dashboard" src="https://github.com/user-attachments/assets/cb320606-3383-47b4-9fa5-7d343e3baec1" />

### Left Panel — Slicers
- **Gender:** Female, Male
- **Product:** Beans, Bread, Butter, Eggs, Milk, Plantain Chips, Rice, Soap, Soft Drink, Yam
- **Region:** Abuja, Ibadan, Kano, Lagos, Port Harcourt
- **Salesperson:** Ade, Bola, Chroma, Emeka, Fatima, John, Ngozi, Tunde
- **Category:** Bakery, Beverages, Dairy, Grains, Household, Legumes, Protein, Roots, Snacks, Spread

### Top Row — Headline KPIs
- **Total Sales:** ₦36,014,075.00
- **Total Profit:** ₦10,671,625.00
- **Profit Margin (%):** 29.57%
- **Sales Count:** 800 transactions

### Center — Core Visuals
- **Sales By Region** — horizontal bar chart ranking all 5 regions
- **Ranking Salespersons by Total Sales** — vertical bar chart of all 8 salespersons
- **Customers by Gender** — donut chart (Male 52% / Female 48%)
- **Top-Notch Customers by Total Sales** — ranked bar chart of the top 5 individual customers
- **Total Sales for Q2** — triangular chart showing April, May, and June sales
- **Best Seller Product Category** — 3D ribbon chart ranking all 10 categories
- **Top 3 Products by Profit Margin (%)** — pie chart of the three highest-margin products
- **Daily Sales Trend** — line chart of daily sales from April through June 2025

### Right Column — Product Profitability
- **Top 10 Most Profitable Products** — horizontal bar chart ranking all 10 products by total profit contribution

---

## 🔎 Detailed Findings by Visual

### Overall Performance
- **Total Sales:** ₦36,014,075.00 across 800 transactions — an average transaction value of **₦45,018**
- **Total Profit:** ₦10,671,625.00
- **Profit Margin:** 29.57% — meaning roughly ₦30 of every ₦100 in sales is retained as profit after cost of goods sold

### Regional Performance
Ranked from lowest to highest total sales:

| Region | Total Sales |
|---|---|
| Kano | ₦6,247,986.00 |
| Ibadan | ₦7,147,173.00 |
| Abuja | ₦7,306,128.00 |
| Port Harcourt | ₦7,629,861.00 |
| **Lagos** | **₦7,682,927.00** |

**Lagos is the top-performing region**, generating roughly ₦1.43M more than Kano, the lowest-performing region — a gap of about 23%. The remaining three regions (Ibadan, Abuja, Port Harcourt) sit in a fairly tight band between ₦7.1M and ₦7.6M, suggesting the real regional performance gap is Kano *underperforming* relative to a fairly consistent baseline elsewhere, rather than any single region dramatically overperforming.

### Salesperson Performance
The dashboard ranks all 8 salespersons (John, Bola, Chroma, Fatima, Emeka, Tunde, Ngozi, Ade) by total sales on a shared axis running from ₦0 to ₦6,000,000+. Individual bar values are not numerically labeled on the chart, but the visual shows a **relatively gradual decline from the top performer to the lowest**, rather than one salesperson dramatically outperforming the rest — indicating a reasonably balanced sales team rather than a single-rep dependency risk.

### Customer Demographics
- **Gender split:** Male 52% / Female 48% — a near-even customer base by transaction count
- Despite males representing a slightly larger share of transactions, the accompanying narrative analysis indicates **female customers generate a higher average transaction value** — meaning gender-based revenue contribution is more balanced (or potentially female-skewed) than the 52/48 transaction split alone would suggest

### Top Customers
The five highest-spending individual customers:

| Rank | Customer | Total Sales |
|---|---|---|
| 1 | Customer_618 | ₦142,704.00 |
| 2 | Customer_555 | ₦141,365.00 |
| 3 | Customer_624 | ₦137,690.00 |
| 4 | Customer_83 | ₦136,758.00 |
| 5 | Customer_588 | ₦134,504.00 |

These top 5 customers are tightly clustered (within ~₦8,200 of each other), indicating no single "whale" customer dominates revenue — spend is spread across a healthy base of high-value repeat shoppers rather than concentrated risk in one account.

### Q2 2025 Seasonality
| Month | Total Sales |
|---|---|
| April | ₦12,111,948.00 |
| May | ₦11,219,036.00 |
| **June** | **₦12,683,091.00** |

Sales dipped in May before rebounding to peak in June — consistent with the narrative finding that **sales performance peaks in June**.

### Product Profitability (Top 10)
Ranked from lowest to highest total profit contribution:

| Rank | Product | Profit |
|---|---|---|
| 10 | Butter | ₦904,793.00 |
| 9 | Rice | ₦940,213.00 |
| 8 | Yam | ₦950,911.00 |
| 7 | Plantain Chips | ₦1,006,636.00 |
| 6 | Eggs | ₦1,048,627.00 |
| 5 | Soft Drink | ₦1,072,235.00 |
| 4 | Milk | ₦1,152,544.00 |
| 3 | Soap | ₦1,170,844.00 |
| 2 | Beans | ₦1,191,753.00 |
| **1** | **Bread** | **₦1,233,069.00** |

**Bread is the single most profitable product**, followed closely by Beans and Soap. Notably, the spread between the #1 product (Bread, ₦1.23M) and the #10 product (Butter, ₦0.90M) is relatively narrow (~₦328K) — profitability is fairly evenly distributed across the top 10 products rather than dominated by one or two items.

### Product Category Performance
The "Best Seller Product Category" visual ranks all 10 categories (Dairy, Protein, Grains, Household, Snacks, Roots, Spread, Beverages, Bakery, Legumes), with **Dairy emerging as the top-selling category** — consistent with the reported finding that dairy products are the most profitable category overall. Sales decline steadily across the remaining categories toward Legumes at the low end.

### Profit Margin Leaders
The three products with the highest profit margins:

| Product | Profit Margin |
|---|---|
| Beans | 30.85% |
| Soft Drink | 30.75% |
| Soap | 29.99% |

Interestingly, **none of these three margin leaders is the single most profitable product in absolute terms** (that's Bread) — Beans ranks #2 in absolute profit but #1 in margin, while Soap ranks #3 in absolute profit and #3 in margin. This distinction matters: a product can generate strong margins per unit while still being outpaced in total profit by a higher-volume item like Bread.

### Daily Sales Trend
The daily sales line chart (April 1 – June 30, 2025) shows **high day-to-day volatility**, with daily sales swinging between roughly ₦200,000 and ₦1,200,000. There is no strong single directional trend visible day-to-day — the volatility appears to reflect normal retail demand fluctuation (e.g., weekday/weekend or restocking cycles) rather than a steady climb or decline, even though the monthly aggregates show June as the strongest month overall.

---

## 💡 Key Insights

1. **Sales performance is concentrated but not fragile.** Lagos leads regional sales, and Bread/Beans/Soap lead product profitability — but in both cases, the gap between the top performer and the rest of the pack is narrow enough that the business isn't overly dependent on a single region or product.
2. **Female customers appear more valuable per transaction.** Even with a near-even 52/48 male-female transaction split, the higher average transaction value among female customers suggests targeted engagement with this segment could disproportionately grow revenue.
3. **Dairy is the category to protect and grow.** As both the best-selling category and (per the source analysis) the most profitable, Dairy is the clearest single lever for overall store performance.
4. **June is the seasonal high point.** With April also strong and May the Q2 trough, this dashboard's data hints at a mid-quarter dip worth investigating — is May consistently softer, or was this specific to 2025?
5. **Margin leaders and profit leaders are different products.** Beans, Soft Drink, and Soap have the best margins, but Bread generates the most absolute profit. Store strategy should treat these as two distinct optimization targets, not one.
6. **The salesforce is balanced.** No single salesperson dominates the ranking chart, which reduces key-person dependency risk but also means there isn't an obvious "top performer" playbook to replicate — further analysis of *why* top performers outperform (not just *that* they do) would need additional data.

---

## ⚠️ Data Limitations & Unanswerable Questions

In line with the original analysis, not every business question that might be asked of this dataset can be reliably answered with its current structure:

- **No repeat-purchase or loyalty tracking field:** While top customers by total sales are identifiable, the dataset does not capture purchase frequency or basket composition per visit, limiting true customer loyalty or retention analysis.
- **No cost driver breakdown:** Cost Price is captured per unit, but the dataset does not distinguish between supplier, shipping, or overhead cost components — so profitability drivers can be measured but not fully diagnosed.
- **No time-of-day or weekday/weekend field:** The daily sales trend shows volatility, but without a day-of-week or time-stamp breakdown, it isn't possible to confirm whether volatility follows a weekly pattern.
- **No customer demographic fields beyond gender:** Age, location, or customer segment data was not available, limiting demographic analysis to the gender dimension only.
- **Salesperson bar values not numerically labeled:** The dashboard's "Ranking Salespersons by Total Sales" visual displays relative performance clearly but without labeled figures per bar, exact totals per salesperson are not independently quotable from the dashboard alone.

Explicitly documenting these gaps — rather than guessing at answers the data can't support — was treated as part of the analytical deliverable itself, consistent with the original project brief.

---

## 🧭 Recommendations

1. **Prioritize high-margin and high-revenue products** — specifically Bread (top absolute profit) and Beans/Soft Drink/Soap (top margins) — in promotional planning and shelf placement.
2. **Strengthen marketing and inventory strategies in high-performing regions**, particularly Lagos, while investigating why Kano trails the other four regions by a meaningful margin.
3. **Use salesperson performance metrics for training and incentive design**, leveraging the relatively even spread across the team to identify specific, transferable behaviors from top performers rather than relying on one outlier.
4. **Investigate the May dip** in the Q2 trend to determine whether it reflects a recurring seasonal pattern or a one-off dip worth correcting operationally.
5. **Expand the data schema** to capture purchase frequency, time-of-day, and additional customer demographics, closing the analytical gaps identified above and enabling deeper loyalty and behavioral segmentation in future dashboard iterations.
6. **Investigate the female average-transaction-value premium** further — a targeted campaign or loyalty program aimed at female shoppers could be tested against this baseline.

---

## 🛠️ Tools & Tech Stack

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Core workbook — data storage and pivot table analysis |
| **PivotTables & PivotCharts** | Aggregation engine behind every dashboard visual |
| **Calculated Fields** | Total Sales, Total Costs, Profit, Profit Margin (%) |
| **Slicers** | Interactive filtering across Gender, Product, Region, Salesperson, and Category |
| **Google Drive** | Hosted, shareable copy of the workbook and supporting files |

---

## 📂 How to Use This Repo

```
├── data/
│   └── keithston_sales_transactions.csv
├── workbook/
│   └── Keithston_Grocery_Store_Sales_Dashboard.xlsx
├── README.md
```

1. Clone or download this repository
2. Open the workbook in **Microsoft Excel** to explore the underlying pivot tables and calculated fields behind each visual
3. Use the **Gender / Product / Region / Salesperson / Category** slicers on the Dashboard tab to filter all visuals interactively — for example, filter to Lagos + Dairy to see how that specific combination performs against the whole-store benchmarks above
4. **Link to Excel and report:** https://drive.google.com/drive/folders/1rCr57GP1-VMGOOsS9NvlMyOD_qeS342T?usp=sharing

---

## 👤 Author

**(Add your name, role, and LinkedIn- www.linkedin.com/in/yusuf-shotunde /GitHub- https://github.com/Yusinho)**

---

## 📄 Disclaimer

This report was produced as a portfolio and educational analytics project. All figures are drawn directly from the Keithston Grocery Store dashboard and its underlying pivot tables. Where a chart did not display a numerically labeled value (e.g., individual salesperson totals), this report describes the relative pattern shown rather than inventing precise figures. Any strategic recommendations above are illustrative and should be validated against the full underlying dataset and current business context before being acted upon operationally.




