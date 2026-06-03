# 📊 Retail Sales Dashboard (Databricks)



---

## 🧩 Business Problem

Retail businesses generate large volumes of transactional data daily, but without proper transformation and visualization, this data remains underutilized.

The challenge:

> **How can raw retail sales data be transformed into actionable insights that enable decision-makers to monitor performance, understand customer behavior, and identify growth opportunities?**

Stakeholders needed:
- A clear view of **overall sales performance**
- Insights into **top-performing product categories**
- Visibility into **customer purchasing patterns**
- The ability to analyze **daily and monthly trends**

---

## 🎯 Project Objective

To build a scalable analytics solution using **Databricks** that:

- Transforms raw transactional data into a clean dataset  
- Enables time-based analysis  
- Tracks customer activity  
- Supports interactive dashboarding  

---

## 🛠️ Solution Approach

### 🔹 Data Processing (Databricks SQL)

```sql
SELECT 
    COUNT(DISTINCT `Customer ID`) AS unique_customers,
    Date,
    YEAR(Date) AS trans_year,
    MONTH(Date) AS trans_month,
    MONTHNAME(Date) AS trans_month_name,
    DAY(Date) AS trans_day,
    DAYNAME(Date) AS trans_day_name,
    `Product Category`,
    SUM(`Total Amount`) AS revenue,
    SUM(Quantity) AS Number_of_units_sold
FROM retail.sales.dataset
GROUP BY ALL;
