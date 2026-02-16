# Real Estate Sales Dashboard

## Table of Content

1. [Introduction](#Introduction)
2. [Objectives](#Objectives)
3. [Key Metrics](#KeyMetrics)
4. [Steps Taken](#StepsTaken)
5. [Dashbord](#Dashboard)
6. [Insights and Conclusions](#InsightsandConclusions)
   
--- 

## Introduction

Real estate revenue can look strong at a glance, but without structured analysis, it is difficult to understand what truly drives growth, profitability, and regional performance.

This dashboard transforms raw sales transactions, inventory data, and pricing records into a clear story of where revenue is generated, which products drive volume versus profit, and how individual salespeople and regions influence overall performance.

With $564M in total sales and $56M in profit, the key question becomes:
Is growth driven by the right products, markets, and people or is revenue masking deeper opportunity gaps?

The dashboard provides visibility into product performance, salesperson contribution, and country-level distribution, enabling leadership to shift from reactive reporting to strategic planning.

---

## Objectives

The goal of this project is to move beyond surface-level revenue reporting and answer critical business questions:

**Evaluate Sales Performance**

- How much revenue and profit is the business truly generating?
- Which product categories contribute the most to revenue versus profitability?

**Analyze Product and Inventory Dynamics**

- Are high-volume products also high-margin products?
- Where is inventory demand strongest?

**Understand Regional and Sales Team Performance**

- Which countries drive the highest revenue?
- Which salespeople generate the most value versus volume?

**Enable Strategic Decision-Making**

- Identify top-performing markets and products
- Detect profitability gaps hidden behind high sales volume
- Support performance management across the sales team

---

## Key Metrics

- Total Sales: $564M
- Total Profit: $56M
- Quantity Sold: 3K

**Performance Leaders:**

- Top Revenue Product: Villa ($140M)
- Top Volume Product: Villa (574 units, 19.15%)
- Top Profit Product: Land ($14.29M)
- Top Salesperson by Revenue: John Doe ($124.98M, 631 units)
- Top Salesperson by Quantity: Chris Johnson (656 units, $119.87M)
- Top Revenue Country: UK ($94.92M)

These figures reveal that revenue concentration exists across specific products, individuals, and regions.

---

## Steps Taken

### 1. Data Loading and Preparation

- Imported Customer Transactions data
- Imported Product Inventory and Pricing data
- Cleaned inconsistencies and removed duplicates
- Standardized naming conventions
- Merged datasets using Product Type as the relational key

This ensured a unified model connecting transactions with cost and pricing data.

### 2. Data Transformation

* Renamed columns for clarity.
* Merged tables on **Product Type** to calculate metrics.
* Calculated **Total Profit** using the formula:
```Dax
SUMX(
    'Customer Transactions',
    RELATED('Product Inventory & Pricing'[Invoice Amount])
    - RELATED('Product Inventory & Pricing'[Cost])
)
```
This allowed profitability to be analyzed at transaction level rather than relying on aggregated assumptions.

### 3. DAX Calculations

 Created DAX measures:

 * **Total Sales:**
    ```Dax
    SUM('Customer Transactions'[Amount Paid]).
    ```
  * **Total Profit:**
   ``` Dax
   SUMX(
    'Customer Transactions',
    RELATED('Product Inventory & Pricing'[Invoice Amount]) - RELATED('Product Inventory & Pricing'[Cost])).
   ```
  * **Quantity Sold:**
  ``` Dax
  SUM('Customer Transactions'[Quantity Purchased]).
  ```
  These measures power all KPI and visual insights within the dashboard.

---

### 4. Visualization

The dashboard includes:

- KPI cards for Total Sales, Total Profit, and Quantity Sold
- Bar chart for Sales by Product Type
- Doughnut chart for Quantity Distribution
- Geographic map for Sales by Country
- Matrix table for Salesperson performance
- Interactive slicers for Country and Salesperson

Conditional formatting highlights top contributors to immediately surface performance leaders.

---

### Dashboard

<img width="716" alt="Image" src="https://github.com/user-attachments/assets/4f022f96-6e78-40fb-b465-b1fe6f3909d0" />

---

## Insights and Conclusions

The data reveals a clear revenue concentration pattern.

Villa dominates both revenue and sales volume, contributing $140M and nearly one fifth of total units sold. However, the most profitable product is Land, generating $14.29M in profit, showing that revenue and profitability do not always align.

John Doe leads in total revenue, while Chris Johnson leads in quantity sold, demonstrating that high volume does not automatically translate to highest revenue generation.

Regionally, the UK contributes the largest share of total sales, positioning it as a strategic priority market.

Overall, the dashboard reveals three critical insights:

- High revenue products are not always the most profitable.
- Individual performance varies between revenue efficiency and sales volume.
- Revenue concentration in specific countries presents both strength and risk exposure.

---

### Recommendation

- Focus on scaling high-margin products like Land while maintaining Villa’s strong revenue contribution.
- Develop targeted strategies to replicate UK performance in emerging regions.
- Align sales incentives not only to volume but also to profitability.
- Use performance benchmarking to elevate mid-performing sales representatives.

This dashboard converts transaction-level data into strategic intelligence, enabling leadership to optimize product mix, regional focus, and sales team effectiveness for sustained growth.

