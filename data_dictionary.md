# Data Dictionary — Sales Dashboard

This document describes all fields present in `sales_data.csv`.

---

## Table: Sales

| Field Name | Data Type | Example Value | Description |
|---|---|---|---|
| `Order ID` | Text | `ORD-10001` | Unique identifier for each sales transaction |
| `Order Date` | Date | `2024-01-15` | Date the order was placed (YYYY-MM-DD) |
| `Month` | Text | `January` | Calendar month derived from Order Date |
| `Quarter` | Text | `Q1` | Fiscal quarter derived from Order Date (Q1–Q4) |
| `CustomerName` | Text | `Vrinda` | Full name of the customer |
| `Category` | Text | `Electronics` | High-level product category |
| `Sub-Category` | Text | `Printers` | Specific product sub-category |
| `Quantity` | Integer | `3` | Number of units sold in the transaction |
| `Amount` | Decimal | `15000.00` | Total sale value (revenue) in local currency |
| `Profit` | Decimal | `3200.00` | Net profit from the transaction |
| `PaymentMode` | Text | `Online` | Payment method used by the customer |
| `State` | Text | `Maharashtra` | State where the order was delivered *(if applicable)* |

---

## Categorical Values

### Category
- `Electronics`
- `Clothing`
- `Furniture`

### Sub-Category
- `Printers`
- `Bookcases`
- `Saree`
- `Accessories`
- `Tables`
- `Trousers`

### PaymentMode
- `Online` / `UPI`
- `Credit Card`
- `Debit Card`
- `EMI`
- `Cash on Delivery`

### Quarter
- `Q1` → January, February, March
- `Q2` → April, May, June
- `Q3` → July, August, September
- `Q4` → October, November, December

---

## Notes
- All monetary values are in **Indian Rupees (₹)**
- Negative profit values indicate loss-making transactions
- `Amount` represents gross sale value; `Profit = Amount - Cost`
