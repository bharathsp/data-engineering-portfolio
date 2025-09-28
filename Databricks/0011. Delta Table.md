## Delta Table

A **Delta Table** is a **data storage format** based on **Delta Lake**, an open-source storage layer that brings **ACID transactions**, **versioning**, and **schema enforcement** to data lakes (like S3, ADLS, etc.), typically used with **Apache Spark**.

Delta Tables are foundational to the **Databricks Lakehouse architecture**, blending the reliability of data warehouses with the scale of data lakes.

---

### 🧠 **In Simple Terms:**

A **Delta Table** is like a **Parquet table with superpowers** — you can query it like a normal table, but it supports updates, deletes, merges, time travel, and much more.

---

### ✅ **Key Features of Delta Table**

| Feature                     | Description                                                         |
| --------------------------- | ------------------------------------------------------------------- |
| 🔄 **ACID Transactions**    | Guarantees consistency for concurrent reads/writes                  |
| 📜 **Schema Enforcement**   | Prevents bad data from corrupting the table                         |
| 🕒 **Time Travel**          | Query previous versions of data using timestamps or version numbers |
| 🗃️ **Efficient Storage**   | Stores data in **Parquet** + transaction log (`_delta_log`)         |
| 🔍 **Fast Reads/Writes**    | Optimized with **data skipping**, **Z-ordering**, and **caching**   |
| 🔧 **Merge/Upsert Support** | Supports `MERGE`, `UPDATE`, and `DELETE`                            |
| 🚀 **Streaming + Batch**    | Works seamlessly with streaming and batch data                      |

---

### 📂 **Delta Table File Structure**

```
/my_delta_table/
├── part-0001.parquet
├── part-0002.parquet
└── _delta_log/
    ├── 00000000000000000000.json
    ├── 00000000000000000001.json
    └── ...
```

---

### 💻 **Creating Delta Tables in PySpark**

#### 1️⃣ **From a DataFrame**

```python
df.write.format("delta").save("/path/to/delta-table")
```

#### 2️⃣ **Using SQL (Databricks or Spark SQL)**

```sql
CREATE TABLE sales
USING DELTA
AS SELECT * FROM sales_data;
```

---

### 🔁 **Update, Merge, and Delete in Delta Table**

```python
from delta.tables import DeltaTable

delta_table = DeltaTable.forPath(spark, "/path/to/delta-table")

# Update
delta_table.update(
    condition="region = 'APAC'",
    set={"sales": "sales * 1.1"}
)

# Delete
delta_table.delete("sales < 100")

# Merge (Upsert)
delta_table.alias("target").merge(
    source_df.alias("source"),
    "target.id = source.id"
).whenMatchedUpdateAll().whenNotMatchedInsertAll().execute()
```

---

### 🕰️ **Time Travel**

```python
# Read an old version
df = spark.read.format("delta").option("versionAsOf", 2).load("/path/to/delta-table")

# Or read as of timestamp
df = spark.read.format("delta").option("timestampAsOf", "2024-07-10").load("/path/to/delta-table")
```

---

### 🔄 **Convert Parquet to Delta**

```python
from delta.tables import DeltaTable

DeltaTable.convertToDelta(spark, "parquet.`/path/to/parquet-folder`")
```

---

### 🧾 Summary

| Property         | Delta Table                      |
| ---------------- | -------------------------------- |
| Storage Format   | Parquet + Delta transaction log  |
| ACID Support     | ✅ Yes                            |
| Time Travel      | ✅ Yes                            |
| Schema Evolution | ✅ Yes                            |
| Update/Delete    | ✅ Yes (not in regular Parquet)   |
| Query Support    | SQL / DataFrame API / Delta APIs |
