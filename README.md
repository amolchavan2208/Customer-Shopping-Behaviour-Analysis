# Customer Shopping Behaviour Analysis

**Python | Pandas | SQL Server | SSMS | Power BI | Jupyter Notebook**

End-to-end customer shopping behaviour analysis of 3,900 retail purchase records, covering purchasing patterns, product preferences, discount usage, subscription behaviour and repeat purchases.

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Business Problem](#2-business-problem)
3. [Dataset](#3-dataset)
4. [Tools and Technologies](#4-tools-and-technologies)
5. [Python Data Cleaning and Preparation](#5-python-data-cleaning-and-preparation)
6. [SQL Business Analysis](#6-sql-business-analysis)
7. [Power BI Dashboard](#7-power-bi-dashboard)
8. [Business Recommendations](#8-business-recommendations)
9. [Repository Structure](#9-repository-structure)
10. [How to Run the Project](#10-how-to-run-the-project)
11. [Key Learnings and Future Improvements](#11-key-learnings-and-future-improvements)
12. [Conclusion](#12-conclusion)

## 1. Project Overview

This project analyses a retail dataset of 3,900 purchase records across multiple product categories to understand how customers shop, what they buy, how discounts relate to purchasing, and how subscription status and previous purchases describe different customer groups. The workflow combines data preparation, SQL-based business analysis and interactive visualisation to support data-driven retail decisions.

- Explore and prepare the dataset using Python and Pandas.
- Store and analyse the prepared data in SQL Server using SSMS.
- Answer ten business questions with SQL queries.
- Present shopping patterns through a Power BI dashboard and derive potential recommendations.

## 2. Business Problem

A retail company wants to improve sales, customer satisfaction and long-term loyalty by understanding its customers' shopping habits: popular products, discount usage and ratings, spending patterns across customer groups, and the link between purchase history and subscription status.

**Main question:**

> How can the company use customer shopping data to identify trends, improve engagement, and optimise marketing and product strategies?

## 3. Dataset

The dataset is structured tabular retail data with **3,900 rows and 18 columns**. The only missing values are 37 entries in `review_rating`.

| Field group | Columns and purpose |
| --- | --- |
| Customer | `customer_id`, `age`, `gender`, `location` – customer-level and demographic analysis |
| Product | `item_purchased`, `category`, `size`, `color`, `season` – product, preference and seasonal analysis |
| Transaction | `purchase_amount_usd`, `payment_method`, `shipping_type` – purchase amount and payment/shipping comparisons |
| Promotions | `discount_applied`, `promo_code_used` – discount and promo-code usage |
| Behaviour | `previous_purchases`, `frequency_of_purchases`, `subscription_status`, `review_rating` – segmentation, repeat purchases, ratings |

## 4. Tools and Technologies

| Tool | Purpose |
| --- | --- |
| Python, Pandas, Jupyter Notebook | Data exploration, cleaning, preparation and analysis |
| Microsoft SQL Server, SSMS | Database storage, query execution and result inspection |
| SQL | Answering the ten business questions |
| Power BI | Interactive dashboards and visualisation |
| GitHub | Version control and project documentation |

## 5. Python Data Cleaning and Preparation

- **Loading and exploration:** loaded the data into a DataFrame and reviewed structure with `df.info()` and `df.describe()`.
- **Missing values:** found 37 missing `review_rating` values and filled each with the median rating of its product category.
- **Column renaming:** converted column names to `snake_case` for readability in Python and SQL.
- **Feature engineering:** created `age_group` for comparative analysis and `purchase_frequency_days` from the purchase-frequency field (interpretation depends on the mapping used).
- **Discount review:** checked whether `discount_applied` and `promo_code_used` carry overlapping information.
- **Database integration:** connected Python to SQL Server and loaded the prepared dataset for SQL analysis.

## 6. SQL Business Analysis

Ten business questions were answered in SQL Server, covering spending, ratings, discount usage, subscriptions, segmentation and purchase history.

| No. | Business question | Objective |
| --- | --- | --- |
| 1 | Revenue by gender | Compare total recorded purchase amount for male and female customers |
| 2 | High-spending discount users | Find discounted purchases at or above the overall average amount |
| 3 | Top five products by rating | Identify the five products with the highest average review rating |
| 4 | Shipping type comparison | Compare average purchase amount for Standard vs Express shipping |
| 5 | Subscribers vs non-subscribers | Compare average and total spending by subscription status |
| 6 | High discount-usage products | Find the five products with the highest share of discounted purchases |
| 7 | Customer segmentation | Group customers as New, Returning or Loyal by previous purchases |
| 8 | Top three products per category | Find the three most frequently purchased products in each category |
| 9 | Repeat buyers and subscriptions | Examine subscription status where previous purchases exceed five |
| 10 | Revenue by age group | Calculate total purchase amount across age groups |

**SQL concepts used:** `SELECT`/`WHERE`, aggregates (`SUM`, `AVG`, `COUNT`), `GROUP BY`/`ORDER BY`, `CASE` logic, subqueries, and ranking and percentage calculations where applicable.

> Query results should be added to this README only after the executed outputs are verified.

## 7. Power BI Dashboard

The dashboard presents customer purchasing patterns interactively so they are easier to explore and compare. It covers:

- Purchases by product category and customer demographics
- Discount and promo-code usage, and payment-method preferences
- Customer review ratings and seasonal purchasing patterns
- Subscription status and previous-purchase behaviour

![Power BI Dashboard](images/powerbi_dashboard.png)

> Add your dashboard screenshot as `images/powerbi_dashboard.png` so the image displays here.

## 8. Business Recommendations

These are potential recommendations based on the types of analysis performed; their effectiveness must be evaluated against actual results and additional business data.

| Area | Recommendation |
| --- | --- |
| Subscriptions | Explore exclusive benefits, targeted offers and incentives to encourage subscriptions |
| Customer loyalty | Consider loyalty programmes, rewards and personalised offers for repeat buyers |
| Discount policy | Evaluate discount usage alongside purchase amount; add profit-margin data where available |
| Product positioning | Feature highly rated, frequently purchased products in campaigns, subject to verified results |
| Targeted marketing | Use demographics and purchasing patterns to tailor campaigns by customer group |
| Seasonal planning | Use seasonal patterns to guide promotions, inventory and product availability |

## 9. Repository Structure

Suggested structure (adjust to the files actually uploaded):

```text
Customer-Shopping-Behaviour-Analysis/
├── data/
├── notebooks/
├── python/
│   └── data_cleaning.py
├── sql/
├── powerbi/
├── images/
│   └── powerbi_dashboard.png
├── report/
└── README.md
```

| Folder / file | Purpose |
| --- | --- |
| `data/` | Dataset information and, if permitted, data files |
| `notebooks/` | Jupyter Notebook with the analysis |
| `python/` | Data preparation scripts (e.g. `data_cleaning.py`) |
| `sql/` | SQL queries for the ten business questions |
| `powerbi/` and `images/` | Power BI `.pbix` file and dashboard screenshots |
| `report/` and `README.md` | Project report and documentation |

## 10. How to Run the Project

**1. Clone the repository**

```bash
git clone <your-github-repository-url>
cd Customer-Shopping-Behaviour-Analysis
```

**2. Install the Python libraries**

```bash
pip install pandas sqlalchemy pyodbc jupyter
```

**3. Run the Python analysis**

Open the notebook with `jupyter notebook` and run the cells in order, or run the script:

```bash
python python/data_cleaning.py
```

**4. Configure SQL Server**

Connect in SSMS and set your own server, database and authentication. Use environment variables rather than hard-coded credentials.

**5. Analyse in SQL**

Load the prepared data, run the queries in SSMS and review the results before documenting findings.

**6. Open Power BI**

Open the `.pbix` file in Power BI Desktop and refresh the data source if required.

## 11. Key Learnings and Future Improvements

**Key learnings**

- Data exploration and cleaning in Python
- SQL filtering, aggregation, grouping and conditional logic
- Customer segmentation by previous purchases
- Power BI visualisation
- Translating analytical questions into potential retail recommendations

**Future improvements** (potential enhancements, not part of the current analysis)

- Time-based trend analysis with transaction dates
- Sales-channel comparison (online vs offline)
- Profitability analysis with cost and margin data
- Advanced segmentation such as clustering
- Automated reporting with scheduled refresh

## 12. Conclusion

This project combines Python, Pandas, SQL Server and Power BI to explore customer shopping behaviour. Python prepares the data, SQL enables structured analysis, and Power BI presents the results visually, demonstrating a practical end-to-end analytics workflow for identifying opportunities in retail decision-making.

---

**Technologies:** Python | Pandas | SQL Server | SSMS | Power BI | Jupyter Notebook
