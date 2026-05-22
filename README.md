# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project analyzing **3,900 customer transactions** to uncover spending patterns, product preferences, customer segments, and subscription behavior — built with Python, PostgreSQL, and Power BI.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Project Pipeline](#project-pipeline)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [SQL Business Analysis](#sql-business-analysis)
- [Power BI Dashboard](#power-bi-dashboard)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Project Structure](#project-structure)

---

## 📋 Project Overview

This project performs a comprehensive analysis of retail customer shopping data to answer real business questions:

- Who are our most valuable customers?
- Which products and categories drive the most revenue?
- How does discount behavior affect spending?
- What separates subscribers from non-subscribers?
- Which age groups and demographics contribute the most revenue?

---

## 📊 Dataset

| Property | Details |
|---|---|
| Total Records | 3,900 purchases |
| Features | 18 columns |
| Missing Data | 37 values in `review_rating` (imputed using category median) |

**Feature Groups:**

- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Behavior** — Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

---

## 🛠 Tech Stack

| Layer | Tool |
|---|---|
| Data wrangling | Python (pandas) |
| Database | PostgreSQL |
| Visualization | Power BI |
| Analysis | SQL (PostgreSQL queries) |

---

## 🔄 Project Pipeline

```
Raw CSV Data
     │
     ▼
Python (EDA & Cleaning)
     │  • Handle missing values
     │  • Feature engineering
     │  • Column standardization
     ▼
PostgreSQL (SQL Analysis)
     │  • 10 business queries
     │  • Segmentation & ranking
     ▼
Power BI Dashboard
     │  • Interactive visuals
     │  • KPI metrics
     ▼
Business Recommendations
```

---

## 🔍 Exploratory Data Analysis

All data preparation was done in Python using `pandas`.

**Steps performed:**

1. **Data Loading** — Imported dataset using `pandas`
2. **Initial Exploration** — Used `df.info()` and `.describe()` for structure and summary stats
3. **Missing Data Handling** — Imputed 37 missing `review_rating` values using the median rating per product category
4. **Column Standardization** — Renamed all columns to `snake_case`
5. **Feature Engineering**
   - Created `age_group` by binning customer ages (Young Adult, Adult, Middle-aged, Senior)
   - Created `purchase_frequency_days` from frequency-of-purchase data
6. **Data Consistency Check** — Found `discount_applied` and `promo_code_used` to be redundant; dropped `promo_code_used`
7. **Database Integration** — Loaded cleaned DataFrame into PostgreSQL for SQL analysis

---

## 🗄️ SQL Business Analysis

Ten business questions were answered using PostgreSQL:

| # | Analysis | Key Result |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 · Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers spent above average even with discounts |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78) |
| 4 | Shipping Type Comparison | Express avg: $60.48 · Standard avg: $58.46 |
| 5 | Subscribers vs. Non-Subscribers | Avg spend nearly equal (~$59.49 vs $59.87); subscribers far fewer (1,053 vs 2,847) |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) |
| 7 | Customer Segmentation | Loyal: 3,116 · Returning: 701 · New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | Of customers with >5 purchases: 2,518 non-subscribers vs. 958 subscribers |
| 10 | Revenue by Age Group | Young Adult: $62,143 · Middle-aged: $59,197 · Adult: $55,978 · Senior: $55,763 |

---

## 📈 Power BI Dashboard

An interactive dashboard was built in Power BI featuring:

- **KPI Cards** — 3.9K customers · $59.76 avg purchase · 3.75 avg rating
- **Subscription Breakdown** — 27% subscribers vs. 73% non-subscribers
- **Revenue by Category** — Clothing leads, followed by Accessories, Footwear, Outerwear
- **Revenue & Sales by Age Group** — Young Adults contribute the highest revenue
- **Slicers** — Filter by Subscription Status, Gender, Category, Shipping Type

---

## 💡 Key Findings

- **Male customers** account for ~2× the revenue of female customers
- **Loyalty is strong** — 80% of the customer base (3,116) falls in the "Loyal" segment
- **Subscriptions are underutilized** — Despite nearly identical avg spend, only 27% of customers subscribe
- **Discounts are widespread** — Top products like Hat and Sneakers see ~50% discounted purchase rates, potentially compressing margins
- **Express shipping users** spend slightly more on average — a signal of higher purchase intent
- **Young Adults** are the most valuable age group by total revenue

---

## ✅ Business Recommendations

| Recommendation | Rationale |
|---|---|
| **Boost subscriptions** | Subscribers have similar spend to non-subscribers — exclusive benefits could convert the 73% non-subscriber base |
| **Launch loyalty programs** | 3,116 loyal customers deserve recognition; rewards could increase purchase frequency further |
| **Review discount policy** | Hat and Sneakers see ~50% discount rates — assess margin impact vs. incremental sales |
| **Highlight top-rated products** | Gloves, Sandals, and Boots have the highest ratings — feature in marketing campaigns |
| **Target young adults & express-shipping users** | These segments show the highest revenue and purchase intent respectively |

---

## 📁 Project Structure

```
customer-shopping-analysis/
├── data/
│   ├── raw/                    # Original dataset
│   └── cleaned/                # Cleaned CSV after Python processing
├── notebooks/
│   └── eda.ipynb               # Exploratory Data Analysis notebook
├── sql/
│   ├── 01_revenue_by_gender.sql
│   ├── 02_high_spending_discount_users.sql
│   ├── 03_top_products_by_rating.sql
│   ├── 04_shipping_comparison.sql
│   ├── 05_subscribers_vs_non.sql
│   ├── 06_discount_dependent_products.sql
│   ├── 07_customer_segmentation.sql
│   ├── 08_top_products_per_category.sql
│   ├── 09_repeat_buyers_subscriptions.sql
│   └── 10_revenue_by_age_group.sql
├── dashboard/
│   └── customer_behavior.pbix  # Power BI dashboard file
├── reports/
│   └── Customer_Shopping_Behavior_Analysis.pdf
└── README.md
```
## Author
Kavya Kumar
