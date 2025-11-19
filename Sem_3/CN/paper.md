# Question 1 

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

# Question 2 ✅ **TCP vs UDP (10-Point Table)**

| **Point**              | **TCP**                                         | **UDP**                             |
| ---------------------- | ----------------------------------------------- | ----------------------------------- |
| **1. Full Form**       | Transmission Control Protocol                   | User Datagram Protocol              |
| **2. Connection**      | Connection-oriented (handshake hota hai)        | Connectionless (no handshake)       |
| **3. Reliability**     | Reliable – data guaranteed                      | Not reliable – data guarantee nahi  |
| **4. Ordering**        | Packets always arrive **in order**              | Order **not guaranteed**            |
| **5. Speed**           | Slower (checks + confirmations)                 | Faster (no checks)                  |
| **6. Error Checking**  | Strong error checking + recovery                | Basic error checking only           |
| **7. Acknowledgement** | Uses ACKs                                       | No ACK system                       |
| **8. Use Cases**       | Web browsing (HTTP/HTTPS), Email, File Transfer | Streaming, Gaming, VoIP, Live video |
| **9. Overhead**        | High overhead (more control data)               | Low overhead (minimum control)      |
| **10. Packet Size**    | Large, structured packets                       | Small, lightweight packets          |

# Question 3

| **IP Address**   | **Class**               |
| ---------------- | ----------------------- |
| **192.168.1.10** | **Class C**             |
| **10.10.200.6**  | **Class A**             |
| **172.15.165.1** | **Class B**             |
| **230.10.65.30** | **Class D** (Multicast) |

### ✔ **192.168.1.10 → First octet = 192**

192 falls in **192–223** → **Class C**

---

### ✔ **10.10.200.6 → First octet = 10**

10 falls in **1–126** → **Class A**

---

### ✔ **172.15.165.1 → First octet = 172**

But careful!
Students often confuse 172.16–31 = Private, but **class check is separate**.

172 falls in **128–191** → **Class B**

---

### ✔ **230.10.65.30 → First octet = 230**

230 falls in **224–239** → **Class D (Multicast)**

# Question 4

Got you dear — here are **bigger, proper-English, well-structured short notes** on **WWW, HTTP, and E-mail** with:
✔ Definition
✔ Need / Purpose
✔ Features
✔ Related concepts
✔ Easy, exam-friendly flow

---

# ⭐ **1. WWW (World Wide Web)**

### **Definition**

The World Wide Web (WWW) is a large system of interlinked web pages that can be accessed through the internet using a web browser. It uses hyperlinks, URLs, and web protocols to provide information in a multimedia format.

### **Need / Purpose**

* To provide a simple and universal way to access information from anywhere.
* To allow people to share documents, images, videos, and services easily.
* To support online communication, education, shopping, and entertainment.

### **Features**

* Uses **HTTP** to transfer data between client and server.
* Based on **HTML** for designing web pages.
* Provides **hyperlinks** for easy navigation.
* Uses **URLs** to identify each resource uniquely.
* Supports text, images, audio, video, and interactive content.

### **Related Concepts**

* **Web Browser** (Chrome, Firefox) – used to access the web.
* **Web Server** – stores and serves web pages.
* **Search Engine** – helps users find information (Google, Bing).

---

# ⭐ **2. HTTP (HyperText Transfer Protocol)**

### **Definition**

HTTP is a communication protocol that controls how web browsers request web pages and how web servers send responses. It enables the transfer of hypertext (HTML) and other resources across the web.

### **Need / Purpose**

* To define a standard method for communication between client and server.
* To ensure smooth delivery of web pages, images, forms, and website data.
* To support interactive operations like login, form submission, and browsing.

### **Features**

* **Stateless** protocol: every request is independent.
* Supports request methods like **GET**, **POST**, **PUT**, **DELETE**.
* Works on **port 80** (HTTP) and **443** (HTTPS).
* **HTTPS** adds encryption using SSL/TLS for secure communication.
* Lightweight and widely used across all web applications.

### **Related Concepts**

* **Request–Response Model**
* **Status Codes** (200 OK, 404 Not Found, 500 Error)
* **Cookies and Sessions** (used to overcome HTTP’s stateless nature)

---

# ⭐ **3. E-mail (Electronic Mail)**

### **Definition**

E-mail is a digital communication system that allows users to send and receive messages electronically through the internet. It supports text, attachments, images, and documents.

### **Need / Purpose**

* To provide fast, reliable, and cost-effective communication.
* To share files, documents, and official messages instantly.
* To support business communication, notifications, and online services.

### **Features**

* Uses **SMTP** for sending messages.
* Uses **POP3 or IMAP** for receiving messages.
* Allows attachments, formatting, signatures, and CC/BCC.
* Can be accessed from computers or mobile devices.
* Stores messages in an inbox for future reference.

### **Related Concepts**

* **Email Address** – identifies sender/receiver ([example@domain.com](mailto:example@domain.com)).
* **Mailbox** – stores incoming and sent emails.
* **Spam Filtering** – blocks unwanted messages.
* **Attachments** – files sent with the email.

# Question 5

