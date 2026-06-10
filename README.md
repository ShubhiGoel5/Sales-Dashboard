# Sales Dashboard — Power BI: KPI Analysis & Business Intelligence

A comprehensive **Sales Analytics Dashboard** built with Microsoft Power BI, designed for advanced **KPI Analysis**, data-driven decision-making, and real-time business insights.

<img width="607" height="341" alt="Dahboard" src="https://github.com/user-attachments/assets/14bbddc1-212a-4746-b26c-47ce5edc6d0e" />


---

## Overview

This dashboard empowers sales teams and management to monitor **Key Performance Indicators (KPIs)** at a glance. It provides a deep dive into revenue generation, profit margins, sales volume, and customer behavior across multiple dimensions. By leveraging this tool, businesses can perform robust **KPI Analysis** to track growth and optimize strategies.

### Key Performance Indicators (KPIs)
| Metric | Value | Impact |
|---|---|---|
| **Total Quantity Sold** | 5,615 | Measures product demand and inventory movement |
| **Total Profit** | 37K | Indicates overall financial health and margin success |
| **Total Revenue (Amount)** | 438K | Tracks top-line sales performance |

---

## Dashboard Features & Visualizations

### Advanced Visual Analytics
- **KPI Cards** — Instant visibility into Total Quantity, Profit, and Revenue.
- **Quarterly Trend Filters** — Dynamic toggles to analyze performance across Q1, Q2, Q3, and Q4.
- **Sub-Category Performance (Bar Charts)** — Profitability ranking of top sub-categories.
- **Payment & Category Insights (Donut Charts)** — Breakdown of payment modes and category-wise sales distribution.
- **Customer Revenue Tracking (Column Chart)** — Identifies top-performing customers and key accounts.
- **Monthly Profitability (Line Chart)** — Month-over-month trend analysis to spot seasonal patterns.

### Tracked Dimensions
- **Sub-Categories:** Printers, Bookcases, Saree, Accessories, Tables, Trousers
- **Payment Modes:** Online/UPI (43.74%), Credit/Debit Card (~33%), EMI (13.2%), Cash (20.61%)

---

## Repository Structure

```text
sales-dashboard-repo/
│
├── README.md                   # Project overview (this file)
├── SalesDashboard.pbix         # Power BI Desktop file (main report)
│
├── data/
│   ├── sales_data.csv          # Raw sales transaction dataset
│   └── data_dictionary.md      # Field descriptions & data types
│
├── docs/
│   ├── setup_guide.md          # Setup and configuration instructions
│   ├── dax_measures.md         # Comprehensive DAX formulas reference
│   └── color_theme.json        # Custom Power BI color theme file
│
└── screenshots/
    └── dashboard_preview.png   # High-resolution dashboard screenshot
```

---

## Getting Started

### Prerequisites
- [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Free download)
- Windows 10 / 11 recommended

### Quick Setup
1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/sales-dashboard.git
   cd sales-dashboard
   ```

2. **Launch the Dashboard**
   - Open Power BI Desktop.
   - Load the `SalesDashboard.pbix` file.

3. **Connect the Dataset** *(for live data updates)*
   - Navigate to **Home → Transform Data → Data Source Settings**.
   - Update the file path to target `data/sales_data.csv`.
   - Click **Refresh** to load the latest data.

4. **Apply Custom Theme** *(Optional)*
   - Go to **View → Themes → Browse for themes**.
   - Import `docs/color_theme.json`.

---

## Data Model & Architecture

### Core Fields
| Field | Type | Description |
|---|---|---|
| `Order ID` | Text | Unique identifier for the transaction |
| `CustomerName` | Text | Full name of the purchasing customer |
| `Category` / `Sub-Category` | Text | Product classification hierarchy |
| `Quantity` | Integer | Volume of units sold |
| `Amount` / `Profit` | Decimal | Financial metrics (Revenue and Margin) |
| `PaymentMode` | Text | Transaction method used |
| `Order Date` / `Month` / `Quarter`| Date/Text | Temporal dimensions for time-series analysis |

*For a complete schema, refer to [`data/data_dictionary.md`](data/data_dictionary.md).*

---

## Design & Aesthetics

- **Color Palette:** Premium purple-to-pink gradient background with striking blue/pink accents for visual hierarchy.
- **Theme:** Dark mode optimized for high contrast, reducing eye strain while highlighting critical data points.
- **Typography:** Segoe UI (Power BI default) for clean, professional readability.
- **Layout:** Intuitive 3-column grid structure topped with a prominent KPI strip header.

---

## Core DAX Measures

The backbone of our **KPI Analysis** relies on optimized DAX queries. Here are a few essential measures:

```dax
Sum of Profit = SUM(Sales[Profit])

Sum of Amount = SUM(Sales[Amount])

Sum of Quantity = SUM(Sales[Quantity])

Profit Margin % = DIVIDE([Sum of Profit], [Sum of Amount], 0)
```
*Explore all measures in [`docs/dax_measures.md`](docs/dax_measures.md).*

---

## Contributing

We welcome contributions to enhance the analytics capabilities!
1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/advanced-kpis`
3. Commit your changes: `git commit -m 'Add: Year-over-Year growth KPI'`
4. Push and open a Pull Request.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Author

**Your Name**
- GitHub: [@ShubhiGoel5](https://github.com/ShubhiGoel5)
- LinkedIn: [Shubhi Goel](https://www.linkedin.com/in/shubhi-goel-8aaa5a28a/)

---

*Built using Microsoft Power BI for Next-Generation Data Analytics*
