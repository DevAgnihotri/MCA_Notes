# PostgreSQL Notes (Simple English)

## Table of Contents

- [1. PostgreSQL Fundamentals](#1-postgresql-fundamentals)
  - [What is PostgreSQL](#what-is-postgresql)
  - [PostgreSQL architecture](#postgresql-architecture)
    - [Postmaster & background processes](#postmaster--background-processes)
    - [Shared buffers, WAL, storage overview](#shared-buffers-wal-storage-overview)
  - [Database objects](#database-objects)
  - [System catalogs](#system-catalogs)
  - [Connecting to PostgreSQL](#connecting-to-postgresql)
- [2. Data Types](#2-data-types)
  - [Scalar types](#scalar-types)
  - [Date / Time types](#date--time-types)
  - [JSON vs JSONB](#json-vs-jsonb)
  - [Array type](#array-type)
  - [Network types & UUID](#network-types--uuid)
  - [Composite & ENUM types](#composite--enum-types)
- [3. SQL Operations in PostgreSQL](#3-sql-operations-in-postgresql)

  - [CREATE / ALTER / DROP](#create--alter--drop)
  - [INSERT / UPDATE / DELETE / SELECT](#insert--update--delete--select)
  - [PostgreSQL-specific clauses](#postgresql-specific-clauses)
    - [RETURNING](#returning)
    - [DISTINCT ON](#distinct-on)
    - [LIMIT, OFFSET, FETCH](#limit-offset-fetch)
    - [WITH (CTE and recursive CTE)](#with-cte-and-recursive-cte)
  - [Joins](#joins)
  - [Subqueries & correlated subqueries](#subqueries--and-correlated-subqueries)
  - [Aggregate & window functions](#aggregate--window-functions)
  - [Upsert: INSERT ON CONFLICT](#upsert-insert-on-conflict)
  - [Null handling](#null-handling)
  - [Grouping sets (ROLLUP, CUBE)](#grouping-sets)

- [4. Constraints & Keys](#4-constraints--keys)

  - [PRIMARY / FOREIGN / UNIQUE / CHECK / NOT NULL](#primary--foreign--unique--check--not-null)
  - [Deferrable and immediate constraints](#deferrable-and-immediate-constraints)
  - [Referential integrity](#referential-integrity)

- [5. Functions, Procedures & Triggers](#5-functions-procedures--triggers)

  - [Writing SQL and PL/pgSQL functions](#writing-sql-and-plpgsql-functions)
  - [Input/output params and control structures](#inputoutput-params-and-control-structures)
  - [RETURN QUERY, SETOF, CURSOR](#return-query-setof-cursor)
  - [Triggers & event triggers](#triggers--event-triggers)
  - [FUNCTION vs PROCEDURE](#function-vs-procedure)

- [6. Administration (DBA Topics)](#6-administration-dba-topics)
  - [Role & user management](#role--user-management)
  - [Managing privileges & ownership](#managing-privileges--ownership)
  - [Configuration files](#configuration-files)
    - [postgresql.conf](#postgresqlconf)
    - [pg_hba.conf and pg_ident.conf](#pg_hbaconf-and-pg_identconf)
  - [WAL, Checkpoints & bgwriter](#wal-checkpoints--bgwriter)
  - [Backup & restore](#backup--restore)
  - [Tablespaces](#tablespaces)
  - [Replication (logical & streaming)](#replication-logical--streaming)
  - [PITR (Point-In-Time Recovery)](#pitr-point-in-time-recovery)
  - [Managing connections & limits](#managing-connections--limits)
  - [Monitoring views (pg_stat_activity etc.)](#monitoring-views)

---

## 1. PostgreSQL Fundamentals

This section explains what PostgreSQL is and why we study it. Read these basics first so the rest of the notes make sense.

### What is PostgreSQL

- PostgreSQL is a free, open-source database system. It stores data and lets programs ask for it using SQL.
- Main advantages: reliable, works well with big data, supports many features (transactions, indexes, JSON, extensions).
- Used by small apps and big companies because it is powerful and can be extended.

Example: A website can save user accounts, posts, and comments in PostgreSQL.

---

### PostgreSQL architecture

Why we study architecture: understanding the parts helps you know how PostgreSQL keeps data safe, fast, and available.

PostgreSQL uses a server process and helper processes to manage data and keep it safe.

#### Postmaster & background processes

- The `postmaster` (main server process) starts and watches other worker processes.
- Background processes include:
  - `WAL writer` (writes the write-ahead log to disk),
  - `checkpointer` (makes sure data files and WAL are in sync),
  - `autovacuum` (cleans up dead rows so tables stay fast),
  - `bgwriter` (background writer for dirty pages).

These helpers run automatically; they keep the database healthy without user action.

#### Shared buffers, WAL, and storage overview

- `Shared buffers` are an in-memory area where PostgreSQL keeps recently used table pages for fast reads and writes.
- `WAL` (Write-Ahead Log) records every change before it is applied. If the server crashes, WAL helps recover data.
- Data files store the actual table rows on disk. The combination of buffers and WAL makes PostgreSQL safe and fast.

Example: When you insert a row, PostgreSQL writes the change to WAL first, then updates the shared buffers, and later the background writer flushes it to disk.

---

### Database objects: database, schema, table, sequence, view, index

Why database objects matter: they are the building blocks you will use to design and store data (tables, indexes, views, etc.).

- `Database`: a top-level container for data (many databases can live in one server).
- `Schema`: a namespace inside a database to group tables and other objects.
- `Table`: stores rows and columns (the main data container).
- `Sequence`: generates unique numbers (useful for `serial` primary keys).
- `View`: a saved SELECT query that behaves like a table.
- `Index`: speeds up lookups on columns (like an index in a book).

Example SQL:

```sql
CREATE TABLE student (id SERIAL PRIMARY KEY, name VARCHAR(100));
CREATE INDEX idx_student_name ON student(name);
CREATE VIEW v_students AS SELECT id, name FROM student;
```

---

### PostgreSQL system catalogs (pg_class, pg_attribute, etc.)

Why catalogs are useful: catalogs are special internal tables that tell you what objects and columns exist in the database.

- PostgreSQL stores metadata in system catalogs (special tables) like `pg_class` and `pg_attribute`.
- `pg_class` lists tables and indexes; `pg_attribute` lists columns for each table.
- You can query these catalogs to learn about database objects.

Example: find column names for a table:

```sql
SELECT attname FROM pg_attribute WHERE attrelid = 'student'::regclass AND attnum > 0;
```

---

### Connecting to PostgreSQL (psql, pgAdmin, connection strings)

Why connecting matters: you use tools like `psql` or `pgAdmin` to run SQL and manage your databases — this is how you interact with PostgreSQL.

- `psql` is the command-line tool to connect to PostgreSQL and run SQL.
- `pgAdmin` is a graphical tool to manage databases with a visual interface.
- A connection string looks like: `postgresql://user:password@host:port/dbname`.

Example `psql` command:

```powershell
powershell> psql -h localhost -U postgres -d school_db
```

---

## 2. Data Types

Why data types matter: data types decide what kind of information a column can hold and affect storage, speed, and correctness.

PostgreSQL supports many data types. Below are common types with short, simple notes and examples.

### Scalar types

Why scalar types: use these for single simple values like numbers, text, and booleans — the most common columns in tables.

- `integer` (INT): whole numbers. Example: `age INT`.
- `serial` / `bigserial`: auto-incrementing integer (backs a sequence).
- `float`, `real`, `double precision`: for decimal numbers.
- `boolean`: `TRUE` / `FALSE`.
- `char(n)`, `varchar(n)`, `text`: for short and long text.

Example:

```sql
CREATE TABLE person (id SERIAL PRIMARY KEY, name TEXT, age INT, active BOOLEAN);
```

---

### Date / Time types

Why date/time types: they let you store dates and times correctly and do calculations like adding days or comparing timestamps.

- `DATE`: store a date (year-month-day).
- `TIME`: store a time of day.
- `TIMESTAMP` (with or without time zone): store date and time.
- `INTERVAL`: a span of time (like "2 days").

Example:

```sql
SELECT now(); -- returns current timestamp
SELECT '2025-11-30'::date + INTERVAL '7 days';
```

---

### JSON and JSONB — differences and performance

Why JSON/JSONB: JSON lets you store flexible structured data; `JSONB` is faster for searching and indexing JSON content.

- `JSON`: stores JSON text; PostgreSQL keeps it as text and checks syntax.
- `JSONB`: stores JSON in a binary format that is faster to query and index.
- Use `JSONB` when you will search or index JSON fields; use `JSON` only when you need the exact original text.

Example: store a user profile

```sql
CREATE TABLE profile (id SERIAL PRIMARY KEY, data JSONB);
INSERT INTO profile (data) VALUES ('{"city":"Delhi","age":22}');
SELECT data->>'city' AS city FROM profile;
```

---

### Array data type and array functions

Why arrays: arrays let one column hold a small list of values (like tags) when that is simpler than a separate table.

- PostgreSQL supports arrays like `integer[]` or `text[]` to store multiple values in one column.
- Useful functions: `unnest()` to expand array into rows, `array_length()` to get size.

Example:

```sql
CREATE TABLE survey (id SERIAL, tags TEXT[]);
INSERT INTO survey (tags) VALUES (ARRAY['easy','beginner']);
SELECT unnest(tags) FROM survey;
```

---

### UUID, CIDR, INET, MACADDR

Why these special types: they store identifiers, IP addresses, and MAC addresses in a compact, validated form.

- `UUID`: a universal unique id (good for distributed systems).
- `CIDR`, `INET`: store IP networks and addresses.
- `MACADDR`: store Ethernet MAC addresses.

Example:

```sql
CREATE TABLE devices (id UUID DEFAULT gen_random_uuid(), ip INET, mac MACADDR);
```

Note: `gen_random_uuid()` requires the `pgcrypto` extension or `uuid-ossp` depending on the setup.

---

### Composite and custom data types

Why composite types: they let you group related fields together into a single column type for clarity and reuse.

- You can create a composite type that groups multiple fields into one column type.
- Useful when you want a column to hold a small structured value.

Example:

```sql
CREATE TYPE full_name AS (first TEXT, last TEXT);
CREATE TABLE person2 (id SERIAL, name full_name);
INSERT INTO person2 (name) VALUES (ROW('Rita','Kumar'));
```

---

### Enumerated (ENUM) types

Why ENUMs: use ENUM when a column should only have a small set of allowed values (like status flags).

- `ENUM` defines a set of allowed text values (like a small fixed list).
- Good for small, unchanging sets (status = 'new','open','closed').

Example:

```sql
CREATE TYPE order_status AS ENUM ('new','processing','shipped','delivered');
CREATE TABLE orders (id SERIAL, status order_status DEFAULT 'new');
```

---

If you want, I can:

- Add short examples file `sq_examples_postgres.md` with `CREATE TABLE` and `INSERT` statements to try locally in PostgreSQL.
- Expand any topic further (like WAL internals or autovacuum tuning) in simple language.

---

## 3. SQL Operations in PostgreSQL

This section shows the common SQL commands you will use. Each short explanation is followed by examples.

### CREATE / ALTER / DROP

- `CREATE` makes new objects (databases, schemas, tables).
- `ALTER` changes existing objects (add column, change type).
- `DROP` removes objects (be careful — this deletes data).

Examples:

```sql
CREATE DATABASE school_db;
CREATE SCHEMA hr;
CREATE TABLE hr.employee (id SERIAL PRIMARY KEY, name TEXT, salary NUMERIC);
ALTER TABLE hr.employee ADD COLUMN hired DATE;
DROP TABLE hr.employee;
```

### INSERT / UPDATE / DELETE / SELECT

- `INSERT` adds rows, `UPDATE` changes rows, `DELETE` removes rows, `SELECT` reads rows.

Examples:

```sql
INSERT INTO hr.employee (name, salary) VALUES ('Asha', 50000);
UPDATE hr.employee SET salary = salary * 1.05 WHERE id = 1;
DELETE FROM hr.employee WHERE id = 1;
SELECT * FROM hr.employee WHERE salary > 40000;
```

### PostgreSQL-specific clauses

#### RETURNING

- `RETURNING` gives back rows changed by `INSERT`/`UPDATE`/`DELETE` so you can use them immediately.

Example:

```sql
INSERT INTO hr.employee (name, salary) VALUES ('Rita', 45000) RETURNING id, name;
```

#### DISTINCT ON

- `DISTINCT ON (col)` keeps the first row for each value of `col` (Postgres-specific helpful trick).

Example:

```sql
SELECT DISTINCT ON (course_id) course_id, student_id, score
FROM Enrollment ORDER BY course_id, score DESC;
```

#### LIMIT, OFFSET, FETCH

- Use `LIMIT` (or `FETCH`) to get a subset of rows; `OFFSET` skips rows (useful for pagination).

Example:

```sql
SELECT * FROM Student ORDER BY name LIMIT 10 OFFSET 20;
```

#### WITH (CTE and recursive CTE)

- `WITH` names a subquery (CTE). `WITH RECURSIVE` can loop for hierarchical data.

Example:

```sql
WITH top_courses AS (
  SELECT course_id, COUNT(*) AS cnt FROM Enrollment GROUP BY course_id
)
SELECT * FROM top_courses WHERE cnt > 5;
```

### Joins (INNER, LEFT, RIGHT, FULL, CROSS, SELF)

- `INNER JOIN`: rows where match exists in both tables.
- `LEFT JOIN`: keep all left rows; unmatched right columns are NULL.
- `RIGHT JOIN`: keep all right rows; unmatched left columns are NULL.
- `FULL JOIN`: keep rows when match on either side.
- `CROSS JOIN`: cartesian product (every row × every row).
- `SELF JOIN`: join table to itself (useful for hierarchies).

Example:

```sql
SELECT s.name, e.course_id FROM Student s JOIN Enrollment e ON s.student_id = e.student_id;
```

### Subqueries and correlated subqueries

- Subquery: a query inside another query (can return value(s)).
- Correlated subquery: inner query uses outer query values and runs per row.

Example (correlated):

```sql
SELECT s.name FROM Student s WHERE EXISTS (
  SELECT 1 FROM Enrollment e WHERE e.student_id = s.student_id AND e.score > 90
);
```

### Aggregate & window functions (OVER, PARTITION BY)

- Aggregates (`SUM`, `AVG`, `COUNT`) summarize groups.
- Window functions (`OVER(...)`) compute values across rows without collapsing them.

Examples:

```sql
SELECT course_id, AVG(score) FROM Enrollment GROUP BY course_id;
SELECT student_id, score, RANK() OVER (PARTITION BY course_id ORDER BY score DESC) FROM Enrollment;
```

### Upsert: INSERT ON CONFLICT DO UPDATE

- Upsert lets you insert or update if a unique conflict occurs.

Example:

```sql
INSERT INTO student (student_id, name) VALUES (1, 'Asha')
ON CONFLICT (student_id) DO UPDATE SET name = EXCLUDED.name;
```

### Null handling (IS DISTINCT FROM, COALESCE, NULLIF)

- `IS DISTINCT FROM` treats `NULL` safely when comparing.
- `COALESCE(a,b)` returns the first non-null value.
- `NULLIF(a,b)` returns `NULL` if `a=b`, else `a`.

Examples:

```sql
SELECT COALESCE(nickname, name) FROM student;
SELECT * FROM t WHERE a IS DISTINCT FROM b;
```

### Grouping sets: GROUPING SETS, ROLLUP, CUBE

- These let you get multiple grouping levels in one query (useful for reports).

Example:

```sql
SELECT product, region, SUM(sales) FROM sales
GROUP BY ROLLUP (product, region);
```

---

## 4. Constraints & Keys

This section explains how PostgreSQL enforces data rules and relationships.

### PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK, NOT NULL

- `PRIMARY KEY`: unique identifier for rows (cannot be NULL).
- `FOREIGN KEY`: link to another table's primary key (enforces relationships).
- `UNIQUE`: no duplicate values allowed.
- `CHECK`: a custom rule (e.g., `age >= 0`).
- `NOT NULL`: column must have a value.

Examples:

```sql
CREATE TABLE course (id SERIAL PRIMARY KEY, title TEXT NOT NULL);
CREATE TABLE enrollment (
  id SERIAL,
  student_id INT REFERENCES student(student_id),
  course_id INT REFERENCES course(id),
  grade INT CHECK (grade BETWEEN 0 AND 100)
);
```

### Deferrable and immediate constraints

- Constraints can be `DEFERRABLE` so they are checked at transaction end instead of immediately.
- `SET CONSTRAINTS ... DEFERRED` postpones checks (useful for complex transactions).

Example:

```sql
ALTER TABLE enrollment ADD CONSTRAINT fk_student FOREIGN KEY (student_id) REFERENCES student(student_id) DEFERRABLE INITIALLY IMMEDIATE;
-- inside a transaction you can set it deferred
BEGIN;
SET CONSTRAINTS fk_student DEFERRED;
-- make changes that temporarily break the FK
COMMIT;
```

### Referential integrity in PostgreSQL

- Referential integrity means the database keeps relationships correct (foreign keys prevent or cascade deletes/updates).
- Use `ON DELETE CASCADE` or `ON UPDATE SET NULL` to control behavior when referenced rows change.

Example:

```sql
FOREIGN KEY (student_id) REFERENCES student(student_id) ON DELETE CASCADE
```

---

## 5. Functions, Procedures & Triggers

This section covers writing code that runs inside the database for logic, automation, and performance.

### Writing SQL and PL/pgSQL functions

- PostgreSQL supports SQL functions and `PL/pgSQL` (a simple procedural language).
- Functions can return values and be used in queries.

Example (PL/pgSQL function):

```sql
CREATE FUNCTION add_numbers(a INT, b INT) RETURNS INT AS $$
BEGIN
  RETURN a + b;
END;
$$ LANGUAGE plpgsql;
SELECT add_numbers(2,3);
```

### Input and output parameters (IN, OUT, INOUT)

- `IN` parameters are inputs; `OUT` parameters are returned; `INOUT` are both.

Example:

```sql
CREATE FUNCTION swap_vals(INOUT a INT, INOUT b INT) AS $$
BEGIN
  RETURN; -- INOUT values are returned automatically
END;
$$ LANGUAGE plpgsql;
```

### Control structures: IF, LOOP, WHILE, FOR, EXIT, RAISE

- PL/pgSQL supports normal programming constructs to run logic.

Example:

```sql
CREATE FUNCTION count_to(n INT) RETURNS VOID AS $$
DECLARE i INT := 1;
BEGIN
  WHILE i <= n LOOP
    RAISE NOTICE 'Number: %', i;
    i := i + 1;
  END LOOP;
END;
$$ LANGUAGE plpgsql;
```

### RETURN QUERY, SETOF, CURSOR

- `RETURN QUERY` and `SETOF` let functions return multiple rows.
- `CURSOR` is useful for row-by-row processing.

Example:

```sql
CREATE FUNCTION recent_students() RETURNS SETOF student AS $$
BEGIN
  RETURN QUERY SELECT * FROM student ORDER BY student_id DESC LIMIT 10;
END;
$$ LANGUAGE plpgsql;
```

### Triggers — BEFORE/AFTER INSERT/UPDATE/DELETE

- Triggers run automatically when rows change. Use them for auditing or automatic fields.

Example:

```sql
CREATE FUNCTION set_created_at() RETURNS trigger AS $$
BEGIN
  NEW.created_at := CURRENT_TIMESTAMP;
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_set_created_at BEFORE INSERT ON student FOR EACH ROW EXECUTE FUNCTION set_created_at();
```

### Event triggers (DDL triggers)

- Event triggers fire on DDL events (like CREATE TABLE) and help audit or prevent changes.

### Differences: FUNCTION vs PROCEDURE

- `FUNCTION` returns values and can be used in queries. `PROCEDURE` (Postgres 11+) does not return a value and is called with `CALL`.

Example:

```sql
CREATE PROCEDURE do_cleanup() LANGUAGE SQL AS $$
  DELETE FROM temp_table WHERE created_at < NOW() - INTERVAL '1 day';
$$;
CALL do_cleanup();
```

---

If you want, I can now:

- Create `sq_examples_postgres.md` with `CREATE TABLE` + `INSERT` sample data and runnable examples for sections 3–5.
- Or expand any subsection into more detail (examples, tips, and best practices).

Tell me which option you prefer and I'll continue.

---

## 6. Administration (DBA Topics)

This section covers common DBA tasks and why they matter in simple language.

### Role & user management (CREATE ROLE, GRANT, REVOKE)

- Roles and users control who can do what in the database. Think of a role as a job: "reader", "writer", "admin".
- `CREATE ROLE` or `CREATE USER` makes a new role. `GRANT` gives privileges; `REVOKE` removes them.

Examples:

```sql
CREATE ROLE reader NOINHERIT;
CREATE USER alice WITH PASSWORD 'secret';
GRANT reader TO alice;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO reader;
```

### Managing privileges and ownership

- Ownership decides who can `ALTER` or `DROP` an object. Use `ALTER TABLE ... OWNER TO ...` to change.
- `GRANT` / `REVOKE` control access to tables, functions, schemas, and more.

Example:

```sql
ALTER TABLE student OWNER TO admin;
GRANT INSERT, UPDATE ON student TO writer_role;
```

### Configuration files: postgresql.conf, pg_hba.conf, pg_ident.conf

- `postgresql.conf` holds server settings (memory, WAL settings, logging, max connections).
- `pg_hba.conf` controls which hosts/users can connect and how they authenticate (password, trust, md5).
- `pg_ident.conf` maps external system usernames to database roles.

Tip: After editing `postgresql.conf` or `pg_hba.conf`, reload or restart the server:

```powershell
-- Reload config without full restart
psql -c "SELECT pg_reload_conf();"
```

### WAL (Write Ahead Log) concepts

- WAL safely records changes before they are applied. This helps recover data after a crash.
- WAL files live in the `pg_wal` directory (formerly `pg_xlog`).

Why it matters: without WAL, recovery and replication would not be safe.

### Checkpoints and bgwriter

- `checkpointer` writes dirty pages from shared buffers to disk periodically.
- `bgwriter` helps write changed pages in the background to avoid big pauses.

Example: tuning `checkpoint_timeout` in `postgresql.conf` affects how often checkpoints run.

### Backup and restore: pg_dump, pg_restore, pg_basebackup

- `pg_dump` creates logical backups (SQL) for a single database. Use `pg_restore` to load from a custom-format dump.
- `pg_basebackup` creates a physical copy of the data directory for full backups (used with streaming replication).

Examples:

```powershell
psql -U postgres -c "\l"        -- list databases
pg_dump -U postgres -F c school_db > school_db.dump
pg_restore -U postgres -d new_db school_db.dump
pg_basebackup -D /var/lib/postgresql/backup -F tar -z -P -U replication_user
```

### Tablespaces

- Tablespaces let you place data files on different disks (useful for performance or storage planning).

Example:

```sql
CREATE TABLESPACE fastspace LOCATION '/mnt/fast_ssd';
CREATE TABLE bigdata (id BIGSERIAL, data TEXT) TABLESPACE fastspace;
```

### Logical and streaming replication

- Streaming replication copies WAL to standby servers in real time (physical replication).
- Logical replication sends logical changes (tables/rows) to subscribers and allows different schema on subscriber.

Simple streaming setup steps (high level):

1. Enable WAL shipping and set `wal_level = replica` or `logical` in `postgresql.conf`.
2. Create a replication user with `REPLICATION` privilege.
3. Use `pg_basebackup` to copy primary to standby and configure `recovery.conf`/`standby.signal`.

### PITR (Point-In-Time Recovery)

- With WAL and base backups you can restore the database to a specific time (PITR). Useful to undo mistakes.

High-level steps:

1. Take a base backup (pg_basebackup).
2. Keep WAL archives (`archive_command`) and the WAL files.
3. Restore base backup and replay WAL up to desired timestamp.

### Managing connections and connection limits

- `max_connections` in `postgresql.conf` sets the maximum client connections.
- Use a connection pooler (PgBouncer) in production to handle many client requests efficiently.

Example: show current connections

```sql
SELECT count(*) FROM pg_stat_activity;
SELECT pid, usename, application_name, state FROM pg_stat_activity ORDER BY backend_start DESC LIMIT 20;
```

### Monitoring using pg_stat_activity, pg_stat_database, pg_locks

- `pg_stat_activity` shows current sessions and running queries.
- `pg_stat_database` gives database-level stats (transactions, commits, rollbacks).
- `pg_locks` shows locks held and waiting (useful to diagnose blocking).

Examples:

```sql
SELECT * FROM pg_stat_activity WHERE state <> 'idle';
SELECT datname, numbackends, xact_commit, xact_rollback FROM pg_stat_database;
SELECT pid, locktype, relation::regclass, mode, granted FROM pg_locks JOIN pg_stat_activity USING (pid) WHERE NOT granted;
```

---

If you want, I will now:

- Create `sq_examples_postgres.md` with `CREATE TABLE` and `INSERT` sample data and runnable queries covering sections 1–6.
- Or expand any of the DBA topics into deeper, simple explanations with commands and examples.

Tell me which you prefer and I'll continue.
