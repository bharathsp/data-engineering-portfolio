## **Data Warehouse (DWH)**

A **Data Warehouse (DWH)** is a **centralized repository** that stores large volumes of structured data collected from different sources, such as transactional systems, operational databases, CRM systems, or external data sources. The primary goal is to support **business intelligence (BI)** activities like reporting, data analysis, and decision-making.

---

### 🔍 **Key Characteristics of a Data Warehouse:**

1. **Subject-Oriented**

   * Organized around key subjects (e.g., sales, customers, inventory).
   * Focuses on analysis rather than day-to-day operations.

2. **Integrated**

   * Consolidates data from multiple heterogeneous sources into a consistent format.

3. **Non-Volatile**

   * Once data enters the warehouse, it isn’t updated or deleted frequently.
   * Supports historical analysis.

4. **Time-Variant**

   * Stores historical data (e.g., last 5 years) for trend analysis.

---

### 🧱 **Data Warehouse Architecture Layers:**

1. **Data Source Layer**

   * Operational databases, flat files, cloud services, APIs, etc.

2. **ETL Layer (Extract, Transform, Load)**

   * Extracts data from sources, cleans and transforms it, and loads into the warehouse.

3. **Data Storage Layer**

   * Central warehouse where cleaned, historical data is stored (often in star or snowflake schemas).

4. **Presentation/BI Layer**

   * Tools like Tableau, Power BI, Looker used for querying, reporting, and dashboarding.

---

### 💡 **Why Use a Data Warehouse?**

* Faster query performance for analytics
* Unified view of business data
* Better data quality and consistency
* Enables historical trend analysis
* Scalable for large datasets

---

### 🛠️ **Popular Data Warehousing Technologies:**

* **Cloud-based**: Snowflake, Amazon Redshift, Google BigQuery, Azure Synapse
* **On-premise**: Teradata, Oracle Exadata, IBM DB2 Warehouse

---

### 📈 **Example Use Case:**

A retail company uses a data warehouse to combine sales data from all stores, customer feedback from CRM, and website analytics. This helps in:

* Forecasting sales trends
* Identifying best-selling products
* Understanding customer behavior across channels
