# Customer_Behavior_Analysis

It's an end-to-end data analytics project focused on understanding customer behavior using transactional, demographic, and engagement data. Tools used are Python, SQL and Power BI.

**📝 Overview**

This project focuses on analyzing customer shopping behaviour using Python and SQL to derive actionable business insights.
The workflow includes loading the dataset, performing Exploratory Data Analysis (EDA), cleaning and transforming data, answering business questions with SQL, and finally building an interactive dashboard for reporting and decision-making.
The goal is to demonstrate end-to-end data analytics capability—from raw data to insights to visualization.

**📂 Dataset**

Source: Provided CSV dataset
Size: 3900 rows & 18 columns
Description: The dataset provides a comprehensive view of customer shopping behaviour across various demographics, product attributes, and transactional details. It includes information on what customers purchase, how much they spend, their preferences in size, color, and seasonality, as well as engagement indicators such as subscription status, review ratings, and frequency of purchases. Along with product-level details, the dataset captures shopping patterns like payment methods, discounts used, promo codes applied, and past purchase history. Overall, it enables a complete end-to-end analysis of customer behaviour, spending habits, and factors influencing purchase decisions.

**🚀 Project Workflow Summary**

*1. Data Loading*

Installed required libraries and loaded the dataset into Python using Pandas.
Imported the CSV file using pd.read_csv() and created a working DataFrame (df).
Performed initial checks, including the number of rows and columns, data types, and null value counts.

*2. Exploratory Data Analysis (EDA)*

Reviewed dataset structure and descriptive statistics for both numerical and categorical variables.
Identified missing values, especially in the Review Rating column.
Evaluated overall data quality, column formats, and value distributions to plan necessary cleaning steps.

*3. Data Cleaning & Feature Engineering*

Handled Missing Values:
Filled missing Review Rating values by replacing them with the median rating of each category using group-wise imputation.

Standardized Column Names:
Converted all column names to lowercase and replaced spaces with underscores for consistency and SQL compatibility.

Renamed Columns:
Renamed long or inconsistent column names (e.g., purchase_amount_(usd)) for easier handling.

Created Age Group Segments:
Generated quantile-based age groups using pd.qcut.
Added an alternative fixed age segmentation using pd.cut for flexibility.

Converted Purchase Frequency to Numeric Days:
Mapped text-based purchase frequency (Weekly, Monthly, Quarterly, etc.) to numeric day values to support analysis.

Removed Redundant Columns:
Verified that discount_applied and promo_code_used contained the same information and dropped the redundant column.

*4. Preparing Data for SQL Analysis*

Installed PostgreSQL connector libraries (psycopg2-binary, sqlalchemy).
Cleaned and transformed dataset made ready for database insertion.
Established a connection between Jupyter Notebook and PostgreSQL.
Loaded the final cleaned DataFrame into a PostgreSQL table to run SQL queries efficiently and answer business questions.

**🗄️ SQL Analysis**

A set of business-focused SQL queries was executed on the cleaned PostgreSQL dataset to uncover customer behavior, spending patterns, and product performance. Key analysis includes:

Revenue by Gender: Calculated total revenue generated from male and female customers to identify spending differences across demographics.

High-Spend Discount Users: Identified customers who used discounts but still spent above the average purchase amount.

Top-Rated Products: Retrieved the top five products with the highest average review ratings.

Shipping Impact on Spending: Compared average purchase amounts between Standard and Express shipping types.

Subscription Value Analysis: Measured whether subscribed customers spend more by comparing average spend, customer count, and revenue.

Discount Effectiveness: Ranked products with the highest percentage of discounted purchases to understand promotion impact.

Customer Segmentation: Categorized customers into New, Returning, and Loyal based on historical purchases and counted segment sizes.

Top Products by Category: Identified the top three most purchased items within each category.

Subscription Likelihood of Repeat Buyers: Checked whether frequent buyers (5+ previous purchases) are more likely to be subscribers.

Age-Group Revenue Contribution: Calculated revenue contribution across age-group segments to reveal top-performing customer cohorts.

These SQL-driven insights enabled deeper understanding of customer patterns, purchase behavior, and product dynamics—supporting data-backed business decision-making.

**📊 Dashboard Development**

An interactive Customer Behavior Dashboard was built to visualize key insights derived from the cleaned dataset. The dashboard includes dynamic filters for subscription status, gender, category, and shipping mode, enabling user-driven exploration of customer trends.

*Key components featured in the dashboard*

KPIs: Total customers, average purchase amount, and average review rating.

Customer Segmentation: Subscription-based distribution and age-group performance.

Revenue Insights: Revenue by category and by age group.

Sales Insights: Sales volume analyzed across product categories and customer segments.

This dashboard provides a comprehensive, business-focused view of customer behavior and helps identify high-value segments, top-performing categories, and purchase patterns for data-driven decision-making.

**🔍 Key Insights**

1. Middle-aged customers (46-60) contribute the highest revenue and show the strongest purchase activity among all age groups.
2. Female customers contribute almost exactly in proportion to their presence in the customer base, with a very slight overperformance (+0.26%).
Male customers contribute slightly less than expected (–0.26%) based on how many of them there are.
3. Clothing categories contribute the highest revenue and highest sales among all other categories.
4. Subscribed customers do not spend more on average — their average purchase amount (59.49) is slightly lower than non-subscribers (59.87).
However, subscribers still contribute a significant portion of total revenue (≈37%), despite being only about 27% of the customer base.
Non-subscribers drive the majority of revenue (≈73%) simply because they make up a much larger share of total customers.
5. Higher-frequency buyers spend marginally more, while periodic shoppers contribute the bulk of customer volume.

📊 Dashboard Preview

The image below shows a snapshot of the Customer Behavior Analytics Dashboard built in Power BI, highlighting key KPIs, customer segmentation, and revenue insights to support data-driven analysis:

![Dashboard Preview].(https://github.com/Anishsarkar10/Customer_Behavior_Analysis/blob/main/Snapshot%20of%20the%20Dashboard.png)

