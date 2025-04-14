# 📘 Data Definition Language (DDL)

Data Definition Language (DDL) is a set of SQL commands used to define, modify, and manage the structure of database objects such as tables, indexes, and constraints.

---

## 🛠️ List of DDL Commands
- **CREATE**
- **ALTER**
- **DROP**
- **TRUNCATE**

---

### 🆕 CREATE
**Description:**
Creates a new database object like a table, index, view, etc.

**Syntax:**
```sql
CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  ...
);
```

**Example:**
```sql
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  department VARCHAR(50)
);
```
Creates a table named `employees` with columns `id`, `name`, and `department`.

---

### ✏️ ALTER
**Description:**
Modifies an existing database object.

**Syntax:**
```sql
ALTER TABLE table_name
ADD column_name datatype;
```

**Example:**
```sql
ALTER TABLE employees
ADD salary DECIMAL(10,2);
```
Adds a new column `salary` to the `employees` table.

---

### ❌ DROP
**Description:**
Deletes an existing database object.

**Syntax:**
```sql
DROP TABLE table_name;
```

**Example:**
```sql
DROP TABLE employees;
```
Deletes the `employees` table and all its data.

---

### 🧹 TRUNCATE
**Description:**
Deletes all rows from a table without deleting the table structure.

**Syntax:**
```sql
TRUNCATE TABLE table_name;
```

**Example:**
```sql
TRUNCATE TABLE employees;
```
Removes all data from the `employees` table, but keeps the table structure intact.

---

## 📌 Summary
DDL commands are essential for defining and managing the structure of database objects. These commands allow users to create, modify, and delete tables, indexes, views, and other database elements, shaping how data is stored and accessed within a database system.

Understanding DDL is crucial for anyone working with databases, as it provides the foundational tools for database design and management.
