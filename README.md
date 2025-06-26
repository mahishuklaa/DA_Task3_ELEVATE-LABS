# DA_Task3_ELEVATE-LABS
# Task 3: Dashboard Design
<b>Objective:</b> Design an interactive dashboard for business stakeholders.<br><br>
<b>Tools:</b> Power BI<br><br>
<b>Dataset from Kaggle</b>: [Company Financials Dataset](https://www.kaggle.com/datasets/atharvaarya25/financials)<br><br>

# Financial Analysis Power BI Dashboard

![Financial Analysis Power BI Dashboard](https://github.com/user-attachments/assets/4b807f3b-2aa8-41e9-86dc-60d23153928a)

This Power BI dashboard provides a comprehensive financial overview using dynamic KPIs, charts, and slicers for interactive analysis of sales, profit, and business performance across multiple dimensions.

## Objectives

- Summarize key financial metrics (Sales, Profit, Units Sold, Margin)
- Analyze profitability and sales by Segment, Country, and Product
- Visualize profit trends over time
- Enable interactive filtering through Year, Month, Country, and Segment

## Data Source

- CSV file: `Financials.csv`
- Columns used: `Sales`, `Profit`, `Units Sold`, `Date`, `Segment`, `Country`, `Product`

## Key Features

| Section              | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| KPIs (Top Row)       | Total Sales (₹118M), Profit ($16.89M), Units Sold (1M), Profit Margin (14.33%) |
| Line Chart           | Monthly Profit Trend (2013–2014)                                            |
| Bar Charts           | Profit by Country, Sales by Segment, Profit by Product                      |
| Interactive Slicers  | Year, Month, Country, Segment                                               |
| Design               | One-page layout with teal theme, rounded visuals, and minimalist font       |

## DAX Measures Used

```dax
Total Sales = SUM(Financials[Sales])
Total Profit = SUM(Financials[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))
Sales Growth % = DIVIDE([Total Sales] - [Sales LY], [Sales LY])
Profit LY = CALCULATE([Total Profit], SAMEPERIODLASTYEAR(DateTable[Date]))
Profit Growth % = DIVIDE([Total Profit] - [Profit LY], [Profit LY])
