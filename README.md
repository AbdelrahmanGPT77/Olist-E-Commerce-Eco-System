# Olist-E-Commerce-Eco-System
Analyzed the Olist Brazilian E-commerce dataset to uncover sales and delivery insights, understand customer behavior, and segment customers using RFM Analysis and K-Means clustering


# 🛒 Olist E-commerce Ecosystem Analysis

## 📌 Project Overview

This project analyzes the **Olist Brazilian E-commerce dataset** to understand the overall performance of an e-commerce ecosystem from different perspectives, including orders, products, customers, sellers, revenue, and delivery performance.

The project focuses on turning raw e-commerce data into meaningful business insights and identifying customer segments based on their purchasing behavior.

---

## 🎯 Project Objectives

The main objectives of this project were to:

- Analyze the overall order and sales performance.
- Investigate delivery performance and identify late deliveries.
- Understand product and category revenue distribution.
- Identify the cities with the highest sales.
- Analyze seller and customer distribution.
- Segment customers based on their purchasing behavior using **RFM Analysis**.
- Use clustering techniques to identify meaningful customer groups.
- Visualize the results to make the insights easier to understand.

---

## 📊 Dataset

The project uses multiple tables from the **Olist Brazilian E-commerce dataset**, including:

- Orders
- Order Items
- Payments
- Reviews
- Products
- Sellers
- Customers
- Product Categories
- Geolocation

The dataset contains approximately:

- **99K orders**
- **112K order items**
- **32K products**
- **3K sellers**
- **99K customers**
- **1M+ geolocation records**

The different tables were combined where necessary to create a more complete view of the e-commerce ecosystem.

---

## 🔍 Data Preparation & Exploration

The first stage focused on understanding the structure and quality of the data.

### Data Type Handling

The order timestamp columns were converted from `object` to `datetime` to allow accurate time-based analysis.

### Missing Values

Missing values were investigated, especially in delivery-related columns such as:

- `order_approved_at`
- `order_delivered_carrier_date`
- `order_delivered_customer_date`

Instead of simply removing these records, the missing values were analyzed in relation to the **order status** to understand whether they represented orders that were still in progress, canceled, unavailable, or in another stage of the order lifecycle.

---

## 🚚 Delivery Performance Analysis

One of the main parts of the project was analyzing delivery performance.

For delivered orders, two important metrics were calculated:

### Delivery Days

The number of days between:

`Order Purchase Date → Customer Delivery Date`

### Delivery Delay

The difference between:

`Actual Delivery Date → Estimated Delivery Date`

Based on this calculation:

- **88,652 orders** were delivered on time.
- **7,826 orders** were delivered late.

This allowed the project to evaluate delivery performance based on actual delivery dates rather than treating missing delivery timestamps as simple data-cleaning problems.

---

## 📦 Product & Revenue Analysis

The products, categories, and order items were merged to analyze revenue across different product categories.

The analysis identified the highest-revenue categories, including:

- **Health & Beauty**
- **Watches & Gifts**
- **Bed & Bath Table**
- **Sports & Leisure**
- **Computers & Accessories**

The project also identified the individual products generating the highest total revenue.

This provides a better understanding of which product categories contribute most to the overall sales performance.

---

## 🌎 Geographic Sales Analysis

Customer information was combined with order data to investigate sales distribution across different cities.

The highest-sales cities identified in the analysis included:

- São Paulo
- Rio de Janeiro
- Belo Horizonte
- Brasília
- Curitiba

This type of analysis can help understand where customer demand is concentrated geographically.

---

## 👥 Customer Segmentation – RFM Analysis

To better understand customer behavior, the project used **RFM Analysis**.

RFM stands for:

- **Recency** – How recently the customer made a purchase.
- **Frequency** – How often the customer made purchases.
- **Monetary** – How much the customer spent.

Only delivered orders were used for the RFM analysis.

The three RFM features were standardized using `StandardScaler` before applying clustering because they have very different numerical scales.

---

## 🤖 Customer Clustering

**K-Means Clustering** was used to segment customers based on their RFM behavior.

The number of clusters was investigated using:

- **Elbow Method**
- **Silhouette Score**

The final analysis used **3 customer segments** to provide a more useful level of business granularity.

The resulting segments showed three main behavioral groups:

### 🟢 VIP Customers
Customers with higher purchasing frequency and spending.

### 🔵 Regular Customers
Customers with average activity and spending levels.

### 🟠 Dormant Customers
Customers with lower activity and spending who have not purchased recently.

These segments can help support different customer strategies, such as loyalty programs, promotional campaigns, and re-engagement offers.

---

## 📉 PCA Visualization

**Principal Component Analysis (PCA)** was used to reduce the scaled RFM features to two dimensions for visualization.

The first two principal components explained approximately **70.3% of the variance**, allowing the customer segments to be visualized in a 2D space.

PCA was used here primarily as a **visualization technique**, while the actual customer segmentation was performed using the RFM features and K-Means.

---

## 🛠️ Tools & Technologies

- **Python**
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Scikit-learn**
  - K-Means Clustering
  - StandardScaler
  - PCA
  - Silhouette Score

---

## 💡 Key Business Insights

The analysis provides several useful insights into the Olist e-commerce ecosystem:

- Most analyzed delivered orders arrived **on time**, while a smaller portion experienced delivery delays.
- **Health & Beauty** generated the highest revenue among the analyzed product categories.
- Sales were highly concentrated in major Brazilian cities, particularly **São Paulo** and **Rio de Janeiro**.
- Customer behavior was not uniform; RFM analysis revealed distinct purchasing patterns.
- Customer segmentation can help businesses move from a general marketing strategy toward more targeted customer engagement.

---

## 📌 Project Outcome

This project demonstrates how multiple e-commerce datasets can be combined and analyzed to move from **raw data → data exploration → business metrics → customer segmentation → actionable insights**.

It combines traditional **Exploratory Data Analysis (EDA)** with **unsupervised machine learning** to provide a broader understanding of an e-commerce business and its customers.
