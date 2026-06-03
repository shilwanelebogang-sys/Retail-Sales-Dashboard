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

### ✅ Key Transformations

- Customer deduplication using `COUNT(DISTINCT)`  
- Time breakdown (year, month, day)  
- Revenue aggregation  
- Units sold aggregation  

---

### 🔹 Dashboard Development (Databricks)

The transformed dataset was visualized directly in **Databricks dashboards**, enabling:

- KPI summary cards  
- Product category comparisons  
- Time-series visualizations  
- Interactive filters (date, category, customer metrics)  

---

## 📖 Case Study: From Data to Decisions

### 🔎 Scenario

A retail business lacked visibility into:

- Revenue fluctuations  
- Category performance  
- Customer growth trends  

Although the data existed, it was stored at a **transaction level**, making it difficult to extract meaningful insights.

---

### 🔄 Data Transformation

The dataset was structured into meaningful analytical dimensions:

- 📅 **Time Intelligence** → Daily & monthly trends  
- 👥 **Customer Metrics** → Unique customers  
- 💰 **Performance Metrics** → Revenue & units sold  
- 🛍️ **Segmentation** → Product categories  

---

## 📊 Dashboard Overview

### KPI Highlights

- **Total Revenue:** 456K  
- **Total Units Sold:** 2.51K  

---

## 🔍 Key Insights

### 💰 Revenue Performance

- Total revenue indicates strong overall performance  
- Daily fluctuations suggest inconsistent demand patterns  

---

### 🛍️ Product Category Distribution

Revenue is evenly split (~31–34%) across:

- Beauty  
- Clothing  
- Electronics  

**Insight:**
- Business is well-diversified  
- Opportunity exists to grow a dominant category  

---

### 📈 Customer Trends

- Customer counts fluctuate over time  

**Insight:**
- Indicates potential retention challenges  
- Opportunity for targeted marketing or loyalty strategies  

---

### 📉 Daily Revenue Trends

- Revenue shows spikes and dips across days  

**Insight:**
- Likely influenced by:
  - Promotions  
  - Customer purchasing behavior  

- Opportunity to optimize campaign timing  

---

### 📊 Category Performance Trends

- Electronics shows variability  
- Beauty and Clothing remain relatively stable  

**Insight:**
- Electronics may be seasonal or promotion-driven  
- Stable categories provide a consistent revenue base  

---

## 🧠 Business Value

This dashboard enables:

- Data-driven decision-making  
- Identification of growth opportunities  
- Improved customer insights  
- Better planning of sales and marketing strategies  
