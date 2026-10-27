# Cafe Sales Data Cleaning and Analysis

## Project Overview

This project focuses on cleaning and analyzing a dirty cafe sales dataset to improve data quality and generate meaningful business insights.

The dataset contains transaction records with data quality issues such as missing values, inconsistent entries, and invalid values. The project begins with data inspection and cleaning before proceeding to exploratory data analysis (EDA) to understand cafe sales performance and purchasing patterns.

**Tools:** Microsoft Excel, Tableau

## Project Objectives

- Identify and investigate data quality issues in the raw dataset.
- Clean and standardize data to improve consistency and usability.
- Validate transaction data and investigate potential inconsistencies.
- Analyze overall sales performance and monthly sales trends.
- Identify popular products and products contributing the highest sales.
- Examine sales patterns by day of the week.
- Compare sales performance between in-store and takeaway transactions.

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

### 5. In-Store vs Takeaway
- How do total sales differ between in-store and takeaway transactions?
- How do transaction counts and average transaction values compare between the two order types?

## Data Analysis

The analysis will focus on the following metrics:

- Total Sales
- Number of Valid Transactions
- Average Transaction Value
- Monthly Sales
- Units Sold by Product
- Total Sales by Product
- Sales by Day of the Week
- Sales by Order Type

The analysis will use cleaned and validated records, with exclusions and limitations documented where relevant.

## Visualizations

Planned visualizations include:

- KPI cards for total sales, valid transactions, and average transaction value.
- Line chart for monthly sales trends.
- Horizontal bar charts for product popularity and sales contribution.
- Bar chart for sales by day of the week.
- Bar charts comparing in-store and takeaway performance.

**Dashboard:** [Insert Tableau Public link]

## Key Findings

1. **Overall Sales Performance**
- Total sales revenue: $89,096, across 9,977 transactions with a known total. Another 23 transactions have no recoverable total and aren't counted.
- Average transaction value: $8.93 (median 8.00). Values move in steps because menu prices are fixed and quantities run from $1 to $5, so transactions range from 1.0 to 25.0.
2. **Monthly Trends**
- Average Monthly Sales: The average monthly sales were approximately $7,076.88, based on total annual sales of $84,922.50 across 12 months.
- Month-to-Month Trends: Sales fluctuated throughout the year rather than following a consistent upward or downward trend. Sales increased from February to March, declined slightly in May, and reached their highest level in June before fluctuating during the second half of the year. Sales rose again in October before declining in November and December.
- Highest and lowest month: June recorded the highest total sales at $7,353 while February  February recorded the lowest total sales a at $6,644, about 11% below June. February's low is partly the calendar, since it has 28 days.
3. **Product Performance**
- Most popular by units sold: Coffee (3,904), followed by Salad (3,819), Tea (3,650) and Cookie (3,598). Coffee also leads on transactions (1,291). Smoothie is lowest at 3,336.
- Highest total sales: Salad ($19,095), about 23% of sales. Sandwich ($13,716) and Smoothie ($13,344) follow. Cookie is lowest at $3,598.
- The most popular products are not the biggest earners. Coffee is 1st on units sold but 6th on sales, because it costs $2. Sandwich are 7th on units sold but 2nd on sales.
4. **Sales by Day:**
- Day with highest total sales: Thursday ($12,401.5), then Friday ($12,334.0) and Sunday ($12,287.5). Wednesday is lowest ($11,680.5). Thursday also leads on average daily sales (238.5 vs 224.6 for Wednesday). That comparison matters because 2023 had 53 Sundays and 52 of every other day.
- Transaction counts are close across the week. Friday has the most (1,388) and Tuesday the fewest (1,311), a spread of about 6%. Every weekday averages 25 to 27 transactions a day.
- **Order Type Comparison:** [Insert key finding]
5. **In-Store vs Takeaway**
- Total sales: In-store $27,174.0 vs Takeaway $26,552.5. The gap is $621.5, or 2.3%, which is 50.6% vs 49.4% of sales where the location is known.
- Transaction counts: 3,017 in-store vs 3,022 takeaway, effectively identical.
- Average transaction value: 9.03 in-store vs 8.80 takeaway. The 0.23 gap is about 1.5 standard errors, which isn't convincing evidence of a real difference. In-store's small edge in sales comes from slightly higher spend per transaction, not more transactions.
Location is unknown for 3,961 transactions (39.6%, worth 35,369.5 in sales), so this comparison covers about 60% of the data.

## Business Recommendations

*To be updated based on the actual findings.*

Potential recommendations may include reviewing inventory planning, identifying products for further investigation, and evaluating staffing needs based on observed sales patterns.

Recommendations will be made only where supported by the analysis.

## Limitations

- The analysis depends on the completeness and accuracy of the available transaction records.
- Missing or invalid values may affect calculated sales metrics and comparisons.
- The dataset does not provide sufficient information to calculate actual profit, operating costs, or individual customer behavior.
- Observed patterns do not necessarily establish causal relationships.

## Project Status

**Status:** In Progress

Data cleaning, validation, exploratory data analysis, and visualization results will be updated as the project develops.
