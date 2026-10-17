# Sales Performance & Profitability Analysis | Power BI

## Project Overview

This project uses **Power BI** to explore sales performance and profitability across products, product categories, sales channels, payment methods, and time. The report is designed to help users review headline performance measures and investigate how sales are distributed across the business.

The repository includes the Power BI report and its supporting Excel workbook.

## Business Objectives

- Monitor overall sales, buying cost, profit, and profit percentage.
- Explore sales and profit trends by month and year.
- Compare product and category sales performance.
- Understand sales distribution by sale type and payment mode.
- Use report filters to investigate results for selected years and months.

## Tools Used

- **Microsoft Power BI Desktop** — report design, visualizations, filtering, and measures
- **Microsoft Excel** — source workbook and tabular data
- **GitHub** — project versioning and portfolio presentation

## Dataset Overview

The Excel workbook contains the following sheets:

| Sheet | Purpose |
|---|---|
| `Input Data` | Transaction-level sales data used by the report |
| `Master Data` | Product reference data, including product ID, product name, category, unit of measure, buying price, and selling price |
| `Sheet1` | Supporting summary/pivot-style calculations |
| `Dashboard` | Empty worksheet in the supplied workbook |

### Input Data fields

The transaction data includes:

- `DATE`, `Year`, `Month`, `Day`
- `PRODUCT ID`, `PRODUCT`, `CATEGORY`, `UOM`
- `QUANTITY`
- `BUYING PRIZE`, `SELLING PRICE`
- `Total Buying`, `Total Selling`
- `SALE TYPE`, `PAYMENT MODE`, `DISCOUNT %`

### Dataset profile

Based on the supplied workbook:

- **527** transaction rows in `Input Data`
- Transaction dates from **1 January 2021 to 31 December 2022**
- **45** product records in `Master Data`
- **5** product categories
- **3** sale types and **2** payment modes in the transaction data

The supplied transaction sheet has no blank values in its 16 columns. This is a basic completeness check, not a guarantee that every business rule or calculation is correct.

## Dashboard Features

The Power BI report includes:

- **KPI cards:** Total Sales, Total Profit, and Profit %
- **Year and month slicers:** filter the report by time period
- **Monthly performance chart:** compare sales and profit by month
- **Product sales chart:** compare sales across products
- **Category sales view:** compare sales across product categories
- **Sales-type breakdown:** compare Direct Sales, Online, and Wholesaler
- **Payment-mode breakdown:** compare Cash and Online payments
- **Daily sales view:** examine sales by day number

## Initial Data Summary

The following totals are calculated from the supplied `Input Data` worksheet by summing its existing transaction-level totals:

| Metric | Value |
|---|---:|
| Total Selling | 401,411.92 |
| Total Buying | 332,504.00 |
| Difference between selling and buying totals | 68,907.92 |
| Difference as a share of Total Selling | 17.16% |

**Calculation note:** The difference above is calculated as `Total Selling - Total Buying`. It is a simple dataset-level calculation and should be treated as profit only if the workbook's buying and selling totals represent the intended business definitions and exclude/handle discounts, returns, taxes, and other costs appropriately. The source workbook does not specify the currency, so confirm the currency and number formatting in Power BI before presenting these figures externally.

## Questions This Dashboard Can Help Explore

- How do sales and profit vary across months and years?
- Which products contribute the most to sales?
- Which categories have the highest and lowest sales?
- How are sales split across Direct Sales, Online, and Wholesaler?
- How do sales compare between Cash and Online payment modes?
- How do results change when a year or month is selected?

## Key Interpretation Notes

- **Sales are not the same as profit.** High sales do not necessarily mean a product is the most profitable.
- **The daily chart uses `Day` (day of month).** If the report includes multiple months, days such as the 1st or 15th can aggregate across different months. Use the full `DATE` field or a proper calendar table when the goal is a continuous daily trend.
- **Month ordering should be chronological.** Sort the text `Month` field by a month-number column so charts show Jan–Dec rather than alphabetical order.
- **Discount values are all zero in the supplied transaction sheet.** Therefore, this workbook currently cannot support a meaningful comparison of different discount levels against sales or profit.
- **Quantity combines multiple units of measure.** Avoid interpreting a total quantity across Kg, Ft, and other units as one directly comparable physical total unless the units are standardized.
- **Currency and profit definitions should be validated.** The report's display formatting and the business meaning of `BUYING PRIZE`, `SELLING PRICE`, `Total Buying`, and `Total Selling` should be confirmed before drawing financial conclusions.

## Repository Contents

Suggested repository structure:

```text
sales-performance-profitability-analysis/
├── README.md
├── Sales-Dashboard-File.pbix
├── Sales-Dashboard-File.xlsx
└── screenshots/
    ├── sales-dashboard-overview.png
    ├── monthly-sales-profit-trend.png
    ├── top-products-performance.png
    └── sales-by-category.png
```

Use the exact filenames that you upload to GitHub. Add screenshots to the `screenshots/` folder and embed the main report image below when it is available.

## Dashboard Preview

<!-- After uploading a screenshot, uncomment and update this path:
![Sales dashboard overview](screenshots/sales-dashboard-overview.png)
-->

## How to View the Project

1. Download or clone this repository.
2. Open `Sales-Dashboard-File.pbix` in **Power BI Desktop**.
3. If Power BI asks to locate or refresh the source data, point it to the included Excel workbook and confirm the relevant sheet/table connection.
4. Use the Year and Month slicers to explore the report.
5. Open the Excel workbook to review the source data and supporting sheets.

## Limitations and Future Improvements

- Add a proper calendar table and use it for date filtering and time-intelligence calculations.
- Confirm month sorting and ensure all trend visuals use the appropriate date granularity.
- Add dedicated measures for revenue, cost, profit, and profit margin with documented business definitions.
- Add a profitability-focused product view rather than ranking products only by sales.
- Validate the source currency, discounts, returns, and other costs before treating the dashboard as a financial reporting tool.
- Consider replacing or supplementing pie charts with bar charts when precise category comparisons are important.
- Add a short findings section supported by verified dashboard results and screenshots.

## Author

**Karandeep Sandul**

This project was created as a data analytics portfolio project to practice data exploration, business reporting, and dashboard development with Power BI.
