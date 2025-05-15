# Real Estate Sales Dashboard

## Table of Content

1. [Introduction](#Introduction)
2. [Objectives](#Objectives)
3. [Key Metrics](#KeyMetrics)
4. [Steps Taken](#StepsTaken)
5. [Dashbord](#Dashboard)
6. [Insights and Conclusions](#InsightsandConclusions)
## Introduction

The Real Estate Sales Dashboard provides a comprehensive overview of a company's sales performance, product distribution and regional market insights. It is designed to facilitate data-driven decision-making by offering clear visualizations and key performance indicators (KPIs).

This dashboard highlights total sales, profit, and quantity sold, while also breaking down performance by product type, country, and salesperson. It enables stakeholders to monitor revenue trends, identify top-selling products and evaluate the effectiveness of the sales team. Additionally, the interactive slicers allow for focused analysis by country and salesperson, helping the management make more informed strategic decisions.

By leveraging this dashboard, the company can optimize inventory management, enhance regional targeting, and maximize overall profitability.

## Objectives

The primary objective of the Real Estate Sales Dashboard is to provide a holistic view of the company’s sales performance and profitability. By leveraging key metrics and interactive visualizations, the dashboard aims to:

1. **Evaluate Sales Performance:**

   * Track total sales, profit, and quantity sold to gauge the overall business performance.
   * Identify top-selling products and high-revenue regions to inform strategic decision-making.

2. **Analyze Product and Inventory Data:**

   * Assess sales by product type to understand customer preferences and optimize product offerings.
   * Monitor quantity sold versus available stock to ensure efficient inventory management.

3. **Understand Regional and Sales Team Dynamics:**

   * Visualize sales distribution by country to identify key markets and growth opportunities.
   * Analyze individual salesperson performance to recognize top performers and address gaps.

4. **Enhance Data-Driven Decision-Making:**

   * Use interactive slicers for country and salesperson to focus on specific data points.
   * Generate actionable insights to support sales strategy, product planning, and team performance evaluation.

## Key Metrics

* **Total Sales:** \$564M
* **Total Profit:** \$56M
* **Quantity Sold:** 3K
* **Top Product Type by Sales:** Villa (\$140M)
* **Top Product Type by Quantity Sold:** Villa (574, 19.15%)
* **Top Product Type by Profit:** Land (\$14,292,083)
* **Highest Salesperson by Revenue:** John Doe (\$124,979,481), Quantity Sold (631)
* **Highest Salesperson by Quantity Sold:** Chris Johnson (656), Revenue (\$119,868,403)
* **Country with Highest Sales:** UK (\$94,921,747)

## Steps Taken

### 1. Data Loading and Preparation

* Imported the Customer Data and Product Inventory and Pricing worksheets into Power BI.
* Ensured data consistency, performed cleaning, and removed duplicates.
* Combined data from the two sheets using Product Type as the key.

### 2. Data Transformation

* Renamed columns for clarity.
* Merged tables on **Product Type** to calculate metrics.
* Calculated **Total Profit** using the formula:  
SUMX(
    'Customer Transactions',
    RELATED('Product Inventory & Pricing'[Invoice Amount])
    - RELATED('Product Inventory & Pricing'[Cost])
)

### 3. DAX Calculations

* Created DAX measures:

  * **Total Sales:**  SUM('Customer Transactions'[Amount Paid]).
  * **Total Profit:** SUMX(
    'Customer Transactions',
    RELATED('Product Inventory & Pricing'[Invoice Amount]) - RELATED('Product Inventory & Pricing'[Cost])).
  * **Quantity Sold:** SUM('Customer Transactions'[Quantity Purchased]).
  

### 4. Visualization

* **KPIs:** Total Sales, Total Profit, Quantity Sold.
* **Bar Chart:** Total Sales by Product Type.
* **Doughnut Chart:** Quantity Sold by Product Type.
* **Map:** Sales by Country.
* **Table Matrix:** Salesperson, Sales by Salesperson, Quantity Sold.
* **Slicers:** Country and Salesperson for interactive filtering.

### 5. Formatting and Interaction

* Applied conditional formatting to highlight the highest values (i.e. highest sales in a distinct color).
* Ensured slicers function seamlessly across visuals.
* Customized the bar chart to display the highest bars in a specific color.

### Dashboard

<img width="716" alt="Image" src="https://github.com/user-attachments/assets/4f022f96-6e78-40fb-b465-b1fe6f3909d0" />

## Insights and Conclusions

* **High Revenue Product:** Villa, contributing \$140M.
* **Top Profit Product:** Land, with \$14.29M profit.
* **Top Salesperson:** John Doe with \$124.98M in sales.
* **Top Sales Country:** UK with \$94.92M.

### Recommendation

Focus on high-revenue products (like Villas) and profitable products (like Land) while maintaining sales performance in high-yield regions such as the UK.

