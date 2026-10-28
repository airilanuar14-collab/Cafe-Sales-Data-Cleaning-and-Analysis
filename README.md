# Cafe Sales Data Cleaning and Analysis

## Project Overview

This project focuses on cleaning and analysing a cafe sales dataset containing missing values, inconsistent entries, and other data quality issues. Microsoft Excel was used to clean the data, perform exploratory data analysis, and build an interactive dashboard using PivotTables, PivotCharts, Slicers, and Timeline.

The goal is to transform raw sales data into meaningful business insights that can help understand sales performance, product popularity, monthly trends, and customer purchasing patterns.

The dataset contains transaction records with data quality issues such as missing values, inconsistent entries, and invalid values. The project begins with data inspection and cleaning before proceeding to exploratory data analysis (EDA) to understand cafe sales performance and purchasing patterns.

## Tools 
Microsoft Excel : Data cleaning, data validation, exploratory analysis, PivotTables, PivotCharts, interactive Slicers, Timeline, and dashboard development.

## Project Objectives

- Identify and investigate data quality issues in the raw dataset.
- Clean and standardize data to improve consistency and usability.
- Validate transaction data and investigate potential inconsistencies.
- Analyze overall sales performance and monthly sales trends.
- Identify popular products and products contributing the highest sales.
- Examine sales patterns by day of the week.

## Dataset

**Source:** [Cafe Sales - Dirty Data for Cleaning Training (Kaggle)](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)

The dataset contains cafe transaction records with the following columns:

| Column | Description |
|---|---|
| Transaction ID | Unique identifier intended to identify a transaction |
| Item | Product purchased |
| Quantity | Number of units purchased |
| Price Per Unit | Price of each unit |
| Total Spent | Total amount recorded for the transaction |
| Payment Method | Payment method used |
| Location | Transaction location or order type |
| Transaction Date | Date of the transaction |

The raw dataset is intentionally imperfect and is used to practice data cleaning and validation techniques.

## Data Cleaning Process

The following checks and cleaning activities are planned for this project:

1. **Data Inspection**
   - Review dataset dimensions and column data types.
   - Check for missing values and invalid entries.
   - Investigate duplicate records and transaction identifiers.

2. **Missing Value Handling**
   - Identify missing values in each column.
   - Evaluate appropriate handling methods based on the context of each field.
   - Document decisions to retain, correct, exclude, or impute records where justified.

3. **Data Standardization**
   - Standardize categorical values and inconsistent text entries.
   - Convert numeric columns to appropriate data types.
   - Convert transaction dates into a valid date format.

4. **Data Validation**
   - Investigate invalid or implausible quantities and prices.
   - Compare `Total Spent` against `Quantity × Price Per Unit`, where applicable.
   - Review duplicate records before deciding whether removal is appropriate.

5. **Post-Cleaning Validation**
   - Recheck missing values, data types, and data consistency.
   - Compare the dataset before and after cleaning.
   - Document the final dataset dimensions and any remaining limitations.


## Research Questions

### 1. Overall Sales Performance
- What is the total sales revenue recorded in the dataset?
- What is the average transaction value?

### 2. Monthly Sales Trends
- How do sales change from month to month?
- Which month records the highest and lowest sales?

### 3. Product Performance
- Which products are the most popular based on units sold?
- Which products contribute the highest total sales?
- Do the most popular products also generate the highest sales?

### 4. Sales by Day of the Week
- Which day of the week records the highest total sales?
- How does the number of transactions compare across different days?

## Data Analysis

The analysis will focus on the following metrics:

- Total Sales
- Number of Valid Transactions
- Average Transaction Value
- Monthly Sales
- Units Sold by Product
- Total Sales by Product
- Sales by Day of the Week

The analysis will use cleaned and validated records, with exclusions and limitations documented where relevant.

## Visualizations

An interactive dashboard was developed in Microsoft Excel using PivotTables, PivotCharts, Slicers, and Timeline.

The dashboard is designed to help users explore sales performance dynamically without manually changing the underlying analysis.

**Dashboard components:**

- KPI cards for total sales, total of valid transactions, and average transaction value.
- Line chart for monthly sales trends.
- bar charts for product popularity and sales contribution.
- Horizontal Bar chart for sales by day of the week.
- Interactive Slicers for selected dimensions such as Item and Payment Method
- Timeline for filtering transaction dates

## Key Findings

1. **Overall Sales Performance**
- Total sales revenue: $89,096, across 9,977 transactions with a known total. Another 23 transactions have no recoverable total and aren't counted.
- Average transaction value: $8.93.
2. **Monthly Trends**
- Average Monthly Sales: The average monthly sales were approximately $7,076.88, based on total annual sales of $84,922.50 across 12 months.
- Month-to-Month Trends: Sales fluctuated throughout the year rather than following a consistent upward or downward trend.
- Highest and lowest month: June recorded the highest total sales at $7,353 while February  February recorded the lowest total sales a at $6,644, about 11% below June. February's low is partly the calendar, since it has 28 days.
3. **Product Performance**
- Most popular by units sold: Coffee (3,904), followed by Salad (3,819), Tea (3,650) and Cookie (3,598). Coffee also leads on transactions (1,291). Smoothie is lowest at 3,336.
- Highest total sales: Salad ($19,095). Sandwich ($13,716) and Smoothie ($13,344) follow. Cookie is lowest at $3,598.
- The most popular products are not the biggest earners. Coffee is 1st on units sold but 6th on sales, because it costs $2. Sandwich are 7th on units sold but 2nd on sales.
4. **Sales by Day:**
- Day with highest total sales: Thursday ($12,401.5), then Friday ($12,334.0) and Sunday ($12,287.5). Wednesday is lowest ($11,680.5). Thursday also leads on average daily sales (238.5 vs 224.6 for Wednesday). That comparison matters because 2023 had 53 Sundays and 52 of every other day.
- Transaction counts are close across the week. Friday has the most (1,388) and Tuesday the fewest (1,311), a spread of about 6%. Every weekday averages 25 to 27 transactions a day.

## Business Recommendations

Based on the sales analysis, the following recommendations could help the cafe improve sales performance, product planning, and operational decision-making.

1. Overall Sales Performance
- Investigate transactions with missing or unrecoverable totals to identify potential issues in data entry or transaction recording.
- Use average transaction value as a baseline for monitoring changes in spending patterns over time, rather than treating a single period as a performance target.
2. Monthly Sales Trends
- Investigate factors that may explain monthly fluctuations, such as promotions, product availability, operating days, and seasonal demand.
- Compare sales across equivalent periods and consider the number of operating days when evaluating monthly performance.
- Review the November and December declines to determine whether they reflect normal seasonal variation or specific operational factors.
- Use historical monthly sales patterns to support inventory planning and promotional scheduling, while validating the trends with additional data where available.
3. Product Performance
- Prioritize stock availability for high-volume products such as Coffee and Salad to reduce the risk of stockouts.
- Review Salad's sales contribution and consider maintaining its availability, while assessing its ingredient costs and profitability before making major investment decisions.
- Evaluate opportunities to increase the sales value of popular lower-priced products through suitable product combinations or optional add-ons, provided these align with customer preferences.
- Avoid discontinuing lower-ranked products based on sales revenue alone. Consider unit demand, ingredient costs, waste, and profit margins before making product assortment decisions.
4. Sales by Day of the Week
- Review staffing and inventory requirements for Thursday, Friday, and Sunday to ensure the cafe can accommodate observed demand.
- Consider testing targeted midweek promotions and evaluate their results before adopting them permanently.
5. Data Quality and Reporting Improvements
- Fix data capture first. 32% of transactions have no payment method, 40% have no location and 5% have no date. That makes channel and payment analysis unreliable. Make these fields required at the till, and validate that quantity × price = total at entry.


## Limitations

- The analysis depends on the completeness and accuracy of the available transaction records.
- Missing or invalid values may affect calculated sales metrics and comparisons.
- The dataset does not provide sufficient information to calculate actual profit, operating costs, or individual customer behavior.
- Observed patterns do not necessarily establish causal relationships.

## Conclusion

This project demonstrates an end-to-end beginner data analytics workflow, from investigating and cleaning a messy dataset to analysing business performance and presenting findings through an interactive Excel dashboard.

By combining data quality checks, exploratory analysis, and interactive filtering, the project provides a practical way to explore cafe sales performance and communicate findings that can support further business investigation.
