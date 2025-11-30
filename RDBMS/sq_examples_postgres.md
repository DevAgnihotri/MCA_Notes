# Example: PostgreSQL schema and runnable queries (step-by-step)

This file is written for someone who is just starting (zero knowledge). It contains:

- A tiny friendly setup you can run locally (PowerShell examples).
- A small schema: `student`, `course`, `enrollment` (ready to copy/paste).
- Sample rows to insert.
- Many example queries that map to topics in your notes (sections 1–6).
- Simple, 1–2 line explanations for each step and each SQL word used.

How to use this file

- Option A (recommended if you have `psql` installed): open PowerShell, connect to PostgreSQL, then copy and paste the SQL blocks below into the `psql` prompt.
- Option B: save the SQL blocks to a file (e.g., `examples.sql`) and run `psql -d school_db -f examples.sql`.

Quick: create and connect to a test database (PowerShell)

```powershell
# create db (run as a user who can create DBs, e.g. postgres)
psql -U postgres -c "CREATE DATABASE school_db;"
# connect
psql -U postgres -d school_db
```

Part A — Create schema (tables) and small sample data

What we are doing: create three tables to practice queries. `student` stores students, `course` stores courses, `enrollment` links students and courses and stores a score and enrollment date.

Copy and paste this whole block into `psql` (connected to `school_db`):

```sql
-- 1. Create tables (simple names and explanations)
CREATE TABLE student (
  student_id SERIAL PRIMARY KEY, -- SERIAL makes an auto-increment integer
  name TEXT NOT NULL,            -- student name, must be present
  email TEXT UNIQUE,             -- email, unique so two students can't share it
  birthdate DATE,
  active BOOLEAN DEFAULT TRUE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE course (
  course_id SERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  credits INT DEFAULT 3
);

CREATE TABLE enrollment (
  enrollment_id SERIAL PRIMARY KEY,
  student_id INT REFERENCES student(student_id) ON DELETE CASCADE,
  course_id INT REFERENCES course(course_id) ON DELETE CASCADE,
  score INT, -- numeric score, 0-100 in our sample
  enrollment_date DATE DEFAULT CURRENT_DATE
);

-- 2. Insert sample data: a few students, courses, and enrollments
INSERT INTO student (name, email, birthdate) VALUES
  ('Alice', 'alice@example.com', '2002-05-12'),
  ('Bob', 'bob@example.com', '2001-08-20'),
  ('Carol', 'carol@example.com', '2003-10-02');

INSERT INTO course (title, credits) VALUES
  ('Databases', 4),
  ('Networks', 3),
  ('Algorithms', 4);

INSERT INTO enrollment (student_id, course_id, score, enrollment_date) VALUES
  (1, 1, 85, '2024-08-01'),
  (1, 3, 78, '2024-08-05'),
  (2, 1, 92, '2024-08-02'),
  (3, 2, 66, '2024-08-10');
```

Short explanation of key words used above

- `CREATE TABLE`: makes a new table (a list of rows with columns).
- `SERIAL PRIMARY KEY`: creates a column that auto-increments for each new row and identifies each row.
- `NOT NULL`: the column must have a value.
- `DEFAULT`: value used if none is provided.
- `REFERENCES`: creates a foreign-key link to another table.
- `ON DELETE CASCADE`: if the referenced row is deleted, delete these rows too.

Part B — Basic SELECT queries (section 1 & 3)

1. Select all students

```sql
SELECT * FROM student;
```

What it does: shows every column for every student. `*` means "all columns".

2. Select only names and emails, sorted by name

```sql
SELECT name, email FROM student ORDER BY name;
```

Explain: `SELECT name, email` picks columns. `ORDER BY name` sorts rows by name alphabetically.

3. Filtered select (WHERE)

```sql
SELECT name, birthdate FROM student WHERE birthdate >= '2002-01-01';
```

Explain: `WHERE` keeps only rows that match a condition (here, students born in or after 2002).

4. LIMIT and OFFSET (pagination)

```sql
SELECT * FROM student ORDER BY student_id LIMIT 2 OFFSET 1;
```

Explain: `LIMIT 2` returns at most 2 rows. `OFFSET 1` skips the first row.

Part C — INSERT / UPDATE / DELETE with RETURNING (section 3)

1. Insert and get back the new id immediately

```sql
INSERT INTO student (name, email, birthdate) VALUES ('Deepa','deepa@example.com','2004-03-12') RETURNING student_id, name;
```

Explain: `RETURNING` makes the `INSERT` return the inserted row (or columns) right away.

2. Update and return the changed row

```sql
UPDATE student SET email = 'alice.new@example.com' WHERE student_id = 1 RETURNING *;
```

3. Delete with RETURNING

```sql
DELETE FROM student WHERE student_id = 4 RETURNING name;
```

Part D — Joins (section 3: INNER, LEFT, RIGHT, FULL, CROSS, SELF)

1. INNER JOIN: students with their enrollments (only matching rows)

```sql
SELECT s.student_id, s.name, e.course_id, c.title, e.score
FROM student s
JOIN enrollment e ON s.student_id = e.student_id
JOIN course c ON e.course_id = c.course_id;
```

Explain: `JOIN` connects rows in two tables where the `ON` condition matches. `s` and `e` are short names (aliases) so we write less.

2. LEFT JOIN: all students, show course if they have one (NULL if none)

```sql
SELECT s.student_id, s.name, c.title
FROM student s
LEFT JOIN enrollment e ON s.student_id = e.student_id
LEFT JOIN course c ON e.course_id = c.course_id
ORDER BY s.student_id;
```

Explain: `LEFT JOIN` keeps every row from the left table (`student`) and adds matching course info when present. If there's no match, the course columns will be `NULL`.

3. SELF JOIN example (student mentoring another student) — small demo

```sql
-- make temporary example table with manager_id
ALTER TABLE student ADD COLUMN mentor_id INT;
UPDATE student SET mentor_id = 2 WHERE student_id = 1; -- Alice's mentor is Bob

SELECT a.name AS mentor, b.name AS mentee
FROM student b
JOIN student a ON b.mentor_id = a.student_id;
```

Explain: a `SELF JOIN` treats the same table as two different tables to compare rows inside it.

Part E — Subqueries and correlated subqueries

1. Subquery: find students in the course with id=1

```sql
SELECT name FROM student WHERE student_id IN (SELECT student_id FROM enrollment WHERE course_id = 1);
```

Explain: the inner query finds student IDs who are in course 1; the outer query gets names for those IDs.

2. Correlated subquery: find students who scored above the average in their course

```sql
SELECT s.name, e.course_id, e.score
FROM enrollment e
JOIN student s ON e.student_id = s.student_id
WHERE e.score > (
  SELECT AVG(score) FROM enrollment WHERE course_id = e.course_id
);
```

Explain: the inner `SELECT AVG(score)` uses `e.course_id` from the outer query — it runs per row and is "correlated".

Part F — Aggregates and GROUP BY (section 3)

1. Count students per course

```sql
SELECT c.title, COUNT(e.student_id) AS student_count
FROM course c
LEFT JOIN enrollment e ON c.course_id = e.course_id
GROUP BY c.course_id, c.title;
```

Explain: `GROUP BY` groups rows by `course_id`; `COUNT` counts rows in each group.

2. HAVING (filter groups)

```sql
SELECT course_id, COUNT(*) AS cnt
FROM enrollment
GROUP BY course_id
HAVING COUNT(*) > 1;
```

Explain: `HAVING` is like `WHERE` but for groups — it filters group results.

Part G — Window functions (OVER, PARTITION BY)

1. Rank students per course by score (top N)

```sql
SELECT student_id, course_id, score,
  ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
FROM enrollment;

-- to get top 1 per course
SELECT * FROM (
  SELECT student_id, course_id, score,
    ROW_NUMBER() OVER (PARTITION BY course_id ORDER BY score DESC) AS rn
  FROM enrollment
) t WHERE rn = 1;
```

Explain: `OVER (PARTITION BY ...)` says: apply the function over groups of rows but keep each row; `ROW_NUMBER()` gives a rank within each course.

Part H — CTEs (WITH) and recursive example (section 3)

1. Simple CTE to find courses with more than 1 student

```sql
WITH course_counts AS (
  SELECT course_id, COUNT(*) AS cnt FROM enrollment GROUP BY course_id
)
SELECT * FROM course_counts WHERE cnt > 1;
```

Explain: `WITH` names the inside query (`course_counts`) and lets you use it in the main `SELECT`.

2. Recursive CTE short note (hierarchies)

- Recursive CTEs are used when data has parent-child relations and you want to walk the tree (example: categories or manager chains). We won't create a full recursive example here to keep things simple, but the pattern is `WITH RECURSIVE ...`.

Part I — DISTINCT ON, DISTINCT, LIMIT, OFFSET (Postgres specifics)

1. `DISTINCT ON` — keep the first row for each group

```sql
SELECT DISTINCT ON (course_id) course_id, student_id, score
FROM enrollment ORDER BY course_id, score DESC;
```

Explain: `DISTINCT ON (course_id)` returns one row per `course_id` — the first row according to the `ORDER BY` (so highest score per course here).

Part J — UPSERT: INSERT ON CONFLICT DO UPDATE

1. Upsert example: insert a student or update email if the student_id conflicts

```sql
INSERT INTO student (student_id, name, email) VALUES (1, 'Alice', 'alice@new.com')
ON CONFLICT (student_id) DO UPDATE SET email = EXCLUDED.email;
```

Explain: `ON CONFLICT (student_id)` handles the case when the inserted `student_id` already exists; `EXCLUDED` refers to the attempted insert row.

Part K — NULL handling: COALESCE, NULLIF, IS DISTINCT FROM

1. COALESCE gives the first non-null

```sql
SELECT name, COALESCE(NULLIF(email,''), 'no-email') AS contact FROM student;
```

Explain: `NULLIF(email,'')` returns NULL if email is empty string; `COALESCE(...,'no-email')` returns the first non-null value.

2. IS DISTINCT FROM compares NULLs safely

```sql
SELECT * FROM student WHERE email IS DISTINCT FROM 'alice@example.com';
```

Explain: `IS DISTINCT FROM` treats `NULL` as a comparable value (so `NULL` is distinct from any non-null value).

Part L — Grouping sets, ROLLUP, CUBE (short demo)

1. ROLLUP example (product, region style)

```sql
-- pretend we have a sales table; here is the pattern
SELECT course_id, enrollment_date, COUNT(*) FROM enrollment
GROUP BY ROLLUP(course_id, enrollment_date);
```

Explain: `ROLLUP` gives subtotals and totals for combinations of grouping columns.

Part M — Indexes and simple performance tips

1. Create a simple index on student email

```sql
CREATE INDEX idx_student_email ON student(email);
```

Explain: an index helps the database find rows faster when searching by `email`.

Part N — Backup and restore quick examples (section 6)

1. Logical backup (single database)

```powershell
pg_dump -U postgres -F c -d school_db -f school_db.dump
pg_restore -U postgres -d school_db_restored school_db.dump
```

2. Physical backup with pg_basebackup (for replication / PITR)

```powershell
pg_basebackup -D /var/lib/postgresql/backup -F tar -z -P -U replication_user
```

Explain: `pg_dump` saves data as SQL or custom format; `pg_basebackup` copies the database files (used for standby servers and PITR).

Part O — Monitoring quick queries (section 6)

```sql
SELECT pid, usename, application_name, state, query FROM pg_stat_activity WHERE state <> 'idle';
SELECT datname, numbackends, xact_commit, xact_rollback FROM pg_stat_database;
SELECT pid, locktype, relation::regclass, mode, granted FROM pg_locks JOIN pg_stat_activity USING (pid) WHERE NOT granted;
```

Explain: these show active sessions, per-database stats, and locks that are blocking.

Part P — Cleanup example (drop sample objects)

```sql
DROP TABLE IF EXISTS enrollment;
DROP TABLE IF EXISTS course;
DROP TABLE IF EXISTS student;
```

Explain: `DROP TABLE` deletes the table and its data. Use `IF EXISTS` to avoid errors if it is already gone.