# ⚡ **Latency vs Throughput**

## ⏱️ **Latency**

* **Definition**: Time taken to complete a **single request** (end-to-end).
* **Unit**: milliseconds (ms), seconds.
* **Focus**: "How fast is one task?"

👉 Example:

* An API responds in **200 ms**.
* A Spark query completes in **5 seconds**.

---

## 📦 **Throughput**

* **Definition**: Number of **requests processed per unit of time**.
* **Unit**: requests/sec, rows/sec, MB/sec.
* **Focus**: "How many tasks per second?"

👉 Example:

* API server handles **10,000 requests per second**.
* Spark job processes **1 million rows per second**.

---

# 🖼️ **Analogy**

Imagine a **restaurant 🍽️**:

* **Latency** = How long it takes a single customer to get their food after ordering.
* **Throughput** = How many customers the restaurant serves per hour.

👉 Fast-food chain (McDonald’s):

* **Low latency** (food ready quickly).
* **High throughput** (serves thousands per hour).

👉 Fine-dining restaurant:

* **High latency** (meal takes long).
* **Low throughput** (few tables served per night).

---

# 📊 **Latency vs Throughput Example in Systems**

* **API Call**:

  * Latency = 120 ms per call.
  * Throughput = 800 requests/sec.

* **Spark Job**:

  * Latency = 10 seconds to finish a query.
  * Throughput = 50,000 rows/sec processed.

---

# ✅ **When to Optimize**

* Optimize **latency** when:

  * User-facing apps (APIs, dashboards).
  * Real-time systems (trading, fraud detection).

* Optimize **throughput** when:

  * Batch processing (ETL pipelines).
  * High data ingestion (IoT, log analytics).

---

# 📌 **Summary**

| Metric         | Meaning                             | Unit              | Focus          | Example             |
| -------------- | ----------------------------------- | ----------------- | -------------- | ------------------- |
| **Latency**    | Time for 1 request                  | ms, sec           | Speed per task | 200 ms API response |
| **Throughput** | Requests processed per unit of time | req/sec, rows/sec | Capacity       | 10k req/sec handled |
