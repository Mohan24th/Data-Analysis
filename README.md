# Customer Shopping Behavior Analysis

An end-to-end data analytics learning project exploring customer purchasing patterns using Python, PostgreSQL, SQL, and Power BI.

## Project Overview

This project analyzes customer shopping behavior to understand purchasing patterns, customer segments, product preferences, discount usage, and subscription behavior.

I worked through this project as part of my learning journey in data analytics, following a tutorial-based approach to gain practical experience with the tools and techniques used in a typical analytics workflow. The project helped me understand how raw data can be cleaned, stored, queried, visualized, and translated into business-oriented insights.

The objective is to explore how customer data can support better marketing decisions, customer engagement, product positioning, and loyalty strategies.

## Business Problem

A retail business wants to better understand its customers and purchasing patterns. The analysis focuses on questions such as:

- Which customer segments contribute the most revenue?
- How do purchasing patterns differ across age groups and genders?
- Which products receive the highest ratings and generate the most purchases?
- How are discounts associated with customer purchasing behavior?
- How do subscribers and non-subscribers compare?
- What patterns can be identified among repeat buyers and loyal customers?

The goal is to use data analysis to identify meaningful patterns and develop practical business recommendations.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data preparation, cleaning, and feature engineering |
| Pandas | Data manipulation and exploratory data analysis |
| Jupyter Notebook | Interactive analysis and documentation |
| PostgreSQL | Structured data storage and querying |
| SQL | Business analysis, aggregations, filtering, and customer segmentation |
| SQLAlchemy | Connecting Python with PostgreSQL |
| Power BI | Interactive dashboard and visual reporting |
| Git and GitHub | Version control and project documentation |

## Dataset

The dataset contains **3,900 customer purchase records and 18 original columns**.

It includes information about:

- **Customer demographics:** Age, gender, location, and subscription status.
- **Purchase details:** Item purchased, category, purchase amount, season, size, and color.
- **Shopping behavior:** Discount usage, previous purchases, and purchase frequency.
- **Customer experience:** Review ratings and shipping preferences.

The original dataset contains 37 missing values in the review rating column. The notebook addresses these missing values during the data preparation stage.

## Project Workflow

### 1. Data Preparation and Exploratory Data Analysis — Python

The dataset was loaded into Pandas and explored to understand its structure, data types, summary statistics, and missing values.

The preparation process includes:

- Loading and inspecting the dataset.
- Examining column information and descriptive statistics.
- Identifying missing values.
- Imputing missing review ratings using the median rating within each product category.
- Standardizing column names to snake_case for consistency.
- Creating an `age_group` feature using age-based quantile bins.
- Converting purchase frequency categories into an approximate number of days using a mapping.
- Checking whether `discount_applied` and `promo_code_used` contain redundant information and removing the latter based on the check performed.
- Connecting Python to PostgreSQL and loading the prepared DataFrame into a database table.

These steps provided practical exposure to data cleaning, feature engineering, consistency checks, and database integration.

### 2. SQL Analysis — PostgreSQL

After preparing the data, I used SQL to answer business-oriented questions and practice querying structured data.

The analysis covers the following ten questions:

1. **Revenue by Gender:** Compare total purchase revenue between male and female customers.
2. **High-Spending Discount Users:** Identify customers who used discounts and spent at least the average purchase amount.
3. **Top-Rated Products:** Find the five products with the highest average review ratings.
4. **Shipping Type Comparison:** Compare average purchase amounts for Standard and Express shipping.
5. **Subscription Analysis:** Compare customer counts, average spending, and total revenue between subscribers and non-subscribers.
6. **Discount-Dependent Products:** Identify the five products with the highest percentage of purchases involving discounts.
7. **Customer Segmentation:** Categorize customers as New, Returning, or Loyal based on previous purchase counts.
8. **Top Products by Category:** Rank the three most frequently purchased products within each category.
9. **Repeat Buyers and Subscriptions:** Examine subscription status among customers with more than five previous purchases.
10. **Revenue by Age Group:** Calculate and compare revenue contributions across age groups.

The SQL queries provide practice with `GROUP BY`, aggregate functions, `CASE` expressions, subqueries, common table expressions (CTEs), and window functions.

### 3. Interactive Dashboard — Power BI

The Power BI dashboard presents key metrics and comparisons in a visual format.

The dashboard includes:

- Total customer count.
- Average purchase amount.
- Average review rating.
- Customer distribution by subscription status.
- Revenue and sales comparisons by product category.
- Revenue and sales comparisons by age group.
- Filters for subscription status, gender, category, and shipping type.

The purpose of the dashboard is to make the results easier to explore and interpret without relying exclusively on SQL query outputs.

### 4. Reporting and Documentation

The project also includes supporting documentation describing the business problem, analytical workflow, findings, and recommendations.

The report connects the Python, SQL, and Power BI stages and summarizes potential actions that a retail business could consider based on the observed patterns.

## Selected Findings

The following are examples of results documented in the project report:

- **Revenue by gender:** Male customers contributed 157,890 in purchase revenue, compared with 75,191 for female customers.
- **Subscription behavior:** Subscribers had an average purchase amount of 59.49, while non-subscribers averaged 59.87.
- **Shipping comparison:** Average purchase amounts were 58.46 for Standard shipping and 60.48 for Express shipping.
- **Customer segments:** The SQL segmentation query classified 3,116 records as Loyal, 701 as Returning, and 83 as New.
- **Age groups:** Young Adults contributed the highest total revenue among the four age groups in the reported analysis.

These findings describe the analyzed dataset; they do not establish that any particular factor caused a purchasing outcome. Revenue and segment counts should also be interpreted in the context of the dataset and the definitions used in the analysis.

## Business Recommendations

Based on the patterns explored, the project report proposes the following potential actions:

- **Improve subscription engagement:** Explore subscriber benefits and targeted campaigns to encourage subscription adoption.
- **Encourage customer loyalty:** Consider loyalty rewards and retention initiatives for repeat customers.
- **Review discount strategies:** Examine discount usage across products while considering profitability and margins.
- **Promote relevant products:** Use product ratings and purchase frequency to inform product campaigns.
- **Use customer segmentation:** Tailor marketing initiatives to different age groups and purchasing segments.

These recommendations are starting points for further analysis and would require additional validation before implementation.

## Repository Structure

```text
Customer-trend/
│
├── customer_shopping_behavior.csv
├── Customer_Shopping_Behavior_Analysis.ipynb
├── customer_behavior_sql_queries.sql
├── customer_behavior_dashboard.pbix
├── Business Problem  Document.pdf
├── Customer Shopping Behavior Analysis.pdf
└── README.md
```

### File Description

| File | Description |
|---|---|
| `customer_shopping_behavior.csv` | Original customer shopping dataset |
| `Customer_Shopping_Behavior_Analysis.ipynb` | Python notebook for data cleaning, exploration, feature engineering, and PostgreSQL integration |
| `customer_behavior_sql_queries.sql` | SQL queries used to investigate the business questions |
| `customer_behavior_dashboard.pbix` | Power BI dashboard file |
| `Business Problem  Document.pdf` | Business problem statement and project objectives |
| `Customer Shopping Behavior Analysis.pdf` | Project report containing methodology, results, dashboard, and recommendations |
| `README.md` | Project overview and documentation |

## How to Explore the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook
- Pandas
- PostgreSQL
- SQLAlchemy
- `psycopg2-binary`
- Power BI Desktop

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mohan24th/Data-Analysis.git
cd Data-Analysis
```

### Step 2: Set Up the Python Environment

Create and activate a virtual environment if desired, then install the required packages:

```bash
pip install pandas sqlalchemy psycopg2-binary jupyter
```

### Step 3: Run the Notebook

Open Jupyter Notebook:

```bash
jupyter notebook
```

Open `Customer_Shopping_Behavior_Analysis.ipynb` and execute the cells in sequence.

Ensure the CSV file is available at the path expected by the notebook.

### Step 4: Configure PostgreSQL

Install and start PostgreSQL, create a database named `customer_behavior`, and update the connection settings in the notebook to match your local configuration.

The notebook uses SQLAlchemy and the PostgreSQL driver to load the prepared DataFrame into a table named `customer`.

**Note:** Replace the example connection credentials in the notebook with your own local credentials. Do not commit database passwords or other secrets to GitHub.

### Step 5: Run the SQL Queries

Open `customer_behavior_sql_queries.sql` in your preferred PostgreSQL client, such as pgAdmin.

Connect to the database containing the prepared `customer` table and execute the queries to explore the business questions.

### Step 6: Explore the Dashboard

Open `customer_behavior_dashboard.pbix` using Power BI Desktop to interact with the dashboard and explore the available filters and visualizations.

## Learning Outcomes

Working through this project gave me practical exposure to:

- Exploring and cleaning structured datasets using Pandas.
- Handling missing values and creating derived features.
- Writing SQL queries to answer business questions.
- Using aggregations, subqueries, CTEs, and window functions.
- Integrating Python with PostgreSQL.
- Designing an interactive dashboard in Power BI.
- Presenting analytical results through reports and business recommendations.
- Organizing an analytics project using Git and GitHub.

## Project Scope and Learning Approach

This is a tutorial-based learning project built using a conventional customer shopping dataset. The implementation follows a guided workflow, and the project serves as a practical exercise in applying data analytics tools together.

I am sharing it as part of my ongoing learning journey to strengthen my understanding of data analytics concepts and build hands-on experience with real-world analytical workflows.

The project is a foundation for further practice, including more independent analysis, additional validation, and exploration of more advanced analytical methods.

## Future Improvements

- Perform deeper exploratory analysis to identify additional patterns.
- Add more robust data validation and automated quality checks.
- Expand the SQL analysis with additional customer and product metrics.
- Improve dashboard interactivity and visual design.
- Investigate relationships between discounts, repeat purchases, and subscription behavior.
- Explore statistical methods to validate observed patterns.

## Acknowledgment

This project was completed as a learning exercise using a tutorial-guided approach. The purpose of publishing it is to document my practical experience, demonstrate the analytics workflow I have worked through, and continue improving my skills in Python, SQL, PostgreSQL, and Power BI.
