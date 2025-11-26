# Database Systems — Basics (Unit 1)

## Table of Contents

- [1. Introduction to Database Systems](#1-introduction-to-database-systems)
  - [What is Data, Information, Metadata?](#what-is-data-information-metadata)
  - [What is a Database?](#what-is-a-database)
  - [Why Database instead of File System?](#why-database-instead-of-file-system)
  - [Drawbacks of File Systems](#drawbacks-of-file-systems)
  - [DBMS Definition and Role](#dbms-definition-and-its-role)
  - [Characteristics of DBMS](#characteristics-of-dbms)
  - [Advantages of DBMS over File System](#advantages-of-dbms-over-file-system)
  - [Applications of DBMS](#applications-of-dbms)
  - [Data Models](#data-models)
  - [4. Relational Model](#4-relational-model)
    - [Relational Data Structure](#relational-data-structure)
    - [Relational Keys](#relational-keys)
    - [Relational Integrity Constraints](#relational-integrity-constraints)
    - [Relational Algebra](#relational-algebra-simple-explanation--examples)
  - [6. Normalization](#6-normalization)
    - [Need for Normalization](#need-for-normalization)
    - [Functional Dependencies (FDs)](#functional-dependencies-fds)
    - [Anomalies in Unnormalized Data](#anomalies-in-unnormalized-data)
    - [Normal Forms (1NF–5NF)](#types-of-normal-forms)
    - [Decomposition and Denormalization](#decomposition)
  - [7. Database Security & Authorization](#7-database-security--authorization)
  - [8. NoSQL Databases](#8-nosql-databases)
  - [9. Big Data & Data Warehousing](#9-big-data--data-warehousing)
- [2. Database Architecture & Data Abstraction](#2-database-architecture--data-abstraction)
  - [Levels of Data Abstraction](#levels-of-data-abstraction)
  - [Data Independence](#data-independence)
  - [DBMS Architecture (1/2/3-tier)](#dbms-architecture-12-3-tier)
  - [DBMS Components](#dbms-components)
- [3. Entity-Relationship (ER) Model](#3-entity-relationship-er-model)
  - [Basic Concepts: Entities, Attributes, Keys](#basic-concepts-entities-attributes-keys)
  - [Relationships and Cardinality](#relationships-and-cardinality)
  - [ER Diagram Notations](#er-diagram-notations)
  - [Weak Entities, Specialization, Aggregation](#weak-entities-specialization-aggregation)
  - [Converting ER Diagrams to Tables](#converting-er-diagrams-to-tables)

---

## 1. Introduction to Database Systems

### What is Data, Information, Metadata?

- Data: Raw facts or numbers without meaning by themselves. Examples: `24`, `Alice`, `1001`.
- Information: Data that is processed and given meaning. Example: "Alice scored 24 on the test" is information.
- Metadata: Data about data. It describes structure or rules, for example column names, data types, or descriptions (like "column `age` is an integer"). Metadata helps people and programs understand stored data.

### What is a Database?

- A database is an organized collection of data stored so it can be easily accessed, managed, and updated. It groups related information together so software and people can find answers quickly.
- Example: A university database stores student records, courses, and grades in a structured way instead of many separate text files.

### Quick real-world story (simple)

Think of a library at school. If every librarian kept notes in separate notebooks, finding who borrowed a book is slow. A database keeps one clean list so librarians can find who has a book fast.

Small table: `Books` (example)

| book_id | title              | author   | copies |
| ------- | ------------------ | -------- | ------ |
| 101     | Introduction to DB | J. Smith | 3      |
| 102     | Learning SQL       | A. Kumar | 2      |

This shows how a table stores many items of the same type and makes searching easy.

### Why Database instead of File System?

- A simple file system stores data in separate files with little structure. Databases organize data, enforce rules, and make it easy to search and change data safely.
- Databases offer better ways to prevent errors, share data, and run queries (searches) quickly.

### Drawbacks of File Systems

- **Redundancy:** Same data stored in many files (wastes space).
- **Inconsistency:** Copies of the same data may not match (conflicting values).
- **Isolation:** Data is spread across files; combining it is hard.
- **Integrity Issues:** No easy way to enforce rules (like "age must be positive").
- These problems make large systems hard to maintain with file systems alone.

### DBMS Definition and its Role

- **DBMS (Database Management System):** Software that helps create, manage, and use databases. It provides tools to store data, run queries, and control access.
- **Role:** DBMS acts as an intermediary between applications/users and the physical data. It handles storage, retrieval, security, and consistency.

### Characteristics of DBMS

- **Self-describing nature:** The DBMS keeps metadata (data about data) in a catalog so the system knows structure and rules.
- **Data abstraction:** Users can work with a simplified view of data without seeing physical storage details.
- **Support for multiple views:** Different users can see different parts or views of data according to needs.
- **ACID properties:** Ensure reliable transactions:
  - Atomicity: a transaction is all or nothing.
  - Consistency: changes move database from one valid state to another.
  - Isolation: concurrent transactions do not interfere.
  - Durability: once committed, changes persist even after failures.

### Advantages of DBMS over File System

- Reduced redundancy and improved consistency.
- Easier data sharing and concurrent access control.
- Stronger data integrity and security controls.
- Powerful query languages (like SQL) for searching and reporting.
- Backup, recovery, and transaction support to protect data.

### Applications of DBMS

- **Banking:** Manage accounts, transactions, and customer data.
- **Airlines:** Reservation systems track seats and schedules.
- **University:** Student records, enrollment, and grades.
- **Online shopping:** Product catalogs, orders, and user accounts.
- Any system that needs organized, reliable, multi-user data storage.

### Data Models

- **Hierarchical Model:** Data arranged in a tree. Fast for fixed parent-child data but rigid.
- **Network Model:** More flexible graph structure allowing many-to-many links.
- **Relational Model:** Data stored in tables (relations); rows are records and columns are attributes. Most common today.
- **Object-Oriented Model:** Stores objects like in programming languages (objects with methods and attributes).
- **ER Model (Entity-Relationship):** A conceptual model used to design databases using entities and relationships before implementation.

---

### Section 1 — More Examples and a Simple Table

Here is a small example table and a simple exercise to make the ideas clearer.

Example table: `Student` (showing four rows)

| student_id | name   | birthdate  | age |
| ---------- | ------ | ---------- | --- |
| 1          | Alice  | 2002-05-12 | 23  |
| 2          | Bob    | 2001-11-02 | 24  |
| 3          | Carol  | 2003-01-30 | 22  |
| 4          | Deepak | 2000-08-14 | 25  |

Simple exercise:

- Show how `name` is information derived from data (strings), and `age` is derived from `birthdate` (a derived attribute).
- Try writing a one-line SQL query to list `name` and `age` for students older than 23:
  - `SELECT name, age FROM Student WHERE age > 23;`

## 2. Database Architecture & Data Abstraction

### Levels of Data Abstraction

- **Physical Level:** How data is actually stored on disk (files, indexes). This level is concerned with storage details.
- **Logical Level:** The schema of the whole database—tables, columns, relationships. It hides storage details and shows the structure used by applications.
- **View Level:** What each user or application sees. Views show only relevant data and can hide sensitive parts.

### Data Independence

- **Physical Data Independence:** The ability to change physical storage (like adding indexes or moving files) without changing the logical schema or applications.
- **Logical Data Independence:** The ability to change the logical schema (like adding a new column) without changing user views or application programs.
- Data independence makes systems easier to maintain and evolve.

### DBMS Architecture (1-tier, 2-tier, 3-tier)

- **1-tier (Single-tier):** Database and user interface on the same machine. Simple but not scalable.
- **2-tier (Client-Server):** Client application talks directly to a database server (e.g., a desktop app connecting to a DB server). Good for small networks.
- **3-tier (Three-tier):** Separates presentation (UI), application logic (business rules), and database. The middle tier (application server) improves scalability and security for web and enterprise apps.

### DBMS Components

- **Query Processor:** Interprets and executes database queries (like SQL). It parses queries, plans steps, and runs them efficiently.
- **Storage Manager:** Handles physical storage: files, indexes, and space allocation.
- **Transaction Manager:** Ensures ACID properties for transactions, handling commit and rollback.
- **Metadata Catalog (Data Dictionary):** Stores metadata—descriptions of tables, columns, types, constraints.
- **Buffer Manager:** Manages in-memory pages (buffers) to reduce disk I/O and speed up access.

---

### DBMS Components — Short Roles (very simple)

Here are each component in one short sentence and a tiny ASCII flow.

- **Query Processor:** Reads the SQL and decides how to get answers.
- **Storage Manager:** Keeps data on disk and reads/writes files.
- **Transaction Manager:** Makes sure many users can work without breaking data (ACID).
- **Metadata Catalog:** Keeps the list of tables, columns and rules so DBMS knows the structure.
- **Buffer Manager:** Keeps recently used data in memory to answer queries faster.

Tiny ASCII flow of a query:

```
User -> Query Processor -> Storage Manager -> Buffer Manager -> Disk
                 ^                                           |
                 |-------------------------------------------|
```

The arrows show that the query processor asks storage manager for pages; buffer manager gives pages if available, otherwise disk is used.

### Section 2 — Architecture Diagram and Example

Below is a simple ASCII diagram showing a 3-tier architecture and how a query flows.

Simple 3-tier ASCII diagram:

```
[Client/UI] -- HTTP --> [App Server / Business Logic] -- SQL --> [DBMS Server]
   |                         |                                |
 (web browser)           (validates input)                  (storage + query engine)
```

Example flow (short):

- A user on the client clicks "Show Grades".
- The app server creates a SQL query and sends it to the DBMS.
- The DBMS query processor plans the query and buffer manager reads pages from disk.
- The DBMS returns results to the app server, which formats them for the client.

Small note on buffers: if the `Student` table's pages are already in memory (buffer), the DBMS avoids disk I/O and returns results faster.

## 3. Entity-Relationship (ER) Model

### Basic Concepts: Entity, Entity Set

- **Entity:** A real-world object or concept with an identity (for example, a `Student` or `Course`).
- **Entity Set:** A group of similar entities (all students make the `Student` entity set).

### Attributes (Simple, Composite, Derived, Multivalued)

- **Simple attribute:** Cannot be divided (e.g., `age`).
- **Composite attribute:** Made of parts (e.g., `name` = `first_name` + `last_name`).
- **Derived attribute:** Can be calculated from other data (e.g., `age` derived from `birthdate`).
- **Multivalued attribute:** Can have multiple values (e.g., `phone_numbers`).

### Keys (Primary, Candidate, Super, Foreign)

- **Primary Key:** A chosen attribute (or set) that uniquely identifies an entity (e.g., `student_id`).
- **Candidate Key:** Any attribute (or set) that can uniquely identify entities. One candidate key is chosen as primary.
- **Super Key:** A set of attributes that can uniquely identify entities (possibly more attributes than needed).
- **Foreign Key:** An attribute that points to a primary key in another table to show a relationship.

### Relationships: Relationship Set, Degree, Mapping Cardinalities

- **Relationship Set:** A set of associations among entities (for example, `Enrollment` links `Student` and `Course`).
- **Degree:** Number of entity types in a relationship:
  - Unary (degree 1), Binary (degree 2), Ternary (degree 3).
- **Mapping Cardinalities:** How many entities relate to others:
  - 1:1 (one-to-one), 1:N (one-to-many), M:N (many-to-many).
- **Participation:** Whether all entities must participate:
  - Partial participation (some may not join) or Total participation (all must join).

### ER Diagram Notations

- Rectangles for entities, ovals for attributes, diamonds for relationships, and lines to connect them. Keys are underlined.

### Weak Entity Sets and Identifying Relationships

- **Weak Entity:** An entity that depends on another (owner) entity and has no full key on its own (example: `Dependent` depends on `Employee`).
- **Identifying Relationship:** Connects a weak entity to its owner; the weak entity's key includes the owner's key.

### Specialization, Generalization, Aggregation

- **Specialization:** Top-down process dividing an entity into sub-entities (e.g., `Employee` -> `Faculty`, `Staff`).
- **Generalization:** Bottom-up process combining sub-entities into a general entity.
- **Aggregation:** Treats a relationship as a higher-level entity when it needs to be related to others.

### Converting ER Diagram to Tables (Steps)

1. **Entities to Tables:** Create a table for each strong entity; attributes become columns. Use primary keys.
2. **Relationships:**
   - For 1:1 relationships, you can add the primary key of one table as a foreign key in the other.
   - For 1:N relationships, add the primary key of the "one" side as a foreign key in the "many" side.
   - For M:N relationships, create a new join table (association table) holding foreign keys to both related tables and any relationship attributes.
3. **Weak Entities:** Create a table that includes the owner entity's primary key as part of the weak entity's primary key.
4. **Attributes:** Map simple attributes to columns, handle multivalued attributes by making a separate table, and derived attributes are usually computed, not stored.

**Example:** A small ER to tables example:

- Entities: `Student(student_id, name)`, `Course(course_id, title)`
- Relationship: `Enrollment(student_id, course_id, grade)` — this `Enrollment` is the M:N join table.

Example conversion for a small `Library` ER where `Borrow` is M:N:

ER entities:

- `Book(book_id, title)`
- `Member(member_id, name)`
- `Borrow(member_id, book_id, borrow_date)` (M:N relationship turned table)

Sample rows (Borrow):

| member_id | book_id | borrow_date |
| --------- | ------- | ----------- |
| 201       | 101     | 2024-03-10  |
| 202       | 101     | 2024-03-12  |

This shows the join table contains foreign keys to both `Book` and `Member`.

---

## Quick Example SQL Snippet

```sql
-- Student table
CREATE TABLE Student (
  student_id INT PRIMARY KEY,
  name VARCHAR(100),
  birthdate DATE
);

-- Course table
CREATE TABLE Course (
  course_id INT PRIMARY KEY,
  title VARCHAR(200)
);

CREATE TABLE Enrollment (
  student_id INT,
  course_id INT,
  grade CHAR(2),
  PRIMARY KEY (student_id, course_id),
  FOREIGN KEY (student_id) REFERENCES Student(student_id),
  FOREIGN KEY (course_id) REFERENCES Course(course_id)
);
```

## 4. Relational Model

### Relational Data Structure

- **Relation (Table):** A relation is a table with rows and columns. Each table stores data about one type of thing, for example `Student` or `Course`.
- **Tuple (Row):** A tuple is one row in a relation. It represents a single record, e.g., one student.
- **Attribute (Column):** An attribute is a named column in a table, such as `student_id` or `name`.
- **Domain:** The domain is the set of allowed values for an attribute (for example the domain of `age` might be integers from 0 to 150).

### Relational Keys

- **Super Key:** A set of one or more attributes that can uniquely identify a tuple in a relation. Example: `{student_id, email}` may be a super key.
- **Candidate Key:** A minimal super key (no subset of it is a super key). A relation can have multiple candidate keys.
- **Primary Key:** A candidate key chosen by the designer as the main way to identify tuples (e.g., `student_id`).
- **Alternate Key:** A candidate key that is not chosen as primary (e.g., `email` if not primary).
- **Foreign Key:** An attribute in one relation that refers to the primary key of another relation. It creates a link between tables (e.g., `course_id` in `Enrollment`).
- **Composite Key:** A key made of two or more attributes together (e.g., `(student_id, course_id)` as the primary key of `Enrollment`).

### Relational Integrity Constraints

- **Domain Constraint:** Each attribute value must come from the attribute's domain (type and allowed values).
- **Key Constraint:** Primary (or candidate) keys must be unique; no two tuples can have the same key value(s).
- **Entity Integrity:** Primary key attributes cannot be NULL. This ensures each row can be identified.
- **Referential Integrity:** A foreign key must either be NULL (if allowed) or match a primary key value in the referenced table. This prevents broken links.

### Relational Algebra (Simple Explanation & Examples)

Relational algebra is a set of operations used to query relations (tables). These operations return new relations as results.

**Basic Operations:**

- **Select (σ):** Choose rows that satisfy a condition.
  - Example: `σ_{age > 20}(Student)` returns students older than 20.
- **Project (π):** Choose certain columns.
  - Example: `π_{name, student_id}(Student)` returns only name and id columns.
- **Union (∪):** Combine tuples from two relations with the same schema.
- **Set Difference (-):** Tuples in one relation but not in another.
- **Cartesian Product (×):** Combine every row of one relation with every row of another.
- **Rename (ρ):** Rename a relation or attributes for clarity.

**Derived Operations:**

- **Join:** Combine related tuples from two relations. Often written as `R ⨝ S`.
  - Example: `Student ⨝ Enrollment` links students with their enrollments.
- **Intersection:** Tuples common to two relations.
- **Division:** Useful for queries like "find students who took all courses in a set".
- **Assignment:** Store result of expression into a temporary relation name.

**Types of Joins:**

- **Inner Join:** Returns rows that have matching values in both tables.
- **Outer Join (Left/Right/Full):** Returns matching rows plus unmatched rows from left, right, or both sides with NULLs for missing values.
- **Natural Join:** Automatically joins on attributes with the same name, removing duplicate columns.
- **Equi Join:** Join using equality condition on specified attributes.
- **Theta Join:** General join using any comparison operator (like `>`, `<`, `=`).

### Examples of Algebraic Queries (Simple)

- Find names of students enrolled in course with id 101:
  - `π_{name}(Student ⨝_{Student.student_id = Enrollment.student_id} σ_{course_id = 101}(Enrollment))`
- List student ids who are not enrolled in any course (using set difference):
  - `π_{student_id}(Student) - π_{student_id}(Enrollment)`
- Find students who have taken every course in a set `C` (division use):
  - `Students ÷ CoursesInC` (conceptual; division returns students associated with all items in `CoursesInC`)

---

### Section 3 — ER Example + Conversion Steps (Worked)

Small ER example (ASCII) for `Student`, `Course`, `Enrollment`:

```
  [Student] ---< Enrollment >--- [Course]
    | student_id (PK)            | course_id (PK)
    | name                       | title
    | birthdate                  |
```

Conversion to tables (quick recap with sample rows):

- `Student(student_id PK, name, birthdate)`
- `Course(course_id PK, title)`
- `Enrollment(student_id FK, course_id FK, grade, PK(student_id,course_id))`

Sample rows (Enrollment):

| student_id | course_id | grade |
| ---------- | --------- | ----- |
| 1          | 101       | A     |
| 2          | 101       | B     |
| 1          | 102       | A-    |

This shows how M:N relationships become a join table with two foreign keys.

---

### Section 4 — Worked Relational Algebra Examples with SQL Equivalents

Let's use small sample tables to show step-by-step algebra and the matching SQL.

Sample tables:

`Student`
| student_id | name |
|------------|-------|
| 1 | Alice |
| 2 | Bob |
| 3 | Carol |

`Enrollment`
| student_id | course_id |
|------------|-----------|
| 1 | 101 |
| 2 | 101 |
| 1 | 102 |

Example 1 — Names of students in course 101:

- Relational algebra step-by-step:
  1. Select enrollments for `course_id = 101`: E1 = σ\_{course_id=101}(Enrollment)
     - E1 rows: (1,101), (2,101)
  2. Join with Student on `student_id`: R = Student ⨝\_{Student.student_id=E1.student_id} E1
     - R rows: (1,Alice,101), (2,Bob,101)
  3. Project the `name`: π\_{name}(R) => {Alice, Bob}
- SQL equivalent:
  - `SELECT s.name FROM Student s JOIN Enrollment e ON s.student_id = e.student_id WHERE e.course_id = 101;`

Example 2 — Students not enrolled in any course:

- Algebra:
  1. All student ids: A = π\_{student_id}(Student) => {1,2,3}
  2. Enrolled ids: B = π\_{student_id}(Enrollment) => {1,2}
  3. Difference: A - B => {3}
- SQL equivalent:
  - `SELECT student_id FROM Student WHERE student_id NOT IN (SELECT student_id FROM Enrollment);`

Example 3 — Division concept (students who took both 101 and 102):

- We want students who have taken all courses in set C = {101,102}.
- One approach using algebra and SQL idea:
  - Algebra (conceptual): `Students ÷ CoursesInC` returns students linked to every course in `CoursesInC`.
  - SQL equivalent (count method):
    - `SELECT e.student_id FROM Enrollment e WHERE e.course_id IN (101,102) GROUP BY e.student_id HAVING COUNT(DISTINCT e.course_id) = 2;`

---

## 6. Normalization

- **Need for Normalization:** Makes tables simpler, reduces repeated data, and prevents mistakes when updating data.
- **Functional Dependencies (FDs):** If A -> B, then value of A decides value of B. Example: `student_id -> name`.
- **Anomalies in Unnormalized Data:**
  - **Insertion anomaly:** Hard to add data without extra or empty fields.
  - **Deletion anomaly:** Deleting a row may remove other important data.
  - **Update anomaly:** Changing one value needs many row changes and can cause inconsistency.
- **Types of Normal Forms (simple):**
  - **1NF:** Remove repeating groups so each cell has one value.
  - **2NF:** Remove partial dependency — every non-key column depends on whole primary key.
  - **3NF:** Remove transitive dependency — non-key columns should not depend on other non-key columns.
  - **BCNF:** Stronger form of 3NF; every dependency's left side must be a key.
  - **4NF:** Handles multivalued dependencies (when one column has many independent values).
  - **5NF:** Deals with join dependencies when data must be split to remove redundancy.
- **Decomposition:**
  - **Lossless Decomposition:** Splitting a table so no data is lost when joining back.
  - **Dependency Preservation:** After splitting, we still can check original rules (FDs) without joining.
- **Denormalization:** Intentionally merge tables back (for speed) at the cost of some redundancy.

### Normalization — Examples and Walkthrough (simple)

Example (unnormalized table): `StudentEnroll`
| student_id | name | course_ids | course_names |
|------------|-------|------------------|---------------------|
| 1 | Alice | 101,102 | DB,Math |
| 2 | Bob | 101 | DB |

Problems here:

- `course_ids` contains multiple values in one cell (not 1NF).
- Hard to add a course for a student (insertion anomaly). Hard to remove one course without touching the row (deletion anomaly).

Step 1 — Convert to 1NF:

- Make each course a separate row in a proper `Enrollment` table.

`Enrollment` (1NF)
| student_id | course_id |
|------------|-----------|
| 1 | 101 |
| 1 | 102 |
| 2 | 101 |

Step 2 — Example of 2NF problem (partial dependency):
Suppose a table `OrderLine(order_id, product_id, product_name, quantity)` where primary key is `(order_id, product_id)`.

- `product_name` depends only on `product_id`, not on the full composite key — this is a partial dependency.
  Fix: move product details into `Product(product_id, product_name)` and keep `OrderLine(order_id, product_id, quantity)`.

Step 3 — Example of 3NF problem (transitive dependency):
Table: `Student(student_id, dept_id, dept_name)`

- `dept_name` depends on `dept_id`, which depends on `student_id` (student -> dept_id -> dept_name). This is transitive.
  Fix: create `Department(dept_id, dept_name)` and keep `Student(student_id, dept_id)`.

BCNF note (simple):

- BCNF is like 3NF but stricter: every determinant must be a candidate key. Use BCNF when a non-key attribute functionally determines part of the key.

Quick checklist when normalizing:

- Remove repeating groups (1NF).
- Remove partial dependencies (2NF).
- Remove transitive dependencies (3NF).
- Check special cases for BCNF, 4NF, 5NF only when needed.

## 7. Database Security & Authorization

- **Database Security Goals:** Keep data private (Confidentiality), correct (Integrity), and available when needed (Availability).
- **Authentication & Authorization:**
  - Authentication: check who you are (passwords, keys).
  - Authorization: decide what you can do (roles, permissions).
- **Privileges:** Use `GRANT` to give rights and `REVOKE` to take rights away.
- **Encryption techniques:** Store sensitive data encrypted and use secure connections so data cannot be read by others.
- **Database Auditing:** Keep logs of who did what so admins can check for mistakes or bad behavior.

## 8. NoSQL Databases

- **Need for NoSQL:** When data is very large, or has flexible structure, or needs very fast access, NoSQL can help.
- **Difference between SQL vs NoSQL:** SQL uses tables and fixed schemas; NoSQL is more flexible and can store documents, key-value pairs, columns, or graphs.
- **Types of NoSQL Databases:**
  - **Document-based:** Store JSON-like documents (example: MongoDB).
  - **Column-based:** Store by columns for very large tables (example: Cassandra).
  - **Key-Value:** Very fast lookups by key (example: Redis).
  - **Graph-based:** Store nodes and edges for relationships (example: Neo4j).
- **CAP Theorem (simple):** In a distributed system you can pick two: Consistency, Availability, Partition tolerance. You cannot guarantee all three at once.

## 9. Big Data & Data Warehousing

- **Concept of Data Warehouse:** A special database that stores cleaned, historical data for reporting and analysis.
- **OLTP vs OLAP:**
  - **OLTP (Online Transaction Processing):** Many small transactions (insert/update), used by apps.
  - **OLAP (Online Analytical Processing):** Big queries for reports and analysis on historical data.
- **Star Schema, Snowflake Schema:** Ways to design a data warehouse.
  - **Star schema:** One central fact table (numbers) with small dimension tables (labels) around it.
  - **Snowflake schema:** Dimension tables are normalized into more tables (looks like a snowflake).
- **ETL Process:** Extract data from sources, Transform it (clean and shape), Load into the warehouse.
- **Data Mining basics:** Find patterns and simple rules in large datasets (examples: frequent itemsets, simple classification).
