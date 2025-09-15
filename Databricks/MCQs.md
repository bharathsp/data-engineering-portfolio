## 📝 Databricks Fundamentals – Practice MCQ Test

### 1. What is the core purpose of Databricks?

* A. Web application hosting
* B. Unified analytics platform for data engineering, data science, and machine learning
* C. File storage service
* D. Cloud networking service

```
B. Unified analytics platform for data engineering, data science, and machine learning
```

---

### 2. Databricks is built on top of which open-source framework?

* A. Hadoop
* B. Apache Spark
* C. Apache Flink
* D. Kafka

```
B. Apache Spark
```

---

### 3. What is the Databricks Lakehouse?

* A. A tool only for machine learning
* B. A combination of data warehouse and data lake features
* C. A type of cluster
* D. A visualization library

```
B. A combination of data warehouse and data lake features
```

---

### 4. Which of the following is NOT a Databricks cluster type?

* A. All-purpose cluster
* B. Job cluster
* C. Pool cluster
* D. Storage cluster

```
D. Storage cluster
```

---

### 5. What is a Databricks notebook primarily used for?

* A. Writing SQL only
* B. Developing code, running queries, and visualizing results interactively
* C. Only storing datasets
* D. Only scheduling jobs

```
B. Developing code, running queries, and visualizing results interactively
```

---

### 6. In Databricks, a “Workspace” is best described as:

* A. A storage volume for raw data
* B. A collaborative environment for notebooks, libraries, and experiments
* C. A compute engine for ML models
* D. A job scheduling dashboard only

```
B. A collaborative environment for notebooks, libraries, and experiments
```

---

### 7. Delta Lake provides which main feature?

* A. Streaming-only data pipelines
* B. ACID transactions on data lakes
* C. Serverless compute
* D. Data visualization

```
B. ACID transactions on data lakes
```

---

### 8. Which of these languages is NOT supported in Databricks notebooks?

* A. Python
* B. SQL
* C. Scala
* D. PHP

```
D. PHP
```

---

### 9. Databricks “pools” are used to:

* A. Store datasets efficiently
* B. Reduce cluster startup times by pre-warming instances
* C. Increase SQL query cache performance
* D. Deploy dashboards faster

```
B. Reduce cluster startup times by pre-warming instances
```

---

### 10. In Databricks, MLflow is used for:

* A. Workflow scheduling
* B. Machine learning experiment tracking and model management
* C. Streaming data ingestion
* D. Security and governance

```
B. Machine learning experiment tracking and model management
```

---

### 11. What is the default file format for Delta Lake tables?

* A. Parquet with transaction log
* B. ORC
* C. Avro
* D. CSV

```
A. Parquet with transaction log
```

---

### 12. Databricks SQL is designed for:

* A. Writing machine learning code
* B. Data governance
* C. Querying structured data in the Lakehouse using SQL
* D. Configuring clusters

```
C. Querying structured data in the Lakehouse using SQL
```

---

### 13. What is a “job” in Databricks?

* A. A long-running cluster
* B. A scheduled or triggered execution of a notebook, JAR, or Python script
* C. A Spark SQL query
* D. A data governance policy

```
B. A scheduled or triggered execution of a notebook, JAR, or Python script
```

---

### 14. Unity Catalog in Databricks helps with:

* A. Data governance, access control, and lineage across the Lakehouse
* B. Dashboard creation
* C. Streaming ingestion
* D. Visualization only

```
A. Data governance, access control, and lineage across the Lakehouse
```

---

### 15. What does “Photon” in Databricks refer to?

* A. A hardware accelerator for ML
* B. A vectorized query engine for fast execution of SQL and DataFrame operations
* C. A data ingestion framework
* D. A machine learning library

```
B. A vectorized query engine for fast execution of SQL and DataFrame operations
```

---

## **Section A: Basics (Q1–15)**

**1.** What type of platform is Databricks?
A. Data storage service
B. Unified data and AI platform
C. Cloud monitoring tool
D. CRM tool

```
B. Unified data and AI platform
```

**3.** Which cloud providers support Databricks?
A. AWS
B. Azure
C. GCP
D. All of the above

```
D. All of the above
```

**4.** The Lakehouse architecture combines:
A. Data warehouse + Data mart
B. Data lake + Data warehouse
C. Data warehouse + Streaming
D. Data lake + OLTP

```
B. Data lake + Data warehouse
```

**5.** What is the default workspace storage for notebooks?
A. MySQL
B. GitHub
C. Databricks File System (DBFS)
D. MongoDB

```
C. Databricks File System (DBFS)
```

**6.** Which language is NOT supported in Databricks notebooks?
A. SQL
B. Scala
C. Python
D. Ruby

```
D. Ruby
```

**7.** What are the two main cluster types?
A. Job and Storage clusters
B. Job and All-purpose clusters
C. Runtime and SQL clusters
D. Small and Large clusters

```
B. Job and All-purpose clusters
```

**9.** In Databricks, a notebook is:
A. A file storage system
B. A collaborative code environment
C. A cluster
D. A SQL optimizer

```
B. A collaborative code environment
```

**10.** Which UI component allows SQL analysts to run queries in Databricks?
A. Jobs UI
B. Notebooks
C. Databricks SQL
D. MLflow

```
C. Databricks SQL
```

**11.** Which of these is used for ML experiment tracking?
A. Unity Catalog
B. MLflow
C. Photon
D. Pooling

```
B. MLflow
```

**12.** What format does Delta Lake use internally?
A. Avro
B. ORC
C. Parquet + transaction logs
D. CSV

```
C. Parquet + transaction logs
```

**13.** Which of the following supports real-time data ingestion?
A. Structured Streaming
B. Unity Catalog
C. MLflow
D. Jobs API

```
A. Structured Streaming
```

---

## **Section B: Intermediate (Q16–35)**

**16.** Which of these is an advantage of using job clusters?
A. Always running
B. Cost-efficient for scheduled workloads
C. Multi-user collaboration
D. Supports only Python

```
B. Cost-efficient for scheduled workloads
```

**17.** Which feature helps manage costs by automatically terminating idle clusters?
A. Photon
B. Auto-stop
C. Auto-scaling
D. Pools

```
B. Auto-stop
```

**18.** Which cluster type is best for ad-hoc analysis?
A. Job cluster
B. All-purpose cluster
C. Storage cluster
D. Pool cluster

```
B. All-purpose cluster
```

**19.** In Delta Lake, time travel enables:
A. Faster SQL queries
B. Querying historical versions of data
C. ML model training
D. Real-time streaming

```
B. Querying historical versions of data
```

**20.** What is the function of the Delta transaction log (\_delta\_log)?
A. Stores data partitions
B. Tracks commits, schema changes, and versions
C. Stores query execution plans
D. Manages caching

```
B. Tracks commits, schema changes, and versions
```

**21.** Which API allows automation of job creation and monitoring?
A. MLflow API
B. Databricks REST API
C. Delta API
D. Unity Catalog API

```
B. Databricks REST API
```

**22.** In Unity Catalog, which is the highest-level container?
A. Table
B. Schema
C. Catalog
D. Notebook

```
C. Catalog
```

**23.** Which statement about Photon is true?
A. It only supports Python
B. It speeds up SQL/DataFrame queries
C. It is a machine learning library
D. It is for job scheduling

```
B. It speeds up SQL/DataFrame queries
```

**24.** What is MLflow’s Model Registry used for?
A. Data versioning
B. Deployment and lifecycle management of ML models
C. Stream ingestion
D. Job scheduling

```
B. Deployment and lifecycle management of ML models
```

**25.** Which Databricks feature allows you to connect to external BI tools like Tableau?
A. Jobs
B. JDBC/ODBC connectors
C. Pools
D. MLflow

```
B. JDBC/ODBC connectors
```

**26.** Delta Lake ensures schema enforcement by:
A. Ignoring mismatched data
B. Automatically converting data types
C. Rejecting records not matching schema
D. Dropping the table

```
C. Rejecting records not matching schema
```

**27.** Which of the following does **NOT** reduce cluster costs?
A. Pools
B. Auto-scaling
C. Auto-termination
D. Increasing cluster size

```
D. Increasing cluster size
```

**28.** Which cloud service does Databricks rely on for storage?
A. Its own proprietary file system only
B. Underlying cloud storage (S3, ADLS, GCS)
C. HDFS
D. MongoDB

```
B. Underlying cloud storage (S3, ADLS, GCS)
```

**29.** Which of these is a governance feature in Unity Catalog?
A. Access controls at table level
B. Visualization dashboards
C. Job scheduling
D. Auto-scaling

```
A. Access controls at table level
```

**30.** Jobs in Databricks can execute:
A. Only SQL queries
B. Notebooks, JARs, or Python scripts
C. Only Delta table updates
D. Dashboards

```
B. Notebooks, JARs, or Python scripts
```

**31.** Which of these languages can be mixed inside a Databricks notebook with magic commands?
A. SQL and Python
B. Scala and Java
C. R and Ruby
D. PHP and Python

```
A. SQL and Python
```

**32.** DBFS (Databricks File System) is:
A. An external data warehouse
B. A distributed file system over cloud object storage
C. A caching layer only
D. Local disk storage

```
B. A distributed file system over cloud object storage
```

**33.** What is the smallest unit of compute in Databricks?
A. Node
B. Cluster
C. Pool
D. Notebook

```
A. Node
```

**34.** Databricks Repos is primarily used for:
A. Data ingestion
B. Version controlling notebooks with Git
C. Cluster optimization
D. Governance

```
B. Version controlling notebooks with Git
```

**35.** A dashboard in Databricks is created from:
A. Delta logs
B. Queries and visualizations
C. Jobs
D. Unity Catalog

```
B. Queries and visualizations
```

---

## **Section C: Advanced (Q36–50)**

**36.** Which of the following helps in reducing shuffle operations in Spark?
A. Photon
B. Bucketing
C. Unity Catalog
D. Pools

```
B. Bucketing
```

**37.** Which scaling option allows adding/removing workers based on workload?
A. Auto-stop
B. Auto-scaling
C. Photon scaling
D. Job scaling

```
B. Auto-scaling
```

**38.** What is Z-order clustering used for in Delta Lake?
A. Improving joins
B. Optimizing data skipping for queries
C. ML training
D. Faster streaming ingestion

```
B. Optimizing data skipping for queries
```

**39.** Which feature provides column-level lineage in Databricks?
A. Photon
B. Unity Catalog
C. Pools
D. Jobs

```
B. Unity Catalog
```

**40.** What is the main benefit of Delta Live Tables (DLT)?
A. Real-time chat feature
B. Declarative ETL pipelines with built-in quality checks
C. Query visualization
D. Model registry

```
B. Declarative ETL pipelines with built-in quality checks
```

**41.** What does “medallion architecture” refer to?
A. Bronze-Silver-Gold layered data pipelines
B. Cluster security layers
C. Dashboard themes
D. Governance levels

```
A. Bronze-Silver-Gold layered data pipelines
```

**42.** Which Databricks feature is used for serverless SQL execution?
A. SQL Warehouses
B. Jobs
C. Pools
D. Photon only

```
A. SQL Warehouses
```

**43.** Which command enables switching between languages in notebooks?
A. %lang
B. %magic
C. %sql, %python, %scala
D. %switch

```
C. %sql, %python, %scala
```

**44.** Which Delta feature ensures that read and write operations do not conflict?
A. Schema evolution
B. ACID transactions
C. Z-ordering
D. Compaction

```
B. ACID transactions
```

**45.** What is the main difference between “schema enforcement” and “schema evolution”?
A. Enforcement allows changes; evolution blocks changes
B. Enforcement blocks invalid records; evolution updates schema automatically
C. Both block changes
D. Both update schema automatically

```
B. Enforcement blocks invalid records; evolution updates schema automatically
```

**46.** Which Databricks feature helps in governing ML model usage?
A. Pools
B. MLflow Model Registry
C. Photon
D. Jobs UI

```
B. MLflow Model Registry
```

**47.** Which file type is NOT natively supported by Databricks?
A. JSON
B. CSV
C. Avro
D. XLSX

```
D. XLSX
```

**48.** Which cluster configuration is most cost-effective for production pipelines?
A. All-purpose clusters
B. Job clusters with auto-termination
C. Always-on clusters
D. Clusters without auto-scaling

```
B. Job clusters with auto-termination
```

**49.** Which of the following is a vectorized query engine in Databricks?
A. Photon
B. Spark Streaming
C. Unity Catalog
D. DBFS

```
A. Photon
```

**50.** A key security practice in Databricks is:
A. Allowing open access to all users
B. Using Unity Catalog for fine-grained permissions
C. Running clusters with no auto-stop
D. Sharing tokens in notebooks

```
B. Using Unity Catalog for fine-grained permissions
```


---

Would you like me to **format this into a PDF exam paper with answers hidden** (so you can take it like a real test and then check later)?

