Got you Dev — I’ll make **super clean, fully detailed SQL notes**, with **simple English**, **examples**, and **syntax for every topic**.
This will be long and perfect for your exam + interview prep.
Let’s begin.

---

# **SQL NOTES (Clear, Detailed & Example-Rich)**

---

# **5. STRUCTURED QUERY LANGUAGE (SQL)**

---

# **A. SQL FUNDAMENTALS REFRESHER**

---

## **1. What is SQL?**

SQL stands for **Structured Query Language**.
It is used to **store**, **manage**, **manipulate**, and **retrieve** data from relational databases.

SQL is divided into several sub-languages:

### **DDL – Data Definition Language**

Used to **define** or **change** the structure of database objects.
Examples:

* `CREATE`
* `ALTER`
* `DROP`
* `TRUNCATE`

### **DML – Data Manipulation Language**

Used to **insert, update, delete** actual data.

* `INSERT`
* `UPDATE`
* `DELETE`

### **DCL – Data Control Language**

Controls **permissions** and **security**.

* `GRANT`
* `REVOKE`

### **TCL – Transaction Control Language**

Controls **transactions** (all-or-nothing operations).

* `COMMIT`
* `ROLLBACK`
* `SAVEPOINT`

---

## **2. Case Sensitivity & Syntax Rules**

* SQL **keywords are NOT case sensitive**:
  `SELECT` = `select` = `SeLeCt`
* Table names & column names **may be case sensitive depending on the DB**.
* Strings are written inside quotes:

  ```sql
  WHERE name = 'Dev';
  ```
* Statements usually end with **semicolon `;`**.

---

## **3. Schema vs Database vs Table**

### **Database**

A collection of schemas, tables, views, and other objects.

### **Schema**

A logical group of database objects (tables, views, procedures).

Example:
Schema = folder
Database = hard drive

### **Table**

A structure with **rows and columns** storing actual data.

---

## **4. SQL Data Types**

Common data types:

| Type                   | Meaning                | Example                 |
| ---------------------- | ---------------------- | ----------------------- |
| **CHAR(n)**            | Fixed-length string    | `'ABC'`                 |
| **VARCHAR(n)**         | Variable-length string | `'Hello'`               |
| **INT / INTEGER**      | Whole numbers          | `24`                    |
| **DECIMAL(p,s)**       | Exact numeric          | `DECIMAL(10,2)`         |
| **FLOAT/DOUBLE**       | Approx numeric         | `23.567`                |
| **DATE**               | YYYY-MM-DD             | `'2024-05-12'`          |
| **TIME**               | Time of day            | `'14:23:55'`            |
| **DATETIME/TIMESTAMP** | Date + time            | `'2024-05-12 14:23:55'` |
| **BOOLEAN**            | TRUE/FALSE             | `TRUE`                  |

---

# **B. DATA DEFINITION LANGUAGE (DDL)**

---

## **1. CREATE TABLE**

Creates a new table.

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```

---

## **2. ALTER TABLE**

Modify existing table.

### **Add column**

```sql
ALTER TABLE students ADD email VARCHAR(100);
```

### **Modify column**

```sql
ALTER TABLE students MODIFY age DECIMAL(3,0);
```

### **Drop column**

```sql
ALTER TABLE students DROP COLUMN email;
```

---

## **3. DROP TABLE**

Deletes the table permanently (structure + data).

```sql
DROP TABLE students;
```

---

## **4. TRUNCATE TABLE**

Deletes all rows but **keeps the structure**.

```sql
TRUNCATE TABLE students;
```

---

## **5. CREATE DATABASE**

```sql
CREATE DATABASE collegeDB;
```

## **6. USE DATABASE**

```sql
USE collegeDB;
```

---

## **7. Constraints**

Constraints protect the **quality, uniqueness, and rules** of data.

### **PRIMARY KEY**

Uniquely identifies each row.

```sql
id INT PRIMARY KEY
```

### **FOREIGN KEY**

Links one table to another.

```sql
FOREIGN KEY (dept_id) REFERENCES department(id)
```

### **UNIQUE**

Value must be different in every row.

### **NOT NULL**

Column cannot be empty.

### **DEFAULT**

Sets automatic value.

```sql
status VARCHAR(20) DEFAULT 'active'
```

### **CHECK**

Adds a condition.

```sql
CHECK (age >= 18)
```

---

## **8. Cascading Options**

### **ON DELETE CASCADE**

If parent is deleted → delete child rows.

### **ON UPDATE SET NULL**

If parent key changes → set child key NULL.

Example:

```sql
FOREIGN KEY(dept_id)
REFERENCES department(id)
ON DELETE CASCADE
ON UPDATE SET NULL;
```

---

## **9. CREATE INDEX**

Makes searching faster.

```sql
CREATE INDEX idx_name ON students(name);
```

---

## **10. DROP INDEX**

```sql
DROP INDEX idx_name;
```

---

# **C. DATA MANIPULATION LANGUAGE (DML)**

---

## **1. INSERT (single row)**

```sql
INSERT INTO students (id, name, age)
VALUES (1, 'Dev', 22);
```

## **INSERT (multiple rows)**

```sql
INSERT INTO students VALUES 
(2, 'Amit', 21),
(3, 'Sara', 23);
```

## **INSERT INTO … SELECT**

Copy data from one table to another.

```sql
INSERT INTO backup_students(id, name)
SELECT id, name FROM students;
```

---

## **2. UPDATE**

### **Single column**

```sql
UPDATE students
SET age = 25
WHERE id = 1;
```

### **Multiple columns**

```sql
UPDATE students
SET name = 'Dev A', age = 23
WHERE id = 1;
```

---

## **3. DELETE**

### **With WHERE**

```sql
DELETE FROM students WHERE id = 2;
```

### **Without WHERE (dangerous!)**

```sql
DELETE FROM students;
```

---

## **4. Bulk Insert / Copy**

DB-specific commands:

**MySQL**

```sql
LOAD DATA INFILE 'data.csv'
INTO TABLE students
FIELDS TERMINATED BY ',';
```

**PostgreSQL**

```sql
COPY students FROM '/path/data.csv' CSV;
```

---

# **D. DATA QUERY LANGUAGE (DQL)**

---

# **1. BASIC QUERIES**

## **SELECT**

```sql
SELECT name, age FROM students;
```

## **DISTINCT**

Removes duplicate rows.

```sql
SELECT DISTINCT age FROM students;
```

---

## **Filtering**

```sql
WHERE age >= 20
WHERE name != 'Dev'
```

---

## **Logical Operators**

```sql
WHERE age > 20 AND name = 'Dev'
WHERE age < 18 OR city = 'Kanpur'
WHERE NOT (age = 22)
```

---

## **Pattern Matching (LIKE)**

* `%` = many characters
* `_` = single character

```sql
WHERE name LIKE 'D%'
WHERE name LIKE '_ev'
WHERE name NOT LIKE '%a%'
```

---

## **NULL check**

```sql
WHERE email IS NULL
WHERE email IS NOT NULL
```

---

## **BETWEEN**

```sql
WHERE age BETWEEN 18 AND 25
```

## **IN / NOT IN**

```sql
WHERE city IN ('Kanpur','Delhi')
WHERE age NOT IN (18, 19)
```

---

# **2. SORTING & GROUPING**

---

## **ORDER BY**

```sql
SELECT * FROM students ORDER BY age DESC, name ASC;
```

---

## **GROUP BY**

Used for grouping rows.

```sql
SELECT city, COUNT(*)
FROM students
GROUP BY city;
```

---

## **HAVING**

Works like WHERE but for groups.

```sql
HAVING COUNT(*) > 5
```

---

## **Difference Between WHERE and HAVING**

| WHERE                            | HAVING                            |
| -------------------------------- | --------------------------------- |
| Filters rows **before grouping** | Filters groups **after grouping** |
| Cannot use aggregate functions   | Can use aggregates                |

---

## **Aggregate Functions**

* `COUNT()`
* `SUM()`
* `AVG()`
* `MAX()`
* `MIN()`

Example:

```sql
SELECT city, AVG(age)
FROM students
GROUP BY city;
```

---

# **3. JOINS**

---

## **Inner Join**

Only matching rows.

```sql
SELECT s.name, d.dept_name
FROM students s
INNER JOIN department d
ON s.dept_id = d.id;
```

---

## **Left Join**

All rows from left + matched from right.

## **Right Join**

All rows from right + matched from left.

## **Full Outer Join**

All rows from both sides.

## **Self Join**

Table joins itself.

```sql
SELECT a.name, b.name
FROM employees a
JOIN employees b
ON a.manager_id = b.id;
```

---

## **Cross Join**

Cartesian product.

```sql
SELECT * FROM a CROSS JOIN b;
```

---

## **Natural Join**

Automatically uses columns with **same names**.

---

## **Equi Join**

Join using `=`

## **Non-Equi Join**

Join with `<`, `>`, `BETWEEN`, etc.

---

# **4. SUBQUERIES**

---

## **Single Row Subquery**

```sql
SELECT name
FROM students
WHERE age = (SELECT MAX(age) FROM students);
```

---

## **Multi-row Subquery**

Using `IN`, `ANY`, `ALL`

```sql
WHERE age IN (SELECT age FROM backup)
```

---

## **Correlated Subquery**

Runs *per row*.

```sql
SELECT name
FROM students s
WHERE age > (
    SELECT AVG(age) FROM students WHERE city = s.city
);
```

---

## **Nested Subqueries**

Subquery inside another subquery.

---

## **Subquery in FROM (Inline View)**

```sql
SELECT * FROM (
    SELECT city, COUNT(*) c FROM students GROUP BY city
) t
WHERE t.c > 10;
```

---

## **Subquery in SELECT**

```sql
SELECT name,
       (SELECT dept_name FROM department d WHERE d.id = s.dept_id) AS department
FROM students s;
```

---

## **EXISTS / NOT EXISTS**

Checks if subquery returns rows.

```sql
WHERE EXISTS (SELECT 1 FROM department WHERE id = dept_id)
```

---

# **E. SET OPERATIONS**

---

## **1. UNION**

Removes duplicates.

```sql
SELECT name FROM t1
UNION
SELECT name FROM t2;
```

## **2. UNION ALL**

Keeps duplicates.

---

## **3. INTERSECT**

Common rows in both sets.

---

## **4. MINUS / EXCEPT**

Rows in first query but not in second.

---

## **Difference: UNION vs UNION ALL**

| UNION              | UNION ALL        |
| ------------------ | ---------------- |
| Removes duplicates | Keeps duplicates |
| Slower             | Faster           |
| Performs sorting   | No sorting       |

Alright Dev, **I’ll expand EVERYTHING in deep detail**, line-by-line, with full explanations, logic, examples, outputs — but I’ll only do **HALF** in this message.

When you say **“first batch ok”**, I will give the **second half**.

For now, I’ll cover:

✔ **F. Advanced Querying**
 → 1. CASE Statements
 → 2. IFNULL / COALESCE
 → 3. Conditional Aggregation
✔ **String Functions (FULL deep explanation)**
✔ **Date Functions (FULL deep explanation)**
✔ **Type Conversion Functions**

This is already a LOT of detail… and the rest (math functions, window functions, CTE, views, transactions, optimization, stored procedures, triggers) will come in **batch 2**.

---

# ⭐ **F. ADVANCED QUERYING — FULL DETAILED EXPLANATION (Batch 1)**

---

# **1. CASE & Conditional Expressions**

## 🔥 **CASE WHEN … THEN … ELSE … END**

The **CASE** expression works exactly like an IF-ELSE ladder in programming.
It checks each condition **in order**, and the first TRUE condition’s result is returned.

### ✔ Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ELSE default_value
END
```

---

### ✔ Example 1 — Classifying students by marks

```sql
SELECT name, marks,
       CASE
           WHEN marks >= 90 THEN 'Excellent'
           WHEN marks >= 75 THEN 'Very Good'
           WHEN marks >= 50 THEN 'Average'
           ELSE 'Fail'
       END AS performance
FROM students;
```

### ✔ OUTPUT (explained)

| name  | marks | performance |
| ----- | ----- | ----------- |
| Rohan | 92    | Excellent   |
| Dev   | 78    | Very Good   |
| Anu   | 54    | Average     |
| Raj   | 34    | Fail        |

Logic:

* If marks ≥ 90 → Excellent
* Else if marks ≥ 75 → Very Good
* Else if marks ≥ 50 → Average
* Else Fail

---

### ✔ Example 2 — Dynamic Pricing

```sql
SELECT product, price,
       CASE
           WHEN price > 50000 THEN 'Premium'
           WHEN price BETWEEN 20000 AND 50000 THEN 'Mid-range'
           ELSE 'Budget'
       END AS price_category
FROM mobiles;
```

---

## 🔥 **Searched CASE vs Simple CASE**

### **Simple CASE**

```sql
CASE column
    WHEN value1 THEN ...
    WHEN value2 THEN ...
END
```

### **Searched CASE** (more common)

```sql
CASE 
    WHEN condition THEN ...
END
```

Searched CASE is better because we can use ANY condition (>, <, =, IS NULL, LIKE).

---

# **2. IFNULL(), COALESCE() — Deep Explanation**

---

## 🔥 **IFNULL(expr, replacement)** (MySQL specific)

If expression is NULL → return replacement
Else → return original value.

### Example

```sql
SELECT name, IFNULL(email, 'Email Not Available') AS email_info
FROM users;
```

If email = NULL → “Email Not Available”

---

## 🔥 **COALESCE(value1, value2, value3, …)**

Returns the **FIRST non-NULL value**.

Example:

```sql
SELECT COALESCE(middle_name, nickname, first_name) AS preferred_name
FROM students;
```

Meaning:

* If middle_name exists → use it
* Else nickname → use it
* Else first_name

---

## ✔ Difference Between IFNULL & COALESCE

| Feature        | IFNULL          | COALESCE      |
| -------------- | --------------- | ------------- |
| # of arguments | 2 only          | unlimited     |
| Supported in   | MySQL           | ALL major DBs |
| Speed          | Slightly faster | Standard SQL  |

Use **COALESCE** in professional SQL.

---

# **3. Conditional Aggregation — VERY IMPORTANT**

Let’s say you want to count males and females in the same row.

### ✔ Example

```sql
SELECT 
    COUNT(CASE WHEN gender = 'M' THEN 1 END) AS male_count,
    COUNT(CASE WHEN gender = 'F' THEN 1 END) AS female_count
FROM students;
```

### ✔ How it works

* CASE returns **1** only when gender = 'M'
* COUNT(1) simply counts number of rows where CASE returned 1.

NULL rows are ignored in COUNT → perfect for condition-based counting.

---

### ✔ Example — Count passing & failing students

```sql
SELECT
    COUNT(CASE WHEN marks >= 40 THEN 1 END) AS pass_count,
    COUNT(CASE WHEN marks < 40 THEN 1 END) AS fail_count
FROM students;
```

### ✔ Example — Total salary by department but only for active employees

```sql
SELECT dept,
       SUM(CASE WHEN status = 'active' THEN salary ELSE 0 END) AS active_salary
FROM employees
GROUP BY dept;
```

---

# ⭐ **2. STRING FUNCTIONS — Deep Explanation With Outputs**

I will explain:

* How they work
* Syntax
* Example
* Exact output

---

## **1. CONCAT()**

Joins 2 or more strings.

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM employees;
```

If first_name = "Dev", last_name = "Agnihotri"

✔ Result → `"Dev Agnihotri"`

---

## **2. LENGTH()**

Returns number of characters (not bytes in MySQL).

```sql
SELECT LENGTH('SQL') AS len;
```

✔ OUTPUT → `3`

---

## **3. SUBSTRING(str, start, length)**

Extracts part of a string.

```sql
SELECT SUBSTRING('DATABASE', 1, 4);
```

✔ OUTPUT → `'DATA'`

---

## **4. REPLACE(str, old, new)**

Replace all occurrences of a substring.

```sql
SELECT REPLACE('Hello World', 'World', 'SQL');
```

✔ OUTPUT → `"Hello SQL"`

---

## **5. UPPER() / LOWER()**

```sql
SELECT UPPER('dev');   -- DEV
SELECT LOWER('HELLO'); -- hello
```

---

## **6. INSTR(str, substring)**

Gives starting position of substring.

```sql
SELECT INSTR('HelloWorld', 'World');
```

✔ OUTPUT → `6`
(because W starts at position 6)

---

## **7. TRIM()**

Removes spaces.

```sql
SELECT TRIM('   Dev   ');
```

✔ OUTPUT → `"Dev"`

---

# ⭐ **3. DATE FUNCTIONS — Deep Explanation With Outputs**

Dates are extremely important.

---

## **NOW()**

Current date & time.

```sql
SELECT NOW();
```

✔ OUTPUT → `2025-11-30 18:09:23` (example)

---

## **SYSDATE()**

Similar to NOW but can differ in some DBs.

---

## **DATEDIFF(date1, date2)**

Returns difference in days.

```sql
SELECT DATEDIFF('2025-01-01', '2024-01-01');
```

✔ OUTPUT → `366` (leap year)

---

## **DATEADD(unit, value, date)**

```sql
SELECT DATEADD(day, 10, '2025-02-01');
```

✔ OUTPUT → `'2025-02-11'`

---

## **MONTH(), YEAR()**

```sql
SELECT MONTH('2025-02-10');  -- 2
SELECT YEAR('2025-02-10');   -- 2025
```

---

## **EXTRACT(part FROM date)**

```sql
SELECT EXTRACT(WEEK FROM '2025-01-15');
```

✔ OUTPUT → `3`

---

# ⭐ **4. Conversion Functions — Deep Explanation**

---

## **CAST(expression AS datatype)**

```sql
SELECT CAST('123' AS INT);
```

✔ OUTPUT → `123`

---

## **CONVERT(datatype, expression)**

SQL Server / MySQL style.

```sql
SELECT CONVERT(DATE, '2025-02-01');
```

---

## **TO_CHAR()** (Oracle, PostgreSQL)

Format numbers/dates.

```sql
SELECT TO_CHAR(12345, '99,999');
```

✔ OUTPUT → `"12,345"`

---

## **TO_DATE(string, format)**

```sql
SELECT TO_DATE('01-02-2025','DD-MM-YYYY');
```

Converts string into date object.

### ⭐ **Remaining Topics**

* Math functions
* Aggregate functions
* Window functions (very deep)
* CTE & recursive CTE
* Views & materialized views
* Transactions
* Isolation levels
* Query optimization
* Explain plans
* Stored procedures
* Functions
* Triggers
* Cursors

Great — continuing with **the second half (F → J)** in the same *deep-explanation + syntax + examples + results* style.

---

# **F. ADVANCED QUERYING (DETAILED)**

---

## **1. CASE & Conditional Expressions**

### **CASE WHEN … THEN … ELSE … END**

**Meaning:**
CASE is like **if-else** in SQL.
It checks a condition **for every row** and returns a value based on that condition.

### **Syntax**

```sql
SELECT
    CASE
        WHEN condition1 THEN result1
        WHEN condition2 THEN result2
        ELSE default_value
    END AS alias_name
FROM table_name;
```

### **Example**

```sql
SELECT name, marks,
    CASE
        WHEN marks >= 90 THEN 'A'
        WHEN marks >= 75 THEN 'B'
        ELSE 'C'
    END AS grade
FROM students;
```

### **Result**

| name  | marks | grade |
| ----- | ----- | ----- |
| Aditi | 92    | A     |
| Rohan | 80    | B     |
| Sam   | 60    | C     |

---

### **IFNULL()**

**Use:** replace NULL with another value.

```sql
SELECT name, IFNULL(phone, 'Not Provided') AS phone_no
FROM users;
```

---

### **COALESCE()**

**Use:** returns the **first NON-NULL** value from a list.

```sql
SELECT COALESCE(middle_name, nickname, 'No Name') FROM users;
```

---

### **Conditional Aggregation**

Using CASE inside aggregate functions.

Example: Count number of male and female employees **in one query**.

```sql
SELECT
    COUNT(CASE WHEN gender='M' THEN 1 END) AS male_count,
    COUNT(CASE WHEN gender='F' THEN 1 END) AS female_count
FROM employees;
```

---

# **2. STRING & DATE FUNCTIONS**

---

## **STRING FUNCTIONS**

### **1. CONCAT()**

Join two or more strings.

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM users;
```

---

### **2. LENGTH()**

Returns number of characters.

```sql
SELECT LENGTH('Hello');  
```

**Result:** `5`

---

### **3. SUBSTRING()**

Extract part of string.

```sql
SELECT SUBSTRING('HelloWorld', 1, 5);
```

**Result:** `Hello`

---

### **4. REPLACE()**

Replace part of string.

```sql
SELECT REPLACE('SQL Tutorial', 'SQL', 'My');
```

**Result:** `My Tutorial`

---

### **5. UPPER(), LOWER()**

Convert to uppercase / lowercase.

```sql
SELECT UPPER('hello'); → HELLO
SELECT LOWER('HELLO'); → hello
```

---

### **6. INSTR()**

Find position of substring.

```sql
SELECT INSTR('database', 'base');
```

**Result:** `5`

---

### **7. TRIM()**

Remove spaces from start/end.

```sql
SELECT TRIM('   Hello   ');
```

**Result:** `Hello`

---

---

## **DATE FUNCTIONS**

### **NOW()**

Returns current date and time.

```sql
SELECT NOW();
```

---

### **SYSDATE()**

Similar to NOW but evaluated immediately.

---

### **DATEDIFF()**

Difference between two dates (in days).

```sql
SELECT DATEDIFF('2025-12-31', '2025-01-01');
```

**Result:** `364`

---

### **DATEADD() / ADDDATE()**

Add days, months, years.

```sql
SELECT DATEADD(day, 30, '2025-01-01');
```

---

### **MONTH(), YEAR()**

Extract specific parts.

```sql
SELECT YEAR('2025-09-21'); → 2025
SELECT MONTH('2025-09-21'); → 9
```

---

### **EXTRACT()**

More flexible extraction.

```sql
SELECT EXTRACT(WEEK FROM '2025-04-02');
```

---

## **DATE CONVERSIONS**

### **CAST(), CONVERT()**

Convert data types.

```sql
SELECT CAST('25' AS INT);
SELECT CONVERT('2025-05-09', DATE);
```

---

### **TO_DATE(), TO_CHAR()** (Oracle)

```sql
SELECT TO_DATE('2025-12-10', 'YYYY-MM-DD');
SELECT TO_CHAR(SYSDATE, 'YYYY Month');
```

---

---

# **3. MATHEMATICAL & AGGREGATE FUNCTIONS**

---

### **ROUND()**

Rounds number.

```sql
SELECT ROUND(12.567, 2);
```

**Result:** `12.57`

---

### **CEIL() / FLOOR()**

```sql
SELECT CEIL(4.1);   → 5
SELECT FLOOR(4.9);  → 4
```

---

### **ABS()**

Absolute value.

```sql
SELECT ABS(-50);
```

---

### **MOD()**

Remainder.

```sql
SELECT MOD(10, 3); → 1
```

---

## **AGGREGATE FUNCTIONS**

```sql
SELECT
    COUNT(*) AS total_rows,
    SUM(salary),
    AVG(salary),
    MAX(salary),
    MIN(salary)
FROM employees;
```

---

# **4. WINDOW (ANALYTIC) FUNCTIONS**

Window functions perform calculations on a **set of rows related to the current row**.

Uses **OVER()** clause.

---

## **ROW_NUMBER()**

Gives unique row number within partition.

```sql
SELECT name, salary,
    ROW_NUMBER() OVER(ORDER BY salary DESC) AS rank_num
FROM employees;
```

---

## **RANK() vs DENSE_RANK()**

* **RANK()** → Skips numbers if tie
* **DENSE_RANK()** → No skipping

Example salaries: `5000, 4000, 4000, 3000`

| salary | RANK | DENSE_RANK |
| ------ | ---- | ---------- |
| 5000   | 1    | 1          |
| 4000   | 2    | 2          |
| 4000   | 2    | 2          |
| 3000   | 4    | 3          |

---

## **LEAD() / LAG()**

Used to compare current row with next or previous row.

### **Example**

```sql
SELECT emp_id, salary,
    LAG(salary) OVER(ORDER BY emp_id) AS prev_salary,
    LEAD(salary) OVER(ORDER BY emp_id) AS next_salary
FROM employees;
```

---

## **NTILE()**

Divides rows into equal groups.

```sql
SELECT name, NTILE(4) OVER(ORDER BY score DESC) AS tier
FROM students;
```

---

## **FIRST_VALUE(), LAST_VALUE()**

```sql
SELECT
    FIRST_VALUE(salary) OVER(ORDER BY date_joined) AS first_salary
FROM employees;
```

---

## **PARTITION BY**

Divides data into groups for window calculations.

```sql
SELECT
    department,
    salary,
    ROW_NUMBER() OVER(PARTITION BY department ORDER BY salary DESC) AS dept_rank
FROM employees;
```

---

# **5. COMMON TABLE EXPRESSIONS (CTE)**

---

## **WITH Clause**

Temporary named result set that exists only for one query.

### **Example**

```sql
WITH high_salary AS (
    SELECT * FROM employees WHERE salary > 50000
)
SELECT name FROM high_salary;
```

---

## **Recursive CTE**

Used for hierarchical data (parent → child).

### **Example: Employee Hierarchy**

```sql
WITH RECURSIVE emp_tree AS (
    SELECT id, name, manager_id
    FROM employees
    WHERE manager_id IS NULL   -- root employee

    UNION ALL

    SELECT e.id, e.name, e.manager_id
    FROM employees e
    JOIN emp_tree et ON e.manager_id = et.id
)
SELECT * FROM emp_tree;
```

---

# **G. VIEWS & MATERIALIZED VIEWS**

---

## **CREATE VIEW**

A view is a **virtual table** based on a query.

```sql
CREATE VIEW high_paid AS
SELECT name, salary FROM employees WHERE salary > 60000;
```

---

### **DROP VIEW**

```sql
DROP VIEW high_paid;
```

---

### **REPLACE VIEW / CREATE OR REPLACE VIEW**

```sql
CREATE OR REPLACE VIEW high_paid AS
SELECT name, salary, department FROM employees WHERE salary > 60000;
```

---

## **Updatable vs Non-Updatable Views**

* **Updatable views**: Can run INSERT, UPDATE, DELETE
  → Simple, based on one table.
* **Non-updatable**: Involves joins, group by, distinct, aggregate functions.

---

## **WITH CHECK OPTION**

Prevents inserting rows that don’t satisfy the condition.

```sql
CREATE VIEW dept10 AS
SELECT * FROM employees WHERE dept_id = 10
WITH CHECK OPTION;
```

---

## **Materialized Views**

Stores data **physically** (not virtual).

### **Benefits**

* Faster for heavy aggregations.
* Good for reporting dashboards.

### **Refresh Types**

* **FAST**
* **COMPLETE**
* **ON DEMAND**
* **ON COMMIT**

---

# **H. TRANSACTIONS & CONTROL COMMANDS**

---

## **COMMIT**

Save changes permanently.

```sql
COMMIT;
```

---

## **ROLLBACK**

Undo all changes since last commit.

```sql
ROLLBACK;
```

---

## **SAVEPOINT**

Set a checkpoint inside a transaction.

```sql
SAVEPOINT s1;

DELETE FROM orders;

ROLLBACK TO s1;
```

---

## **Transaction States**

1. **Active** – transaction running
2. **Partially committed** – all statements done
3. **Committed** – saved
4. **Failed** – error
5. **Aborted** – rolled back

---

## **Isolation Levels**

1. **Read Uncommitted** → Dirty reads allowed
2. **Read Committed** → Most common; prevents dirty reads
3. **Repeatable Read** → Prevents non-repeatable reads
4. **Serializable** → Highest, slowest, full isolation

---

# **I. QUERY OPTIMIZATION**

---

## **How SQL Optimizer Works**

Optimizer rewrites your query to find the **fastest execution plan**.

---

## **Indexes & Performance**

Indexes = pointers that help fetch rows faster.

* Good for **WHERE**, **JOIN**, **ORDER BY**
* Avoid for columns frequently updated.

---

## **EXPLAIN PLAN**

Shows how SQL will run the query.

```sql
EXPLAIN SELECT * FROM employees WHERE salary > 50000;
```

---

## **Avoid SELECT ***

Fetch only required columns.

---

## **Avoid Correlated Subqueries** (slow)

Use JOINs instead.

---

### **Execution Order of SQL Clauses**

```
FROM
WHERE
GROUP BY
HAVING
SELECT
ORDER BY
LIMIT
```

---

## **Query Tuning Examples**

### ✔ Convert subquery → join

```sql
SELECT e.name
FROM employees e
JOIN departments d ON e.dept_id = d.id;
```

---

### ✔ Use EXISTS instead of IN

```sql
SELECT name FROM employees e
WHERE EXISTS (
    SELECT 1 FROM sales s WHERE s.emp_id = e.id
);
```

---

### ✔ Use LIMIT/TOP

```sql
SELECT * FROM logs ORDER BY time DESC LIMIT 100;
```

---

# **J. STORED PROCEDURES, FUNCTIONS & TRIGGERS**

---

## **Stored Procedure**

Reusable block of SQL code.

### **Syntax**

```sql
CREATE PROCEDURE getSalary(IN empID INT)
BEGIN
    SELECT salary FROM employees WHERE id = empID;
END;
```

### **Parameters**

* **IN** → input
* **OUT** → return variable
* **INOUT** → acts as both

---

## **Functions**

* Must return a value.
* Cannot use INSERT/UPDATE/DELETE.

### Example

```sql
CREATE FUNCTION getTax(salary INT)
RETURNS INT
BEGIN
    RETURN salary * 0.10;
END;
```

---

## **Triggers**

Automatically run on INSERT, UPDATE, DELETE.

### Example

```sql
CREATE TRIGGER before_insert_employee
BEFORE INSERT ON employees
FOR EACH ROW
SET NEW.created_at = NOW();
```

---

## **Cursors**

Used to fetch row-by-row.

### Syntax

```sql
DECLARE cur CURSOR FOR SELECT name FROM employees;
OPEN cur;
FETCH cur INTO var_name;
CLOSE cur;
```
