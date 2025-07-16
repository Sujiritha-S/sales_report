# Sales Report Dashboard (2023–2024)

This project is a comprehensive Excel dashboard that visualizes and analyzes product sales, profitability, and business trends for the years 2023–2024. It uses clean pivot logic, interactive filters, and formula-driven calculations to provide a decision-making tool for sales performance monitoring.

## Files Included

- `Sales Report Dashboard.xlsx` — Excel workbook containing:
  - **Catalogue** – Master data for products and pricing
  - **Sales Report** – Raw transaction data
  - **Pivot** – Data summaries for the dashboard
  - **Dashboard** – Final visual analytics interface

## Key Features

### Dashboard Components

- **Profit Trend (Monthly)**  
  Line chart showing how profit changes over time, with trendline indicating growth direction.

- **Top 10 Profitable Products**  
  Combo chart visualizing average cost/revenue alongside total profit per product.

- **Top 10 Purchased Products**  
  Table showing products with highest quantity sold, total profit, and profit per unit — color-coded for easy analysis.

- **Average Unit Price by Category**  
  Bar chart comparing price levels across product categories.

- **Payment Mode Analysis**  
  100% stacked column chart showing customer preference for cash or online payments by sales type.

- **Interactive Filters**  
  Slicers for Year and Sales Type allow dynamic views and easy exploration.

## Calculations & Logic

### Price Lookup (INDEX + MATCH)

Product pricing (buying and selling) was dynamically pulled into the Sales Report sheet using `INDEX + MATCH` formulas:

```excel
=INDEX(catalogue[BUYING PRICE],MATCH([@[PRODUCT ID]],catalogue[PRODUCT ID],0))  // Buying Price
=INDEX(catalogue[SELLING PRICE],MATCH([@[PRODUCT ID]],catalogue[PRODUCT ID],0))  // Selling Price
```

This acts as a substitute for XLOOKUP and ensures compatibility with older Excel versions.

### Derived Fields in Sales Report
Column	Formula Example	Purpose
Buying Value	=Buying Price × QTY	Total cost of items sold
Selling Value	=Selling Price × QTY	Total revenue from sales
Profit	=Selling Value – Buying Value	Total gross profit
Profit per Unit	=Profit / QTY	Unit-wise profitability for comparison
These metrics feed directly into pivot tables and dashboard charts.

## Business Insights Enabled
- Track monthly profit performance and trends
- Identify high-demand vs. high-profit products
- Discover low-margin bestsellers that may need repricing
- Analyze payment behavior by customer segment
- Monitor category pricing differences

## Tools Used
- Microsoft Excel 
 - PivotTables and PivotCharts
 - Conditional Formatting
 - INDEX + MATCH lookup formulas
 - Combo charts and trendlines
 - Slicers for interactivity

## Notes
- A data model relationship has been created between the Sales Report and Catalogue tables via PRODUCT ID.
- Both tables are formatted as Named Tables for cleaner references:
 - sales_report
 - catalogue
- While these relationships are not actively used in dashboard visuals, they provide a solid base for future enhancements such as:
 - Power Pivot or Power BI integration
 - Dynamic filtering by category
 - More advanced DAX measures

## Getting Started
- To explore the dashboard:
- Open the Excel file.
- Go to the Dashboard sheet.
- Use the slicers (Year, Sales Type) to filter and analyze data.
- Hover over charts or review tables to interpret insights.

## Future Enhancements
- Add KPI Cards: Total Sales, Average Order, Total Orders
- Export to Power BI for advanced analytics


