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

*Note: The actual cleaning decisions and results will be documented after the process is completed.*

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

*To be updated after completing the analysis.*

- **Overall Sales:** [Insert key finding]
- **Monthly Trends:** [Insert key finding]
- **Product Performance:** [Insert key finding]
- **Sales by Day:** [Insert key finding]
- **Order Type Comparison:** [Insert key finding]

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
