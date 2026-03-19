# 📊 E-Commerce Sales & Conversion Analysis

## 📌 Project Overview

This project focuses on analyzing an e-commerce dataset containing multiple **relational tables** to derive insights into **traffic, conversions, product performance, and refunds**.

The goal was to simulate a **real-world data analyst workflow** — from raw data handling to building an interactive **Power BI dashboard**.

---

## 🗂️ Dataset Description

The dataset consists of the following tables:

### 1. `website_sessions`

* Tracks user sessions on the website
* Key fields:

  * `website_session_id` (PK)
  * `created_at`
  * `user_id` (FK)
  * `is_repeat_session`
  * `utm_source`, `utm_campaign`, `utm_content`
  * `device_type`
  * `http_referer`

⚠️ **Data Quality Note:**

* Missing values found in:

  * `utm_source`, `utm_campaign`, `utm_content`
  * `http_referer`
* Around **40,000 rows were labeled as "Unknown"** after cleaning.

---

### 2. `website_pageviews`

* Tracks page-level user activity
* Fields:

  * `website_pageview_id` (PK)
  * `created_at`
  * `website_session_id` (FK)
  * `pageview_url`

---

### 3. `orders`

* Stores order-level information
* Fields:

  * `order_id` (PK)
  * `created_at`
  * `website_session_id` (FK)
  * `user_id` (FK)
  * `primary_product_id` (FK)
  * `items_purchased`
  * `price_usd`
  * `cogs_usd`

---

### 4. `order_items`

* Item-level breakdown of orders
* Fields:

  * `order_item_id` (PK)
  * `order_id` (FK)
  * `product_id` (FK)
  * `is_primary_item`
  * `price_usd`
  * `cogs_usd`

---

### 5. `order_item_refunds`

* Tracks refunded items
* Fields:

  * `order_item_refund_id` (PK)
  * `order_item_id` (FK)
  * `order_id` (FK)
  * `refund_amount_usd`

---

### 6. `products`

* Product information
* Fields:

  * `product_id` (PK)
  * `product_name`
  * `created_at`

---

### 7. `maven_fuzzy_factory_data_dictionary`

* Contains metadata for all tables and columns

---

## ⚙️ Data Processing Workflow

### 🔹 Step 1: Data Cleaning

* Handled null values in `website_sessions`
* Used relationships to fill missing values where possible
* Remaining null values labeled as `"Unknown"`

---

### 🔹 Step 2: Tool Selection

| Tool          | Outcome                        |
| ------------- | ------------------------------ |
| SQL Workbench | Failed to import large tables  |
| Excel         | Failed due to size limitations |
| Power BI      | Successfully imported          |

👉 Final tool used: **Power BI**

---

### 🔹 Step 3: Data Modeling

* Established relationships using **primary & foreign keys**
* Built a proper **relational model** inside Power BI

---

## 📐 Measures Created

* Total Sessions
* Total Orders
* Total Sales
* Revenue
* Total COGS
* Adjusted COGS
* Total Profit
* Conversion Rate
* Refund Count
* Refund Rate
* Refunded Items
* Refunded COGS
* Total Refunds

---

## 📊 Dashboard Structure

### 📍 Page 1: Traffic Overview

**KPIs:**

* Total Sessions
* Total Orders
* Revenue
* Total Profit
* Conversion Rate

**Visuals:**

* Time trend (line chart)
* Sessions by Device
* Sessions by UTM Source
* Sessions by UTM Campaign

**Filters:**

* Device Type
* UTM Source
* UTM Campaign
* Date

---

### 📍 Page 2: Conversion Analysis

**Visuals:**

* Funnel: Sessions → Orders
* Orders by UTM Source
* Conversion Rate by Device

---

### 📍 Page 3: Product Performance

**Visuals:**

* Revenue by Product
* Orders by Product
* Profit by Product

**Filters:**

* Date
* Product Name

---

### 📍 Page 4: Refund Analysis

**Visuals:**

* Refund Count by Product
* Refunded COGS by Product
* Refund Rate by Product

---

### 📍 Page 5: Website Behavior

**Matrix Visualization:**

* Rows: `pageview_url`
* Columns: `utm_source`
* Values: Pageview count

---

## 📈 Key Insights (Example Directions)

* Identify **top-performing marketing channels**
* Analyze **conversion efficiency by device**
* Detect **high-refund products**
* Understand **user navigation behavior**
* Evaluate **profitability vs revenue**

---

## 🚀 Learnings

* Working with **relational datasets** for the first time
* Handling **large datasets limitations across tools**
* Building **data models in Power BI**
* Creating **business KPIs from raw data**
* Designing **multi-page analytical dashboards**

---

## 🛠️ Tech Stack

* Power BI
* Excel (initial attempt)
* SQL (conceptual understanding)

---

## 📌 Conclusion

This project demonstrates the complete journey of a data analyst:
➡️ Raw Data → Cleaning → Tool Selection → Modeling → Dashboard → Insights

It highlights the importance of choosing the **right tool for large relational datasets** and showcases how Power BI can effectively handle such scenarios.
