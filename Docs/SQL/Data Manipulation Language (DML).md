## 📊 Data Manipulation Language (DML) in SQL

Data Manipulation Language is a subset of SQL commands used to manage and manipulate data within a database. It includes operations like inserting, updating, deleting, and retrieving data.

---

### 🗂️ List of DML Commands:

#### 🔍 SELECT
**Description:**  
Retrieves data from one or more tables without modifying the data.

**Syntax:**
```sql
SELECT column1, column2
FROM table_name WHERE condition;
```

**Example:**
```sql
SELECT name, age
FROM students WHERE age > 18;
```
*Retrieves the name and age of students from the `students` table where the age is greater than 18.*

---

#### ➕ INSERT
**Description:**  
Adds new records (rows) to a table.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

**Example:**
```sql
INSERT INTO employees (name, department, salary)
VALUES ('Alice', 'Marketing', 50000);
```
*Inserts a new employee into the `employees` table.*

---

#### 📝 UPDATE
**Description:**  
Modifies existing records in a table.

**Syntax:**
```sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;
```

**Example:**
```sql
UPDATE employees
SET salary = 65000
WHERE name = 'John Doe';
```
*Updates the salary of the employee named 'John Doe' in the `employees` table.*

---

#### ❌ DELETE
**Description:**  
Deletes existing records from a table.

**Syntax:**
```sql
DELETE FROM table_name
WHERE condition;
```

**Example:**
```sql
DELETE FROM employees
WHERE department = 'HR';
```
*Deletes all records from the `employees` table where the department is 'HR'.*

---

### 📌 Summary
Data Manipulation Language (DML) commands — `SELECT`, `INSERT`, `UPDATE`, and `DELETE` — are essential for managing and manipulating data within a database. These commands allow users to:
- Retrieve specific information
- Add new records
- Update existing data
- Remove unwanted data

Understanding DML is fundamental for anyone working with databases, as it provides the tools to interact with and modify data effectively.

