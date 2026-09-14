# Data Quality Assessment

## Objective

The purpose of the data-quality assessment is to identify issues in the raw transactional dataset before performing business analysis.

The raw data is preserved separately from the cleaned analytical dataset.

## Data Quality Checks

| Check | Purpose |
|---|---|
| Total Rows | Validate dataset size |
| Missing CustomerID | Identify incomplete customer information |
| Cancellation Invoices | Identify cancelled transactions |
| Negative Quantity | Identify invalid/return-related quantities |
| Non-positive Unit Price | Identify invalid pricing records |
| Missing Description | Identify incomplete product information |
| Duplicate Records | Identify potential duplicate transactions |
| Revenue Validation | Validate calculated revenue |
| Date Validation | Check transaction date consistency |

## 1. Total Rows

### Excel Check

```excel
=ROWS(tbl_raw[InvoiceNo])
```

### Result

**541,909 rows**

This provides the baseline record count for the raw dataset.

## 2. Missing CustomerID

### Excel Check

```excel
=COUNTBLANK(tbl_raw[CustomerID])
```

### Treatment

Missing `CustomerID` values are not automatically removed.

### Reason

`CustomerID` is required for customer-level analysis, but transactions without `CustomerID` can still contribute to:

- Overall revenue
- Product analysis
- Market analysis
- Order analysis

Therefore, these records are retained where analytically appropriate.

## 3. Cancellation Invoices

### Excel Check

```excel
=COUNTIF(tbl_raw[InvoiceNo],"C*")
```

### Treatment

Cancellation invoices are excluded from the core sales analysis.

### Reason

The primary analysis focuses on completed sales transactions rather than cancelled transactions.

## 4. Negative Quantity

### Excel Check

```excel
=COUNTIF(tbl_raw[Quantity],"<0")
```

### Treatment

Transactions with non-positive quantities are excluded from the core sales dataset.

### Reason

The core revenue analysis is intended to represent completed positive sales.

## 5. Non-positive Unit Price

### Excel Check

```excel
=COUNTIF(tbl_raw[UnitPrice],"<=0")
```

### Treatment

Transactions with non-positive `UnitPrice` values are excluded from the core sales analysis.

### Reason

Revenue is calculated as:

```text
Revenue = Quantity × UnitPrice
```

Non-positive prices would distort standard sales-revenue analysis.

## 6. Missing Product Description

### Check

Identify blank or missing values in the `Description` field.

### Treatment

Investigate missing descriptions and retain or remove records based on whether the product identifier remains usable.

### Reason

A missing description does not necessarily mean the transaction itself is invalid.

## 7. Duplicate Records

Duplicate transactions are investigated using relevant transaction-level fields.

### Treatment

Exact duplicates are reviewed before removal.

### Reason

Blindly deleting duplicate-looking rows can remove legitimate repeated purchases.

## 8. Date Validation

`InvoiceDate` is checked for:

- Valid date/time values
- Correct chronological ordering
- Expected analysis period

### Purpose

Accurate date handling is required for:

- Monthly revenue
- MoM growth
- Cohort analysis
- Recency calculation
- Retention analysis

## 9. Revenue Validation

Revenue is calculated as:

```text
Revenue = Quantity × UnitPrice
```

The cleaned dataset is validated by comparing:

```text
Sum of transaction-level revenue
=
Total Revenue KPI
```

Monthly revenue is also validated against the overall revenue total.

## Data Treatment Summary

| Issue | Treatment | Reason |
|---|---|---|
| Missing CustomerID | Retain where appropriate | Needed for non-customer analyses |
| Cancellation invoices | Exclude from core sales | Not completed sales |
| Quantity ≤ 0 | Exclude from core sales | Avoid invalid sales volume |
| UnitPrice ≤ 0 | Exclude from core sales | Avoid invalid revenue |
| Missing Description | Investigate | Product code may still be usable |
| Exact duplicates | Review before removal | Avoid deleting legitimate transactions |
| Invalid dates | Investigate/remove if invalid | Required for time analysis |

## Clean Dataset Rules

The core analytical dataset follows these rules:

```text
InvoiceNo is not a cancellation
        AND
Quantity > 0
        AND
UnitPrice > 0
```

`CustomerID` is handled separately depending on the analytical requirement.

## Data Quality Principle

> **Do not remove data simply because it looks unusual. First determine whether the record is invalid, cancelled, incomplete, or analytically relevant.**

## Validation Checks

After cleaning, the following validations are performed:

- Total revenue reconciles to transaction-level revenue.
- Monthly revenue reconciles to total revenue.
- Distinct orders are used instead of row counts.
- Customer counts use unique `CustomerID` values.
- Customer-attributed revenue is clearly distinguished from total revenue.
- Product rankings are checked for unusual bulk transactions.
- RFM results are checked against the full customer population.
- Cohort outputs are validated before executive interpretation.

## Important Analytical Limitation

Total revenue and customer-attributed revenue are different because some transactions have missing `CustomerID` values.

Therefore:

```text
Total Revenue
≠
Customer-attributed Revenue
```

This distinction is explicitly maintained throughout the project to avoid misleading business conclusions.

## Data Quality Outcome

The cleaned dataset provides a reliable foundation for:

- Revenue analysis
- Customer analysis
- Product analysis
- Market analysis
- RFM segmentation
- Repeat-purchase analysis
- Cohort analysis
- Product basket analysis

All major analytical outputs are validated before being used as executive insights.
