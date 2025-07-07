## **PySpark SQL functions**

---

### 📌 1. `col()`

**Description**: Refers to a column in a DataFrame; used for transformations.

**Syntax**:

```python
from pyspark.sql.functions import col
df.select(col("column_name"))
```

**Example**:
Input:

```python
+-------+-----+
| Name  | Age |
+-------+-----+
| Alice | 30  |
| Bob   | 25  |
+-------+-----+
```

Code:

```python
df.select(col("Name")).show()
```

Output:

```python
+-------+
|  Name |
+-------+
| Alice |
|  Bob  |
+-------+
```

---

### 📌 2. `lit()`

**Description**: Adds a constant/literal value as a new column.

**Syntax**:

```python
from pyspark.sql.functions import lit
df.withColumn("Country", lit("India"))
```

**Example**:
Input:

```python
+-----+
| Name|
+-----+
| John|
+-----+
```

Output:

```python
+-----+--------+
| Name| Country|
+-----+--------+
| John|  India |
+-----+--------+
```

---

### 📌 3. `when()`, `otherwise()`

**Description**: Used for conditional logic similar to if-else.

**Syntax**:

```python
from pyspark.sql.functions import when, col
df.withColumn("Status", when(col("Age") >= 18, "Adult").otherwise("Minor"))
```

**Example**:
Input:

```python
+-------+-----+
| Name  | Age |
+-------+-----+
| Alice | 30  |
| Bob   | 15  |
+-------+-----+
```

Output:

```python
+-------+-----+--------+
| Name  | Age | Status |
+-------+-----+--------+
| Alice | 30  | Adult  |
| Bob   | 15  | Minor  |
+-------+-----+--------+
```

---

### 📌 4. `sum()`, `avg()`, `count()`, `max()`, `min()`

**Description**: Aggregation functions.

**Syntax**:

```python
from pyspark.sql.functions import sum, avg, count, max, min
df.groupBy("Department").agg(sum("Salary"), avg("Salary"))
```

**Example**:
Input:

```python
+----------+------+
|Department|Salary|
+----------+------+
|   IT     | 5000 |
|   IT     | 7000 |
+----------+------+
```

Output:

```python
+----------+-----------+-----------+
|Department|sum(Salary)|avg(Salary)|
+----------+-----------+-----------+
|   IT     | 12000     | 6000.0    |
+----------+-----------+-----------+
```

---

### 📌 5. `lower()`, `upper()`

**Description**: Converts string column values to lowercase or uppercase.

**Syntax**:

```python
from pyspark.sql.functions import lower, upper
df.withColumn("LowerName", lower(col("Name")))
```

**Example**:
Input:

```python
+-------+
| Name  |
+-------+
| Alice |
+-------+
```

Output:

```python
+-------+----------+
| Name  |LowerName |
+-------+----------+
| Alice |  alice   |
+-------+----------+
```

---

### 📌 6. `regexp_replace()`

**Description**: Replaces substrings in a column using a regex.

**Syntax**:

```python
from pyspark.sql.functions import regexp_replace
df.withColumn("Cleaned", regexp_replace(col("Text"), "[^a-zA-Z ]", ""))
```

**Example**:
Input:

```python
+---------------+
|     Text      |
+---------------+
| Hello, World! |
+---------------+
```

Output:

```python
+---------------+-----------+
|     Text      |  Cleaned  |
+---------------+-----------+
| Hello, World! | Hello World |
+---------------+-----------+
```

---

### 📌 7. `concat()`, `concat_ws()`

**Description**: Concatenates multiple columns (with or without separator).

**Syntax**:

```python
from pyspark.sql.functions import concat, concat_ws
df.withColumn("FullName", concat_ws(" ", col("First"), col("Last")))
```

**Example**:
Input:

```python
+-------+--------+
| First |  Last  |
+-------+--------+
| John  |  Doe   |
+-------+--------+
```

Output:

```python
+-------+--------+-----------+
| First |  Last  | FullName  |
+-------+--------+-----------+
| John  |  Doe   | John Doe  |
+-------+--------+-----------+
```

---

### 📌 8. `year()`, `month()`, `dayofmonth()`

**Description**: Extract year, month, or day from date column.

**Syntax**:

```python
from pyspark.sql.functions import year, month, dayofmonth
df.withColumn("Year", year(col("Date")))
```

**Example**:
Input:

```python
+----------+
|   Date   |
+----------+
|2023-05-12|
+----------+
```

Output:

```python
+----------+------+
|   Date   | Year |
+----------+------+
|2023-05-12| 2023 |
+----------+------+
```

---

### 📌 9. `to_date()`, `date_format()`

**Description**:

* `to_date()`: Converts string to DateType.
* `date_format()`: Formats a date column into a string.

**Syntax**:

```python
from pyspark.sql.functions import to_date, date_format
df.withColumn("Formatted", date_format(to_date(col("Date")), "MMM-yyyy"))
```

**Example**:
Input:

```python
+-------------+
|     Date    |
+-------------+
| 12-05-2023  |
+-------------+
```

Output:

```python
+-------------+-----------+
|     Date    | Formatted |
+-------------+-----------+
| 12-05-2023  | May-2023  |
+-------------+-----------+
```

---

### 📌 10. `isnull()`, `isnotnull()`

**Description**: Used to filter or identify null values.

**Syntax**:

```python
from pyspark.sql.functions import col
df.filter(col("Age").isNull())
```

**Example**:
Input:

```python
+-----+-----+
|Name | Age |
+-----+-----+
|John | 25  |
|Jane |null |
+-----+-----+
```

Output:

```python
+-----+-----+
|Name | Age |
+-----+-----+
|Jane |null |
+-----+-----+
```

---

### 📌 11. `explode()`

**Description**: Converts array or map column into multiple rows (flattens the array).

**Syntax**:

```python
from pyspark.sql.functions import explode
df.withColumn("Hobby", explode(col("Hobbies")))
```

**Example**:
Input:

```python
+--------+--------------------+
|  Name  |      Hobbies       |
+--------+--------------------+
| Alice  | ["Reading", "Swim"]|
+--------+--------------------+
```

Output:

```python
+--------+--------+
|  Name  | Hobby  |
+--------+--------+
| Alice  |Reading |
| Alice  | Swim   |
+--------+--------+
```

---
