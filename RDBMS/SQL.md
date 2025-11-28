# Structured Query Language (SQL)

## Table of Contents

- [A. SQL Fundamentals Refresher](#a-sql-fundamentals-refresher)
- [What is SQL, DDL, DML, DCL, TCL](#what-is-sql)
- [Case Sensitivity and Syntax Rules](#case-sensitivity-and-syntax-rules)
- [Schema vs Database vs Table](#schema-vs-database-vs-table)
- [SQL Datatypes](#sql-datatypes)
- [B. Data Definition Language (DDL)](#b-data-definition-language-ddl)
- [CREATE / ALTER / DROP / TRUNCATE](#create--alter--drop--truncate)
- [CREATE DATABASE / USE](#create-database--use)
- [Columns: Add / Modify / Delete](#columns-add--modify--delete)
- [Constraints and Cascades](#constraints-and-cascades)
- [CREATE INDEX / DROP INDEX](#create-index--drop-index)
- [C. Data Manipulation Language (DML)](#c-data-manipulation-language-dml)
- [INSERT INTO ... VALUES / INSERT INTO ... SELECT](#insert-into--values--insert-into--select)
- [L. Detailed Examples: Easy → Medium → Hard](#l-detailed-examples-easy-→-medium-→-hard)

## K. Querying Examples (Simple to Complex)

This section shows worked queries from very simple to more complex. Each example has a short description of the expected result so you can practice and confirm the output.

### K1 — Simple SELECT and filtering

Query:

```sql
SELECT student_id, name, birthdate
FROM Student
WHERE birthdate >= '2000-01-01'
ORDER BY name;
```

Expected result: a list of students born on or after 2000, sorted by name (one row per student showing id, name, birthdate).

Why practice: learn basic `SELECT`, `WHERE`, and `ORDER BY` usage.

---

### K2 — Aggregation and GROUP BY

Query:

```sql
SELECT course_id, COUNT(*) AS student_count, AVG(score) AS avg_score
FROM Enrollment
GROUP BY course_id
HAVING COUNT(*) > 1
ORDER BY avg_score DESC;
```

Expected result: one row per `course_id` that has more than one student, showing how many students and the average score, sorted by highest average score.

Why practice: learn `GROUP BY`, aggregates (`COUNT`, `AVG`) and `HAVING` to filter groups.

---

### K3 — Joins: inner and left (with simple sample explanation)

Inner join (only matching rows):

```sql
SELECT s.student_id, s.name, e.course_id, e.score
FROM Student s
JOIN Enrollment e ON s.student_id = e.student_id
WHERE e.score >= 70;
```

Expected result: rows of students who have an enrollment record with score >= 70; if a student has multiple such enrollments, they appear multiple times (one per matched enrollment).

Left join (keep all students, show NULL for missing enrollments):

```sql
SELECT s.student_id, s.name, e.course_id
FROM Student s
LEFT JOIN Enrollment e ON s.student_id = e.student_id
WHERE e.course_id IS NULL;
```

Expected result: students who are not enrolled in any course (their `course_id` will be `NULL` in the output). This shows how outer joins reveal missing matches.

Why practice: understand the difference between inner and outer joins and how `NULL` appears for missing data.

---

### K4 — Subquery and CTE (better readability)

Subquery example (find students in the most-popular course):

```sql
SELECT name FROM Student
WHERE student_id IN (
  SELECT student_id FROM Enrollment WHERE course_id = (
    SELECT course_id FROM Enrollment GROUP BY course_id ORDER BY COUNT(*) DESC LIMIT 1
  )
);
```

CTE version (same idea, easier to read):

```sql
WITH top_course AS (
  SELECT course_id FROM Enrollment GROUP BY course_id ORDER BY COUNT(*) DESC LIMIT 1
)
SELECT s.name
FROM Student s
JOIN Enrollment e ON s.student_id = e.student_id
JOIN top_course t ON e.course_id = t.course_id;
```

Expected result: names of students enrolled in the single course that has the most enrollments.

Why practice: prefer CTEs for clarity and reuse in complex queries.

---

### K5 — Window functions (ranking and running total)

Top N per group (rank students by score inside each course):

```sql
SELECT student_id, course_id, score
FROM (
  SELECT student_id, course_id, score,
    ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
  FROM Enrollment
) t
WHERE rn <= 3; -- top 3 students per course
```

Running total example:

```sql
SELECT student_id, score,
  SUM(score) OVER (ORDER BY student_id ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS running_total
FROM Enrollment;
```

Expected result: `ROW_NUMBER()` assigns ranks per `course_id`; the top-N query returns the highest scorers per course. The running total shows cumulative sums across ordered rows.

Why practice: window functions let you compute values across rows without collapsing results.

---

### K6 — A realistic combined example (complex): top students with recent enrollments

Problem: For each course, show the top student (by score) who enrolled in the last year, including the student's name and score.

Solution (CTE + window + join):

```sql
WITH recent AS (
  SELECT * FROM Enrollment WHERE enrollment_date >= CURRENT_DATE - INTERVAL '1 year'
), ranked AS (
  SELECT student_id, course_id, score,
    ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
  FROM recent
)
SELECT r.course_id, s.name, r.score
FROM ranked r
JOIN Student s ON r.student_id = s.student_id
WHERE r.rn = 1;
```

Expected result: one row per course showing the best student (name and score) among enrollments from the past year.

Why practice: combines many skills — filtering, CTEs, window functions, and joins — exactly what you need to master more complex queries.

---

### K7 — Quick performance tips while practicing

- Add indexes on columns used in `WHERE`, `JOIN`, and `ORDER BY` for faster tests on larger data.
- Use `EXPLAIN` to see how a query will run before trying to optimize it.
- For learning, run queries on small sample datasets first, then scale up.

---

Try these examples in order: K1 → K2 → K3 → K4 → K5 → K6. Start simple and add complexity. If you want, I can create a runnable `sq_examples.md` with sample `CREATE TABLE` + `INSERT` statements for a small dataset so you can paste and run these examples locally.

Tell me which next step you prefer.

---

## L. Detailed Examples: Easy → Medium → Hard

This long section gives practice examples with clear, simple (8th-grade) explanations and step-by-step notes. Work through the Easy ones first, then the Medium, then the Hard examples. Each example includes what to expect and why each step is used.

### L1 — Easy: Single-table SELECTs and simple filters

Example 1 — List student names and emails:

```sql
SELECT name, email FROM Student ORDER BY name;
```

What this does (8th-grade): We ask the database to give us two columns — the student's name and email — for every student. `ORDER BY name` makes the list sorted by the name so it's easier to read.

Step-by-step:

- `SELECT name, email` tells which columns you want.
- `FROM Student` tells which table has those columns.
- `ORDER BY name` sorts the rows by the `name` column.

Practice task: Change `ORDER BY name` to `ORDER BY email` and see the result.

Example 2 — Find students older than 21:

```sql
SELECT student_id, name, birthdate
FROM Student
WHERE birthdate <= '2004-11-28'; -- adjust date for "21 years old"
```

What this does: `WHERE` keeps only the rows that match the rule. We compare birthdate to a date to get students older than or equal to 21.

Why practice: Learn how `WHERE` filters rows and how dates work.

---

### L2 — Easy: INSERT / UPDATE / DELETE with safety notes

Insert a new student safely (explicit columns):

```sql
INSERT INTO Student (student_id, name, birthdate, email)
VALUES (101, 'Sam Example', '2003-07-15', 'sam@example.com');
```

Why use explicit columns: If table gets a new column later, your insert still works and puts values in the right places.

Update with a safe WHERE:

```sql
UPDATE Student SET email = 'sam.new@example.com' WHERE student_id = 101;
```

Why practice: If you forget `WHERE`, you change every row. Always include `WHERE` unless you really mean to affect all rows.

Delete one row safely:

```sql
DELETE FROM Student WHERE student_id = 101;
```

Tip: If you want to preview which rows will be deleted, run a `SELECT` with the same `WHERE` first.

---

### L3 — Medium: JOINs with step-by-step reasoning

Problem: Show each student and the courses they are enrolled in (if any). If a student is not enrolled, show the student but show `NULL` for course id.

Query (LEFT JOIN):

```sql
SELECT s.student_id, s.name, e.course_id, e.score
FROM Student s
LEFT JOIN Enrollment e ON s.student_id = e.student_id
ORDER BY s.name;
```

8th-grade explanation: We start with the Student list, and for every student we try to find matching rows in Enrollment. `LEFT JOIN` means: keep all students; when there is no enrollment, the `course_id` and `score` will be empty (`NULL`).

Step-by-step:

- `FROM Student s` pick students as the main list.
- `LEFT JOIN Enrollment e ON s.student_id = e.student_id` attach enrollments when they match.
- `ORDER BY s.name` sorts the result.

Practice task: Change `LEFT JOIN` to `INNER JOIN` and see how the output changes (students with no enrollments disappear).

---

### L4 — Medium: Aggregation with explanation (grouping)

Problem: For each course, show how many students enrolled and the highest score.

Query:

```sql
SELECT course_id, COUNT(*) AS students, MAX(score) AS top_score
FROM Enrollment
GROUP BY course_id
ORDER BY students DESC;
```

8th-grade explanation: We put rows together by `course_id`. For each course we count how many rows (students) there are and find the highest score. `GROUP BY` is how we make one row per course.

Step-by-step:

- `SELECT course_id` chooses the grouping column.
- `COUNT(*)` counts rows in each group.
- `MAX(score)` picks the highest score in the group.
- `GROUP BY course_id` makes groups.

Practice task: Replace `MAX(score)` with `AVG(score)` to see the average.

---

### L5 — Medium: Subqueries vs CTEs (clear comparison)

Goal: Find student names who scored above average in course 101.

Subquery approach:

```sql
SELECT name FROM Student WHERE student_id IN (
  SELECT student_id FROM Enrollment WHERE course_id = 101 AND score > (
    SELECT AVG(score) FROM Enrollment WHERE course_id = 101
  )
);
```

CTE approach (cleaner):

```sql
WITH course_avg AS (
  SELECT AVG(score) AS avg_score FROM Enrollment WHERE course_id = 101
)
SELECT s.name
FROM Student s
JOIN Enrollment e ON s.student_id = e.student_id
JOIN course_avg a ON e.score > a.avg_score
WHERE e.course_id = 101;
```

8th-grade explanation: Both ways find students who beat the average. The CTE version names the average so the main query is easier to read.

Step-by-step: compute average first, then pick students with score bigger than that average.

Practice task: Change `>` to `>=` to include students exactly equal to average.

---

### L6 — Hard: Window functions and top-N per group (detailed)

Problem: For each course, list the top 2 students by score and include their rank.

Query:

```sql
SELECT course_id, student_id, score, rn
FROM (
  SELECT course_id, student_id, score,
    ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
  FROM Enrollment
) t
WHERE rn <= 2
ORDER BY course_id, rn;
```

8th-grade explanation: Inside the parentheses we give every enrollment a rank number `rn` inside its course group. `ROW_NUMBER()` starts at 1 for the highest score per course. Outside, we keep only rows where `rn` is 1 or 2 (top two).

Step-by-step:

- `ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC)` gives a separate count for each course, ordered by score.
- Wrapping it and filtering by `rn <= 2` keeps top two per course.

Practice task: Replace `ROW_NUMBER()` with `RANK()` and try a tie in scores to see the difference.

---

### L7 — Hard: Complex real-world example with explanation

Problem: Produce a report showing, for the last 6 months, each course's average score, how many students improved compared to their previous attempt, and the top student name.

Notes: This combines filtering, window functions, aggregates, and joins. The exact schema may differ by your data; this is a template you can adapt.

Template solution (explanatory):

```sql
WITH recent AS (
  SELECT * FROM Enrollment WHERE enrollment_date >= CURRENT_DATE - INTERVAL '6 months'
),
ranked AS (
  SELECT r.*,
    ROW_NUMBER() OVER (PARTITION BY student_id, course_id ORDER BY enrollment_date) AS attempt_no,
    LAG(score) OVER (PARTITION BY student_id, course_id ORDER BY enrollment_date) AS prev_score
  FROM recent r
),
improvements AS (
  SELECT course_id, student_id, score, prev_score,
    CASE WHEN prev_score IS NOT NULL AND score > prev_score THEN 1 ELSE 0 END AS improved
  FROM ranked
),
course_summary AS (
  SELECT course_id, COUNT(*) AS attempts, AVG(score) AS avg_score, SUM(improved) AS improved_count
  FROM improvements
  GROUP BY course_id
)
SELECT cs.course_id, cs.attempts, cs.avg_score, cs.improved_count, s.name AS top_student
FROM course_summary cs
LEFT JOIN (
  SELECT course_id, student_id, score,
    ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
  FROM recent
) top ON cs.course_id = top.course_id AND top.rn = 1
LEFT JOIN Student s ON top.student_id = s.student_id;
```

8th-grade explanation (step-by-step):

- `recent`: keep only enrollments from last 6 months.
- `ranked`: for each student's attempts in a course, order them and find the previous score with `LAG()`.
- `improvements`: mark a row as `improved` if the current score is higher than the previous one.
- `course_summary`: for each course, count attempts, average scores, and how many improved.
- final `SELECT`: find the top student per course by score and bring their name into the summary.

Practice task: Try running smaller parts of the CTE (just `recent` or `ranked`) to inspect intermediate results.

---

### L8 — Learning checklist and practice routine

- Work Easy examples until you can write and explain them without a cheat sheet.
- Move to Medium: focus on join logic and grouping.
- For Hard: break each problem into smaller parts (use CTEs to test intermediate steps).
- Use `EXPLAIN` to see if your query will use indexes.
- When optimizing, measure with real data and compare run times.

If you want, I can now:

- Create `sq_examples.md` with `CREATE TABLE` and `INSERT` statements for a small sample dataset (Student, Course, Enrollment) so you can run all these examples locally.
- Or I can convert these examples into a short quiz with answers.

Tell me which I should do next and I will continue.

Syntax:

```

INSERT INTO table_name (col1, col2, ...) VALUES (val1, val2, ...);

```

Example:

```

INSERT INTO Student (student_id, name, birthdate) VALUES (1, 'Alice', '2002-05-12');

```

2. INSERT INTO ... SELECT (copy rows from another table)

```

INSERT INTO OldStudents (student_id, name)
SELECT student_id, name FROM Student WHERE birthdate < '2000-01-01';

```

### UPDATE

3. UPDATE (single and multiple columns)

Syntax:

```

UPDATE table_name
SET col1 = val1, col2 = val2
WHERE some_condition;

```

Example:

```

```

If you run `UPDATE Student SET name = 'X';` without `WHERE`, it changes every row. Be careful.

### DELETE

4. DELETE (with and without WHERE)

- Delete one row:

```

DELETE FROM Student WHERE student_id = 2;

```

- Delete all rows:

DELETE FROM Student; -- removes all rows but keeps table

### Bulk Insert & Copy (simple)

5. Bulk Insert & Copy (simple):

- Many DBs support `COPY` or bulk load commands to load data from files. Example in PostgreSQL:

```
COPY Student(student_id, name, birthdate) FROM '/path/students.csv' CSV HEADER;
```

---

## D. Data Query Language (DQL)

### Basic Queries

SELECT basics:

```
SELECT column_list
FROM table_name
WHERE condition
ORDER BY column;
```

Examples:

- Select all columns:

```
SELECT * FROM Student;
```

- Select specific columns and remove duplicates:

```
SELECT DISTINCT name FROM Student;
```

Filters and operators:

- `=` equal, `!=` or `<>` not equal, `<`, `>`, `<=`, `>=`.
- Logical: `AND`, `OR`, `NOT`.
- Pattern matching:
  - `LIKE 'A%'` finds names starting with A.
  - `%` matches any number of characters, `_` matches one character.
- `IS NULL` and `IS NOT NULL` test null values.
- `BETWEEN a AND b` checks range (inclusive).
- `IN (x, y, z)` checks membership.

Examples:

```
SELECT name FROM Student WHERE age >= 20 AND name LIKE 'A%';
SELECT * FROM Student WHERE student_id IN (1,3,5);
SELECT * FROM Student WHERE birthdate BETWEEN '2000-01-01' AND '2004-12-31';
```

### Sorting and Grouping

- `ORDER BY column [ASC|DESC]` sorts results. Default is `ASC` (ascending).

```
SELECT name, birthdate FROM Student ORDER BY birthdate DESC;
```

- `GROUP BY` groups rows that share a value, used with aggregate functions.
- `HAVING` filters groups (useful with `GROUP BY`). `WHERE` filters rows before grouping.

Example:

```
SELECT course_id, COUNT(*) AS students_count
FROM Enrollment
GROUP BY course_id
HAVING COUNT(*) > 1;
```

This returns courses with more than one student.

### Joins (simple explanations + examples)

- Inner Join: returns rows where the join condition matches both tables.

```
SELECT s.name, e.course_id
FROM Student s
JOIN Enrollment e ON s.student_id = e.student_id;
```

- Left (Outer) Join: returns all rows from left table and matched rows from right. If no match, right columns are `NULL`.

```
SELECT s.name, e.course_id
FROM Student s
LEFT JOIN Enrollment e ON s.student_id = e.student_id;
```

- Right (Outer) Join: opposite of left join (not always supported in every DB).
- Full (Outer) Join: returns rows when there is a match in one of the tables.
- Self Join: join a table with itself (useful for hierarchies).

```
SELECT a.name AS manager, b.name AS employee
FROM Employee b
JOIN Employee a ON b.manager_id = a.employee_id;
```

- Cross Join (Cartesian product): every row of A paired with every row of B.
- Natural Join: auto-joins on columns with the same name (be careful — may hide which columns are used).
- Equi Join vs Non-Equi Join: Equi join uses `=`; non-equi uses other comparisons like `<`.

### Subqueries

- Single-row subquery (returns one value):

```
SELECT name FROM Student WHERE age = (SELECT MAX(age) FROM Student);
```

- Multi-row subquery:

```
SELECT name FROM Student WHERE student_id IN (SELECT student_id FROM Enrollment WHERE course_id = 101);
```

- Correlated subquery: the inner query uses values from the outer row and runs per row.

```
SELECT s.name
FROM Student s
WHERE EXISTS (
  SELECT 1 FROM Enrollment e WHERE e.student_id = s.student_id AND e.course_id = 101
);
```

- Subquery in FROM (inline view):

```
SELECT t.course_id, t.count FROM (
  SELECT course_id, COUNT(*) AS count FROM Enrollment GROUP BY course_id
) t WHERE t.count > 1;
```

- `EXISTS` returns true if subquery returns any row.

---

## E. Set Operations

- `UNION` combines results from two queries and removes duplicates.
- `UNION ALL` combines results and keeps duplicates.
- `INTERSECT` returns rows common to both queries (not supported in every DB).
- `MINUS` or `EXCEPT` returns rows from the first query not in the second (name depends on DB).

Example:

```
SELECT student_id FROM Enrollment WHERE course_id = 101
UNION
SELECT student_id FROM Enrollment WHERE course_id = 102;
```

This returns student ids in course 101 or 102, with duplicates removed.

Difference UNION vs UNION ALL:

- `UNION` removes duplicates (slower).
- `UNION ALL` keeps duplicates (faster) and is used when duplicates are fine.

---

## Examples

Here are some examples of SQL queries:

1.  **Select Query**:

```sql
SELECT * FROM Student WHERE age > 20;
```

2.  **Insert Query**:

```sql
INSERT INTO Student (student_id, name) VALUES (2, 'Bob');
```

3.  **Update Query**:

```sql
UPDATE Student SET name = 'Alice' WHERE student_id = 1;
```

4.  **Delete Query**:

```sql
DELETE FROM Student WHERE student_id = 2;
```

Tell me which next step you prefer.
