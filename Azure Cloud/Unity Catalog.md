## Unity Catalog

**Unity Catalog** is a unified **data governance and cataloging** solution developed by **Databricks**. It provides a **centralized system** for managing **metadata, access control, auditing**, and **data lineage** across all **workspaces and data assets** (e.g., tables, files, machine learning models, etc.) in the **Databricks Lakehouse Platform**.

---

### 🔑 **Key Features of Unity Catalog:**

1. **Centralized Metadata Management**

   * Stores metadata (schemas, tables, views, etc.) in one place.
   * Shared across multiple Databricks workspaces.

2. **Fine-Grained Access Control**

   * Implements access at the **table**, **column**, or **row level**.
   * Uses standard SQL `GRANT` and `REVOKE` commands.

3. **Data Lineage**

   * Automatically tracks how data flows from one table to another.
   * Helps in understanding transformations and auditing.

4. **Unified Governance**

   * Governs structured (tables), semi-structured (JSON, Parquet), and unstructured (images, PDFs) data across clouds.
   * Enforces consistent policies across AWS, Azure, and GCP.

5. **Audit Logging**

   * Tracks who accessed what data and when.
   * Useful for compliance and security.

6. **Support for External Locations and Volumes**

   * Manages access to data stored in external locations like S3, ADLS, and GCS.

---

### 🏗️ **Logical Hierarchy in Unity Catalog:**

```
Metastore (1 per region per cloud account)
  └── Catalog
        └── Schema (Database)
              └── Table / View / Function
```

---

### 🛡️ **Why Use Unity Catalog?**

| Feature             | Traditional Workspaces | Unity Catalog                 |
| ------------------- | ---------------------- | ----------------------------- |
| Access Control      | Workspace-scoped       | Cross-workspace, fine-grained |
| Data Governance     | Manual & fragmented    | Centralized & consistent      |
| Data Lineage        | Limited or external    | Built-in & automatic          |
| Multi-cloud Support | Per-cloud              | Unified across clouds         |
| Scalability         | Limited by workspace   | Enterprise-wide               |

---

### 🧠 Example SQL for Access Control:

```sql
-- Grant select on a table
GRANT SELECT ON TABLE catalog_name.schema_name.table_name TO `user@example.com`;

-- Revoke access
REVOKE SELECT ON TABLE catalog_name.schema_name.table_name FROM `user@example.com`;
```

---

### ✅ Use Cases:

* Enforcing **data security** and **privacy policies**.
* Supporting **multi-tenant** and **multi-cloud** architectures.
* Enabling **collaboration** across data science, engineering, and analytics teams.
