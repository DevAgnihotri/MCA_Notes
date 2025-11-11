## Switching Techniques: Circuit Switching, Packet Switching, Message Switching

### 🟦 **1. What is Switching?**

- 2024 Paper (KCA303) — Section B (c): Define switching. Briefly explain Packet Switching, Message Switching and Circuit Switching.
- Related network-layer forwarding/service question:
  - 2024 Paper (KCA303) — Section A (e): Differentiate between Datagram approach and Virtual circuit approach.

**Definition:**
Switching is the process of **transferring data from one device to another** within a network through intermediate devices known as **switches**.

In simpler words —

> Switching decides **how data travels from sender to receiver** through the network.

It helps establish a communication path between multiple connected devices and ensures **efficient and reliable data transmission**.

---

### 🟩 **2. Types of Switching Techniques**

Switching techniques are mainly of three types:

#### ⚙️ **A. Circuit Switching**

##### 📘 **Concept:**

In **Circuit Switching**, a **dedicated communication path (circuit)** is established between sender and receiver **before** data transfer begins.

- This path remains **reserved** for that communication until it ends.
- Commonly used in **telephone networks**.

##### 🔄 **Phases:**

1. **Circuit Establishment**
2. **Data Transfer**
3. **Circuit Termination**

##### ⚡ **Features:**

- Data is transferred in a **continuous stream**.
- **No delay once circuit is set up**.
- **Inefficient for bursty data** (since the line stays reserved even if no data is being sent).

##### 🌐 **Example:**

Traditional **landline phone calls** use circuit switching.

---

#### ⚙️ **B. Packet Switching**

##### 📘 **Concept:**

In **Packet Switching**, the message is **divided into small packets**, and each packet is sent **independently** through the network.

Each packet carries:

- **Source & destination addresses**
- **Sequence number** (for reassembly)

Packets may travel through **different routes** and are reassembled at the destination.

##### ⚡ **Features:**

- Efficient use of bandwidth.
- Can handle **bursty traffic**.
- **Packets may arrive out of order** but can be rearranged.

##### 🌐 **Example:**

The **Internet** (using IP) works on packet switching.

---

#### ⚙️ **C. Message Switching**

##### 📘 **Concept:**

In **Message Switching**, the **entire message** is treated as a single unit and sent from one node to another.

Each node **stores the complete message** before forwarding it to the next — known as **store and forward** technique.

##### ⚡ **Features:**

- No dedicated path is required.
- **Intermediate nodes** temporarily store messages.
- Causes **more delay** (because of storage at each node).
- Suitable for **non-real-time communication** (like emails).

##### 🌐 **Example:**

Early **telegraph systems** and **email services** use message switching concepts.

---

### 🟨 **3. Difference Between Datagram and Virtual Circuit Approach (in Packet Switching)**

| **Basis**       | **Datagram Approach**                            | **Virtual Circuit Approach**                |
| --------------- | ------------------------------------------------ | ------------------------------------------- |
| **Connection**  | Connectionless                                   | Connection-oriented                         |
| **Path**        | Each packet takes **different paths**            | All packets follow **same path**            |
| **Addressing**  | Each packet carries **full destination address** | Only a **virtual circuit number** is needed |
| **Reliability** | Less reliable, but faster                        | More reliable, requires setup               |
| **Example**     | **IP (Internet Protocol)**                       | **ATM, Frame Relay**                        |

## Logical addressing: IPv4 and IPv6 address schemes, Classes and subnetting

- 2019 Paper (RCA402) — Section B (c): What is IP addressing? How would you design Class A, Class B and Class C of IP addresses?
- 2021 Paper (NMCAE25) — Section C Q5(b): What do you mean by IP address? (IP 142.10.20.12) Subnetting tasks: class, default mask, custom masks, #subnets, bits borrowed, #hosts, usable hosts, subnet & broadcast of 2nd subnet.
- 2021 Paper (NMCAE25) — Section B (c): Discuss IPv4 frame format.
- 2022 Paper (KCA303) — Section C Q5(b): What do you mean by IP address? Explain IP addressing method.
- 2022 Paper (KCA303) — Section B (c): What are the Unicast, Multicast and Broadcast Address? (identify given destination addresses)
- 2023 Paper (KCA303) — Section B (c): Consider IP 196.10.19.10 /26 — find network address, custom mask, #subnets, total host addresses, subnet & broadcast of every subnet.
- 2023 Paper (KCA303) — Section C Q5(a): What is need of IP address? Discuss Classful addressing in IPv4.
- 2023 Paper (KCA303) — Section C Q5(b): Discuss IPv4 packet format with suitable diagram.
- 2024 Paper (KCA303) — Section C Q5(b): What is Internet Protocol (IP)? State and describe various classes used for IP addressing.

### 🟦 **1. What is IP Addressing?**

**Definition:**
An **IP (Internet Protocol) address** is a **unique numerical label** assigned to each device (computer, phone, router) connected to a network.

> It helps us **identify** each device and **locate** it so that data can travel correctly between source and destination.

**Example:**
`142.10.20.12` — this is an IPv4 address.

---

### 🟩 **2. Need for IP Address**

- We need IP addresses to **uniquely identify** devices on the Internet.
- They act like **home addresses** for computers — data packets know exactly **where to go**.
- Every data packet carries **source IP** and **destination IP**.

---

### 🟦 **3. IPv4 (Internet Protocol Version 4)**

**Definition:**
IPv4 is the **4th version** of IP that uses **32 bits** for addressing.

Each IPv4 address is divided into **4 octets (bytes)** — for example:
`192.168.1.10`

**Structure:**

```
192.168.1.10
↑   ↑   ↑   ↑
8b  8b  8b  8b  = 32 bits
```

- Each octet can have a value from **0 to 255**.
- Total possible addresses: **2³² = 4,294,967,296**.

---

### 🟨 **4. Classes of IPv4 Addressing**

IPv4 addresses are divided into **5 classes (A to E)** based on their **first octet range** and purpose.

| **Class** | **Range (First Octet)** | **Default Mask** | **Use**             | **Example**  |
| --------- | ----------------------- | ---------------- | ------------------- | ------------ |
| **A**     | 1 – 126                 | 255.0.0.0        | Very large networks | 10.0.0.5     |
| **B**     | 128 – 191               | 255.255.0.0      | Medium networks     | 172.16.0.1   |
| **C**     | 192 – 223               | 255.255.255.0    | Small networks      | 192.168.1.10 |
| **D**     | 224 – 239               | N/A              | Multicasting        | 224.1.1.1    |
| **E**     | 240 – 255               | N/A              | Experimental        | 245.12.1.3   |

> Note: **127.x.x.x** is reserved for **loopback (localhost)** testing.

---

### 🟩 **5. Types of IPv4 Addresses**

| **Type**      | **Purpose**                  | **Example**                 |
| ------------- | ---------------------------- | --------------------------- |
| **Unicast**   | One-to-one communication     | Sending email to one person |
| **Multicast** | One-to-many (specific group) | Live video conference       |
| **Broadcast** | One-to-all in a network      | Sending ARP request         |

---

### 🟦 **6. IPv4 Packet Format**

Each IPv4 packet has several important fields:

```
 ------------------------------------------------------------
|Version|IHL|Type of Service|Total Length|
|Identification|Flags|Fragment Offset|
|Time to Live|Protocol|Header Checksum|
|Source Address|Destination Address|
|Options|Padding|Data|
 ------------------------------------------------------------
```

**Important Fields:**

- **Version:** IP version (4 for IPv4)
- **Header Length:** Length of IP header
- **TTL (Time to Live):** Maximum hops allowed
- **Protocol:** Next layer protocol (TCP/UDP)
- **Source/Destination Address:** Sender and receiver IPs

---

### 🟩 **7. IPv6 (Internet Protocol Version 6)**

**Definition:**
IPv6 is the **next-generation** IP version that uses **128-bit** addresses.

- Written in **hexadecimal** and separated by colons (`:`).
- Example:
  `2001:0db8:0000:0000:0000:ff00:0042:8329`

**Features of IPv6:**

1. **Huge address space** — 2¹²⁸ addresses.
2. **No need for NAT** (Network Address Translation).
3. **Auto-configuration** support.
4. **Improved security** (IPSec is built-in).
5. **Simpler header structure** for faster routing.

---

### 🟨 **8. Subnetting in IPv4**

**Definition:**
Subnetting is the process of **dividing one large network** into **smaller subnetworks (subnets)**.

> It helps in **efficient IP address management** and improves **security and speed** within networks.

**Example:**
Given IP: `196.10.19.10/26`

- **Default mask (Class C):** 255.255.255.0
- **Custom mask:** /26 → 255.255.255.192
- **Bits borrowed:** 2 bits
- **# of subnets:** 2² = 4
- **Hosts per subnet:** 2⁶ – 2 = 62
- **Usable hosts:** 62 per subnet

Subnets:

| **Subnet** | **Network Address** | **Broadcast Address** |
| ---------- | ------------------- | --------------------- |
| 1          | 196.10.19.0         | 196.10.19.63          |
| 2          | 196.10.19.64        | 196.10.19.127         |
| 3          | 196.10.19.128       | 196.10.19.191         |
| 4          | 196.10.19.192       | 196.10.19.255         |

---

### 🟩 **9. Classless Addressing (CIDR)**

Instead of using fixed classes (A, B, C), **CIDR (Classless Inter-Domain Routing)** allows variable-length subnet masks, written as `/n` (like `/24`, `/26`).

- Helps save IP addresses.
- Common in modern networks and ISPs.

---

### 🟦 **10. Difference Between IPv4 and IPv6**

| **Feature**       | **IPv4**       | **IPv6**             |
| ----------------- | -------------- | -------------------- |
| **Address size**  | 32 bits        | 128 bits             |
| **Notation**      | Decimal (dots) | Hexadecimal (colons) |
| **Header length** | Variable       | Fixed (40 bytes)     |
| **Security**      | Optional       | Built-in (IPSec)     |
| **Address space** | 4 billion      | 3.4×10³⁸             |
| **Example**       | 192.168.1.1    | 2001:0db8::1         |

---

### 🟩 **11. Importance of Logical Addressing in Cloud and Networking**

- Ensures **unique identification** of every device.
- Supports **efficient routing** of data packets.
- Enables **security filtering** and **access control**.
- Makes it possible for **millions of devices** to communicate globally.

---

### 🟦 **12. Diagram: IPv4 vs IPv6 Overview**

```
IPv4:  192.168.1.10      (32 bits)
IPv6:  2001:db8:85a3::8a2e:0370:7334   (128 bits)
```

🧩 IPv6 solves the problem of **address exhaustion** and provides **faster, safer, and more scalable** networking.

# **“Network Layer Protocols: ARP, RARP, BOOTP, and DHCP”**

- DHCP:
  - 2023 Paper (KCA303) — Section A (e): Discuss Dynamic Host Configuration Protocol (DHCP).

## 🟦 **1. Introduction to Network Layer Protocols**

At the **Network Layer**, some special protocols help in **address mapping and automatic IP assignment**.
These protocols are important for communication between devices in a TCP/IP network.

---

## 🟩 **2. Address Resolution Protocol (ARP)**

### 📘 **Definition:**

**ARP (Address Resolution Protocol)** is used to **find the physical address (MAC address)** of a device from its **IP address**.

> In short: ARP converts **IP address → MAC address**.

### ⚙️ **Working:**

1. When a computer wants to send data, it knows the **IP address** but not the **MAC address**.
2. It broadcasts an **ARP Request** on the network:
   “Who has IP 192.168.1.5?”
3. The device with that IP replies with its **MAC address**.
4. The sender stores this mapping in an **ARP cache** for future use.

### 🌐 **Example:**

If our PC wants to talk to the printer (IP 192.168.1.10), ARP helps find its MAC address first.

---

## 🟩 **3. Reverse Address Resolution Protocol (RARP)**

### 📘 **Definition:**

**RARP** is the **opposite of ARP** — it is used to **find the IP address** of a device when it only knows its **MAC address**.

> Converts **MAC address → IP address**.

### ⚙️ **Use Case:**

Used by **diskless computers** or **network devices** (that don’t store IPs) to obtain their IP from a server.

### 🌐 **Example:**

A workstation sends a RARP request with its MAC address, and the RARP server replies with its assigned IP address.

---

## 🟩 **4. BOOTP (Bootstrap Protocol)**

### 📘 **Definition:**

**BOOTP (Bootstrap Protocol)** is used by a computer to **get its IP address automatically** from a **BOOTP server** when it boots up.

> It was the **earlier version of DHCP**.

### ⚙️ **Functions:**

- Provides **IP address**, **subnet mask**, **gateway**, and **boot file name** to clients.
- Used mainly by diskless workstations.

### ⚙️ **Working:**

1. The client sends a **BOOTP request** when powered on.
2. The BOOTP server replies with **IP configuration details**.
3. The client uses this info to join the network.

---

## 🟩 **5. DHCP (Dynamic Host Configuration Protocol)**

### 📘 **Definition:**

**DHCP** is a network protocol used to **automatically assign IP addresses** and other network settings (like gateway, DNS) to devices.

> It is an **improved and dynamic version of BOOTP**.

---

### ⚙️ **DHCP Working Process (4 Steps)**

| **Step**                | **Message**        | **Description**                        |
| ----------------------- | ------------------ | -------------------------------------- |
| **1. DHCP Discover**    | Client → Broadcast | Client searches for a DHCP server.     |
| **2. DHCP Offer**       | Server → Client    | Server offers an available IP address. |
| **3. DHCP Request**     | Client → Server    | Client requests the offered IP.        |
| **4. DHCP Acknowledge** | Server → Client    | Server confirms and assigns the IP.    |

This 4-step exchange is often remembered as **DORA (Discover, Offer, Request, Acknowledge)**.

---

### 📦 **Information DHCP Provides:**

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server
- Lease Time (how long the IP is valid)

---

### 🌐 **Example:**

When we connect our laptop or phone to Wi-Fi, we don’t manually set an IP address —

> the **DHCP server (usually the router)** automatically gives one to us.

---

### ⚙️ **Advantages of DHCP:**

1. **Automatic Configuration** – No manual IP setup needed.
2. **Avoids IP Conflicts** – Ensures unique IPs for all devices.
3. **Saves Time** – Especially useful in large networks.
4. **Flexible** – IPs can be reused (leased temporarily).
5. **Centralized Management** – Admin controls all IP settings from one server.

---

## 🟨 **6. Difference Between ARP, RARP, BOOTP, and DHCP**

| **Protocol** | **Purpose**                              | **Conversion / Function** | **Dynamic or Static** |
| ------------ | ---------------------------------------- | ------------------------- | --------------------- |
| **ARP**      | Find MAC for given IP                    | IP → MAC                  | Static                |
| **RARP**     | Find IP for given MAC                    | MAC → IP                  | Static                |
| **BOOTP**    | Assign IP at boot                        | MAC → IP (from server)    | Semi-Dynamic          |
| **DHCP**     | Assign IP automatically with full config | MAC → IP + Other info     | Dynamic               |

---

## 🟩 **7. Importance in Cloud and Networking**

- These protocols make **network communication automatic and smooth**.
- In cloud environments, **DHCP** ensures VMs and containers get IPs instantly.
- **ARP and RARP** handle device-level communication efficiently.

---

### 🧩 **Diagram: DHCP DORA Process**

```
Client                      Server
  |---- DHCP Discover ----> |
  |<---- DHCP Offer --------|
  |---- DHCP Request -----> |
  |<---- DHCP Ack ----------|

```

# **“Routing Techniques: Interdomain and Intradomain Routing”**

- 2021 Paper (NMCAE25) — Section C Q5(a): What is need of routing algorithms? Discuss the classification of routing algorithms. (intra/interdomain classification)
- 2024 Paper (KCA303) — Section A (f): Define the function of router?

## 🟦 **1. What is Routing?**

### 📘 **Definition:**

**Routing** is the process of **selecting the best path** for data to travel from a **source** to a **destination** across a network.

> In short, routing decides **“which way the data should go.”**

It is performed by a device called a **Router**.

---

## 🟩 **2. Function of a Router**

A **router** is a networking device that:

- Connects **different networks** together.
- **Receives, examines, and forwards** data packets to their correct destination.
- Uses **routing tables and protocols** to decide the best path.

### ⚙️ **Main Functions:**

1. **Path Determination** – Finds the best route for data.
2. **Packet Forwarding** – Moves packets toward their destination.
3. **Network Segmentation** – Reduces traffic and improves performance.
4. **Interconnectivity** – Links LANs and WANs together.

---

## 🟨 **3. Need for Routing Algorithms**

Routing algorithms are needed to:

1. **Find the most efficient path** between devices.
2. **Handle dynamic network changes** (like congestion or link failure).
3. **Balance network load** across different routes.
4. **Ensure reliability and quick delivery** of packets.
5. **Update routing tables automatically** when topology changes.

---

## 🟩 **4. Classification of Routing Algorithms**

Routing algorithms are broadly divided into two types:

| **Type**                | **Operates Within**                 | **Used By**                    | **Example Protocols** |
| ----------------------- | ----------------------------------- | ------------------------------ | --------------------- |
| **Intradomain Routing** | A single autonomous system (AS)     | Organizations, ISPs internally | RIP, OSPF, IGRP       |
| **Interdomain Routing** | Between multiple autonomous systems | Internet-level routing         | BGP                   |

Let’s understand both 👇

---

## 🟦 **5. Intradomain Routing**

### 📘 **Definition:**

Intradomain routing refers to routing **within one autonomous system (AS)** — a network or group of networks managed by one organization.

> It helps all devices inside the same domain communicate efficiently.

### ⚙️ **Examples of Intradomain Routing Protocols:**

#### 🔹 **a. RIP (Routing Information Protocol)**

- Uses **Distance Vector Algorithm**.
- Chooses the path with **minimum hop count**.
- Updates routing tables periodically.
- **Best for small networks.**

#### 🔹 **b. OSPF (Open Shortest Path First)**

- Uses **Link-State Algorithm**.
- Selects route based on **cost (bandwidth)**.
- Automatically updates when a route fails.
- **Scalable for large organizations.**

#### 🔹 **c. IGRP (Interior Gateway Routing Protocol)**

- Developed by Cisco.
- Uses multiple metrics (bandwidth, delay, reliability).
- **Better than RIP** for complex networks.

### 🌐 **Example:**

Within a university’s internal network, OSPF helps route data among departments like Library, Admin, and Labs.

---

## 🟦 **6. Interdomain Routing**

### 📘 **Definition:**

Interdomain routing happens **between multiple autonomous systems (AS)** on the Internet.

> It decides how data travels **from one organization’s network to another’s**.

### ⚙️ **Example Protocol:**

#### 🔹 **BGP (Border Gateway Protocol)**

- The **main protocol used on the Internet**.
- Uses **path vector algorithm**.
- Each AS shares only summarized route information with others.
- Maintains **routing policies** and controls how traffic enters/exits the network.

### 🌐 **Example:**

When we access a website hosted in another country, **BGP** helps route packets between our ISP’s network and the foreign data center’s network.

---

## 🟩 **7. Comparison Between Intradomain and Interdomain Routing**

| **Basis**             | **Intradomain Routing**      | **Interdomain Routing**           |
| --------------------- | ---------------------------- | --------------------------------- |
| **Area of Operation** | Within a single AS           | Between different ASs             |
| **Control**           | Managed by one organization  | Managed by multiple organizations |
| **Protocols Used**    | RIP, OSPF, IGRP              | BGP                               |
| **Algorithm Type**    | Distance Vector / Link State | Path Vector                       |
| **Policy Control**    | Less focus on policy         | Strong policy control             |
| **Example Use**       | Inside a company             | Between ISPs or countries         |

---

## 🟨 **8. Diagram: Routing Types Overview**

```
          +----------------------------+
          |   Internet (Multiple ASs)  |
          +------------+---------------+
                       |
                Interdomain (BGP)
                       |
       ---------------------------------------
       |                |                    |
   AS 1 (RIP)       AS 2 (OSPF)         AS 3 (IGRP)
     |                 |                   |
Intradomain        Intradomain         Intradomain
 Routing             Routing             Routing
```

---

## 🟩 **9. Importance of Routing in Networking**

- Ensures **efficient data delivery** across networks.
- Handles **large-scale communication** across the Internet.
- Provides **fault tolerance** and **load balancing**.
- Keeps **network communication smooth and reliable.**

---
