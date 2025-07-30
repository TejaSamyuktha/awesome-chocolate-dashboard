# awesome-chocolate-dashboard

## Table of Contents

- [Case Study](#case-study)
- [Dataset Description](#dataset-description)
- [Data Analysis](#data-analysis)
- [Dashboard](#dashboard)
- [Dashboard-2](#dashboard)

## Case Study
The objective is to analyze Awesome Chocolates sales performance by tracking total sales, boxes shipped, shipment counts, and sales distribution across geographies and salespersons. The dashboard aims to uncover performance trends and highlight opportunities for improved sales strategies.

## Dataset Description

Our dataset contains information regarding sales transactions, product details, salespeople, and geographical data. Below are the key tables and fields:

### **Geo**
- **geoid** – Geography key  
- **geo** – Geography name (e.g., USA, Canada, India)  
- **region** – Regional grouping (e.g., North America, APAC, EMEA)

---

### **Products**
- **pid** – Product key  
- **product** – Product name  
- **category** – Product category  
- **size** – Pack/box size or weight (e.g., 24‑pc, 500g)  
- **cost_per_box** – Standard cost per box (used for margin analysis if needed)

---

### **People**
- **salesperson** – Salesperson full name  
- **spid** – Salesperson key  
- **team** – Team or business unit  
- **location** – Base location of the salesperson

---

### **Sales** *(fact table — row grain: `saledate × spid × geoid × pid`)*
- **spid** – Salesperson key  
- **geoid** – Geography key  
- **pid** – Product key  
- **saledate** – Calendar date of the sale  
- **amount** – Sales value in USD for the row’s grain  
- **customers** – Number of customers/transactions represented by the row  
- **boxes** – Boxes sold
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
### 1.   Sales Trend (Jan‑2021 → Mar‑2022)
Insight:

The line shows steady baseline sales through 2021 with visible micro‑peaks in mid‑year (Jun–Aug) and a sharp spike around Jan‑2022 approaching the $5M tick.
Early 2022 pullback after the spike (Feb–Mar 2022), but levels remain within the typical 2021 band.
### 2.  Sales by Geography
Insight:

New Zealand appears top, followed closely by Canada and India.
Australia sits mid‑pack; UK and USA are lower in this slice.

### 3.  Salesperson Performance (Table)
Insight:

(Top names in your grid include: Wilone O’Kielt, Van Tuxwell, Roddy Speechley, Madeleine Upcott, Karlen McCaffrey… with ~$1.80–$1.91M sales and ~114K–129K boxes each; LBS% mostly ~8–11%.)

Leaders are clustered around ~$1.8–$1.9M; no single outlier dominates → healthy distribution.

Wilone O’Kielt tops with ~$1.91M and ~126.8K boxes.

LBS% ranges indicate mix differences by rep (heavier vs lighter products).

## Dashboard


<img width="1920" height="1019" alt="chocolate screenshot 1" src="https://github.com/user-attachments/assets/d44df9cd-85fe-4ba4-8fa1-c42334486775" />

## Dashboard-2

<img width="1920" height="1019" alt="chocolate screenshot -2" src="https://github.com/user-attachments/assets/63659fd9-4776-44d8-9341-2f74008dc152" />

## Parameterization (Manage Parameters)

This report uses **Power Query Parameters** to keep the model flexible and reusable. Parameters let us focus the dashboard on a specific slice (e.g., **Product 6 / P06**) without rebuilding visuals.

### Parameters Created

- **`ProductId`** *(Text, Current Value: `P06`)*  
  Controls which product the **sales** fact table loads for **Dashboard 2 – Product View**.  
  Change it in **Home ▸ Transform data ▸ Manage Parameters** and then **Close & Apply** to refresh for a different product.

