# 📊 E-Commerce Customer & Revenue Analytics

**Excel | Power Query | PivotTables | RFM Analysis | Cohort Analysis | Customer Retention**

> An end-to-end data analytics project analyzing 541K+ e-commerce transactions to identify revenue trends, customer value, product performance, market contribution, and retention opportunities.

---

## 🎯 Executive Summary

Management needs to understand **what is driving revenue, which customers are most valuable, where revenue is concentrated, and where future growth opportunities may exist**.

This project transforms raw transactional data into a structured analytical model and translates the results into **executive insights and management recommendations**.

### Key Findings

| KPI                            |        Result |
| ------------------------------ | ------------: |
| Transactions Analyzed          |     **541K+** |
| Total Revenue                  | **₹1.067 Cr** |
| Orders                         |    **19,960** |
| Customers                      |     **4,339** |
| Average Order Value            |   **₹534.40** |
| Repeat Customer Rate           |     **65.6%** |
| Repeat Revenue Contribution    |     **93.1%** |
| UK Revenue Share               |     **84.6%** |
| Top 10 Customer Revenue Share  |     **14.4%** |
| Top 100 Customer Revenue Share |     **33.9%** |

> **Important:** Customer-attributed revenue is ₹89.11 lakh, lower than total revenue, because some transactions do not contain a CustomerID.

---

# 🏢 Business Problem

Management wants to understand its:

* Revenue performance
* Customer value
* Customer concentration
* Product performance
* Market contribution
* Repeat purchasing behavior
* Customer retention opportunities

### Primary Executive Question

> **Which customers, products, and markets are driving revenue, and where are the biggest opportunities to improve customer value and revenue?**

---

# ❓ Executive Questions

The analysis answers the following management questions:

| ID | Executive Question                                        | Decision Focus           |
| -- | --------------------------------------------------------- | ------------------------ |
| Q1 | How has monthly revenue changed over the analysis period? | Revenue growth/decline   |
| Q2 | Which products drive revenue?                             | Product prioritization   |
| Q3 | Which markets generate the most revenue?                  | Market focus             |
| Q4 | Who are our highest-value customers?                      | Customer prioritization  |
| Q5 | How concentrated is revenue among customers?              | Customer risk            |
| Q6 | What proportion of customers are repeat customers?        | Retention strategy       |
| Q7 | Which customers are most valuable based on RFM?           | Targeted engagement      |
| Q8 | When do customers return after their first purchase?      | Cohort retention         |
| Q9 | Which products are purchased together?                    | Cross-sell opportunities |

---

# 🧠 Analytical Framework — READY

This project follows the **READY framework** for building a business-oriented analytics portfolio.

### R — Representative Data

Used the **UCI Online Retail dataset**, containing 541K+ transactional records from a UK-based online retailer.

The dataset includes:

* Invoice number
* Product code
* Product description
* Quantity
* Transaction date
* Unit price
* Customer ID
* Country

### E — Executive Questions

Instead of starting with charts, the project begins with management questions around:

* Revenue
* Customers
* Products
* Markets
* Retention

### A — Analytical Frameworks

Applied:

* Revenue trend analysis
* Customer revenue analysis
* Revenue concentration analysis
* Product performance analysis
* Market analysis
* RFM analysis
* Repeat-purchase analysis
* Cohort retention analysis
* Product basket analysis

### D — Data Best Practices

Applied:

* Raw-data preservation
* Data-quality profiling
* Cancellation handling
* Missing-value assessment
* Positive quantity/price validation
* Revenue calculation
* Distinct-order logic
* Customer-level aggregation
* Validation of analytical outputs

### Y — Your Impact

Converted analytical findings into:

* Management implications
* Business recommendations
* Decision priorities
* Metrics to track

---

# 🔄 Analytical Workflow

```text
Raw Transaction Data
        ↓
Data Quality Assessment
        ↓
Power Query Cleaning
        ↓
Clean Analytical Dataset
        ↓
KPI Layer
        ↓
Revenue Analysis
        ↓
Customer Analysis
        ↓
Product Analysis
        ↓
Market Analysis
        ↓
RFM / Retention / Cohort / Basket Analysis
        ↓
Executive Insights
        ↓
Management Recommendations
```

---

# 📁 Project Structure

```text
ecommerce-customer-revenue-analytics/
│
├── README.md
│
├── data/
│   └── README.md
│
├── excel/
│   └── Ecommerce_Customer_Revenue_Analytics.xlsx
│
├── documentation/
│   ├── business-problem.md
│   ├── data-dictionary.md
│   ├── data-quality.md
│   └── insights.md
│
├── screenshots/
│   ├── 01-executive-summary.png
│   ├── 02-revenue-analysis.png
│   ├── 03-customer-analysis.png
│   ├── 04-product-analysis.png
│   ├── 05-market-analysis.png
│   ├── 06-rfm-analysis.png
│   └── 07-retention-analysis.png
│
└── LICENSE
```

---

# 📊 Workbook Architecture

The Excel workbook follows a structured analytics pipeline:

| Sheet                  | Purpose                              |
| ---------------------- | ------------------------------------ |
| `01_README`            | Project overview                     |
| `02_BUSINESS_PROBLEM`  | Executive questions and decisions    |
| `03_DATA_DICTIONARY`   | Field definitions                    |
| `04_RAW_DATA`          | Original transactional data          |
| `05_DATA_QUALITY`      | Data-quality assessment              |
| `06_CLEAN_DATA`        | Clean analytical dataset             |
| `07_KPI`               | Core business KPIs                   |
| `08_REVENUE_ANALYSIS`  | Revenue trends                       |
| `09_CUSTOMER_ANALYSIS` | Customer value & concentration       |
| `10_PRODUCT_ANALYSIS`  | Product performance                  |
| `11_MARKET_ANALYSIS`   | Country/market analysis              |
| `12_RFM_ANALYSIS`      | Customer segmentation                |
| `13_RETENTION`         | Repeat purchase & cohort analysis    |
| `PRODUCT_BASKET`       | Basket-level transaction data        |
| `Customer_Month`       | Customer cohort preparation          |
| `14_INSIGHTS`          | Executive findings & recommendations |

---

# 💡 Key Business Insights

## 1. Revenue Volatility

Monthly revenue varied significantly throughout the analysis period.

Revenue reached its highest point in **November 2011 at approximately ₹15.09 lakh**.

The largest monthly increase occurred in **May 2011 (+43.3%)**, while the largest decline occurred in **December 2011 (-57.7%)**.

### Business implication

Revenue performance is highly variable across periods.

### Recommendation

Investigate the products, customers and markets contributing to major revenue increases and declines before using these patterns for future planning.

---

## 2. Customer Concentration

The highest-value customers contribute a substantial share of customer-attributed revenue.

* Top 10 customers → **14.4%**
* Top 20 customers → **19.9%**
* Top 50 customers → **27.8%**
* Top 100 customers → **33.9%**

### Business implication

A relatively small customer group represents a meaningful portion of revenue.

### Recommendation

Prioritize retention and personalized engagement for high-value customers while increasing purchasing activity among mid-value customers.

---

## 3. Repeat Customers Drive Revenue

**2,846 of 4,339 customers** were repeat customers.

That represents a:

### **65.6% repeat customer rate**

More importantly, repeat customers generated:

### **93.1% of customer-attributed revenue**

### Business implication

Repeat purchasing is a major driver of customer revenue.

### Recommendation

Focus on protecting existing repeat customers and increasing the probability that one-time customers make a second purchase.

---

## 4. UK Revenue Dependence

The UK generated approximately:

### **₹90.25 lakh**

representing:

### **84.6% of total revenue**

### Business implication

Revenue is heavily dependent on one geographic market.

### Recommendation

Protect the core UK customer base while investigating smaller markets that demonstrate attractive revenue-per-customer characteristics.

---

## 5. Smaller Markets Require Further Investigation

Some smaller markets show substantially higher revenue per customer than the UK.

For example:

| Market      | Revenue / Customer |
| ----------- | -----------------: |
| UK          |          ₹2,301.77 |
| Netherlands |         ₹31,716.26 |
| EIRE        |         ₹70,863.49 |
| Australia   |         ₹15,391.26 |

### Important caveat

These markets have very small customer populations, so high revenue per customer should be treated as a **growth hypothesis**, not proof of market attractiveness.

### Recommendation

Investigate customer and order characteristics before making expansion decisions.

---

# 🎯 Management Recommendations

| Priority  | Recommendation                                |
| --------- | --------------------------------------------- |
| 🔴 High   | Protect high-value repeat customers           |
| 🔴 High   | Increase one-time → repeat conversion         |
| 🔴 High   | Monitor customer revenue concentration        |
| 🔴 High   | Protect the core UK market                    |
| 🟠 Medium | Investigate secondary-market opportunities    |
| 🟠 Medium | Investigate high-volume product opportunities |
| 🟠 Medium | Complete validated product-affinity analysis  |

---

# 🛠️ Tools & Skills

### Excel

* Power Query
* Excel Tables
* PivotTables
* XLOOKUP
* SUMIFS
* COUNTIFS
* Dynamic Arrays
* Conditional Formatting
* KPI Development
* Data Validation

### Analytics

* Revenue Analysis
* Customer Segmentation
* RFM Analysis
* Cohort Analysis
* Retention Analysis
* Customer Concentration
* Product Analysis
* Market Analysis
* Basket Analysis

### Business Analytics

* Executive Question Framing
* KPI Design
* Insight Generation
* Business Recommendations
* Decision-oriented Analytics
* Data Quality Assessment

---

# ⚠️ Data Limitations

This project intentionally avoids making unsupported business claims.

The dataset does **not** contain:

* Product cost
* Profit
* Marketing spend
* Customer acquisition cost
* Inventory levels
* Market size

Therefore, this project does not claim:

* Product profitability
* CAC
* Campaign ROI
* Inventory turnover
* Market share

Customer-attributed revenue is lower than total revenue because some transactions have missing CustomerID values.

The current RFM, cohort and product-affinity outputs should be completed and validated before their results are used as final executive claims.

---

# 📚 Dataset

**Source:** UCI Machine Learning Repository — Online Retail Dataset

The dataset contains transactional records from a UK-based online retailer covering approximately December 2010 to December 2011.

The raw dataset is not committed to this repository.

See `data/README.md` for dataset information.

---

# 👤 Author

**Data Analyst Portfolio Project**

This project demonstrates the ability to move from:

**Raw Data → Analysis → Insight → Business Decision**

rather than producing a dashboard without a defined business problem.
