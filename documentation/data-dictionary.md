# Data Dictionary

## Dataset Overview

The project uses the **UCI Online Retail dataset**.

The dataset contains transactional records from a UK-based online retailer covering approximately December 2010 to December 2011.

The original dataset contains **541,909 transaction records**.

## Source

**Dataset:** Online Retail

**Source:** UCI Machine Learning Repository

**Business Context:** UK-based online retailer

**Analysis Period:** December 2010 – December 2011

## Raw Data Fields

| Column | Description | Data Type | Example | Analytical Role |
|---|---|---|---|---|
| `InvoiceNo` | Transaction/invoice identifier | Text | `536365` | Order identification |
| `StockCode` | Product identifier | Text | `85123A` | Product analysis |
| `Description` | Product description | Text | `WHITE HANGING HEART` | Product analysis |
| `Quantity` | Number of units purchased | Integer | `6` | Sales volume |
| `InvoiceDate` | Date and time of transaction | DateTime | `01-12-2010 08:26` | Time analysis |
| `UnitPrice` | Price per unit | Decimal | `2.55` | Revenue calculation |
| `CustomerID` | Customer identifier | Integer | `17850` | Customer analysis |
| `Country` | Customer country | Text | `United Kingdom` | Market analysis |

## Derived Fields

| Field | Calculation / Definition | Purpose |
|---|---|---|
| `Revenue` | `Quantity × UnitPrice` | Revenue analysis |
| `Year` | Year extracted from `InvoiceDate` | Time analysis |
| `Month` | Month extracted from `InvoiceDate` | Time analysis |
| `Month_Number` | Numeric month | Correct chronological sorting |
| `Month_Year` | Month + Year | Monthly reporting |
| `Orders` | Distinct `InvoiceNo` | Order-level analysis |
| `AOV` | Revenue ÷ Orders | Order-value analysis |
| `Revenue %` | Entity revenue ÷ total revenue | Contribution analysis |
| `Cumulative %` | Running revenue contribution | Concentration analysis |

## RFM Fields

| Field | Definition |
|---|---|
| `Recency` | Days since the customer's most recent purchase |
| `Frequency` | Number of distinct orders |
| `Monetary` | Total customer revenue |
| `Recency Score` | Quintile score from 1–5 |
| `Frequency Score` | Quintile score from 1–5 |
| `Revenue Score` | Quintile score from 1–5 |
| `RFM Composite Score` | Combined RFM score |
| `RFM Code` | Individual RFM score combination |
| `Segment` | Customer segment based on RFM |

### RFM Interpretation

- **Recency:** Lower is better.
- **Frequency:** Higher is better.
- **Monetary:** Higher is better.

## Retention Fields

| Field | Definition |
|---|---|
| `CustomerID` | Customer identifier |
| `First Purchase Date` | Customer's earliest purchase |
| `Last Purchase Date` | Customer's latest purchase |
| `Orders` | Distinct customer orders |
| `Customer Type` | Repeat or One-Time |
| `Revenue` | Customer revenue |

### Repeat Customer Definition

A customer is classified as a **repeat customer** when they have more than one distinct order during the analysis period.

## Cohort Fields

| Field | Definition |
|---|---|
| `CustomerID` | Customer identifier |
| `Cohort_month` | Month of customer's first purchase |
| `purchase_month` | Month in which customer made a purchase |
| `Month_Offset` | Number of months since cohort month |

## Product Basket Fields

| Field | Definition |
|---|---|
| `InvoiceNo` | Order/invoice identifier |
| `StockCode` | Product identifier |
| `Description` | Product description |
| `Quantity` | Units purchased |
| `Revenue` | Transaction revenue |

The basket data can be used to calculate product-pair frequency, support, confidence and lift.

## Important Data Considerations

### Invoice Cancellations

Invoice numbers beginning with `C` represent cancellations and are excluded from the core sales analysis.

### Quantity

Transactions with non-positive quantities are excluded from the core sales analysis.

### Unit Price

Transactions with non-positive unit prices are excluded from the core sales analysis.

### CustomerID

CustomerID can be missing.

Missing CustomerID values are not automatically removed from all analysis.

- Overall revenue/product analysis can use transactions without CustomerID.
- Customer-level analysis requires a valid CustomerID.

This distinction explains why total revenue and customer-attributed revenue are different.

## Analytical Definitions

### Revenue

```text
Revenue = Quantity × UnitPrice
```

### Average Order Value

```text
AOV = Total Revenue ÷ Distinct Orders
```

### Repeat Customer Rate

```text
Repeat Customer Rate =
Repeat Customers ÷ Total Customers
```

### Revenue Contribution

```text
Revenue % =
Entity Revenue ÷ Total Revenue
```

### Revenue per Customer

```text
Revenue per Customer =
Market Revenue ÷ Unique Customers
```

## Data Limitations

The dataset does not contain:

- Product cost
- Profit
- Marketing spend
- Acquisition cost
- Inventory levels
- Total market size

Therefore, the following cannot be reliably calculated from this dataset alone:

- Profit margin
- CAC
- Marketing ROI
- Inventory turnover
- Market share
