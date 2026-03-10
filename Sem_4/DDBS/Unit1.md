## Introduction: Distributed Data Processing

Distributed Data Processing refers to the technique of processing large volumes of data across multiple computers or servers rather than relying on a single machine. This approach enhances scalability, fault tolerance, and efficiency, making it ideal for handling big data applications.

## Key Aspects of Distributed Data Processing:

1. Parallelism – Tasks are split into smaller parts and processed simultaneously across multiple nodes.
2. Scalability – Systems can handle increasing workloads by adding more computing resources.
3. Fault Tolerance – Distributed systems can recover from node failures without data loss.
4. Data Locality – Processing is moved closer to where data is stored, reducing network latency.
5. Coordination & Synchronization – Mechanisms like distributed file systems and consensus algorithms manage consistency.

### Common Frameworks:

- Hadoop – Uses the MapReduce model for batch processing.
- Apache Spark – Provides fast in-memory processing for big data.
- Flink & Storm – Designed for real-time stream processing.

## Introduction of Distributed Database System

A Distributed Database System (DDBS) is a collection of interconnected databases spread across multiple locations but appearing as a single unified system. It enables efficient data management, improved performance, and fault tolerance in large-scale applications.

### Key Characteristics:
1. Data Distribution – Data is stored across multiple sites but remains accessible as a single database
2. Transparency – Users interact with the system without needing to know data locations.
3. Scalability – Supports growing data and user demands by adding more nodes.
4. Replication & Fragmentation – Data can be replicated for redundancy or split (fragmented) for efficiency.
5. Concurrency Control – Ensures consistency when multiple users access data simultaneously.

### Types of Distributed Databases:

- Homogeneous – All databases use the same DBMS.
- Heterogeneous – Different DBMSs are used but are integrated.

### Advantages:
- Improved reliability & fault tolerance.
- Faster data access & reduced network congestion.
- Better resource utilization & scalability

### Promises of DDBSs, Problem areas

#### **Promises of DDBSs:**

1. Improved Performance – Queries run faster by distributing workload across multiple sites.
2. Scalability – Easily expands by adding more nodes without major system redesign.
3. Fault Tolerance & Reliability – Data replication ensures system continues functioning even if some nodes fail.
4. Better Resource Utilization – Optimizes computing power by distributing tasks efficiently.
5. Data Localization – Reduces network traffic by processing data closer to where it is needed.
6. Autonomy & Flexibility – Different sites can operate independently while still being part of the system.

#### **Problem Areas of DDBSs:**

1. Complexity – Managing distributed databases requires advanced coordination mechanisms.
2. Data Consistency – Ensuring consistency across multiple sites is challenging.
3. Security Concerns – Data spread across different locations increases vulnerability to breaches.
4. High Communication Overhead – Synchronizing distributed data generates significant network traffic.
5. Query Optimization Issues – Efficient query processing across distributed sites is complex.
6. Concurrency Control – Preventing conflicts when multiple users access data simultaneously is difficult.

## Types of Distributed Database System
Some of the types of distributed database systems are:

1. Homogeneous Database: 
In a homogeneous database, all different sites store database identically. The operating system, database management system, and the data structures used all are the same at all sites.

Features:

- Unified query language and interface.
- Low integration complexity.
- Efficient synchronization.

Example: A bank with branches in different cities uses Oracle DB at every location. All databases have the same structure and are synchronized regularly.

2. Heterogeneous Database
In a heterogeneous distributed database, different sites may use different DBMSs, schemas, or data models, making query processing and transactions difficult. Some sites may not even be aware of others, so translation mechanisms are needed for communication. 

Features:

- Supports interoperability between diverse systems.
- Complex query optimization and transaction management.
- Useful in mergers or collaborations between organizations.

Example: A logistics company uses MySQL for inventory, MongoDB for vehicle tracking, and PostgreSQL billing. Integration middleware allows unified querying across these platforms.

3. Client-Server Distributed Database System
The server stores and manages the database, while clients send queries over the network. It offers centralized control with distributed access, making it ideal for enterprise systems and web applications. Clients can be lightweight while the server handles heavy processing. Example: Web application interacting with a central PostgreSQL server.

Features:

- Simplifies resource management.
- Central servers can be optimized for performance.
- Easily scalable with more clients.
Example: An e-commerce website where the frontend (client) is hosted separately and interacts with a central PostgreSQL server to manage orders, users, and inventory.

![Image1](https://media.geeksforgeeks.org/wp-content/uploads/20240806125841/Client-Server-Architecture-in-Distributed-Systems.webp)

4. Peer-to-Peer Distributed Database System
All nodes are equal, with no fixed client or server roles. Each node can store data and also process queries, leading to decentralized control. It supports fault tolerance and high availability. Example: Blockchain networks like Ethereum, where each node maintains a part of the distributed ledger.

Features:

- No single point of failure.
- Useful in decentralized and distributed apps.
- High availability and data redundancy.
Example: Blockchain-based databases like Ethereum or BitTorrent-based systems, where each peer maintains part of the ledger and participates equally in transactions.

![Image2](https://media.geeksforgeeks.org/wp-content/uploads/20240806125428/Peer-to-Peer.webp)

5. Cloud-Based Distributed Database System
These systems are deployed on cloud platforms and span multiple geographic regions for scalability and reliability. They abstract infrastructure details and are offered as DBaaS, making them ideal for dynamic workloads. Example: Google Cloud Spanner and Amazon DynamoDB used for global applications.

Features:

- Automatic scaling and replication.
- Pay-as-you-use pricing.
- Global availability and disaster recovery.

Example:
- Google Cloud Spanner: Global-scale relational database.
- Amazon DynamoDB: Key-value and document database with high performance.
- Azure Cosmos DB: Multi-model, globally distributed DBMS.

Here is the **same simple, learnable format** with **clear definitions and points**.

![Image4](https://yqintl.alicdn.com/5c6e8f4d20700b090dd2423bf661f47ee2fa6bde.png)

---

## Alternative Design Strategies in Distributed DBMS

### 1. Non-Replicated and Non-Fragmented

#### Definition

In this strategy, **each table is stored at only one site and the table is kept as a complete unit without replication or fragmentation.**

#### Points

1. The **entire table is stored at one location**.
2. The table is **not divided into parts**.
3. The table is **not copied to other sites**.
4. Data access from other sites may require **remote access**.
5. It is **simple to manage but may cause slower access for distant users**.

#### Example

A **student table stored only in the main university server**, and other campuses access it remotely.

---

### 2. Fully Replicated

#### Definition

In this strategy, **a complete copy of the database or table is stored at every site in the distributed system.**

#### Points

1. Each site contains **a full copy of the database**.
2. Data can be **accessed locally at any site**.
3. It provides **high availability and reliability**.
4. Updates must be **synchronized across all copies**.
5. Requires **more storage and maintenance**.

#### Example

Every branch of a company stores **a full copy of the employee database**.

---

### 3. Partially Replicated

#### Definition

In this strategy, **only some tables or fragments are replicated at selected sites instead of all sites.**

#### Points

1. **Some data is copied to multiple sites**, but not all.
2. Frequently used data is **replicated for faster access**.
3. Less storage is required compared to full replication.
4. Updates must be **managed for replicated data**.
5. It provides a **balance between performance and storage cost**.

#### Example

Important **customer tables are copied to major branches**, but not to every branch.

---

### 4. Fragmented

#### Definition

In this strategy, **a database table is divided into smaller parts called fragments and each fragment is stored at different sites.**

#### Points

1. Tables are **split into smaller fragments**.
2. Each fragment is **stored at a different location**.
3. Fragments may contain **different rows or columns**.
4. Improves **local data access speed**.
5. Queries may require **combining fragments from multiple sites**.

#### Example

A **sales table divided by region**, where each region’s data is stored in its own branch.

---

### 5. Mixed

#### Definition

Mixed strategy combines **both replication and fragmentation** to distribute data efficiently.

#### Points

1. Tables may be **fragmented and then replicated**.
2. Some fragments can **exist at multiple sites**.
3. Provides **better performance and availability**.
4. More **complex to design and manage**.
5. Commonly used in **large distributed systems**.

### Example

A **sales table fragmented by region**, and important fragments are **replicated at multiple regional offices**.

Here is a **simple flow explanation** so it becomes **easy to learn and remember for exams**.

---

# Fragmentation in Distributed DBMS

### Definition

**Fragmentation** is the process of **dividing a database table into smaller parts called fragments and storing them at different sites in a distributed system.**

The goal is to **store data closer to where it is used**, which improves **performance and efficiency**.

## Types of Fragmentation

There are **three main types**:

1. **Horizontal Fragmentation**
2. **Vertical Fragmentation**
3. **Hybrid (Mixed) Fragmentation**

### 1. Horizontal Fragmentation

#### Definition

**Horizontal fragmentation divides a table into fragments based on rows (records).**

Each fragment contains **different rows but the same columns**.

#### Points

1. The table is split **row-wise**.
2. Each fragment has **some records of the table**.
3. The **structure of the table remains the same**.
4. Used when **different locations need different rows of data**.
5. Fragments can be combined using **UNION operation**.

#### Example

Original Table (Student)

| ID | Name | City   |
| -- | ---- | ------ |
| 1  | Ravi | Delhi  |
| 2  | Aman | Kanpur |
| 3  | Neha | Delhi  |
| 4  | Riya | Kanpur |

Fragment 1 (Delhi Students)

| ID | Name | City  |
| -- | ---- | ----- |
| 1  | Ravi | Delhi |
| 3  | Neha | Delhi |

Fragment 2 (Kanpur Students)

| ID | Name | City   |
| -- | ---- | ------ |
| 2  | Aman | Kanpur |
| 4  | Riya | Kanpur |

### 2. Vertical Fragmentation

#### Definition

**Vertical fragmentation divides a table into fragments based on columns (attributes).**

Each fragment contains **some columns of the table**.

#### Points

1. The table is split **column-wise**.
2. Each fragment contains **some attributes of the table**.
3. A **primary key is included in each fragment** to reconnect them.
4. Used when **different locations use different attributes**.
5. Fragments can be combined using **JOIN operation**.

#### Example

Original Table

| ID | Name | Age | City |

Fragment 1

| ID | Name |

Fragment 2

| ID | Age | City |

### 3. Hybrid (Mixed) Fragmentation

#### Definition

**Hybrid fragmentation is a combination of horizontal and vertical fragmentation.**

The table can be **fragmented by rows and then by columns (or vice versa).**

#### Points

1. Combines **horizontal and vertical fragmentation**.
2. Used in **large distributed databases**.
3. Provides **better flexibility in data distribution**.
4. Can improve **query performance**.
5. More **complex to design and manage**.

### Example

First divide students **by city (horizontal)** and then divide columns **like ID–Name and ID–Age (vertical)**.

Here is the **same topic in Challenge → Impact → Solution format**, which is **very good for theory answers and easy to remember**.

---

# Distribution Design Issues in Distributed Databases

### Definition

**Distribution design issues** are the **challenges faced when distributing data across multiple sites in a Distributed Database Management System (DDBMS).**

These issues affect **performance, reliability, and data management**.

1. Data Fragmentation

### Challenge

Large tables must be **divided and stored at different locations** without losing the relationship between data.

### Impact

If fragmentation is done poorly, **queries become slow and data reconstruction becomes difficult**.

### Solution

Use proper **fragmentation techniques (Horizontal, Vertical, Hybrid)** so that fragments can easily be **combined to form the original table**.

2. Data Replication

### Challenge

Copies of data are stored at **multiple sites**, which makes it difficult to keep all copies **consistent during updates**.

### Impact

If synchronization fails, **different sites may contain different data**, causing **data inconsistency**.

### Solution

Use **replication control mechanisms and synchronization techniques** to ensure **all copies remain updated**.

3. Data Allocation

### Challenge

It is difficult to **decide where fragments or data copies should be stored** in the network.

### Impact

Poor allocation can cause **high communication cost and slow system performance**.

### Solution

Allocate data based on **user access patterns and network efficiency** so data is **stored closer to the users who access it frequently**.

4. Transparency

### Challenge

The distributed nature of the database makes the system **complex for users to understand**.

### Impact

Users may need to know **where the data is located or how it is stored**, which makes the system difficult to use.

### Solution

Provide **transparency mechanisms** so the distributed database **appears as a single database to the user**.

5. Reliability and Availability

### Challenge

In a distributed system, **site or network failures can occur**.

### Impact

Failure of a site may lead to **data inaccessibility or system downtime**.

### Solution

Use **replication, backup systems, and fault tolerance techniques** so the database **continues working even if some sites fail**.