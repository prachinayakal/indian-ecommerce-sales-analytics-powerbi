# Indian E-Commerce Sales Analytics Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Analytics-yellow)
![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Transformation-blue)
![DAX](https://img.shields.io/badge/DAX-Measures-orange)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Business%20Insights-green)

## 📊 Project Overview

**Indian E-Commerce Sales Analytics** is an interactive Power BI dashboard developed to analyze e-commerce sales, customer behavior, product performance, and order operations.

The project analyzes **250,000 e-commerce orders** using three datasets:

* Sales
* Products
* Customers

A three-page Power BI report was developed to provide executive-level performance analysis, product and customer insights, and operational analysis.

> **Project Type:** Power BI Analytics Case Study / Assessment Project
> **Tools:** Power BI, Power Query, DAX
> **Analysis Period:** June 2024 – June 2026

---

## 🎯 Project Objective

The objective of this project was to transform raw e-commerce data into an interactive business intelligence dashboard that demonstrates:

* Data cleaning and transformation
* Data modeling
* DAX calculations
* KPI development
* Interactive data visualization
* Business performance analysis
* Data-driven insights and recommendations

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose                                  |
| ----------------- | ---------------------------------------- |
| **Power BI**      | Dashboard development and visualization  |
| **Power Query**   | Data cleaning and transformation         |
| **DAX**           | KPI and analytical measure creation      |
| **CSV**           | Source data                              |
| **Data Modeling** | Relationship and analytical model design |

---

## 📁 Dataset

The project uses three source datasets:

### Sales

Contains transaction-level order information used for sales, order, quantity, shipping, payment, rating, and order-status analysis.

### Products

Contains product-related information used for product, category, and brand analysis.

### Customers

Contains customer information used for customer segmentation and demographic analysis.

The complete analysis covers **250,000 orders**.

---

## 🧹 Data Cleaning & Transformation

The datasets were reviewed and transformed using Power Query before building the report.

Key activities included:

* Checked datasets for duplicate records
* Validated data types for IDs, dates, quantities, prices, shipping costs, ratings, and categorical fields
* Reviewed missing values in optional fields
* Retained blank ratings instead of replacing them with assumed values
* Validated key fields used for relationships and reporting
* Created a dedicated Calendar table
* Created a Year-Month sorting field for chronological analysis
* Prepared the datasets for Power BI modeling

### Missing Data Handling

The Sales dataset contained missing values in fields such as:

* Coupon Code
* Rating
* Review Text

These fields were treated according to their analytical relevance rather than filling missing values with potentially misleading assumptions.

---

## 🏗️ Data Model

A **star-schema-style data model** was created with the Sales table acting as the central fact table.

### Relationships

```text
                    ┌───────────────┐
                    │   Customers   │
                    └───────┬───────┘
                            │
                            │ 1 : *
                            ▼
┌─────────────┐      ┌───────────────┐      ┌─────────────┐
│   Products  │─────▶│     Sales     │◀─────│  Calendar   │
└─────────────┘ 1 : *└───────────────┘ * : 1└─────────────┘
```

### Main Relationships

* Customers → Sales using `Customer_ID`
* Products → Sales using `Product_ID`
* Calendar → Sales using `Order_Date`

---

## 📐 DAX Measures

The dashboard uses DAX measures to calculate important business KPIs.

Some of the main measures include:

* Total Sales
* Total Orders
* Total Quantity
* Total Profit
* Profit Margin %
* Previous Year Sales
* YoY Sales Growth %
* Delivered Orders
* Returned Orders
* Cancelled Orders
* Delivery Rate %
* Total Customers
* Average Order Value
* Average Rating

Example:

```DAX
Total Sales =
SUM(Sales[Total_Amount])
```

```DAX
Total Orders =
DISTINCTCOUNT(Sales[Order_ID])
```

```DAX
Total Quantity =
SUM(Sales[Quantity])
```

```DAX
Total Profit =
SUMX(
    Sales,
    Sales[Total_Amount] - Sales[Shipping_Cost]
)
```

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```

```DAX
YoY Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
```

---

# 📊 Dashboard Pages

## 1. Executive Performance Overview

The first page provides a high-level overview of overall business performance.

### KPIs

* Total Sales
* Total Orders
* Total Profit
* Total Quantity
* Profit Margin %
* YoY Sales Growth %

### Visualizations

* Monthly Sales Trend
* Sales by Category
* Top States by Sales
* Order Status
* Date, State, and Category filters

### Key Metrics

* **Total Sales:** Approximately ₹5.93 billion
* **Total Orders:** 250K
* **Total Quantity:** 312K
* **YoY Sales Growth:** 92.45%

---

## 2. Product & Customer Analysis

The second page focuses on product performance and customer behavior.

### KPIs

* Total Sales
* Total Customers
* Average Order Value
* Average Rating

### Analysis

* Top 5 Products by Sales
* Top 5 Brands by Sales
* Sales by Customer Tier
* Sales by Age Group
* Sales by Payment Mode

### Key Findings

* Electronics is the leading sales category.
* Platinum customers contribute the largest share of sales.
* The 26–35 age group represents the strongest customer segment by sales.
* UPI is the leading payment mode by sales value.

---

## 3. Order & Operational Analysis

The third page focuses on order fulfilment and operational performance.

### KPIs

* Total Orders
* Delivered Orders
* Returned Orders
* Cancelled Orders
* Delivery Rate %

### Analysis

* Monthly Order Status Trend
* Shipping Cost by State
* Orders by Payment Mode
* Customer Rating Distribution

### Key Metric

The overall delivery rate is approximately **80.06%**, based on 200,139 delivered orders out of 250,000 orders.

---

# 🔍 Key Business Insights

The analysis produced several notable findings:

### 1. Category Performance

Electronics is the dominant category, generating approximately **₹4.31 billion**, representing about **72.6% of total sales**.

### 2. Customer Segmentation

Platinum customers generate approximately **₹5.34 billion** in sales, significantly higher than Gold and Silver customer tiers.

### 3. Age Segment

Customers in the **26–35 age group** represent the strongest age segment, generating approximately **₹2.56 billion** in sales.

### 4. Payment Behaviour

UPI contributes approximately **53.6% of sales value**, followed by Cash on Delivery at approximately **31.1%**.

### 5. Order Fulfilment

Approximately **200,139 orders were delivered**, resulting in an overall delivery rate of approximately **80.06%**.

### 6. Logistics

Shipping costs are highest in states including **Uttar Pradesh, Haryana, and Rajasthan**, highlighting areas where logistics costs can be investigated further.

### 7. Customer Ratings

Five-star ratings represent the largest observed rating group, followed by four-star ratings.

---

# 💡 Business Recommendations

Based on the analysis:

* Protect inventory availability and promotional focus for the Electronics category.
* Explore campaigns to increase sales from lower-contributing categories.
* Prioritize retention strategies and personalized offers for Platinum customers and the 26–35 age segment.
* Optimize the UPI checkout experience because it is the leading payment method by sales value.
* Investigate cancellation and return drivers to improve fulfilment performance.
* Review carrier, warehouse, and routing costs in states with higher shipping costs.
* Analyze lower-rated transactions to identify potential product or service-quality issues.

---

# ⚠️ Analytical Assumption

The source dataset does not contain a true **Cost of Goods Sold (COGS)** or product acquisition-cost field.

Therefore, the project's `Total Profit` measure is calculated as:

```text
Total Profit = Total Amount - Shipping Cost
```

This is treated as a **contribution-style proxy**, not accounting gross profit or net profit.

Consequently, the resulting profit margin should **not be interpreted as an actual accounting profit margin**.

---

# 📷 Dashboard Preview

### Executive Performance Overview

Add your first dashboard screenshot here:

```text
![Executive Performance Overview](Screenshots/Executive_Overview.png)
```

### Product & Customer Analysis

```text
![Product & Customer Analysis](Screenshots/Product_Customer_Analysis.png)
```

### Order & Operational Analysis

```text
![Order & Operational Analysis](Screenshots/Order_Operational_Analysis.png)
```

---

# 📂 Project Structure

```text
Indian-Ecommerce-Sales-Analytics/
│
├── README.md
│
├── PowerBI/
│   └── Indian_Ecommerce_Sales_Analytics.pbit
│
├── Documentation/
│   └── Prachi_Nayakal_PowerBI_Assessment_Documentation.pdf
│
├── Screenshots/
│   ├── Executive_Overview.png
│   ├── Product_Customer_Analysis.png
│   └── Order_Operational_Analysis.png
│
└── Data/
    └── README.md
```

> Raw datasets should only be included if their redistribution/public GitHub upload is permitted.

---

# 🚀 Skills Demonstrated

* Power BI
* Power Query
* DAX
* Data Cleaning
* Data Transformation
* Data Modeling
* Star Schema
* KPI Development
* Data Visualization
* Business Intelligence
* Customer Analytics
* Sales Analytics
* Operational Analytics
* Business Insights

---

# 👩‍💻 Author

**Prachi Nayakal**

Data Analyst | Power BI | SQL | Tableau | Excel | Snowflake

This project was developed as a Power BI analytics assessment/case study demonstrating data preparation, modeling, DAX, visualization, and business analysis skills.
