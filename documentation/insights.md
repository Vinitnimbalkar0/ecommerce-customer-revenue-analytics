# 14_INSIGHTS — Executive Insights & Recommendations

## Executive Insights

| ID | Executive Question | Finding | Evidence | Implication | Recommendation |
|---|---|---|---|---|---|
| **REV-01** | How has monthly revenue changed over the analysis period? | Revenue was highly volatile, with strong growth during several months in the second half of 2011 followed by a sharp December decline. | Revenue peaked at **₹15.09 lakh in Nov-2011**. May-2011 had the largest MoM change (**+43.3%**), while Dec-2011 had the largest decline (**-57.7%**). | Revenue performance is concentrated in a few strong periods, making timing and seasonality important areas for investigation. | Investigate the products, customers and markets contributing to major revenue increases and declines and use these patterns to inform future planning. |
| **CUS-01** | Who are our highest-value customers? | A relatively small group of customers contributes a substantial share of customer-attributed revenue. | Top **10 customers = 14.4%** of customer revenue; top **100 customers = 33.9%**. Highest customer revenue was approximately **₹2.80 lakh**. | Losing a small number of high-value customers could have a meaningful revenue impact. | Prioritize retention and personalized engagement for high-value customers and monitor their purchasing activity. |
| **CUS-02** | How concentrated is revenue among customers? | Customer revenue is strongly concentrated in the highest-value customer segment. | Top **10% of customers (434)** generated **61.4%** of customer-attributed revenue (**₹54.69 lakh of ₹89.11 lakh**). | Revenue has meaningful dependency on high-value customers, creating concentration risk. | Protect high-value customers while increasing purchasing activity among mid- and lower-value customer groups. |
| **PRO-01** | Which products drive revenue? | Revenue is relatively distributed across products, with the top product/service codes contributing a limited share of revenue. | Top **10 product/service codes = 10.8%** of revenue; top **50 = 23.9%**. | The business has relatively broad product-level revenue distribution, reducing dependence on a handful of products. | Prioritize high-revenue products while investigating high-volume products that may offer cross-sell or assortment opportunities. |
| **PRO-02** | Are there products with unusually high sales volume? | Some products generate exceptionally high unit volumes relative to their number of orders. | **PAPER CRAFT , LITTLE BIRDIE** recorded **80,995 units in 1 order**, indicating an unusual bulk transaction. | Volume-based rankings can be distorted by bulk purchases and should not automatically be interpreted as recurring demand. | Flag unusual bulk transactions separately and validate whether they represent repeatable customer demand before making product decisions. |
| **MKT-01** | Which markets generate the most revenue? | The UK is overwhelmingly the largest revenue market. | UK generated approximately **₹90.25 lakh**, representing **84.6% of total revenue**. | The business is highly dependent on one geographic market. | Protect the UK customer base while evaluating smaller markets for diversification opportunities. |
| **MKT-02** | Which smaller markets show potential? | Several smaller markets have substantially higher revenue per customer than the UK, but their customer bases are very small. | Netherlands: **₹31,716 revenue/customer**; EIRE: **₹70,863**; Australia: **₹15,391**, versus UK at **₹2,302**. | High revenue per customer may indicate attractive customer economics, but the small sample sizes require validation. | Investigate customer and order characteristics in these markets before considering targeted expansion. |
| **RET-01** | What proportion of customers are repeat customers? | Repeat customers represent the majority of the customer base and generate most customer-attributed revenue. | **2,846 of 4,339 customers** were repeat customers = **65.6%**. Repeat customers generated **93.1%** of customer revenue. | Repeat purchasing is a major driver of customer revenue. | Focus retention efforts on protecting existing repeat customers and converting one-time buyers into second-time purchasers. |
| **RET-02** | How different are repeat and one-time customers in value? | Repeat customers generate substantially more revenue per customer than one-time customers. | Repeat customer average revenue ≈ **₹2,914.65** versus **₹412.80** for one-time customers. | Encouraging a second purchase could have significant customer-value implications. | Develop targeted post-purchase and re-engagement initiatives designed to encourage one-time customers to purchase again. |
| **RFM-01** | Which customers are most valuable based on RFM? | RFM analysis can identify customer groups based on recency, frequency and monetary value, but the current workbook output is incomplete. | Current RFM table contains only a partial customer population and its segment totals do not reconcile to total customer revenue. | Publishing the current RFM segment totals could lead to misleading executive conclusions. | Complete and validate RFM scoring for all **4,339 customers** before using RFM segments for management decisions. |
| **COH-01** | When do customers return after their first purchase? | Customer-month data has been prepared, but the final cohort retention matrix has not yet been validated. | `Customer_Month` contains **13,055 customer-month records**, including cohort month, purchase month and month offset. | Retention timing cannot yet be reliably quantified from the current output. | Complete the cohort matrix and evaluate M1/M3/M6 retention before making cohort-based decisions. |
| **PA-01** | Which products are purchased together? | Transaction-level basket data is available, but product-pair analysis has not yet been completed. | `PRODUCT_BASKET` contains **524,795 transaction-level records**, but validated pair frequency, support, confidence and lift outputs are not yet available. | Cross-sell opportunities cannot yet be supported with evidence. | Build product-pair analysis and prioritize pairs with meaningful frequency and lift for potential bundling or cross-selling. |

## Executive Snapshot

| KPI | Value |
|---|---:|
| Total Revenue | **₹1.067 crore** |
| Customer-attributed Revenue | **₹89.11 lakh** |
| Customers | **4,339** |
| Repeat Customers | **2,846** |
| Repeat Customer Rate | **65.6%** |
| Repeat Revenue Contribution | **93.1%** |
| UK Revenue Share | **84.6%** |
| Total Orders | **19,960** |
| AOV | **₹534.40** |

## Executive Takeaway

The strongest validated signals are **repeat-customer importance, customer revenue concentration, UK market dependence, and significant monthly revenue volatility**.

Repeat customers account for **65.6% of customers but 93.1% of customer-attributed revenue**, making retention a particularly important management lever.

At the same time, **84.6% of total revenue comes from the UK**, highlighting significant geographic concentration.

The analysis also identifies potential opportunities in smaller markets and across customer segments, but these should be treated as **hypotheses for further investigation rather than proven growth opportunities**.

RFM, cohort retention and product-affinity analyses should be completed and validated before their results are used for executive decisions.

## Management Priorities

1. **Protect high-value repeat customers.**
2. **Increase one-time → repeat conversion.**
3. **Monitor customer revenue concentration.**
4. **Protect the core UK market while evaluating diversification opportunities.**
5. **Investigate high-volume product opportunities.**
6. **Complete and validate RFM, cohort and product-affinity analyses.**

## Data Limitations

- Customer-attributed revenue (**₹89.11 lakh**) is lower than total revenue (**₹1.067 crore**) because some transactions do not have a `CustomerID`.
- The dataset does not contain product cost, so **profit/margin cannot be calculated**.
- The dataset does not contain marketing spend, so **CAC and campaign ROI cannot be calculated**.
- The dataset does not provide inventory levels, so **inventory turnover cannot be calculated**.
- The dataset does not provide total market size, so **market share cannot be calculated**.
- The current RFM, cohort and product-affinity outputs require completion/validation before their results are treated as final executive findings.
