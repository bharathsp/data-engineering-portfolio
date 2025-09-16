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

## Real Exam Questions

**1.** Which two statements provide an explanation of data lakehouse architecture and its benefits?
* A. The data lakehouse architecture provides a new variety of data warehousing technology, in which cloud-based data is stored in a proprietary format for efficient management.
* B. Data lakehouse architecture offers the benefit of bridging the gap between multiple existing platforms within a data ecosystem by adding a data governance layer that manages AI data assets.
* C. The data lakehouse architecture provides a unified platform for all data types with support for both BI and AI workloads.
* D. Data lakehouse architecture offers the benefits of both data warehouses and data lakes by building a data management and formatting layer on top of an open data lake.

```
C. The data lakehouse architecture provides a unified platform for all data types with support for both BI and AI workloads.
D. Data lakehouse architecture offers the benefits of both data warehouses and data lakes by building a data management and formatting layer on top of an open data lake.

Why:
These describe the core benefits: unifying data types/workloads and combining warehouse/lake advantages.
The other options mention proprietary formats (not true) and focus too much on AI governance, which isn't the main lakehouse benefit.
Databricks leverages Unity Catalog to provide a unified governance layer for all data and AI assets housed within the data ecosystem.
```

---

**2.** How does Databricks support data security and governance across different cloud platforms?
* A. Databricks leverages the existing cloud provider’s security infrastructure to inherit permissions and governance settings directly.
* B. Databricks leverages Unity Catalog to provide a unified governance layer for all data and AI assets housed within the data ecosystem.
* C. Databricks depends on the customer’s preferred or existing data governance tooling in the cloud infrastructure where it is deployed.
* D. Databricks uses multiple data security and governance tools within the platform to support various use cases and data teams in the platform.

```
B. Databricks leverages Unity Catalog to provide a unified governance layer for all data and AI assets housed within the data ecosystem.
```

---

**3.** Which statement describes the role of Unity Catalog within the Databricks Data Intelligence Platform?
* A. Unity Catalog provides a single interface to manage platform-wide permissions, audits, and data sharing for all your data and AI governance needs.
* B. Unity Catalog is a data storage solution for managing all your data and AI assets, including structured, semi-structured, and unstructured data.
* C. Unity Catalog brings together your data with an AI-backed intelligence engine to make AI-assisted data visualization possible.
* D. Unity Catalog is the optimized storage layer that provides the foundation for tables in a lakehouse on Databricks.

```
A. Unity Catalog provides a single interface to manage platform-wide permissions, audits, and data sharing for all your data and AI governance needs.

Why:
This is because Unity Catalog is focused on governance, permissions, and unified access management, not storage or AI engines. The other options are incorrect because they confuse storage, intelligence engines, or storage layers with governance.
```

---

**4.** What are three of the main features and benefits DLT provides to data engineering on Databricks?
* A. Unified batch and streaming support
* B. Automatic infrastructure management
* C. Optimized batch-only processing
* D. A declarative ETL framework
* E. Data visualization tooling
* F. Manual infrastructure fine-tuning support

```
A. Unified batch and streaming support
B. Automatic infrastructure management
D. A declarative ETL framework

Why:
These are core DLT features. The others are not main DLT benefits.
```

---

**5.** What is the mission of Databricks?
* A. To democratize data and AI.
* B. To become the leading data and AI company.
* C. To solve the world's toughest problems with AI.
* D. To build the best cloud storage platform.

```
A. To democratize data and AI.
```

---

**6.** What is the significance of the MosaicML acquisition by Databricks?
* A. It extended Databricks’s support and capabilities into the hardware infrastructure market.
* B. It expanded the cloud storage capabilities of the Databricks lakehouse architecture.
* C. It supported the need for powerful Generative AI models and tools within Databricks.
* D. It enhanced Databricks’s support for data visualization tooling for broader BI support.

```
* C. It supported the need for powerful Generative AI models and tools within Databricks.
```

---

**7.** Which three options are benefits of serverless compute in Databricks?
* A. Simplified user experience
* B. Fine-grained and detailed setup
* C. Improved reliability
* D. Usage cost transparency
* E. Faster scaling

```
A. Simplified user experience
C. Improved reliability
E. Faster scaling
```

---

**8.** What is Delta Sharing, and its primary benefit?
* A. Delta Sharing is a proprietary sharing tool unique to Databricks that leverages Unity Catalog and Delta Lake for seamless sharing.
* B. Delta Sharing is an open, cross-platform sharing tool that allows for the sharing of data without duplication.
* C. Delta Sharing securely connects your data with any AI model to create accurate, domain-specific applications.
* D. Delta Sharing is a data storage solution that provides additional permissions settings to Unity Catalog.

```
B. Delta Sharing is an open, cross-platform sharing tool that allows for the sharing of data without duplication.

Why:
This is correct because Delta Sharing is open, not proprietary, and its main benefit is sharing data securely across platforms without copying. The other options are incorrect or too narrow.
```

---

**9.** What two options describe benefits of integrating AI into the core of the Databricks Platform?
* A. Including AI provides an always available customer service tool within the platform for account questions.
* B. Using AI enhances the user experience with an always-ready AI assistant to support debugging and code enhancement.
* C. Applying AI helps the platform to understand data structure, usage, and meaning, it helps users boost productivity and optimize workloads.
* D. Integrating AI provides additional storage optimization on top of the data housed with the cloud storage provider.

```
B. Using AI enhances the user experience with an always-ready AI assistant to support debugging and code enhancement.
C. Applying AI helps the platform to understand data structure, usage, and meaning, it helps users boost productivity and optimize workloads.
```

---

**10.** What is the purpose of Databricks Assistant?
* A. To manage data storage, to provide financial advice, and to handle hardware issues.
* B. To act as a companion for coding and platform needs throughout the platform UI.
* C. To monitor the overall costs of the platform, divided across multiple
* D. To manage data storage optimization within Delta Lake.

```
B. To act as a companion for coding and platform needs throughout the platform UI.
```

---

**11.** What is the role of AI-generated comments in Databricks?
* A. To automatically generate informative table and column comments, improving search and natural language interfaces.
* B. To provide reliable search results through the addition of ad hoc descriptions in the results page.
* C. To efficiently allow developers to enter comments into their code for easier readability and documentation.
* D. To create data visualizations and provide in-the-moment feedback on the accuracy of those visualizations.

```
A. To automatically generate informative table and column comments, improving search and natural language interfaces.

Why:
This is correct because AI-generated comments in Databricks are mainly for metadata enrichment and better searchability, not for code readability or visualization feedback.
```

---

**12.** What is the primary function of Databricks Notebooks?
* A. Databricks Notebooks provide a space to connect with git repositories to manage CI/CD pipelines.
* B. Databricks Notebooks provide a simple and flexible environment for developing dashboards and visualizations for end users.
* C. Databricks Notebooks provide a flexible interface for creating reusable and manageable dashboards for reporting and BI.
* D. Databricks Notebooks provide a collaborative, reproducible environment for data practitioners with support for multiple languages.

```
D. Databricks Notebooks provide a collaborative, reproducible environment for data practitioners with support for multiple languages.
```

---

**13.** What is the significance of the Well-Architected Lakehouse framework?
* A. It is a proprietary development framework for the Databricks Data Intelligence Platform that builds on the structure of the data lakehouse paradigm introduced in 2020.
* B. It extends the cloud well-architected frameworks to the lakehouse, ensuring operational excellence, security, reliability, performance efficiency, and cost optimization.
* C. It introduces the lakehouse concept as an entirely new architectural paradigm that replaces traditional cloud frameworks and prioritizes data silos for better isolated processing.
* D. It builds on the already existing data storage format and structure of data lakes to provide a more robust and beneficial environment to data practitioners with additional tooling and support functionality.

```
B. It extends the cloud well-architected frameworks to the lakehouse, ensuring operational excellence, security, reliability, performance efficiency, and cost optimization.
```

---

**14.** How does Databricks support non-technical users in gaining insights from data using natural language?
* A. Through AI/BI Genie Spaces and Databricks Assistant, which allow users to interact with data using natural language prompts.
* B. By including one-click connections to data sources that currently exist within the overall data ecosystem for a business.
* C. With the inclusion of both our Databricks blogs and cloud-specific documentation available through Intelligent Search.
* D. By providing coding tutorials and prebuilt notebooks, which allows users to have professionally vetted code available in a single click.

```
A. Through AI/BI Genie Spaces and Databricks Assistant, which allow users to interact with data using natural language prompts.

Why:
This is correct because these tools enable non-technical users to gain insights using plain language, not code or technical steps.
```

---

**15.** What is the primary benefit of Delta Lake's support for ACID transactions?
* A. It increases storage capacity
* B. It speeds up data duplication
* C. It enhances data visualization creation
* D. It ensures data reliability and consistency

```
D. It ensures data reliability and consistency
```

---

**16.** What is the core purpose of Databricks Marketplace?
* A. To provide data assets for training and learning purposes to support Databricks Academy in enabling all users on the platform.
* B. To provide an open marketplace for data, analytics, and AI products, enabling collaboration and monetization.
* C. To provide a curated marketplace of verified, approved, and professionally vetted data and AI assets to be purchased as needed.
* D. To provide a shared data storage solution for collaboration between partners and vendors.

```
B. To provide an open marketplace for data, analytics, and AI products, enabling collaboration and monetization.
```

---

**17.** What is the role of Databricks Lakeflow Jobs?
* A. To manage the cloud platform infrastructure from a single interface within Databricks.
* B. To orchestrate all types of jobs within the platform, providing control flows, triggers, and monitoring.
* C. To deliver data from outside sources into the platform through reliable data pipelines.
* D. To provide a dashboard for monitoring all the costs associated with data flowing in and out of the platform.

```
B. To orchestrate all types of jobs within the platform, providing control flows, triggers, and monitoring.
```

---

**18.** Which three of the following benefits are provided directly by Databricks?
* A. It provides a unified security and governance approach to all data assets
* B. It’s built on open source and open standards
* C. It’s efficient on-premises optimized hardware
* D. It’s available on and across multiple cloud platforms
* E. It provides scalable and redundant cloud-based data storage

```
A. It provides a unified security and governance approach to all data assets
B. It’s built on open source and open standards
D. It’s available on and across multiple cloud platforms
```

---

**19.** Which three of the following features are available within the Databricks Workspace?
* A. Lakeflow Jobs
* B. Catalog Explorer
* C. Metastore management
* D. Notebooks
* E. Account principals

```
A. Lakeflow Jobs
B. Catalog Explorer
D. Notebooks

Why:
These are all available features within the Databricks Workspace. Metastore management and Account principals are managed at the account level, not workspace.
```

---

**20.** Which of the following services or capabilities supports data warehousing capabilities on Databricks
* A. Databricks SQL
* B. Lakehouse Federation
* C. Databricks Workflows
* D. MosaicAI

```
A. Databricks SQL

Why:
Databricks SQL is the core service for data warehousing on Databricks, enabling SQL analytics and BI workloads. The others are unrelated to core warehousing.
```
