# random ques

## 📄 **2023 – Distributed Database System (KCA-045)**

## **SECTION A (Attempt all – 2×10=20)**

a) List features of relational data model.
b) What is transparencies in distributed database?
c) Differentiate between homogeneous & heterogeneous DDBMS.
d) Draw transaction state diagram.
e) Differentiate between shared lock & exclusive lock.
f) Discuss the role of client in client/server system.
g) What are the functions of Transaction Manager?
h) What do you understand by semi join?
i) What are the different strategies for designing distributed database?
j) Differentiate between full & partial replication in DDBMS.

---

## **SECTION B (Attempt any 3 – 10×3=30)**

a) Discuss distributed database system. Also explain the promises of DDBS.
b) Explain query processing. Also explain layers of query processing.
c) Discuss transaction. Explain ACID properties with example.
d) Discuss various reasons for failures in distributed systems.
e) Explain fundamental object concepts and models. Also explain abstract data types.

---

## **SECTION C**

### Q3 (Attempt any 1)

a) Discuss technical problems to realize full potential of DDBMS.
b) Architectural models for distributed DBMS.

### Q4 (Attempt any 1)

a) Objectives of query processing.
b) Query optimization & distributed cost model (with example).

### Q5 (Attempt any 1)

a) Serializability & timestamp-based concurrency control.
b) Deadlock handling & avoidance algorithms.

### Q6 (Attempt any 1)

a) Two-phase commit protocol.
b) Parallel DB architecture & shared memory architecture.

### Q7 (Attempt any 1)

a) (i) Inheritance
(ii) Object identity
b) OODBMS and comparison with ORDBMS

---

## 📄 **2022 – Distributed Database System (KCA-045)**

## **SECTION A (2×10=20)**

a) Why distributed databases are essential?
b) What is transaction log? Functions?
c) Explain view serializability.
d) Object vs entity (OO model vs ER).
e) Define recoverable, cascadeless & strict schedules.
f) Designing OO DB vs relational DB.
g) Define Moss concurrency protocol.
h) Backward vs forward recovery.
i) 2PL vs strict 2PL.
j) Types of failures in distributed DBMS.

---

## **SECTION B (10×3=30)**

a) Why recovery is complex in distributed DBMS?
b) Deadlock prevention vs avoidance + detection & recovery scheme.
c) Motivation behind parallel & distributed databases.
d) Object identifier (OID) – explain with pros/cons.
e) Link failure & network partitioning + recovery methods.

---

## **SECTION C**

### Q3

a) Homogeneous vs heterogeneous DB + architecture + query issues
b) Fragmentation with examples

### Q4

a) Prove 3PC is non-blocking
b) Objectives & phases of distributed query processing

### Q5

a) Atomicity issues in distributed transactions
b) Timestamp-based concurrency algorithms

### Q6

a) (i) Consistent checkpoints
(ii) Voting protocols
b) Algorithm for synchronous checkpointing

### Q7

a) Persistent vs transient objects + persistence handling
b) ORDBMS vs OODBMS

---

## 📄 **2022 – (5th Sem Paper)**

## **SECTION A (2×7=14)**

a) Define recoverable, cascadeless & strict schedules
b) Define checkpoint
c) What is bushy join tree?
d) Total cost equation of query execution in distributed system
e) Explain derived horizontal fragmentation

---

## **SECTION B (7×3=21)**

a) Explain ACID properties
b) Prove 3PC is non-blocking
c) Architecture of locking scheduler
d) Deadlock detection + protocols
e) Check conflict serializability of given schedule

---

## **SECTION C**

### Q3

a) Serial vs serializable schedule
b) Check conflict serializability

### Q4

a) Thomas Write Rule
b) Strict vs basic timestamp ordering

### Q5

a) Shadow paging + distributed locking schemes
b) Atomicity issues

### Q6

a) Query optimization techniques + pros/cons
b) Orphan messages + prevention

### Q7

a) Join vs semi-join
b) Eager vs lazy replication

---

## 📄 **2020 – Distributed Database (NBC025)**

## **SECTION A (2×10=20)**

a) Define distributed DB & its types
b) Transaction processing
c) Query optimization
d) Fragment vs allocation
e) Concurrency control
f) SUM, AVG, COUNT (syntax)
g) Semi-join & projection
h) Transaction & properties
i) Grouping function
j) Database design

---

## **SECTION B (10×3=30)**

a) Timestamp-based concurrency algorithms
b) Distributed DB architecture
c) Recovery in message passing + inconsistent states
d) Concurrency techniques
e) Distributed DB administration

---

## **SECTION C**

### Q3

a) Objectives of distributed query processing
b) Distributed vs replicated DB

### Q4

a) Query optimization algorithms
b) Data fragmentation methods

### Q5

a) Grouping & aggregate functions
b) Parametric queries

### Q6

a) Query equivalence transformation
b) Orphan concept

### Q7

a) Distributed transaction management & concurrency control
b) Example of distributed DB system

---

# Formated Questions

Got you 😌 — now this is the **real deal (exact questions, no paraphrasing, clean mapping, MD ready)**

---

```md
# 📚 Distributed Database Systems – Question Mapping (Exact Questions)

---

## 🟦 UNIT I – Introduction & Design

- List features of relational data model. (2023, Sec A)
- What is Transparencies in distributed database? (2023, Sec A)
- Differentiate between homogenous & heterogeneous DDBMS. (2023, Sec A)
- What are the different strategies for designing distributed database? (2023, Sec A)
- Differentiate between full & partial replication in DDBMS. (2023, Sec A)
- Discuss the distributed database system? Also explain the promises of DDBS. (2023, Sec B)
- Give a brief account of architectural models for distributed DBMS. (2023, Sec C)

- Why distributed databases are essential? (2022, Sec A)
- What are the types of failures in distributed DBMS? (2022, Sec A)
- Discuss the motivation behind parallel and distributed databases. (2022, Sec B)
- What are homogenous and heterogeneous database. Give the architecture of heterogeneous database along with some query processing issues. (2022, Sec C)
- Explain briefly about Fragmentation with suitable examples. (2022, Sec C)

- Define distributed database and its types? (2020, Sec A)
- Give the difference between fragments and allocation of fragments? (2020, Sec A)
- Define Database Design? (2020, Sec A)
- Describe Distributed Database Architecture in details? (2020, Sec B)

---

## 🟩 UNIT II – Query Processing & Optimization

### Query Fundamentals

- What do you understand by semi join? (2023, Sec A)
- What do you meant by Semi Join and Projection? (2020, Sec A)
- Compare join with semi join approach in distributed database system and analyze the scenarios of preference. (2022 Sem 5, Sec C)

### Query Processing

- Explain query processing. Also explain the layers of query processing. (2023, Sec B)
- Objectives of distributed query processing? Explain. (2020, Sec C)
- Briefly explain the objectives of query processing. (2023, Sec C)

### Query Optimization

- Discuss query optimization? Explain distributed cost model with an example. (2023, Sec C)
- Define query optimization? (2020, Sec A)
- Explain query optimization algorithms? (2020, Sec C)
- Explain in brief the various query optimization techniques and write their advantages and disadvantages. (2022 Sem 5, Sec C)

### Query Structure & Execution

- What is bushy join tree? (2022 Sem 5, Sec A)
- What is total cost equation of query execution in distributed system? (2022 Sem 5, Sec A)
- Discuss the Equivalence transformation of queries? (2020, Sec C)

---

---

## 🟨 UNIT III – Transaction Management & Concurrency

### Transaction Fundamentals

- What do you meant by Transaction Processing? (2020, Sec A)
- Define transaction and its properties? (2020, Sec A)
- Discuss the Transaction. Explain ACID properties with an example. (2023, Sec B)
- Explain the ACID properties of transaction. (2022 Sem 5, Sec B)

### Transaction State & Structure

- Draw transaction state diagram. (2023, Sec A)
- What is transaction log? What are its functions? (2022, Sec A)
- Define the Concepts of recoverable, cascade less and strict schedules. (2022, Sec A)
- Define the Concepts of recoverable, cascade less and strict schedules. (2022 Sem 5, Sec A)

### Serializability & Schedules

- Explain view serializability. (2022, Sec A)
- What are serial and serializable schedule? Why are serial and serializable schedule considered correct? (2022 Sem 5, Sec C)
- Define schedule and serializable schedule. Check whether the schedule is conflict serializable or not. (2022 Sem 5, Sec C)
- Determine the given schedule is conflict serializable or not. (2022 Sem 5, Sec B)

### Locking & Lock Types

- Differentiate between shared lock & exclusive lock. (2023, Sec A)
- Differentiate between 2PL and strict 2PL. (2022, Sec A)
- Explain the architecture of locking scheduler. (2022 Sem 5, Sec B)

### Concurrency Control Algorithms

- Define Moss Concurrency protocol? (2022, Sec A)
- Discuss the serializability? Explain time stamp based concurrency control algorithm. (2023, Sec C)
- Explain briefly about timestamp-based concurrency algorithms. (2022, Sec C)
- How does Thomas's Write Rule modify the check for the write_item(X) operation? (2022 Sem 5, Sec C)
- How does strict timestamp ordering differ from basic timestamp ordering? (2022 Sem 5, Sec C)
- Explain timestamp based concurrency algorithms in detail? (2020, Sec B)
- Discuss the various concurrency techniques in details? (2020, Sec B)

### Deadlock Management

- Explain deadlock handling. Discuss various deadlock avoidance algorithms. (2023, Sec C)
- Compare Distributed Deadlock prevention to Distributed Deadlock Avoidance. Explain one scheme of Distributed deadlock Detection and Recovery. (2022, Sec B)
- What is deadlock detection? Also explain the protocols for deadlock detection in distributed database system. (2022 Sem 5, Sec B)

### Transaction Manager & Atomicity

- What are the functions of Transaction Manager? (2023, Sec A)
- Discuss the issues to achieve atomicity in distributed transaction management system. (2022, Sec C)
- Discuss the issues to achieve atomicity in distributed transaction management system. (2022 Sem 5, Sec C)
- Discuss the Management of Distributed transaction and concurrency control? (2020, Sec C)

### Checkpoints & Voting

- Describe the followings (i) Consistent Checkpoints (ii) Voting protocols. (2022, Sec C)
- Generate an algorithm for synchronous check pointing in a Distributed database system. (2022, Sec C)

### Concurrency Control General

- Define concurrency control in distributed database? (2020, Sec A)

## 🟥 UNIT IV – Reliability & Parallel DB

### Failures & Recovery Basics

- Discuss various reasons for failures in distributed systems. (2023, Sec B)
- Differentiate between Backward and Forward recovery. (2022, Sec A)
- Why is recovery in a distributed DBMS more complicated than in a centralized system? (2022, Sec B)
- What problem can occur in a distributed system due to the failure of link and partitioning of the network? What are the ways by which recovery can take place? (2022, Sec B)

### Commit Protocols & Atomicity Support

- Explain the working of two phase commit protocol of distributed transactions. (2023, Sec C)
- Justify that three-phase commit (3PC) protocol is a non-blocking protocol. (2022, Sec C)

### Checkpointing & State Preservation

- Define the term Checkpoint? (2022 Sem 5, Sec A)
- Mention about Recovery in Message Passing System. Explain concept of inconsistent states? (2020, Sec B)
- What do you mean by Shadow Paging? Explain the various distributed locking schemes? (2022 Sem 5, Sec C)

### Orphan Process/Message Problems

- Analyze the condition of orphan message generation and discuss the ways to avoid this condition. (2022 Sem 5, Sec C)
- Explain the concepts in Orphan in distributed database. (2020, Sec C)

### Parallel DB & Administration

- Explain general architecture of a parallel database system and shared memory architecture. (2023, Sec C)
- Explain Distributed Database Administration? (2020, Sec B)

---

## 🟪 UNIT V – Object DBMS & OODBMS

### Object-Oriented Concepts & Data Model

- Briefly explain fundamental object concepts and models. Also explain abstract data types. (2023, Sec B)
- Describe following terms with reference to object oriented data model: (i) Inheritance (ii) Object identity. (2023, Sec C)
- How does the concept of an object in object-oriented model differ from the concept of an entity in the ER diagram? (2022, Sec A)
- Explain briefly in what way designing an object-oriented database is different from relational database. (2022, Sec A)

### Object Identity, OID & Persistence

- What is an object identifier? Explain with an example. What are its advantages and disadvantages? (2022, Sec B)
- What is the difference between persistent and transient objects? How is persistence handled in OO database systems? (2022, Sec C)

### OODBMS vs ORDBMS

- Write a short note on OODBMS. Also compare between OODBMS and ORDBMS. (2023, Sec C)
- Compare ORDBMS and OODBMS with respect to Data sharing, data modelling and data accessing. (2022, Sec C)

### Query, Functions & Examples

- Define SUM, AVG, and COUNT function with proper syntax? (2020, Sec A)
- What do you meant by grouping function? (2020, Sec A)
- Explain grouping and aggregate function with example? (2020, Sec C)
- Discuss parametric queries with example? (2020, Sec C)
- What do you meant by Semi Join and Projection? (2020, Sec A)
- Explain the example of Distributed Database System? (2020, Sec C)
```
