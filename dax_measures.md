# DAX Measures — Sales Dashboard

All custom measures used in `SalesDashboard.pbix`.

---

## Core KPI Measures

### Sum of Profit
```dax
Sum of Profit = SUM(Sales[Profit])
```

### Sum of Amount
```dax
Sum of Amount = SUM(Sales[Amount])
```

### Sum of Quantity
```dax
Sum of Quantity = SUM(Sales[Quantity])
```

---

## Ratio & Percentage Measures

### Profit Margin %
```dax
Profit Margin % = 
DIVIDE(
    [Sum of Profit],
    [Sum of Amount],
    0
)
```

### Quantity Share by Category
```dax
Quantity Share % = 
DIVIDE(
    SUM(Sales[Quantity]),
    CALCULATE(SUM(Sales[Quantity]), ALL(Sales[Category])),
    0
)
```

---

## Time Intelligence Measures

### Profit MoM Change
```dax
Profit MoM Change = 
VAR CurrentMonth = [Sum of Profit]
VAR PrevMonth = CALCULATE(
    [Sum of Profit],
    DATEADD(Sales[Order Date], -1, MONTH)
)
RETURN
DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0)
```

### YTD Amount
```dax
YTD Amount = 
TOTALYTD(
    SUM(Sales[Amount]),
    Sales[Order Date]
)
```

### QTD Profit
```dax
QTD Profit = 
TOTALQTD(
    SUM(Sales[Profit]),
    Sales[Order Date]
)
```

---

## Filtering & Ranking Measures

### Top 6 Sub-Categories by Profit
```dax
Top 6 SubCat Profit = 
IF(
    RANKX(
        ALL(Sales[Sub-Category]),
        [Sum of Profit],
        ,
        DESC,
        DENSE
    ) <= 6,
    [Sum of Profit],
    BLANK()
)
```

### Top 6 Customers by Amount
```dax
Top 6 Customer Amount = 
IF(
    RANKX(
        ALL(Sales[CustomerName]),
        [Sum of Amount],
        ,
        DESC,
        DENSE
    ) <= 6,
    [Sum of Amount],
    BLANK()
)
```

---

## Calculated Columns

### Quarter Column *(if not in source)*
```dax
Quarter = 
"Q" & ROUNDUP(MONTH(Sales[Order Date]) / 3, 0)
```

### Month Name Column *(if not in source)*
```dax
Month = FORMAT(Sales[Order Date], "MMMM")
```

### Month Number *(for sorting)*
```dax
Month Number = MONTH(Sales[Order Date])
```

---

## Notes
- All measures reference the `Sales` table
- Use `Month Number` to sort the `Month` column in the Month field settings
- Time intelligence measures require a proper Date table marked as "Date Table" in Power BI
