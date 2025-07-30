# awesome-chocolate-dashboard

## Table of Contents

- [Case Study](#case-study)
- [Dataset Description](#dataset-description)
- [Data Analysis](#data-analysis)
- [Dashboard](#dashboard)

## Case Study
The objective is to analyze Awesome Chocolates sales performance by tracking total sales, boxes shipped, shipment counts, and sales distribution across geographies and salespersons. The dashboard aims to uncover performance trends and highlight opportunities for improved sales strategies.

## Dataset Description

Our dataset contains information regarding sales transactions, product details, salespeople, and geographical data. Below are the key tables and fields:

###  Geo

- **geoid** –Geography key
- **geo** – Geography name (e.g., USA, Canada, India) 
- **region** – Regional grouping (e.g., North America, APAC, EMEA)


---

###  Products

- **pid** – Product key 
- **product** –  Product name
- **category** – Product category 
-**size** –Pack/box size or weight (e.g., 24‑pc, 500g)
-**cost_per_box** – Standard cost per box (used for margin analysis if needed)

---

###  People

- **salesperson ** – Salesperson full name 
- **spid** –  Salesperson key 
- **team** –Team or business unit 
- **location ** – Base location of the salesperson 

---

###  sales

- **spid ** – Salesperson key
- **geoid ** – Geography key 
- **pid ** – Product key 
- **saledate ** –  Calendar date of the sale
- **amount  ** – Sales value in USD for the row’s grain
- **customers ** – Number of customers served/transactions counted in this row
- **boxes ** –  Boxes sold

---




## 📋 Table of Contents
- [DAX Measures for Power BI](#dax-measures-for-power-bi)
  - [• Total sales](#•-total-sales)
  - [• Total Boxes](#•-total-boxes)
  - [• Low Box Shipments](#•-low-box-shipments)
  - [• LBS%](#•-LBS%)

---

DAX Measures for Power BI
### 1.Total sales
            Total sals = SUM(sales[amount])
### 2.Total Boxes
            Total Boxes = SUM(sale[boxes])
### 3.Low Box Shipments
            Low Box Shipments = CALCULATE([Shipment Count],sales[Boxes] <50)
### 4.LBS%
            LBS % = DIVIDE([Low Box Shipments],[Shipment Count])
            
            
            






## Data Analysis
### 1.  Revenue Growth Year-over-Year
Insight:

Revenue has grown steadily from ₹90M in 2017 to ₹130M in 2020, with a peak of ₹145M in 2019.
Interpretation:
The business is scaling well, but the slight dip in 2020 might be due to market conditions (e.g., COVID-19 impact).
### 2. Top Performing Markets
Insight:

Delhi NCR is the most profitable market contributing ~52% of total revenue, followed by Mumbai and Ahmedabad.
Interpretation:
These Tier-1 markets are revenue drivers. Consider expansion or retention strategies here.
### 3.  Best-Selling Products
Insight:

Product types like Consumer Electronics and Grocery Essentials top the sales list both in quantity and revenue.
Interpretation:
These categories could benefit from targeted promotions and stocking priorities.
### 4. Monthly Seasonality in Sales
Insight:

Revenue tends to spike in July and December, indicating seasonal or festival-related boosts.
Interpretation:
These periods can be leveraged with promotions, combo offers, or bundled pricing.
### 5. 🧭 Zone-Wise Distribution
Insight:

Northern and Western zones contribute over 75% of revenue.
Interpretation:
The South and East zones are underperforming — explore local campaigns, logistics, or product adjustments.
## Dashboard

<img width="1913" height="963" alt="sales dashboard" src="https://github.com/user-attachments/assets/3ec86e45-1683-4905-95b6-1e4460f39fb0" />
