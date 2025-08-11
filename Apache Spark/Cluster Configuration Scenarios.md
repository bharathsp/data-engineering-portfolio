# Important Information

**CPU Cores (Hardware level)**

* These are physical or virtual cores on the machines in your cluster.
* Example: If a worker node has 2 CPUs × 8 cores each, that node has 16 CPU cores.
* This is the real hardware your jobs will run on.

**Spark Cores (Spark resource allocation)**

* In Spark, when we talk about “number of cores”, we usually mean:
* How many CPU threads Spark is allowed to use across the cluster.
* This is controlled via executor cores (--executor-cores) × number of executors (--num-executors).
* Spark maps its “cores” to CPU threads, but it’s a logical allocation, not a separate hardware entity.
* Spark can’t use more Spark cores than CPU cores available in the cluster (unless you overcommit in virtualized environments, which can hurt performance).

**Waves**

* In Spark, "waves" refers to how many rounds (batches) of tasks need to run sequentially to process all partitions of your dataset, given the number of available executor cores.
* Spark splits your data into partitions.
* Each partition is processed by one task.
* The number of tasks that can run at the same time is determined by your total available cores (sum of all executor cores).
* If you have more partitions than cores, not all tasks can run at once — they’ll have to be executed in waves.
* If you want 1 wave, your total cores should equal your total partitions (so all partitions run at once).
* If you’re okay with multiple waves, you can use fewer cores — but total job time may increase.

---

# Thumb Rules

Here are some common **thumb rules** that Spark engineers (including me) usually assume when doing cluster configuration sizing:

---

## **📌 Partitioning**

1. **Default partition size:** \~**128 MB** per partition (sometimes 256 MB for large clusters to reduce task scheduling overhead).
2. **#Partitions formula:**

   $$
   \text{Partitions} = \frac{\text{Data size (MB)}}{\text{Partition size (MB)}}
   $$
3. Have **2–4× more partitions than total cores** for good load balancing.
4. Avoid too many small partitions — increases task scheduling overhead.

---

## **📌 Cores per Executor**

5. Recommended: **4–5 cores per executor** for a good balance between parallelism and GC overhead.
6. Never exceed **\~5 cores** unless you know your workload is CPU-bound and GC is tuned well.

---

## **📌 Memory per Executor**

7. **Memory per executor formula:**

Partition size x Cores per executor x Safety factor (2–3×)

   * overhead (≈ 300–500 MB).
8. Keep **executor memory ≤ 32 GB** to avoid Spark switching from “compressed oops” to normal object references (which use more memory).
9. **Heap + Overhead = Total executor memory** (YARN automatically adds overhead unless set manually).

---

## **📌 Total Cores**

10. **Cores = Executors × Cores per executor**.
11. **1 core processes 1 partition at a time** — this is the key driver of waves.
12. For a **1-wave** execution:
* Total cores ≈ Total partitions

For **multi-wave** execution:
* Total cores} ≈ Partitions / waves

---

## **📌 Executor Count**

13. Executors = Total cores ÷ Cores per executor.
14. Keep a couple of cores free for the driver & application master (YARN mode).

---

## **📌 General**

15. **Data locality matters** — having more cores than available local data blocks can cause network shuffling.
16. Always consider **compression factor** — if data is compressed, memory needs post-decompression can be 2–4× higher.
17. Shuffle-heavy jobs (joins, groupBy) require more memory per executor.
18. If caching data, size executors so the dataset fits in memory with safety buffer.

---

# Scenario 1
To process 25GB of data in spark

* a. How many CPU cores are required?
* b. How many executors are required?
* c. How much memory is required for each executor?
* d. What is the total memory required?

---

## **Step 1 – Understanding Spark resource calculation**

When deciding Spark resources, you need:

* **Data size** (25 GB given)
* **Executor memory allocation rule** (leave \~1 GB overhead for Spark/YARN)
* **Number of cores per executor** (usually 4–5 for optimal parallelism)
* **Data-to-memory ratio** (rule of thumb: `2x data size` in memory for shuffle/processing overhead)

---

### **A. Number of CPU Cores**

**Rule:**

* Spark parallelism works best with **\~4 cores per executor**.
* **Number of cores total** ≈ `(Data size / Data per core)` × cores per executor.

We need to know **how much data one core should handle**.
A common guideline is:

> 1 core can comfortably handle **2–3 GB** of in-memory data without becoming a bottleneck.

Let’s assume **2.5 GB per core**:

```
Total cores needed = 25 GB ÷ 2.5 GB = 10 cores
```

✅ **Answer:** **10 CPU cores** (can be split across executors)

---

### **B. Number of Executors**

We don’t want 1 giant executor (bad for fault tolerance), so:

* If each executor has **4 cores**:

```
Executors = Total cores ÷ Cores per executor
Executors = 10 ÷ 4 = 2.5 ≈ 3 executors
```

We’ll slightly over-provision, so **3 executors** is fine.

---

### **C. Memory Required per Executor**

**Rule:**

* Memory per executor = `(Data per executor × Overhead factor)`
* Overhead factor: \~1.2 to 2 (due to shuffle, caching, etc.)
* Also, leave **\~1 GB** for YARN/Mesos overhead.

First, **data per executor**:

```
Data per executor = Total data ÷ Number of executors
= 25 GB ÷ 3 ≈ 8.33 GB
```

Add **2× overhead** for Spark shuffles:

```
8.33 GB × 2 = 16.66 GB
```

Add **1 GB YARN overhead**:

```
16.66 + 1 ≈ 17.66 GB
```

We’ll round up to the nearest GB (and often allocate in even GBs):
✅ **Answer:** **18 GB per executor**

---

### **D. Total Memory Required**

```
Total memory = Memory per executor × Number of executors
= 18 GB × 3 = 54 GB
```

✅ **Answer:** **54 GB total cluster memory**

---

## **Final Spark Resource Plan**

| Parameter                  | Value     | Reason                          |
| -------------------------- | --------- | ------------------------------- |
| **a. CPU cores**           | **10**    | Based on \~2.5 GB/core          |
| **b. Executors**           | **3**     | 4 cores/executor rule           |
| **c. Memory per executor** | **18 GB** | 2× shuffle overhead + 1 GB YARN |
| **d. Total memory**        | **54 GB** | 18 GB × 3 executors             |

---

## **Extra Tip** 🚀

In Spark, this would translate to:

```bash
--num-executors 3 \
--executor-cores 4 \
--executor-memory 18G
```

(Since 3 × 4 cores = 12 cores, a bit more than our minimum 10 cores, giving better parallelism.)
