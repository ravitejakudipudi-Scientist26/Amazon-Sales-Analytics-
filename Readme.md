This **README.md** is designed to showcase your expertise in both **Data Engineering** (the pipeline) and **Data Analytics** (the insights). It focuses on the technical rigor of transforming "dirty" data into a professional BI tool.

Copy and paste the following into your `README.md` file:

---

# Amazon Sales & Discount Analytics Pipeline

A comprehensive Data Engineering and Analytics project that automates the transition from raw, unstructured e-commerce data to high-fidelity business intelligence. This project features a full ETL (Extract, Transform, Load) pipeline using Python and PostgreSQL, finalized with an interactive Power BI dashboard.

## 🚀 Project Overview

This system solves the problem of "Data Debt" in retail datasets. By programmatically cleaning malformed strings and handling data anomalies, the pipeline ensures that all downstream analytics are accurate and actionable.

### **The Technical Stack**

* **Data Processing:** Python (Pandas)
* **Database Management:** PostgreSQL
* **Infrastructure Bridge:** SQLAlchemy & Psycopg2
* **Business Intelligence:** Power BI

---

## 🏗️ Technical Architecture

The project is built on a 4-stage data lifecycle:

1. **Ingestion:** Consumption of raw `amazon.csv` (1,400+ records) containing mixed-type data and currency symbols.
2. **Transformation (ETL):** A Python logic layer that handles RegEx-based cleaning, type conversion, and null-value imputation.
3. **Persistence:** Migration of normalized data into a **PostgreSQL** Relational Database.
4. **Analytics:** A professional **Power BI** dashboard connected to the SQL layer for real-time data exploration.

---

## 🛠️ Logic

### **1. Programmatic ETL (Python)**

The raw dataset was "dirty," with prices stored as strings (e.g., `₹1,299.00`). The Python pipeline:

* **RegEx Normalization:** Stripped currency symbols (`₹`) and separators (`,`) to convert strings to `Float64`.
* **Anomaly Detection:** Corrected malformed entries (e.g., replaced `|` in ratings with the median 4.0).
* **Feature Engineering:** Created the `amount_saved` metric () to measure consumer value.

### **2. Database Schema Design**

Data integrity is enforced through a strictly typed PostgreSQL schema:

```sql
CREATE TABLE product_analysis (
    product_id VARCHAR(50) PRIMARY KEY,
    main_category TEXT,
    actual_price NUMERIC(12, 2),
    discounted_price NUMERIC(12, 2),
    rating DECIMAL(3, 1),
    rating_count INTEGER,
    amount_saved NUMERIC(12, 2)
);

```

---

## 📊 Data Analytics & Insights

The Power BI dashboard delivers three distinct analytical views:

* **Executive KPIs:** High-level tracking of Total Revenue, Average Rating, and Discount Intensity.
* **Sales Volume Analysis:** Horizontal bar charts identifying Top-N categories by revenue.
* **Value Distribution:** Donut charts visualizing the percentage of "Amount Saved" across product categories.
* **Dynamic Filtering:** An interactive slicer pane allowing for instantaneous cross-visual filtering by category.

---

## 🔧 Installation & Usage

1. **Clone the Repository:**
```bash
git clone https://github.com/your-username/amazon-analytics-pipeline.git

```


2. **Install Python Libraries:**
```bash
pip install pandas sqlalchemy psycopg2

```


3. **Configure PostgreSQL:** Create a database named `amazon_db` and update the connection string in the Python script.
4. **Execute Pipeline:** Run the Python script to clean and inject data into SQL.
5. **Launch Analytics:** Open the `.pbix` file in Power BI Desktop and refresh the data source.

---

## 🔮 Future Roadmap

* **Pipeline Automation:** Scheduling the ETL script as a cron job for daily data updates.
* **Advanced SQL Modeling:** Implementing window functions to calculate category-wise ranking and percentiles.
* **Predictive Analysis:** Using historical data to forecast discount trends per category.

---
