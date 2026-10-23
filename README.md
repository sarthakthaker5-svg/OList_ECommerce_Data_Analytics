# 🛒 Olist E-Commerce Analytics Dashboard

<div align="center">

<img src="https://img.shields.io/badge/Power_BI-Data_Visualization-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" alt="Power BI">
<img src="https://img.shields.io/badge/Power_Query-Data_Transformation-2673B8?style=for-the-badge" alt="Power Query">
<img src="https://img.shields.io/badge/Project-E--Commerce_Analytics-17365D?style=for-the-badge" alt="E-Commerce Analytics">
<img src="https://img.shields.io/badge/Report-3_Pages-2E8B57?style=for-the-badge" alt="Three-page report">

<br>

<img src="https://readme-typing-svg.demolab.com?font=Poppins&weight=600&size=28&duration=3000&pause=1000&color=17365D&center=true&vCenter=true&width=750&lines=Olist+E-Commerce+Analytics;Sales+%26+Revenue+Analysis;Geographic+Distribution;Payments+%26+Customer+Reviews" alt="Olist E-Commerce Analytics">

</div>

*An interactive Power BI report for analyzing e-commerce sales, orders, customer and seller locations, payment methods, and customer reviews.*

---
## Project File
https://drive.google.com/file/d/1QN9q12iHAmGJOwV1sianfyWO-qpUx_Kg/view
---
## 📖 Project Overview

The **Olist E-Commerce Analytics Dashboard** is a Power BI data analytics project designed to explore Brazilian e-commerce order data. It transforms data from multiple CSV tables into an interactive report for analyzing sales performance, geographic distribution, payment methods, and customer satisfaction.

The report contains three analytical pages:

1. **Sales Overview** — Key performance indicators, product-category revenue, monthly order trends, customer-state distribution, and a matrix.
2. **Geographic Analysis** — Order distribution by customer state and revenue comparisons across seller cities and states.
3. **Payments & Reviews** — Payment-type analysis by year and customer review scores by product category.

---

# 🎥 Project Demo Video

<p align="center">

<a href="https://drive.google.com/file/d/1vIoU8WCL5t1Iv4XKsmdlf4kcYmqpj_1p/view" target="_blank">

<img src="https://img.shields.io/badge/▶️%20Watch%20Project%20Demo-4285F4?style=for-the-badge&logo=google-drive&logoColor=white"/>

</a>

</p>

> 📺 Click the button above to watch the complete project demonstration and SQL explanation video.
---

## 🎯 Project Objectives

- Import Olist CSV datasets into Power BI.
- Clean and transform data using Power Query.
- Translate product category names into English.
- Build a data model using fact and dimension tables.
- Create a date table for time-based analysis.
- Configure relationships between orders, order items, customers, products, sellers, payments, reviews, and dates.
- Create KPI cards, charts, maps, and matrices.
- Analyze sales, order volume, customer geography, seller revenue, payment methods, and review scores.
- Use slicers and visual interactions to explore the report.
- Design a professional multi-page Power BI dashboard.

---

## 🛠️ Technologies Used

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Report creation and data visualization |
| Power Query Editor | Data cleaning and transformation |
| DAX | Measures and analytical calculations |
| CSV Files | Source datasets |
| Power BI Data Model | Relationships between fact and dimension tables |
| GitHub | Project documentation and version control |

---

## 🗃️ Dataset

The project uses Olist e-commerce CSV datasets containing information about orders, order items, customers, products, sellers, payments, reviews, geolocation, and product category translations.

### Source Tables

| Power BI Table Name | Source Data |
|---|---|
| `FactOrderItems` | Order items |
| `DimOrders` | Orders |
| `DimCustomers` | Customers |
| `DimProducts` | Products |
| `DimSellers` | Sellers |
| `FactPayments` | Order payments |
| `FactReviews` | Order reviews |
| `DimGeolocation` | Geolocation |
| `CategoryTranslation` | Product category translations |
| `DimDate` | Date table created for time analysis |

### Important Fields

- `order_id`
- `customer_id`
- `product_id`
- `seller_id`
- `price`
- `freight_value`
- `payment_type`
- `payment_value`
- `review_score`
- `customer_state`
- `seller_state`
- `Product_Category_EN`

---

## ⚙️ Data Preparation and Modeling

### Power Query Preparation

The main data preparation steps include:

1. Importing the source CSV files into Power BI.
2. Renaming queries to consistent fact-table and dimension-table names.
3. Merging product category translations into `DimProducts`.
4. Expanding the English category name and renaming it `Product_Category_EN`.
5. Checking column data types and reviewing missing values.
6. Keeping legitimate missing delivery dates and optional review comments as null where appropriate.
7. Creating a `DimDate` table for date-based reporting.

### Data Model

The report uses fact and dimension tables to connect order information to descriptive data.

Key relationships include:

- `FactOrderItems[order_id]` → `DimOrders[order_id]`
- `FactOrderItems[product_id]` → `DimProducts[product_id]`
- `FactOrderItems[seller_id]` → `DimSellers[seller_id]`
- `DimOrders[customer_id]` → `DimCustomers[customer_id]`
- `DimDate[Date]` → `DimOrders[order_purchase_timestamp]`
- `FactPayments[order_id]` → `DimOrders[order_id]`
- `FactReviews[order_id]` → `DimOrders[order_id]`

Relationships are configured and checked in Model view.

### Date Analysis

The `DimDate` table supports time-based analysis with fields such as:

- Year
- Quarter
- Month number
- Month name
- Weekday
- Year-quarter

A date hierarchy supports drill-down from Year to Quarter to Month.

---

## 📊 Dashboard Pages and Features

### 📈 Page 1 — Sales Overview

This page provides an overview of order and sales performance.

**KPI Cards**

- Total Orders
- Total Revenue
- Average Order Value
- Average Review Score

**Charts and Visuals**

- **Top 10 Product Categories by Revenue:** Clustered Bar Chart.
- **Monthly Order Volume:** Line Chart with date hierarchy drill-down.
- **Orders by Customer State:** Map visual.
- **Revenue by Year and Product Category:** Matrix.

**Slicers**

- Year
- Order Status
- Product Category

### 🌎 Page 2 — Geographic Analysis

**Header:** Geographic Distribution — Customers & Sellers

This page compares customer order distribution with seller revenue by location.

**Charts and Visuals**

- **Orders by Customer State:** Map visual using the Customer Location hierarchy where appropriate.
- **Top 10 Seller Cities by Revenue:** Clustered Bar Chart.
- **Revenue by Seller State:** Clustered Column Chart using the Seller Location hierarchy where appropriate.

**Slicer**

- Year

### 💳 Page 3 — Payments & Reviews

**Header:** Payment Methods · Customer Satisfaction

This page explores payment behavior and customer review scores.

**Charts and Visuals**

- **Payment Type × Year:** Matrix with conditional formatting.
- **Payment Type Mix:** Donut Chart showing each payment type's share of `payment_value`.
- **Average Review Score by Product Category:** Bar Chart using `FactReviews[review_score]` and the model relationships connecting reviews with products.

**Slicer**

- Year

---

## 🎨 Dashboard Design

The report follows a consistent design across all three pages.

- Clear page titles and section headings.
- Consistent spacing and alignment between visuals.
- KPI cards positioned near the top of the Sales Overview page.
- Charts arranged in a readable layout.
- Slicers grouped together for convenient filtering.
- Appropriate currency, number, and date formatting.
- Conditional formatting in the payment matrix for easier comparison.
- Interactive visual filtering and date hierarchy drill-down.

---
# 📸 Project Output

## Home Page

<p align="center">
  <img src="Home Page.png" width="900" alt="Database">
</p>

---

## Sales Overview

<p align="center">
  <img src="Sales Overview.png" width="900" alt="Database">
</p>

---

## Geographic Analysis

<p align="center">
  <img src="Geopraphic .png" width="900" alt="Database">
</p>

---

## Payments & Reviews

<p align="center">
  <img src="Payment .png" width="900" alt="Database">
</p>

---
## 🚀 How to Open the Report

1. Install **Microsoft Power BI Desktop**.
2. Download or clone this GitHub repository.
3. Open `Olist_E-Commerce_Analytics.pbix`.
4. If Power BI cannot find the source CSV files, go to **Transform data → Data source settings** and update the source file paths.
5. Select **Close & Apply** if changes to the data sources are required.
6. Navigate through **Sales Overview**, **Geographic Analysis**, and **Payments & Reviews**.
7. Use the slicers and select chart elements to explore the report.

---

## 🎓 Learning Outcomes

Through this project, I practiced:

- Importing and preparing multiple CSV datasets.
- Cleaning and transforming data using Power Query.
- Merging lookup data to translate product categories.
- Building a fact-and-dimension data model.
- Creating a date table and date hierarchy.
- Setting up table relationships and checking filter direction.
- Creating KPI cards and analytical measures.
- Building bar charts, column charts, line charts, maps, donut charts, and matrices.
- Using slicers, drill-down, and conditional formatting.
- Designing a multi-page interactive Power BI report.
- Documenting a data analytics project for a portfolio.

---

## 👨‍💻 Author

**Sarth Thakar**
