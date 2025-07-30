# Sales Report 2023-2024

## Project Overview
This project is a comprehensive Excel dashboard that visualizes and analyzes product sales, profitability, and business trends for the years 2023–2024. It uses clean pivot logic, interactive filters, and formula-driven calculations to provide a decision-making tool for sales performance monitoring.

## Files Included
- `Sales Report Dashboard.xlsx` — Excel workbook containing:
  - **Catalogue** – Master data for products and pricing
  - **Sales Report** – Raw transaction data
  - **Pivot** – Data summaries for the dashboard
  - **Dashboard** – Final visual analytics interface
- `dashboard-preview.png` - Dashboard Screenshot

## Features / Highlights
- **Trend Analysis**: Monthly profit trends with visual trendline indicating growth  
- **Combo Chart**: Top 10 Profitable Products with average cost, revenue, and total profit per product  
- **Data Table**: Top 10 Purchased Products with quantity sold, total profit, and profit per unit — color-coded for clarity  
- **Bar Chart**: Average Unit Price across different product categories  
- **Stacked Column Chart**: Payment Mode Analysis comparing cash vs. online by sales type  
- **Interactive Filters**: Year and Sales Type slicers for dynamic and personalized exploration

## Tools & Technologies Used
- Microsoft Excel 
  - PivotTables and PivotCharts
  - Conditional Formatting
  - INDEX + MATCH lookup formulas
  - Combo charts and trendlines
  - Slicers for interactivity

## Calculations & Logic

### Derived Fields 

| Column            | Formula Example                             | Purpose                                 |
|-------------------|---------------------------------------------|-----------------------------------------|
| **Buying Value**  | `=Buying Price × QTY`                       | Total cost of items sold                |
| **Selling Value** | `=Selling Price × QTY`                      | Total income from sales                 |
| **Profit**        | `=Revenue – Cost`                           | Total gross profit                      |
| **Profit/Unit**   | `=Profit / QTY`                             | Profit earned for each unit sold        |

These metrics feed directly into pivot tables and dashboard charts.

### Price Lookup (INDEX + MATCH)

Product pricing (buying and selling) was dynamically pulled into the Sales Report sheet using `INDEX + MATCH` formulas:

```excel
=INDEX(catalogue[BUYING PRICE],MATCH([@[PRODUCT ID]],catalogue[PRODUCT ID],0))  // Buying Price
=INDEX(catalogue[SELLING PRICE],MATCH([@[PRODUCT ID]],catalogue[PRODUCT ID],0))  // Selling Price
```

This acts as a substitute for XLOOKUP and ensures compatibility with older Excel versions.

## Key Insights / Observations
- Profit peaked in March 2024 and showed a declining trend through May, as seen in the monthly profit line chart.
- Product P0031 led both in quantity sold and profit, making it the top-performing product overall.
- Wholesalers made the majority of purchases across both cash and online payments, with a clear preference for online mode.
- Slicers allow filtering by year and sales type, enabling dynamic exploration of data patterns over time and by transaction mode.

## Dashboard Preview 
<img width="1867" height="628" alt="dashboard-preview" src="https://github.com/user-attachments/assets/3768df07-c066-43d3-a113-6beae9783817" />

## Future Enhancements
- Add KPI Cards: Total Sales, Average Order, Total Orders
- Export to Power BI for advanced analytics

## Notes
- A data model relationship has been created between the Sales Report and Catalogue tables via PRODUCT ID.
- Both tables are formatted as Named Tables for cleaner references:
  - sales_report
  - catalogue
- While these relationships are not actively used in dashboard visuals, they provide a solid base for future enhancements such as:
  - Power Pivot or Power BI integration
  - Dynamic filtering by category
  - More advanced DAX measures
- In the raw data sheets (e.g., *Sales Report*), column names like `Buying Price`, `Selling Price`, `Buying Value`, and `Selling Value` are used. In the dashboard and README, we refer to them more clearly as:
  - `Buying Price` → **Unit Cost**
  - `Selling Price` → **Unit Price**
  - `Buying Value` → **Cost**
  - `Selling Value` → **Revenue**

This helps align industry terminology with the visuals in the dashboard.



