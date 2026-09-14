# Dataset

## Source

**UCI Machine Learning Repository — Online Retail Dataset**

The dataset contains transactional records from a UK-based online retailer covering approximately December 2010 to December 2011.

## Key Fields

| Field       | Description                    |
| ----------- | ------------------------------ |
| InvoiceNo   | Transaction/invoice identifier |
| StockCode   | Product identifier             |
| Description | Product description            |
| Quantity    | Units purchased                |
| InvoiceDate | Transaction date and time      |
| UnitPrice   | Price per unit                 |
| CustomerID  | Customer identifier            |
| Country     | Customer country               |

## Data Treatment

For the core sales analysis:

* Cancellation invoices were excluded.
* Transactions with non-positive quantities were excluded.
* Transactions with non-positive unit prices were excluded.
* Missing CustomerID values were retained where appropriate for overall revenue/product analysis.
* Customer-level analysis requires CustomerID.
* Revenue was calculated as `Quantity × UnitPrice`.

The raw dataset is not stored in this repository.
