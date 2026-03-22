# 🧸 Retail Sales & Inventory Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Star Schema](https://img.shields.io/badge/Star%20Schema-Data%20Modeling-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

An end-to-end **multi-page Power BI Dashboard** built to analyze the retail sales and inventory performance of toy stores across Mexico. The dashboard transforms **829K+ raw sales transactions** into actionable business intelligence, helping stakeholders make data-driven decisions on sales strategy, inventory management, and store performance.

| Detail | Info |
|--------|------|
| **Client** | Toy Stores in Mexico |
| **Data Period** | January 2022 – September 2023 (638 Days) |
| **Total Transactions** | 829,000+ |
| **Stores** | 50 Stores across 29 Cities |
| **Products** | 35 Unique Items |
| **Tool Used** | Microsoft Power BI |

---

## 🎯 Problem Statement

- Multiple store locations operated **without a centralized analytics platform**
- Frequent **inventory imbalances** — excess stock or stockouts of popular products
- **Lost revenue** from poor inventory management and increased holding costs
- Management relied on **assumptions rather than real-time data** for decisions

---

## 🎯 Project Objectives

| Objective | Description |
|-----------|-------------|
| 📊 Overall Performance | Monitor business revenue and profitability |
| 🏆 Top Products | Identify best-selling products and categories |
| 📈 Sales Trends | Analyze patterns across different time periods |
| 📦 Stock Risks | Detect inventory shortages and potential issues |
| 🏪 Store Performance | Monitor store revenue by city and location |

---

## 🗂️ Dataset & Data Preparation

### Integrated Tables
- **Sales** — 829K+ transaction records (Fact Table)
- **Products** — 35 unique product catalog
- **Stores** — 50 store locations across 29 cities
- **Inventory** — Stock levels per store and product
- **Calendar** — Custom DAX-generated date table

### Data Cleaning Steps
- Removed dollar signs and converted price columns to numeric format
- Checked and removed duplicate records
- Standardized ID columns as text for consistent relationships
- Performed **feature engineering** — created Stock Status and Age columns
- Replaced and substituted values in columns for consistency
- Created a **Calendar Table using DAX** with Month, Year, Start of Month, Day Name, and Month Name

---

## 🏗️ Data Modeling

Implemented a **Star Schema** data model for optimized query performance:

```
        [Calendar]
            |
[Products]--[Sales (Fact)]--[Stores]
            |
        [Inventory]
```

- **Fact Table:** Sales (transaction data)
- **Dimension Tables:** Products, Stores, Calendar
- **Snapshot Table:** Inventory (stock levels per store/product)
- **Relationships via:** Product_ID, Store_ID, Date

---

## 🧮 DAX Measures Developed

### Revenue & Profit
| Measure | Description |
|---------|-------------|
| Total Revenue | Sales revenue based on units sold × product price |
| Total Cost | Total cost using product cost × units sold |
| Total Profit | Revenue minus cost |
| Profit Margin % | Profit as a percentage of revenue |
| Avg Order Value | Average revenue per transaction |

### Growth & Time Intelligence
| Measure | Description |
|---------|-------------|
| MoM % | Month-over-Month growth rate |
| Revenue MoM % | Month-over-Month revenue change |
| Revenue YoY % | Year-over-Year revenue growth |
| MTD & Previous MTD | Month-to-date revenue tracking |
| Revenue Last Month / Last Year | Period comparison metrics |
| Avg Revenue per Day of Week | Revenue trends by weekday |

### Product & Sales Analytics
| Measure | Description |
|---------|-------------|
| Total Units Sold | Total quantity of products sold |
| Total Transactions | Number of sales transactions recorded |
| Product Rank (RANKX) | Ranks products based on revenue |
| Dynamic Top/Bottom Ranking | Switch between top and bottom products |

### Inventory Monitoring
| Measure | Description |
|---------|-------------|
| Total Stock Available | Current stock levels |
| Out of Stock Count | Products with zero inventory |
| Days of Supply | Days before stock runs out |
| Out of Stock Rate | Percentage of out-of-stock products |

### KPI & Store Measures
| Measure | Description |
|---------|-------------|
| Revenue KPI | Revenue target tracking |
| Units Sold KPI | Units target tracking |
| Profit MoM KPI | Profit Month-over-Month KPI |
| Avg Revenue per Store | Average revenue per store |
| Revenue per Store per Day | Daily revenue efficiency per store |
| Cities Covered | Total cities with active stores |

---

## 📊 Dashboard Pages

### 🏠 Home
Navigation page with light/dark mode toggle and page navigator.

### 🔍 Overview
- **KPIs:** Total Revenue, Total Profit, Profit Margin %, Total Units Sold
- **Visuals:** Line chart (profit trend), Azure Map (geo profit), Donut chart (profit by category), Treemap (profit by location)
- **Key Insight:** Toys = top revenue category (35%), December = peak revenue month

### 📦 Product
- **Visuals:** Bar chart (Revenue by Product), Clustered bar (Top 10 by Profit Margin %), Pivot table (Category Performance), Column chart (Avg Order Value by Category)
- **Key Insight:** Lego Bricks = highest revenue ($2.4M), Jenga = highest profit margin (70%)

### 🏭 Inventory
- **Visuals:** Column chart (Stock Status Distribution), Donut chart (Inventory by Category), Combo chart (Inventory vs Sales Trend), Bar chart (Days of Supply by Category)
- **Key Insight:** 77 out-of-stock products, Electronics = only 12 days of supply remaining

### 🏪 Stores
- **Visuals:** Bar chart (Top 10 Stores by Units Sold), Pivot table (Store Performance Summary), Column chart (Store Count by Location)
- **Key Insight:** Downtown stores = highest profit ($2.2M), Ciudad de Mexico = best city ($465K profit)

### 📈 Sales
- **Visuals:** Combo chart (Transactions vs Revenue Trend), Line chart (MoM Growth %), Bar chart (Avg Revenue by Day of Week), Monthly Profit Margin Trend
- **Key Insight:** Friday & Saturday = best sales days, MoM growth swings -20% to +32%

### 🔎 Category Drill (Drill-Through Page)
- Detailed product-level inventory analysis with drill-through from category visuals
- Shows Days of Supply, Stock Status, Units Sold per product per store

### 💡 Custom Tooltips
- **Top 3 Products Tooltip** — shows top 3 products by profit on hover
- **Daily Sales Tooltip** — shows average daily sales units on hover

---

## 💡 Key Business Insights

### Revenue & Profit
- 🧸 **Toys = 35% of total revenue** — highest performing category
- 📅 **December = peak revenue month** — holiday season drives maximum sales
- 📉 **Summer slump (July–August)** — revenue drops, discounts recommended

### Inventory
- ⚠️ **77 products out of stock** — immediate restocking required
- 🔋 **Electronics = only 12 days of supply** — critical stock risk
- 📦 **15K products on Low stock** — pre-emptive restocking needed
- 🎮 **Games holds 39% of inventory but sells less** — overstock issue

### Store Performance
- 🏙️ **Downtown stores = $2.2M profit** — highest performing location type
- 🌆 **Ciudad de Mexico = best city** ($465K profit, 43K units)
- ✈️ **Airport stores underperform** — lowest ROI location type
- 🏙️ **Guadalajara & Monterrey** — ready for store expansion

### Sales Trends
- 📅 **Friday & Saturday = best sales days**
- 📉 **Monday = slowest day** (17K transactions)
- 📊 **Profit margin dropped from 32% to 27%** — cost review needed

---

## ⚠️ Project Limitations

1. **Limited Historical Data** — Analysis spans only 638 days
2. **Static Datasets** — No real-time data integration
3. **Simplified Inventory** — Lacks safety stock and lead time analysis
4. **No Customer Data** — No demographics or purchasing behavior data

---

## 🚀 How to Use

1. Download the `.pbix` file
2. Open with **Microsoft Power BI Desktop**
3. Use the **Home page navigator** to switch between dashboard pages
4. Toggle **Light/Dark mode** using the slicer on each page
5. Use **slicers** to filter by Store City, Product Category, Year/Month
6. **Right-click** on any category visual to access the **Drill-Through** page
7. **Hover** over visuals to see **custom tooltips**

---

## 👨‍💻 Author

**Supriyo Maity**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-supriyomaity24-blue?style=flat&logo=linkedin)](https://linkedin.com/in/supriyomaity24)
[![GitHub](https://img.shields.io/badge/GitHub-supriyo--24-black?style=flat&logo=github)](https://github.com/supriyo-24)

---

## 📄 License

This project is for educational and portfolio purposes only.
