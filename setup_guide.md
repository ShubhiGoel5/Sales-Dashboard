# Setup Guide — Sales Dashboard

Step-by-step instructions to get the dashboard running locally.

---

## Prerequisites

| Tool | Version | Link |
|---|---|---|
| Power BI Desktop | Latest | [Download](https://powerbi.microsoft.com/desktop/) |
| Windows | 10 / 11 | — |
| Git | Any | [Download](https://git-scm.com/) |

> **Note**: Power BI Desktop is Windows-only. Mac users can use a Windows VM or publish to Power BI Service.

---

## Step 1 — Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/sales-dashboard.git
cd sales-dashboard
```

---

## Step 2 — Open the Report

1. Launch **Power BI Desktop**
2. Click **File → Open report → Browse reports**
3. Navigate to the cloned folder and select `SalesDashboard.pbix`
4. Click **Open**

---

## Step 3 — Connect Data Source

If the data source path is broken (yellow warning banner):

1. Click **Transform Data** in the Home ribbon
2. Go to **Data Source Settings**
3. Click **Change Source...**
4. Browse to `data/sales_data.csv` in the cloned repo
5. Click **OK → Close & Apply**

---

## Step 4 — Apply Custom Theme (Optional)

1. Go to **View** tab → **Themes**
2. Click the dropdown arrow → **Browse for themes**
3. Select `docs/color_theme.json`
4. The purple/pink gradient theme will apply automatically

---

## Step 5 — Refresh Data

Click **Home → Refresh** to reload all visuals with the latest data.

---

## Using the Dashboard

### Quarter Buttons
- Click **Qtr 1 / Qtr 2 / Qtr 3 / Qtr 4** to filter all visuals by quarter
- Click the active button again to clear the filter (show all quarters)

### Cross-Filtering
- Click any bar, slice, or data point to cross-filter all other visuals
- Hold **Ctrl** to select multiple items

### Tooltips
- Hover over any chart element to see detailed values in a tooltip

---

## Publishing to Power BI Service

1. Sign in to your Power BI account in Desktop
2. Click **Home → Publish**
3. Select a workspace
4. Access the report at [app.powerbi.com](https://app.powerbi.com)

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Data source error | Re-link CSV via Transform Data → Data Source Settings |
| Visuals not loading | Click Refresh in the Home ribbon |
| Theme not applying | Manually browse and select `color_theme.json` |
| Profit shows blank | Check that `Profit` column has no text values in the CSV |
| Month order wrong | Sort `Month` column by `Month Number` in column settings |

---

## Folder Reference

```
sales-dashboard-repo/
├── SalesDashboard.pbix     ← Open this in Power BI Desktop
├── data/
│   ├── sales_data.csv      ← Point data source here
│   └── data_dictionary.md
├── docs/
│   ├── setup_guide.md      ← You are here
│   ├── dax_measures.md
│   └── color_theme.json
└── screenshots/
    └── dashboard_preview.png
```
