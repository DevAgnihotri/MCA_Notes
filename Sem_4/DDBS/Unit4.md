# 🧠 DISTRIBUTED DBMS RELIABILITY – MASTER NOTES

# 🔹 1. RELIABILITY IN DISTRIBUTED DBMS

### 📌 Definition:

> **Reliability refers to the ability of a distributed DBMS to continue correct operation even in the presence of failures.**

### 📖 Explanation (6 lines):

Distributed DBMS mein multiple sites, networks aur components involved hote hain. Failure ka chance zyada hota hai compared to centralized system. Reliability ensure karta hai ki system failures ke baad bhi **correct aur consistent results** de. Isme recovery mechanisms, fault tolerance aur backup strategies use hote hain. System ka aim hota hai ki failure ke baad bhi **minimum data loss aur fast recovery ho**. Reliability is a key requirement for real-world systems like banking and cloud.

💡 Hinglish:
“System gir bhi jaye… par data aur logic bachna chahiye 😄”

👉 Mnemonic: **“TRUST”**
(T → Tolerate failures, R → Recover fast, U → Uninterrupted service, S → Safe data, T → Trustworthy)

---

# 🔹 2. RELIABILITY MEASURES

### 📌 Definition:

> **Reliability measures quantify how dependable a system is over time.**

### 📖 Explanation (5–6 lines):

Reliability ko measure karne ke liye kuch metrics use kiye jaate hain. Yeh batate hain ki system kitna stable aur failure-resistant hai. Important measures include availability, MTBF (mean time between failures), aur MTTR (mean time to repair). In distributed systems, availability sabse important hota hai because downtime costly hota hai. High reliability ka matlab hai system failures ke baad bhi jaldi recover ho jaye.

👉 Mnemonic: **“AMT”**

* **A – Availability**
* **M – MTBF**
* **T – MTTR**

---

# 🔹 3. FAILURES IN DISTRIBUTED DBMS ⭐

(**Question Covered: Discuss various reasons for failures in distributed systems – 2023 Sec B**)

### 📌 Definition:

> **Failures are unexpected events that disrupt normal operation of a distributed database system.**

### 📖 Explanation (6 lines – EXTRA DETAIL):

Distributed systems mein failures multiple levels pe ho sakte hain — hardware, software, network, ya transaction level. Centralized systems ke comparison mein yahan complexity zyada hoti hai. Failures data inconsistency, loss ya system crash cause kar sakte hain. Isliye proper fault tolerance aur recovery mechanisms required hote hain. System ko design karte waqt sab types ke failures consider karne padte hain.

👉 Mnemonic: **“HSNT”**

---

## 🔸 Types of Failures

### 1. **H – Hardware Failure**

* Disk crash, power failure

### 2. **S – Software Failure**

* Bugs, OS crash

### 3. **N – Network Failure**

* Link failure, partition

### 4. **T – Transaction Failure**

* Deadlock, abort

---

💡 Hinglish:
“System ka koi bhi part fail ho sakta hai 😅”

---

# 🔹 4. DISTRIBUTED vs CENTRALIZED RECOVERY ⭐

(**Question Covered: Why recovery in distributed DBMS is more complicated? – 2022 Sec B**)

---

### 📌 Definition:

> **Recovery is the process of restoring the database to a consistent state after failure.**

---

### 📖 Explanation (6–7 lines):

Centralized system mein sirf ek site hoti hai, toh recovery simple hota hai. Lekin distributed DBMS mein multiple sites involved hote hain, jisse coordination difficult ho jata hai. Agar ek site fail ho jaye aur dusri continue kare, toh inconsistency aa sakti hai. Network failures bhi recovery ko complex banate hain. Synchronization aur atomicity maintain karna tough hota hai. Isliye distributed recovery zyada complex hota hai.

---

👉 Mnemonic: **“MULTI”**
(M → Multiple sites, U → Uncertain state, L → Link issues, T → Timing issues, I → Inconsistency risk)

---

# 🔹 5. NETWORK FAILURE & PARTITIONING ⭐

(**Question Covered: Link failure & partitioning problems + recovery ways – 2022 Sec B**)

---

### 📌 Definition:

> **Network partitioning occurs when communication between sites is broken into isolated groups.**

---

### 📖 Explanation (6–7 lines):

Network partitioning mein system multiple independent parts mein divide ho jata hai. Har partition apna kaam continue kar sakta hai, lekin global consistency break ho sakti hai. Isse conflicting updates ho sakte hain. Link failure bhi communication disrupt karta hai. Recovery ke liye system ko partitions merge karna aur conflicts resolve karna hota hai.

---

👉 Mnemonic: **“SPLIT”**

---

## 🔸 Problems:

* Data inconsistency
* Duplicate updates
* Lost transactions

---

## 🔸 Recovery Methods:

* Reconciliation
* Rollback
* Logging

---

💡 Hinglish:
“Network toot gaya… sab apni marzi se kaam kar rahe 😄”

---

# 🔹 6. RECOVERY TECHNIQUES ⭐

(**Question Covered: Backward vs Forward recovery – 2022 Sec A**)

---

### 📌 Definition:

> **Recovery techniques restore database after failure.**

---

### 📖 Explanation (6 lines):

Recovery ka main aim hota hai database ko consistent state mein lana. Yeh logs aur checkpoints use karta hai. Do main approaches hote hain: backward (rollback) aur forward (rollforward). Selection depend karta hai failure type aur system design pe. Distributed systems mein dono techniques ka combination use hota hai.

---

👉 Mnemonic: **“BF”**

---

## 🔸 Backward Recovery

* Rollback to previous state

✅ Advantage:

* Safe

❌ Disadvantage:

* Time-consuming

---

## 🔸 Forward Recovery

* Move forward using logs

✅ Advantage:

* Faster

❌ Disadvantage:

* Complex

---

# 🔹 7. TWO-PHASE COMMIT (2PC) ⭐

(**Question Covered: Explain working of 2PC – 2023 Sec C**)

---

### 📌 Definition:

> **2PC is a protocol to ensure atomicity of distributed transactions.**

---

### 📖 Explanation (6–7 lines – EXTRA DETAIL):

2PC ensure karta hai ki distributed transaction either sab sites pe commit ho ya sab pe abort. Isme ek coordinator aur multiple participants hote hain. Phase 1 mein coordinator sabse vote leta hai (commit ya abort). Phase 2 mein final decision announce hota hai. Agar koi site fail ho jaye toh system block ho sakta hai. Yeh atomicity maintain karta hai but blocking problem hai.

---

👉 Mnemonic: **“VOTE”**

---

## 🔸 Phases:

1. **Vote Phase**
2. **Commit Phase**

---

## 🔸 Advantages

* Ensures atomicity

## 🔸 Disadvantages

* Blocking problem

---

# 🔹 8. THREE-PHASE COMMIT (3PC) ⭐

(**Question Covered: Justify 3PC is non-blocking – 2022 Sec C**)

---

### 📌 Definition:

> **3PC is an extension of 2PC that avoids blocking.**

---

### 📖 Explanation (6–7 lines):

3PC mein ek extra phase add hota hai jo uncertainty reduce karta hai. Yeh ensure karta hai ki system kabhi indefinite wait na kare. Isliye ise non-blocking protocol mana jata hai. Yeh network failures ko better handle karta hai. Lekin complexity zyada hoti hai.

---

👉 Mnemonic: **“SAFE3”**

---

## 🔸 Phases:

1. Prepare
2. Pre-commit
3. Commit

---

# 🔹 9. CHECKPOINTING ⭐

(**Question Covered: Define checkpoint – 2022 Sem 5 Sec A**)

---

### 📌 Definition:

> **Checkpoint is a saved consistent state of the database used for recovery.**

---

### 📖 Explanation (5–6 lines):

Checkpoint ek snapshot hota hai jahan system apni current state save karta hai. Crash ke baad system isi point se restart karta hai. Isse recovery fast ho jata hai kyunki pura log replay nahi karna padta. Distributed systems mein consistent checkpoint lena difficult hota hai. Yeh recovery optimization technique hai.

---

👉 Mnemonic: **“SAVE”**

---

# 🔹 10. MESSAGE PASSING RECOVERY ⭐

(**Question Covered: Recovery in message passing + inconsistent state – 2020 Sec B**)

---

### 📌 Definition:

> **Message passing recovery deals with restoring consistent states in distributed systems using communication logs.**

---

### 📖 Explanation (6–7 lines):

Distributed systems mein processes ek dusre ko messages bhejte hain. Failure ke baad inconsistent states aa sakti hain, jahan ek process update ho gaya aur dusra nahi. Isko solve karne ke liye message logging aur checkpoints use hote hain. Recovery ensure karta hai ki sab processes consistent state mein ho.

---

👉 Mnemonic: **“SYNC”**

---

## 🔸 Inconsistent State

* Mismatch between processes
* Incorrect data

---

# 🔹 11. SHADOW PAGING ⭐

(**Question Covered: Shadow paging + locking schemes – 2022 Sem 5 Sec C**)

---

### 📌 Definition:

> **Shadow Paging is a recovery technique where updates are made on a copy of database pages instead of original pages.**

---

### 📖 Explanation (6–7 lines):

Shadow paging mein original data ko change nahi kiya jata. Instead, ek copy (shadow) banayi jati hai aur updates usme kiye jate hain. Agar transaction successful ho, toh pointer new data pe shift ho jata hai. Agar fail ho, toh old data safe rehta hai. Yeh logging avoid karta hai but memory usage zyada hota hai.

---

👉 Mnemonic: **“COPY”**

---

## 🔸 Advantages

* No undo/redo needed

## 🔸 Disadvantages

* High storage use

---

# 🔹 12. DISTRIBUTED LOCKING SCHEMES ⭐

(**Question Covered: Explain distributed locking schemes – 2022 Sem 5 Sec C**)

---

### 📌 Definition:

> **Distributed locking schemes manage locks across multiple sites.**

---

### 📖 Explanation (6 lines):

Distributed locking ensure karta hai ki multiple sites pe data safely access ho. Centralized lock manager ya distributed lock managers use kiye jaate hain. Yeh concurrency control ka part hai. Network delay aur failures ko handle karna difficult hota hai. Proper coordination required hota hai.

---

👉 Mnemonic: **“GLOBAL”**

---

## 🔸 Types:

* Centralized locking
* Distributed locking
* Primary copy

---

# 🔹 1. PARALLEL DATABASE SYSTEM ⭐

(**Question Covered: Explain general architecture of a parallel database system – 2023 Sec C**)

---

### 📌 Definition:

> **A Parallel Database System is a database system that uses multiple processors and storage devices to execute queries simultaneously.**

---

### 📖 Explanation (6 lines):

Parallel DB systems ka main goal hota hai **performance improve karna by parallel execution**. Ek query ko multiple parts mein tod diya jata hai aur alag-alag processors pe run karaya jata hai. Isse execution fast hota hai aur large data efficiently handle hota hai. Yeh systems large-scale applications jaise data warehousing aur big data mein use hote hain. Parallelism ke through **speed + scalability dono milte hain**. Distributed DB se related hai but focus performance pe hota hai.

💡 Hinglish:
“Ek kaam ko 10 log milke karenge toh jaldi khatam hoga 😄”

---

👉 Mnemonic: **“FAST”**
(F → Faster execution, A → अनेक processors, S → Scalability, T → Task split)

---

# 🔹 2. PARALLEL DATABASE ARCHITECTURES ⭐

(**Question Covered: Explain general architecture + shared memory – 2023 Sec C**)

---

### 📌 Definition:

> **Parallel DB architecture defines how processors and memory are organized to execute queries in parallel.**

---

### 📖 Explanation (6–7 lines):

Parallel DB systems mein different architectures use hote hain depending on how processors share memory and disks. Har architecture ka apna advantage aur limitation hota hai. Yeh decide karta hai ki data kaise access hoga aur tasks kaise distribute honge. Main architectures hain: shared memory, shared disk, aur shared nothing. Inka selection performance aur scalability pe depend karta hai.

---

👉 Mnemonic: **“MSN”**
(M → Memory, S → Shared Disk, N → Nothing shared)

---

## 🔸 Types of Architectures

---

### 🔹 1. Shared Memory Architecture ⭐

> All processors share same memory

### 📖 Explanation:

Isme sab processors ek hi memory ko access karte hain. Communication fast hota hai kyunki data same memory mein hota hai. Lekin scalability limited hoti hai kyunki memory bottleneck ban sakti hai.

---

✅ Advantages:

* Fast communication
* Easy to manage

❌ Disadvantages:

* Limited scalability
* Memory contention

---

### 🔹 2. Shared Disk Architecture

> Processors have separate memory but shared disk

---

### 🔹 3. Shared Nothing Architecture

> Each processor has its own memory + disk

---

💡 Hinglish:
“Shared memory = sab ek hi dabbe se kha rahe
Shared nothing = sabka apna dabba 😄”

---

# 🔹 3. PARALLEL DATA PLACEMENT

---

### 📌 Definition:

> **Parallel data placement refers to distributing data across multiple disks or nodes for parallel access.**

---

### 📖 Explanation (5–6 lines):

Data ko different nodes pe distribute kiya jata hai taaki parallel processing possible ho. Isse I/O load distribute hota hai aur performance improve hoti hai. Data placement ka design bahut important hota hai kyunki galat distribution se load imbalance ho sakta hai. Common techniques include partitioning and replication. Goal hota hai **even distribution + fast access**.

---

👉 Mnemonic: **“DRIP”**
(D → Distribution, R → Replication, I → I/O balance, P → Performance)

---

## 🔸 Techniques

* Horizontal partitioning
* Vertical partitioning
* Replication

---

# 🔹 4. PARALLEL QUERY PROCESSING

---

### 📌 Definition:

> **Parallel query processing divides a query into sub-tasks that are executed simultaneously.**

---

### 📖 Explanation (6 lines):

Ek query ko multiple subqueries mein tod diya jata hai. Yeh subqueries parallel processors pe execute hoti hain. Isse response time kam hota hai. Parallelism ke types hote hain: inter-query aur intra-query. Proper coordination required hota hai results combine karne ke liye. Yeh large datasets ke liye essential technique hai.

---

👉 Mnemonic: **“SPLIT”**

---

## 🔸 Types of Parallelism

* **Inter-query** → different queries parallel
* **Intra-query** → same query parallel

---

# 🔹 5. LOAD BALANCING

---

### 📌 Definition:

> **Load balancing is the process of evenly distributing workload across processors.**

---

### 📖 Explanation (5–6 lines):

Agar ek processor overloaded ho aur dusra idle ho, toh performance degrade hoti hai. Load balancing ensure karta hai ki sab processors efficiently kaam karein. Yeh dynamic ya static ho sakta hai. Distributed aur parallel systems mein yeh critical component hai. Proper load balancing se throughput increase hota hai.

---

👉 Mnemonic: **“EQUAL”**

---

## 🔸 Types

* Static load balancing
* Dynamic load balancing

---

# 🔹 6. DATABASE CLUSTERS

---

### 📌 Definition:

> **Database cluster is a group of interconnected computers working together as a single system.**

---

### 📖 Explanation (5–6 lines):

Cluster systems multiple machines ko combine karke ek powerful system banate hain. Yeh high availability aur fault tolerance provide karte hain. Agar ek node fail ho jaye, dusra handle kar leta hai. Yeh parallel DB systems ka important part hai. Clusters performance aur reliability dono improve karte hain.

---

👉 Mnemonic: **“TEAM”**

---

# 🔹 7. ORPHAN PROCESS / MESSAGE ⭐

(**Questions Covered:
Orphan message generation – 2022 Sem 5 Sec C
Concept of orphan – 2020 Sec C**)

---

### 📌 Definition:

> **An orphan process/message is one that continues execution even after its parent transaction has failed or rolled back.**

---

### 📖 Explanation (6–7 lines – EXTRA DETAIL):

Distributed systems mein processes ek dusre pe depend hote hain. Agar parent process fail ho jaye aur child process continue kare, toh inconsistency create hoti hai — ise orphan kehte hain. Yeh problem especially message passing systems mein hoti hai. Orphan messages system ko incorrect state mein le ja sakte hain. Isliye inhe detect aur avoid karna zaroori hota hai.

---

👉 Mnemonic: **“LOST”**

---

## 🔸 Causes:

* Network delay
* Failure during execution
* Message loss

---

## 🔸 Problems:

* Inconsistent data
* Wrong results

---

## 🔸 Prevention Methods ⭐

* Message logging
* Checkpointing
* Rollback mechanisms

---

💡 Hinglish:
“Parent gaya… baccha abhi bhi kaam kar raha 😄”

---

# 🔹 8. DISTRIBUTED DATABASE ADMINISTRATION ⭐

(**Question Covered: Explain Distributed Database Administration – 2020 Sec B**)

---

### 📌 Definition:

> **Distributed Database Administration involves managing and controlling distributed databases across multiple sites.**

---

### 📖 Explanation (6–7 lines – EXTRA DETAIL):

Distributed DB administration ka kaam hota hai system ko properly manage karna across multiple locations. Isme security, backup, recovery, performance tuning sab include hota hai. Admin ensure karta hai ki data consistent aur available rahe. Network aur hardware issues ko bhi handle karna hota hai. Yeh centralized admin se zyada complex hota hai.

---

👉 Mnemonic: **“MANAGE”**

---

## 🔸 Functions:

* Security management
* Backup & recovery
* Performance tuning
* Data distribution

---

## 🔸 Challenges:

* Coordination issues
* Network failures
* Data consistency

---