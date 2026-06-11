# Customer_Shopping_Behavior_Analysis
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)

---

## 📌 Project Overview

This end-to-end data analytics project explores **customer shopping behavior** using transactional data from **3,900 purchases** across multiple product categories. The project demonstrates a complete analytics pipeline — from raw data cleaning in Python, structured querying in PostgreSQL, to interactive business dashboards in Power BI — delivering actionable insights to drive real business decisions.

---

## 🎯 Business Objectives

- Understand **revenue distribution** across gender and age demographics
- Identify **high-value customer segments** for targeted marketing
- Evaluate the impact of **discount strategies** on purchasing behavior
- Compare **subscription vs. non-subscription** customer spending patterns
- Analyze **product performance** by rating, category, and sales volume
- Assess shipping preferences and their **influence on purchase amounts**

---

## 🧰 Tech Stack & Tools

| Layer | Tool / Technology | Purpose |
|---|---|---|
| Data Wrangling | Python (Pandas) | Cleaning, transformation, feature engineering |
| Database | PostgreSQL | Structured querying & business analysis |
| Visualization | Power BI | Interactive executive dashboard |
| Notebook | Jupyter Notebook | EDA documentation & reproducibility |
| Version Control | Git & GitHub | Code management & collaboration |

---

## 📂 Project Structure

```
customer-shopping-behavior-analysis/
│
├── 📓 Python_Customer_Shopping_Behavior_Analysis.ipynb   # EDA & data cleaning
├── 🗄️  SQL_Customer_Behavior.sql                          # 10 business SQL queries
├── 📊 Customer_Behavior_Dashboard.pbix                   # Power BI dashboard file
├── 📑 Customer-Shopping-Behavior-Analysis.pptx           # Project presentation deck
└── 📘 README.md                                          # Project documentation
```

---

## 🗂️ Dataset Summary

| Property | Detail |
|---|---|
| Source | Retail transactional dataset |
| Total Records | 3,900 purchases |
| Features | 18 columns |
| Missing Data | 37 values in `review_rating` (imputed using category median) |

**Key Columns:**

- **Demographics:** Age, Gender, Location
- **Purchase Details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Behavior Signals:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Subscription Status

---

## 🔬 Methodology

### Phase 1 — Data Cleaning & EDA (Python)

- Loaded dataset using `pandas`; performed structural checks via `df.info()` and `.describe()`
- Handled 37 missing values in `Review Rating` by imputing category-level **median ratings**
- Standardized all column names to **snake_case** for consistency
- **Feature Engineering:**
  - `age_group` — binned continuous age into labeled demographic segments
  - `purchase_frequency_days` — derived from purchase frequency data
- Identified and dropped `promo_code_used` as redundant with `discount_applied` (data consistency check)
- Loaded cleaned DataFrame into **PostgreSQL** for structured analysis

### Phase 2 — SQL Business Analysis (PostgreSQL)

Executed **10 targeted business queries** covering advanced SQL techniques:

| # | Business Question | SQL Concept Used |
|---|---|---|
| 1 | Revenue by Gender | `GROUP BY`, `SUM()` |
| 2 | High-spending discount users | Subquery with `AVG()`, `WHERE` filter |
| 3 | Top 5 products by review rating | `ROUND()`, `ORDER BY`, `LIMIT` |
| 4 | Standard vs. Express shipping spend | Conditional `WHERE IN`, aggregation |
| 5 | Subscriber vs. non-subscriber revenue | `COUNT()`, `AVG()`, `SUM()`, `GROUP BY` |
| 6 | Most discount-dependent products | `CASE WHEN`, percentage calculation |
| 7 | Customer segmentation (New/Returning/Loyal) | **CTE**, `CASE WHEN`, binning logic |
| 8 | Top 3 products per category | **Window Function** (`ROW_NUMBER() OVER PARTITION BY`) |
| 9 | Repeat buyers and subscription likelihood | Filtered aggregation |
| 10 | Revenue by age group | Feature-based aggregation |

### Phase 3 — Power BI Dashboard

Built an interactive **Customer Behavior Dashboard** with slicers for Subscription Status, Gender, Category, and Shipping Type — enabling dynamic filtering for business stakeholders.

---

## 📊 Key Findings & Insights

### 💰 Revenue & Demographics
- **Male customers** generated significantly more revenue (**$157,890**) compared to female customers (**$75,191**), suggesting either a larger male customer base or higher average spend
- **Young Adults** led revenue contribution at **$62,143**, followed by Middle-aged (**$59,197**), Adults (**$55,978**), and Seniors (**$55,763**)

### 🏷️ Discount Behavior
- **839 customers** used discounts yet still spent above the average purchase amount — a high-value segment that responds to promotions without sacrificing basket size
- Products with highest discount dependency: **Hat (50%)**, Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%)

### ⭐ Product Performance
- Top-rated products: **Gloves (3.86)**, Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)
- Top-selling items per category: Jewelry (Accessories), Blouse & Pants (Clothing), Sandals (Footwear), Jacket (Outerwear)

### 🚚 Shipping Preferences
- **Express shipping** customers had a slightly higher average spend (**$60.48**) vs. Standard (**$58.46**), indicating a willingness to pay more among express-preference buyers

### 📬 Subscription Analysis
- Only **27% of customers** are subscribers (1,053), yet their average spend ($59.49) nearly matches non-subscribers ($59.87)
- Non-subscribers dominate total revenue (**$170,436** vs. $62,645) — a clear opportunity to convert them through targeted subscription campaigns

### 👥 Customer Segmentation
- **Loyal customers dominate** at 3,116 (80%), with only 83 New customers and 701 Returning — indicating strong retention but a weak new-customer acquisition funnel
- Among repeat buyers (>5 purchases), **2,518 are non-subscribers** vs. 958 subscribers — a missed upsell opportunity

---

## 💡 Business Recommendations

1. **Boost Subscription Conversion** — Target the 2,518 loyal non-subscribers with personalized offers; even a 10% conversion would significantly grow recurring revenue
2. **Leverage High-Value Discount Users** — The 839 customers who spend above average even with discounts should receive loyalty rewards, not deeper discounts
3. **Re-examine Discount Policy** — Products like Hat and Sneakers are nearly 50% discount-dependent; review whether margins are being unnecessarily eroded
4. **Invest in New Customer Acquisition** — Only 83 new customers in the dataset signals a top-of-funnel issue; allocate budget to acquisition campaigns targeting Young Adults
5. **Product Positioning** — Amplify top-rated products (Gloves, Sandals, Boots) in marketing campaigns to drive conversion using social proof
6. **Express Shipping Upsell** — Since express users spend slightly more, offer express shipping upgrades at checkout to increase average order value

---

## 🧠 What I Learned & Challenges Faced

- Connecting pandas to PostgreSQL via SQLAlchemy taught me what a real data pipeline feels like beyond just writing code in isolation.

- A z-order layering bug in Power BI took me time to debug and reminded me that dashboard design has its own technical depth separate from the data work.

- Imputing 37 missing review ratings using category-level medians instead of overall median was a small but important reminder — imputation should reflect
  business logic, not just math.

- Deriving age_group and purchase_frequency_days made me realize raw data rarely has exactly what your business question needs. Feature engineering is where
  analysis actually begins.

  ---

## 📈 Dashboard Preview

> The Power BI dashboard provides interactive filtering across Subscription Status, Gender, Product Category, and Shipping Type.

**Key KPIs displayed:**
- 📦 **3.9K** Total Customers
- 💵 **$59.76** Average Purchase Amount
- ⭐ **3.75** Average Review Rating

**Visuals included:**
- Donut chart: % Customers by Subscription Status
- Bar charts: Revenue & Sales by Category and Age Group
- Dynamic slicers for business-level drill-downs

---

## 🚀 How to Run This Project

### Prerequisites
```bash
pip install pandas psycopg2 sqlalchemy jupyter
```

### Steps
```bash
# 1. Clone the repository
git clone https://github.com/aaravpatial-03/customer-shopping-behavior-analysis.git

# 2. Open the Jupyter Notebook for EDA
jupyter notebook Python_Customer_Shopping_Behavior_Analysis.ipynb

# 3. Set up PostgreSQL and run the SQL queries
# Update your DB connection string in the notebook before pushing to PostgreSQL
psql -U your_username -d your_database -f SQL_Customer_Behavior.sql

# 4. Open the Power BI dashboard
# Open Customer_Behavior_Dashboard.pbix in Power BI Desktop
```

---

## 🧠 Skills Demonstrated

> ✅ **For Hiring Managers & Recruiters — This project validates the following competencies:**

| Skill Area | Evidence |
|---|---|
| Data Cleaning & EDA | Missing value imputation, column standardization, feature engineering |
| Feature Engineering | Age group binning, Purchase frequency calculation |
| Advanced SQL | CTEs, Window Functions, Subqueries, Conditional Aggregation |
| Business Thinking | 10 business-driven queries tied to real KPIs |
| Data Visualization | Executive-level Power BI dashboard with slicers and KPI cards |
| Insight Communication | Findings translated into concrete, prioritized business recommendations |
| End-to-End Pipeline | Python → PostgreSQL → Power BI, fully documented |

---

## 👤 Author

  Aarav Patial
📧 aaravpatial108@gmail.com

🔗 LinkedIn - https://www.linkedin.com/in/contactaaravpatial

💻 GitHub - https://github.com/aaravpatial-03

---

## 📃 License

This project is licensed under the [MIT License](LICENSE) — feel free to use and adapt with attribution.
