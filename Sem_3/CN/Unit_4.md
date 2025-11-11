# 🌐 **Transport Layer — Process-to-Process Delivery**

**Introduction / Process-to-Process Delivery / Responsibilities**
- List responsibilities of Transport Layer (2022 — A, (h))
- Illustrate sockets (2022 — A, (j))

**Reliable vs Unreliable Connections; Port & Socket Addressing**
- Explain three‑way handshake (TCP) (2019 — B, (e))
- Explain three‑way handshake and Two‑Army problem (2021 — C, Q6(b))
- What is three‑way handshaking? (2023 — A, (h))
- Advantages of using port numbers (2024 — A, (h))

---

## 🟦 **1️⃣ Introduction to Transport Layer**

### 📘 **Definition:**

The **Transport Layer** is the **fourth layer** of the OSI model.
It provides **process-to-process communication**, i.e., it ensures that **data is delivered from one application process on a source host to the correct application process on a destination host**.

> In simple words, while the Network Layer delivers data **from one computer to another**, the Transport Layer delivers data **from one program to another** (like browser → web server).

---

## 🟩 **2️⃣ Responsibilities of the Transport Layer**

| **Responsibility**                 | **Explanation**                                                                          |
| ---------------------------------- | ---------------------------------------------------------------------------------------- |
| **1. Process-to-Process Delivery** | Ensures correct delivery between sending and receiving processes using **port numbers**. |
| **2. End-to-End Connection**       | Establishes logical connection between sender and receiver applications.                 |
| **3. Segmentation and Reassembly** | Divides data into smaller segments and reassembles them at destination.                  |
| **4. Flow Control**                | Prevents sender from overwhelming the receiver.                                          |
| **5. Error Control**               | Detects and recovers from errors (lost or corrupted segments).                           |
| **6. Connection Control**          | Can offer **connection-oriented (TCP)** or **connectionless (UDP)** service.             |
| **7. Multiplexing/Demultiplexing** | Handles multiple applications simultaneously by using **different port numbers**.        |

📌 **Example:**
When you open a browser and a mail app together — both use the transport layer (HTTP uses port 80, SMTP uses port 25). The transport layer ensures each gets its own data.

---

## 🟦 **3️⃣ Process-to-Process Delivery**

### 💡 What it Means:

Each application on a system is assigned a **unique port number**.
The Transport Layer uses this to deliver messages to the correct process.

Example:

* HTTP → Port 80
* HTTPS → Port 443
* FTP → Port 21
* DNS → Port 53

So if you are using Chrome (port 80) and sending an email (port 25), both can run simultaneously without confusion.

---

## 🟩 **4️⃣ Port Numbers and Socket Addressing**

### ⚙️ **Port Number:**

* A **16-bit integer** that identifies a specific process on a host.
* Range: **0–65535**

| **Port Range** | **Type**                  | **Example**                     |
| -------------- | ------------------------- | ------------------------------- |
| 0–1023         | **Well-known ports**      | HTTP (80), FTP (21), DNS (53)   |
| 1024–49151     | **Registered ports**      | SQL Server (1433), MySQL (3306) |
| 49152–65535    | **Dynamic/Private ports** | Assigned temporarily by OS      |

---

### ⚙️ **Socket Addressing:**

A **socket** is the **combination of an IP address and a port number**.
It uniquely identifies each connection endpoint.

🧠 **Formula:**

```
Socket = IP Address + Port Number
```

📌 **Example:**

* Client socket: 192.168.1.5:5151
* Server socket: 142.250.1.110:80 (Google)

Together, they form a **communication pair**.

---

## 🟦 **5️⃣ Reliable and Unreliable Connections**

### 🔹 **Reliable Connection (TCP)**

* Uses **connection-oriented** communication.
* Ensures data reaches accurately and in order.
* Provides **error control, flow control, and retransmission**.
* Uses **Three-Way Handshake** to establish connection.

📘 **Example:** Web browsing, Email (uses TCP).

---

### 🔹 **Unreliable Connection (UDP)**

* **Connectionless** service — no prior setup.
* **Faster but no guarantee** of delivery or order.
* Used for **real-time applications** like video calls, online gaming.

📘 **Example:** Streaming, DNS, VoIP.

---

## 🟩 **6️⃣ Three-Way Handshake (TCP Connection Establishment)**

Before communication, TCP establishes a reliable connection using **three steps** 👇

| **Step** | **Sender (Client)** | **Receiver (Server)** | **Action**                             |
| -------- | ------------------- | --------------------- | -------------------------------------- |
| 1️⃣      | Sends **SYN**       | —                     | Requests connection                    |
| 2️⃣      | —                   | Sends **SYN + ACK**   | Acknowledges request and sends its own |
| 3️⃣      | Sends **ACK**       | —                     | Confirms and connection established    |

### 📊 **Diagram:**

```
Client                             Server
  |------ SYN --------------------->|
  |<----- SYN + ACK ---------------|
  |------ ACK --------------------->|
     ✅ Connection Established
```

After this, data transfer begins securely.

---

## 🟦 **7️⃣ The Two-Army Problem (Conceptual Limitation)**

It illustrates that **reliable communication cannot be guaranteed** over an unreliable channel — no matter how many acknowledgments are exchanged.

🧩 **Example:**
Two armies (A & B) on opposite hills must coordinate an attack via messengers.
If even one message is lost, they may act differently — leading to failure.

Similarly, in networks, absolute reliability can’t be guaranteed; TCP just **makes it highly probable**, not perfect.

---

## 🟩 **8️⃣ Advantages of Using Port Numbers**

| **Advantage**                   | **Explanation**                                               |
| ------------------------------- | ------------------------------------------------------------- |
| **1. Multiplexing**             | Allows multiple applications to share one network connection. |
| **2. Identification**           | Uniquely identifies processes at both ends.                   |
| **3. Efficient Routing**        | Data packets reach correct application quickly.               |
| **4. Simultaneous Connections** | Enables several sessions (browser, mail, download) at once.   |
| **5. Security Filtering**       | Firewalls use ports to allow/deny specific services.          |

---

## 🟦 **9️⃣ Sockets — Illustration**

### 🎯 **Definition:**

A **socket** is an endpoint for sending or receiving data between two devices.

### 🖼️ **Illustration Example:**

| **Side**   | **Socket Address** |
| ---------- | ------------------ |
| **Client** | 192.168.1.2:5001   |
| **Server** | 142.250.1.110:80   |

The socket pair forms a **unique link** between the two processes.

```
(Client App) [192.168.1.2:5001] <====> [142.250.1.110:80] (Web Server)
```

---

# 🌐 **Transport Layer Protocols: UDP, TCP, and SCTP**

- UDP header (hex CB84000D001C001C): source port, dest port, data length, total UDP length (2019 — C, Q6(b))
- Same UDP header questions (2022 — C, Q6(a))
- Explain TCP / UDP / SCTP  (2024 — C, Q6(a))
- Explain any two protocols in TCP/IP suite (SCTP, TCP, UDP) (2022 — C, Q6(b))
---


## 🟦 **1️⃣ Introduction**

The **Transport Layer** provides communication between **application processes** running on different hosts.
It uses **protocols** to send and receive data efficiently and reliably.

The three main protocols are:

* **UDP (User Datagram Protocol)**
* **TCP (Transmission Control Protocol)**
* **SCTP (Stream Control Transmission Protocol)**

---

## 🟩 **2️⃣ User Datagram Protocol (UDP)**

### 📘 **Definition:**

UDP is a **connectionless**, **unreliable** protocol that simply sends datagrams (packets) without establishing a connection.

It is used when **speed is more important than reliability**, like in live streaming, DNS lookups, or gaming.

---

### ⚙️ **Features of UDP**

| Feature                  | Description                                   |
| ------------------------ | --------------------------------------------- |
| **Connectionless**       | No need to set up or close connections.       |
| **Unreliable**           | No acknowledgment or retransmission.          |
| **Fast and lightweight** | Very low overhead; quick delivery.            |
| **No Flow Control**      | Sends data without checking receiver’s speed. |
| **Checksum**             | Used for simple error detection.              |

---

### 📊 **UDP Header Format (8 Bytes Total)**

| Field                | Size    | Description                        |
| -------------------- | ------- | ---------------------------------- |
| **Source Port**      | 16 bits | Identifies the sending process.    |
| **Destination Port** | 16 bits | Identifies the receiving process.  |
| **Length**           | 16 bits | Total length of UDP header + data. |
| **Checksum**         | 16 bits | Error detection field.             |

🧩 **Total = 8 Bytes**

---

### 🧠 **Example Question (Exam 2019, 2022):**

**Given UDP header (hex): CB84 000D 001C 001C**

Let's decode it 👇

| Field            | Hex Value | Decimal      | Meaning                      |
| ---------------- | --------- | ------------ | ---------------------------- |
| Source Port      | CB84      | **52100**    | Sender’s port                |
| Destination Port | 000D      | **13**       | Receiver’s port              |
| Length           | 001C      | **28 bytes** | UDP header (8B) + data (20B) |
| Checksum         | 001C      | —            | Used for error check         |

✅ So,

* **Source Port:** 52100
* **Destination Port:** 13
* **Total UDP Length:** 28 bytes
* **Data Length:** 28 − 8 = **20 bytes**

---

### 💡 **Applications of UDP**

* DNS (Port 53)
* VoIP (Voice over IP)
* Video Streaming
* Online Games

---

## 🟦 **3️⃣ Transmission Control Protocol (TCP)**

### 📘 **Definition:**

TCP is a **connection-oriented**, **reliable** transport protocol that ensures **error-free, ordered, and complete data delivery**.

---

### ⚙️ **Features of TCP**

| Feature                 | Description                                             |
| ----------------------- | ------------------------------------------------------- |
| **Connection-Oriented** | Uses **Three-Way Handshake** to establish a connection. |
| **Reliable**            | Retransmits lost data.                                  |
| **Ordered Delivery**    | Keeps packets in sequence.                              |
| **Flow Control**        | Uses sliding window mechanism.                          |
| **Error Control**       | Uses checksum and acknowledgment (ACK).                 |
| **Full Duplex**         | Data can be sent and received simultaneously.           |

---

### 📊 **TCP Header Format (Minimum 20 Bytes)**

| Field                                | Size     | Description                                   |
| ------------------------------------ | -------- | --------------------------------------------- |
| **Source Port**                      | 16 bits  | Sender’s process ID.                          |
| **Destination Port**                 | 16 bits  | Receiver’s process ID.                        |
| **Sequence Number**                  | 32 bits  | Number of the first data byte sent.           |
| **Acknowledgment Number**            | 32 bits  | Confirms receipt of data.                     |
| **Header Length + Reserved + Flags** | 12 bits  | Control bits like SYN, ACK, FIN.              |
| **Window Size**                      | 16 bits  | Size of sender’s receive window.              |
| **Checksum**                         | 16 bits  | Error detection.                              |
| **Urgent Pointer**                   | 16 bits  | Points to urgent data.                        |
| **Options (Optional)**               | Variable | Used for features like scaling or timestamps. |

🧩 **Total: 20 to 60 Bytes**

---

### 📘 **TCP Flags**

| Flag    | Meaning               |
| ------- | --------------------- |
| **SYN** | Start of connection   |
| **ACK** | Acknowledgment        |
| **FIN** | End of connection     |
| **RST** | Reset connection      |
| **PSH** | Push data immediately |
| **URG** | Urgent data           |

---

### 💡 **Applications of TCP**

* Web Browsing (HTTP / HTTPS)
* Email (SMTP)
* File Transfer (FTP)
* Remote Login (SSH, Telnet)

---

## 🟦 **4️⃣ Stream Control Transmission Protocol (SCTP)**

### 📘 **Definition:**

SCTP is a **message-oriented**, **reliable** transport protocol designed to carry multiple streams of data between two systems.

It combines the best features of TCP and UDP.

---

### ⚙️ **Features of SCTP**

| Feature                   | Description                                              |
| ------------------------- | -------------------------------------------------------- |
| **Connection-Oriented**   | Uses a handshake like TCP.                               |
| **Message-Oriented**      | Sends complete messages (not byte streams).              |
| **Multi-Streaming**       | Multiple streams in one connection, preventing blockage. |
| **Multi-Homing**          | Supports multiple IP addresses for redundancy.           |
| **Reliable Transmission** | Acknowledgment and retransmission used.                  |

---

### 📊 **SCTP Header Format (12 Bytes)**

| Field                | Size    | Description               |
| -------------------- | ------- | ------------------------- |
| **Source Port**      | 16 bits | Sender’s port.            |
| **Destination Port** | 16 bits | Receiver’s port.          |
| **Verification Tag** | 32 bits | Unique ID for connection. |
| **Checksum**         | 32 bits | For error control.        |

🧩 **Chunks:**
After the header, SCTP data is divided into **chunks**, such as:

* DATA chunk (actual message)
* INIT chunk (connection setup)
* SACK chunk (acknowledgment)

---

### 💡 **Applications of SCTP**

* Telecom signaling (VoIP control)
* 4G/5G cellular networks
* Multimedia streaming

---

## 🟩 **5️⃣ Comparison Between TCP, UDP, and SCTP**

| Feature         | **TCP**             | **UDP**                | **SCTP**            |
| --------------- | ------------------- | ---------------------- | ------------------- |
| Connection Type | Connection-Oriented | Connectionless         | Connection-Oriented |
| Reliability     | Reliable            | Unreliable             | Reliable            |
| Data Type       | Byte Stream         | Message                | Message             |
| Flow Control    | Yes                 | No                     | Yes                 |
| Error Control   | Yes                 | Simple Checksum        | Yes                 |
| Speed           | Moderate            | Fast                   | Moderate            |
| Use Cases       | HTTP, FTP, Email    | DNS, Streaming, Gaming | VoIP, Telecom Apps  |

---

## 🟦 **6️⃣ Two-Protocol Question Reference (2022, 2024)**

If exam asks:

> **“Explain any two protocols in the TCP/IP suite (TCP, UDP, SCTP)”**

✅ **Answer Example:**

* **TCP:** Reliable, connection-oriented, ordered delivery protocol. Used in web, email, FTP.
* **UDP:** Connectionless, faster but unreliable. Used in DNS, video streaming.

Or choose **TCP & SCTP**:

* TCP handles single-stream byte communication.
* SCTP allows multi-stream message transmission with better reliability.

---

## 🟩 **7️⃣ Summary**

| Concept                                   | Key Point                                                          |
| ----------------------------------------- | ------------------------------------------------------------------ |
| **UDP**                                   | Fast, connectionless, 8-byte header, used for real-time apps.      |
| **TCP**                                   | Reliable, ordered, uses 3-way handshake, 20-byte header.           |
| **SCTP**                                  | Combines TCP’s reliability and UDP’s speed, supports multi-stream. |
| **Example UDP Header (CB84000D001C001C)** | Source=52100, Dest=13, Length=28, Data=20 bytes                    |

# 🚦 **Congestion Control — Techniques for Handling Congestion**

- How is congestion controlled? Explain TCP congestion control (2019 — C, Q6(a))
- Define congestion; open and closed loop methods (2021 — C, Q6(a))
- Differentiate Open Loop vs Closed Loop congestion control (2023 — C, Q6(a))
- Explain a congestion control algorithm (2024 — B, (d))
---

## 🟦 **1️⃣ What is Congestion?**

### 📘 **Definition:**

**Congestion** happens when **too many packets** are present in the network, and **routers or links cannot handle them efficiently**, causing delay and packet loss.

🧠 **In simple words:**

> When traffic on the network is higher than what it can handle — just like a traffic jam on a busy road.

### 📉 **Result of Congestion:**

* Packet loss
* Increased delay
* Low throughput
* Retransmissions (which make it worse!)

---

## 🟩 **2️⃣ Need for Congestion Control**

We use **congestion control techniques** to:

* Avoid network overload
* Maintain good performance
* Reduce packet loss and delay
* Ensure fair use of network resources

---

## 🟦 **3️⃣ Methods of Congestion Control**

Congestion control methods are divided into **two main types:**

| **Type**                   | **Explanation**                                                                           |
| -------------------------- | ----------------------------------------------------------------------------------------- |
| **Open Loop (Preventive)** | Congestion is prevented **before it happens** by designing the network smartly.           |
| **Closed Loop (Reactive)** | Congestion is **detected and controlled** after it occurs using feedback and adjustments. |

---

### 🔹 **(A) Open Loop Congestion Control (Prevention Methods)**

These techniques are built into the network to **avoid congestion before it occurs.**

| **Technique**                | **Explanation**                                             |
| ---------------------------- | ----------------------------------------------------------- |
| **1. Retransmission Policy** | Avoids unnecessary retransmission to prevent extra load.    |
| **2. Window Policy**         | Controls the number of unacknowledged packets sent at once. |
| **3. Acknowledgment Policy** | Reduces ACK traffic (e.g., send cumulative ACKs).           |
| **4. Admission Control**     | Limits number of connections accepted at a time.            |
| **5. Discard Policy**        | Routers discard low-priority packets when full.             |

🧠 **Example:**
Routers use **buffer limits** to stop accepting packets when queues are full.

---

### 🔹 **(B) Closed Loop Congestion Control (Feedback-Based)**

These methods **detect congestion** and take steps to fix it.

| **Technique**             | **Explanation**                                                               |
| ------------------------- | ----------------------------------------------------------------------------- |
| **1. Back Pressure**      | Routers send signals to slow down upstream routers.                           |
| **2. Choke Packet**       | Routers send a “slow down” message to the source.                             |
| **3. Implicit Signaling** | Source guesses congestion using delay or packet loss.                         |
| **4. Explicit Signaling** | Routers explicitly inform source of congestion using special bits in packets. |

🧩 **Example:**
In **TCP**, the sender slows down automatically when ACKs come late or are missing.

---

## 🟦 **4️⃣ TCP Congestion Control (Main Exam Concept)**

### 📘 **Definition:**

TCP congestion control uses **dynamic adjustment of the sending rate** based on network feedback — mainly using a variable called **Congestion Window (cwnd)**.

TCP tries to find the right balance:

> “Send as fast as possible, but without overloading the network.”

---

### ⚙️ **TCP Congestion Control Phases (Algorithm)**

| **Phase**                   | **Purpose**                                                    | **How it Works**                                                            |
| --------------------------- | -------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **1. Slow Start**           | Gradually increases sending rate to discover network capacity. | cwnd starts small (1 MSS) and doubles every RTT until threshold (ssthresh). |
| **2. Congestion Avoidance** | Grows window slowly to prevent congestion.                     | cwnd increases linearly after each successful ACK.                          |
| **3. Fast Retransmit**      | Quickly detects packet loss (without waiting for timeout).     | After 3 duplicate ACKs, retransmit lost packet immediately.                 |
| **4. Fast Recovery**        | Avoids returning to slow start after minor loss.               | Reduces cwnd to half and continues linear growth.                           |

---

### 🧩 **Example:**

Let’s assume:

* Initial cwnd = 1 MSS
* ssthresh = 8 MSS

| **Phase**                | **cwnd Growth**                        |
| ------------------------ | -------------------------------------- |
| **Slow Start**           | 1 → 2 → 4 → 8 (exponential)            |
| **Congestion Avoidance** | 8 → 9 → 10 (linear)                    |
| **If packet loss**       | cwnd = cwnd/2 → 4, enter Fast Recovery |

---

### 🖼️ **Illustration (Text Graph)**

```
      cwnd ↑
        |
   8 ──────────◉  (Threshold reached)
   4 ───◉──◉──◉──→ Linear increase (Avoidance)
   2 ─◉──→ Exponential increase (Slow Start)
   0 ───────────────────────────── time →
```

---

## 🟩 **5️⃣ Common TCP Congestion Control Algorithms**

| **Algorithm**                                         | **Description**                                                     |
| ----------------------------------------------------- | ------------------------------------------------------------------- |
| **Slow Start**                                        | Starts slowly, increases sending rate exponentially.                |
| **Congestion Avoidance**                              | Uses linear increase to prevent congestion.                         |
| **Fast Retransmit**                                   | Quickly resends lost packet after 3 duplicate ACKs.                 |
| **Fast Recovery**                                     | Reduces congestion window slightly, not fully.                      |
| **AIMD (Additive Increase, Multiplicative Decrease)** | Increases rate linearly, decreases sharply when congestion happens. |

🧠 **Example:**
AIMD is the heart of TCP congestion control — it helps stabilize the network.

---

## 🟦 **6️⃣ Difference — Open Loop vs Closed Loop**

| **Basis**                | **Open Loop**     | **Closed Loop**        |
| ------------------------ | ----------------- | ---------------------- |
| **Nature**               | Preventive        | Reactive               |
| **Congestion Detection** | Not required      | Required               |
| **Feedback Used**        | No                | Yes                    |
| **Example**              | Admission Control | TCP Congestion Control |
| **When Used**            | Before congestion | After congestion       |

Got it 👍 — here’s your answer in the **same structured format** as before 👇

---

### **Topic: Quality of Service (QoS): Flow Characteristics and Techniques to Improve QoS**

- Describe QoS and techniques to improve QoS (2024 — C, Q6(b))
- Explain traffic shaping algorithms (2023 — C, Q6(b))
- Explain Round‑Trip Time (RTT) (2023 — A, (f))
- Maximum window size for selective reject with n‑bit sequence numbers (flow control concept) (2021 — A, (h))


---

#### **Definition:**

Quality of Service (QoS) refers to a set of techniques used to ensure the **efficient and reliable delivery of data** over a network.
It helps maintain performance levels by managing **bandwidth, delay, jitter, and packet loss** for different types of traffic.

---

#### **Flow Characteristics:**

QoS depends on the characteristics of a data flow between sender and receiver.
The main flow characteristics are:

1. **Reliability:**
   Ability to deliver data accurately and completely without loss or error.

2. **Delay (Latency):**
   Time taken for a packet to travel from source to destination. Lower delay = better QoS.

3. **Jitter:**
   Variation in packet arrival time; should be minimal for smooth performance (important in voice/video).

4. **Bandwidth:**
   Maximum data that can be transmitted per second — determines network capacity.

5. **Throughput:**
   Actual rate of successful data transfer in a given time period.

---

#### **Techniques to Improve QoS:**

1. **Traffic Shaping:**
   Controls data rate and smooths out bursty traffic to prevent congestion.

   * **Leaky Bucket Algorithm:** Sends packets at a constant rate.
   * **Token Bucket Algorithm:** Allows bursts but within defined limits.

2. **Scheduling:**
   Determines the order in which packets are transmitted based on priority.

   * Example: **Priority Queuing, Weighted Fair Queuing (WFQ)**.

3. **Resource Reservation:**
   Network reserves bandwidth and buffers for high-priority traffic using protocols like **RSVP**.

4. **Admission Control:**
   Network decides whether to accept new traffic based on available resources.

---

#### **Additional Concepts:**

* **Round Trip Time (RTT):**
  The time taken for a packet to go from source → destination → source again.
  Used in TCP to estimate timeout values.

* **Flow Control (Selective Reject):**
  For **n-bit sequence numbers**, the maximum window size = **2ⁿ⁻¹**.