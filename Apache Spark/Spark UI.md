The **Spark UI** is a **web-based interface** that lets you monitor and debug your Spark applications in real time or after they finish running.

Think of it like Spark’s **“mission control dashboard”** — it shows you what’s happening inside your job:

* Which stages and tasks are running
* How much time each took
* Memory, CPU, and shuffle data usage
* Any errors or slowdowns

---

## **1️⃣ Where to Access It**

* **Local mode:** By default at `http://localhost:4040` while your app runs.
* **Cluster mode:** Accessed through the Spark master’s URL or your cluster manager (YARN, Kubernetes, Databricks, etc.).
* After the job ends, it’s available in **Spark History Server** (if enabled).

---

## **2️⃣ Key Tabs in Spark UI**

| **Tab**         | **What It Shows**                                                                  |
| --------------- | ---------------------------------------------------------------------------------- |
| **Jobs**        | High-level list of Spark jobs with status, duration, and links to stages.          |
| **Stages**      | Breakdown of each job into stages; shows task counts, shuffle read/write, GC time. |
| **Tasks**       | Details per task (executor ID, duration, input size, errors).                      |
| **Storage**     | RDD/DataFrame caching info (size, partitions).                                     |
| **Environment** | Spark configuration, JVM settings, classpath info.                                 |
| **Executors**   | Memory and CPU usage per executor; task success/failure rates.                     |
| **SQL**         | (For Spark SQL) Logical and physical query plans, execution time, metrics.         |

---

## **3️⃣ Why It’s Useful**

* **Debugging**: Find slow stages, skewed data, or failed tasks.
* **Performance tuning**: See if jobs are waiting on shuffle, spilling to disk, or running out of memory.
* **Memory monitoring**: Track GC time, storage usage, executor memory pressure.
* **Execution tracing**: View DAG (Directed Acyclic Graph) visualization of transformations.

---

## **4️⃣ Example Workflow**

Let’s say your Spark job is slow:

1. Open Spark UI → **Jobs tab** → Identify the slow job.
2. Click into **Stages** → See if one stage is much slower.
3. Check **Tasks** → Maybe one task took 2 minutes while others took 5 seconds (data skew!).
4. Look at **Executors** → Some executors might be idle while others are overloaded.
5. Tune partitioning, memory, or parallelism accordingly.

---

💡 In short — **Spark UI is your real-time X-ray machine for Spark jobs**. Without it, tuning performance or finding bottlenecks is like driving at night with no headlights.

---

# Apache Spark Docs

https://spark.apache.org/docs/latest/web-ui.html

Apache Spark provides a suite of web user interfaces (UIs) that you can use to monitor the status and resource consumption of your Spark cluster.

Here’s your **Jobs Tab** section rewritten with icons for better readability:

---

## 📊 **Jobs Tab**

The **Jobs** tab provides two key views:

* **📋 Summary Page** – Shows high-level info like status, duration, progress of all jobs, and an overall event timeline.
* **🔍 Details Page** – Opens when you click a job, displaying the event timeline, DAG visualization, and all stages for that specific job.

---

### **📌 Information Displayed**

* 👤 **User** – Current Spark user
* ⏰ **Started At** – Startup time of the Spark application
* ⏳ **Total Uptime** – Time since the Spark application started
* 🗂 **Scheduling Mode** – Job scheduling strategy used
* 📈 **Number of Jobs (by Status)**:

  * 🟢 **Active**
  * ✅ **Completed**
  * 🔴 **Failed**

<img width="230" height="191" alt="image" src="https://github.com/user-attachments/assets/6eb47f7d-9d47-4e8a-a5cf-336e58c65fa2" />



* Event timeline: Displays in chronological order the events related to the executors (added, removed) and the jobs

<img width="1920" height="521" alt="image" src="https://github.com/user-attachments/assets/80d6d0ab-945e-4b43-b0b7-41d4c85e618c" />



* Details of jobs grouped by status: Displays detailed information of the jobs including Job ID, description (with a link to detailed job page), submitted time, duration, stages summary and tasks progress bar

<img width="1328" height="496" alt="image" src="https://github.com/user-attachments/assets/c4f3671a-c291-48d6-997b-b5c5e83c7a97" />



* When you click on a specific job, you can see the detailed information of this job.

---

### 🔎 **Jobs Detail**

This page shows details for a specific job identified by its **Job ID**.

---

### **📌 Job Information**

* 🚦 **Job Status** – `Running` | `Succeeded` | `Failed`
* 📊 **Number of Stages (by Status)** – `Active` | `Pending` | `Completed` | `Skipped` | `Failed`
* 📝 **Associated SQL Query** – Link to the **SQL** tab for this job
* 🕒 **Event Timeline** – Chronological list of events related to:
  * ⚙ **Executors** – Added / Removed
  * 📦 **Stages** – Submitted / Completed / Failed

<img width="1431" height="479" alt="image" src="https://github.com/user-attachments/assets/1822036f-0ddf-4bd0-b0ec-24dff5cfc630" />

---

### **📈 DAG Visualization**

* 🗺 **Representation** – Directed Acyclic Graph where:

  * 🔵 **Vertices** = RDDs or DataFrames
  * 🔗 **Edges** = Operations applied on RDDs
* 🧮 **Example** – `sc.parallelize(1 to 100).toDF.count()`

<img width="569" height="522" alt="image" src="https://github.com/user-attachments/assets/4dbeb741-5a13-4e17-91db-1defbfa62efe" />

---

### **📋 List of Stages** *(Grouped by State)*

`Active` | `Pending` | `Completed` | `Skipped` | `Failed`

For each stage:

* 🆔 **Stage ID**
* 📝 **Description**
* 📅 **Submitted Timestamp**
* ⏳ **Duration**
* 📊 **Tasks Progress Bar**
* 📥 **Input** – Bytes read from storage in this stage
* 📤 **Output** – Bytes written to storage in this stage
* 🔄 **Shuffle Read** – Total shuffle bytes & records read (local + remote)
* 🔀 **Shuffle Write** – Bytes & records written to disk for a future shuffle stage

<img width="1356" height="235" alt="image" src="https://github.com/user-attachments/assets/d1801dd3-eb50-45ed-be46-a9102dc0d814" />

---

## 🎯 **Stages Tab**

The **Stages** tab displays the current state of all stages from all jobs in the Spark application.

---

### **📌 Summary View**

* 📊 **Stage Counts (by Status)** – `Active` | `Pending` | `Completed` | `Skipped` | `Failed`

<img width="332" height="159" alt="image" src="https://github.com/user-attachments/assets/99b59dfc-def4-4231-a77b-09c6152c7afd" />

* 🗂 **Fair Scheduling Mode** – Displays **Pool Properties** table

<img width="1348" height="184" alt="image" src="https://github.com/user-attachments/assets/e66032ab-664c-4429-b61d-d7eb2337e7ad" />

* 🔍 **Stages per Status** – Detailed stage lists by state:
  * In **Active** stages ➡️ Can **Kill** stage via link
  * In **Failed** stages ➡️ Failure reason is displayed
  * Click stage **Description** ➡️ Opens task details

<img width="1323" height="550" alt="image" src="https://github.com/user-attachments/assets/71578dc9-8d24-46cd-9366-871a6ca5ec52" />

---

### **📄 Stage Detail View**

#### **🆔 Stage Header**

* ⏳ **Total Time Across All Tasks**
* 🌍 **Locality Level Summary**
* 🔄 **Shuffle Read Size / Records**
* 🔗 **Associated Job IDs**

<img width="441" height="178" alt="image" src="https://github.com/user-attachments/assets/13e4cf67-6cc6-4d48-8694-6c010655eb0a" />

---

#### **📈 DAG Visualization**

* 🔵 **Vertices** – Represent RDDs or DataFrames
* 🔗 **Edges** – Operations applied on RDDs
* 📦 **Node Grouping** – By operation scope (e.g., `BatchScan`, `WholeStageCodegen`, `Exchange`)
* 🏷 **Annotations** – Whole Stage Code Generation ops include **Codegen ID**
* 🔍 **Cross-Reference** – SQL/DataFrame stages link to SQL Tab’s execution plans

<img width="562" height="661" alt="image" src="https://github.com/user-attachments/assets/ce9e297a-2255-4349-b784-1323b9faa0a2" />

---

### **📊 Stage Metrics Summary**

* 🕵 **Tasks Deserialization Time** – Time to deserialize task
* ⏱ **Duration** – Total execution time of tasks
* 🗑 **GC Time** – Total JVM Garbage Collection time
* 📦 **Result Serialization Time** – Time spent serializing task result before sending to driver
* 📤 **Getting Result Time** – Time driver spends fetching results from workers
* ⏳ **Scheduler Delay** – Wait time before task execution
* 🧠 **Peak Execution Memory** – Max memory used during shuffles, aggregations, joins
* 📥 **Shuffle Read Size / Records** – Includes local + remote reads
* ⏳ **Shuffle Read Fetch Wait Time** – Time blocked waiting for shuffle data from remote executors
* 🌐 **Shuffle Remote Reads** – Bytes read from remote executors
* 📤 **Shuffle Write Time** – Time spent writing shuffle data
* 💾 **Shuffle Spill (Memory)** – Deserialized shuffle data size in memory
* 💿 **Shuffle Spill (Disk)** – Serialized shuffle data size on disk

<img width="1907" height="865" alt="image" src="https://github.com/user-attachments/assets/cca04c1f-90ba-4f5e-a387-4a6209b5e97f" />

---

### **📊 Aggregated Metrics by Executor**

Shows same metrics as above but aggregated **per executor**.

<img width="1332" height="176" alt="image" src="https://github.com/user-attachments/assets/90793eda-5d70-4eaa-98f6-012eac11a472" />

---

### **📦 Accumulators**

* 🔄 Shared variables updated inside transformations
* 🏷 Only **Named Accumulators** are displayed in UI

<img width="1334" height="140" alt="image" src="https://github.com/user-attachments/assets/44b738fb-9319-4735-8a97-4403f9f32dde" />

---

### **📝 Task Details**

* Displays same metrics as summary but **per task**
* 📜 Includes **Log Links** and **Task Attempt Number** (on failure)
* 📊 Shows **Accumulator Value** at end of each task (if named)

<img width="1328" height="300" alt="image" src="https://github.com/user-attachments/assets/18351c52-bfaa-45e6-bf0f-e3ba45265c2b" />

---

## 💾 **Storage Tab**

The **Storage** tab displays the **persisted** `RDDs` and `DataFrames` in the Spark application.

---

### **📌 Summary View**

* 📦 **Storage Level** – e.g., `MEMORY_ONLY`, `MEMORY_ONLY_SER`, `DISK_ONLY`
* 🧮 **Number of Partitions**
* 📏 **Size** – Total memory/disk usage
* 💡 **Note** – Newly persisted RDDs/DataFrames **will not appear** until they are **materialized** via an **action** (e.g., `.count()`, `.collect()`)

---

### **📜 Example**

```scala
scala> import org.apache.spark.storage.StorageLevel._
import org.apache.spark.storage.StorageLevel._

scala> val rdd = sc.range(0, 100, 1, 5).setName("rdd")
rdd: org.apache.spark.rdd.RDD[Long] = rdd MapPartitionsRDD[1] at range at <console>:27

scala> rdd.persist(MEMORY_ONLY_SER)
res0: rdd.type = rdd MapPartitionsRDD[1] at range at <console>:27

scala> rdd.count
res1: Long = 100

scala> val df = Seq((1, "andy"), (2, "bob"), (2, "andy")).toDF("count", "name")
df: org.apache.spark.sql.DataFrame = [count: int, name: string]

scala> df.persist(DISK_ONLY)
res2: df.type = [count: int, name: string]

scala> df.count
res3: Long = 3
```

📊 **Result** – After running this code, the Storage tab will list:

1. **RDD: `rdd`** – Persisted in `MEMORY_ONLY_SER`
2. **DataFrame: `df`** – Persisted in `DISK_ONLY`

<img width="1892" height="210" alt="image" src="https://github.com/user-attachments/assets/89eb0431-7f0c-4d56-89e6-cd78dd8e7b9c" />

---

### **📄 Detail View**

When you click an RDD/DataFrame name (e.g., **`rdd`**), you see:

* 📍 **Data Distribution** across the cluster
* ⚙ **Executors** storing each partition
* 📏 **Partition Sizes**
* 💾 **Memory/Disk Overhead** per partition

<img width="1900" height="605" alt="image" src="https://github.com/user-attachments/assets/eb9af63f-41d3-4be9-9a3f-f80715a093f3" />

---

## ⚙ **Environment Tab**

The **Environment** tab displays values for various **environment** and **configuration variables**, including **JVM**, **Spark**, and **system properties**. It is useful for verifying if your properties are set correctly.

---

<img width="1880" height="843" alt="image" src="https://github.com/user-attachments/assets/6dc50491-8b11-4014-aae5-840a84ab5a7b" />

### **📌 Sections in Environment Tab**

1. 🏃 **Runtime Information**

   * Versions of **Java**, **Scala**, and other runtime details

2. 🚀 **Spark Properties**

   * Application settings such as:

     * `spark.app.name`
     * `spark.driver.memory`
   * ⚠ Properties with prefix `spark.hadoop.*` are shown **here**, not in Hadoop Properties

3. 🗂 **Hadoop Properties** *(clickable link)*

   * Shows properties related to **Hadoop** and **YARN**

<img width="1228" height="389" alt="image" src="https://github.com/user-attachments/assets/f4a958c6-b7a9-499e-97c9-3abc79fd78ae" />

4. 🖥 **System Properties**

   * Detailed **JVM** properties

<img width="1167" height="330" alt="image" src="https://github.com/user-attachments/assets/81fc067e-a4ee-47e8-bd08-1b92fbd38702" />

5. 📚 **Classpath Entries**

   * Lists all loaded classes and their sources
   * 🔍 Useful for **debugging class conflicts**

<img width="1079" height="213" alt="image" src="https://github.com/user-attachments/assets/4e0165ab-48c2-49c2-86a4-93b12c52a56f" />

---

## 🛠 **Executors Tab**

The **Executors** tab displays **summary information** about all executors created for the Spark application, including **memory/disk usage**, **task statistics**, and **shuffle metrics**.

<img width="2466" height="1354" alt="image" src="https://github.com/user-attachments/assets/abf86b1b-06f2-480b-830b-d957b67a9dc4" />

---

### **📌 Information Displayed**

* 💾 **Storage Memory** – Memory used & reserved for caching data
* 🧮 **Resource Usage** – Memory, disk, and cores used by each executor
* 📊 **Performance Metrics** – GC time, shuffle read/write statistics

---

### **🔍 Additional Tools**

* 📜 **Stderr Log**

  * Clicking the **`stderr`** link for **executor 0** opens its **standard error log** in the console

<img width="2510" height="964" alt="image" src="https://github.com/user-attachments/assets/856b6ee6-7105-44f3-ac7f-44ad8e0b0296" />

* 🧵 **Thread Dump**

  * Clicking the **`Thread Dump`** link for **executor 0** shows the **JVM thread dump** for that executor
  * 🛠 Useful for **performance troubleshooting** and identifying blocked threads

<img width="997" height="563" alt="image" src="https://github.com/user-attachments/assets/98489aba-ba15-4f72-ab6d-c31885aafd50" />

---

Here’s your **SQL Tab** section rewritten with icons and consistent formatting so it matches the previous Spark UI tab descriptions:

---

## 🗄 **SQL Tab**

The **SQL** tab appears when the application executes **Spark SQL queries**. It provides details about **query execution time**, **jobs**, and **plans** (logical & physical) along with the **execution DAG**.

---

### **📌 Example**

```scala
val df = Seq((1, "andy"), (2, "bob"), (2, "andy")).toDF("count", "name")
df.count
df.createGlobalTempView("df")

spark.sql("select name, sum(count) from global_temp.df group by name").show
```

📊 After running the above, the SQL tab lists the **three DataFrame/SQL operations**.
Clicking **`show at <console>: 24`** for the last query opens its **DAG** and **execution details**.

---

### **📈 Query Details Page**

* ⏱ **Execution Time & Duration**
* 🔗 **Associated Jobs**
* 🗺 **SQL Execution DAG** – Blocks represent execution stages:

  * 🧮 **WholeStageCodegen (1)** – Combines multiple operators (e.g., `LocalTableScan`, `HashAggregate`) into a single compiled Java function for performance

    * Metrics: **Number of Rows**, **Spill Size**
    * `(1)` = Code generation ID
  * 🔀 **Exchange** – Shows shuffle metrics such as written records & data size

---

### **🛠 Logical & Physical Plans**

* 📜 **Logical Plan** – Shows how Spark parses & optimizes the query
* ⚙ **Physical Plan** – Shows execution steps; whole-stage codegen steps are prefixed with `*(ID)`

  * Example: `*(1) LocalTableScan`

---

### **📊 SQL Metrics Overview**

SQL metrics are shown in the **physical operator blocks** and help in analyzing execution:

| 📏 Metric                                | 📝 Meaning                                 | 🛠 Operators                                 |
| ---------------------------------------- | ------------------------------------------ | -------------------------------------------- |
| 📄 **Number of Output Rows**             | Rows produced by operator                  | Aggregate, Join, Filter, Scan, etc.          |
| 📦 **Data Size**                         | Size of broadcast/shuffled/collected data  | BroadcastExchange, ShuffleExchange, Subquery |
| ⏱ **Time to Collect**                    | Time to gather data                        | BroadcastExchange, Subquery                  |
| 🔍 **Scan Time**                         | Time spent scanning data                   | ColumnarBatchScan, FileSourceScan            |
| 🗂 **Metadata Time**                     | Time fetching metadata (partitions, files) | FileSourceScan                               |
| 📤 **Shuffle Bytes Written**             | Bytes written during shuffle               | CollectLimit, ShuffleExchange                |
| 📝 **Shuffle Records Written**           | Records written during shuffle             | CollectLimit, ShuffleExchange                |
| ⏳ **Shuffle Write Time**                 | Time writing shuffle data                  | CollectLimit, ShuffleExchange                |
| 📦 **Remote Blocks Read**                | Blocks read from remote                    | CollectLimit, ShuffleExchange                |
| 🌐 **Remote Bytes Read**                 | Bytes read from remote                     | CollectLimit, ShuffleExchange                |
| 💾 **Remote Bytes Read to Disk**         | Bytes moved from remote to local disk      | CollectLimit, ShuffleExchange                |
| 📥 **Local Blocks Read**                 | Blocks read locally                        | CollectLimit, ShuffleExchange                |
| 📏 **Local Bytes Read**                  | Bytes read locally                         | CollectLimit, ShuffleExchange                |
| ⏳ **Fetch Wait Time**                    | Time waiting for data fetch                | CollectLimit, ShuffleExchange                |
| 📊 **Records Read**                      | Number of records read                     | CollectLimit, ShuffleExchange                |
| ⏱ **Sort Time**                          | Time sorting data                          | Sort                                         |
| 🧠 **Peak Memory**                       | Max memory used                            | Sort, HashAggregate                          |
| 💿 **Spill Size**                        | Data spilled to disk                       | Sort, HashAggregate                          |
| 🛠 **Time in Aggregation Build**         | Time building aggregation hash             | HashAggregate                                |
| 🔍 **Avg Hash Probe Bucket List Iters**  | Avg bucket list iterations during probe    | HashAggregate                                |
| 📦 **Data Size of Build Side**           | Size of built hash map                     | ShuffledHashJoin                             |
| ⏳ **Time to Build Hash Map**             | Time building hash map                     | ShuffledHashJoin                             |
| 📝 **Task Commit Time**                  | Time committing task output                | File-based writes                            |
| 📜 **Job Commit Time**                   | Time committing job output                 | File-based writes                            |
| 📤 **Data Sent to Python Workers**       | Bytes sent to Python worker                | Python UDFs, Pandas API                      |
| 📥 **Data Returned from Python Workers** | Bytes returned from Python worker          | Python UDFs, Pandas API                      |

---
