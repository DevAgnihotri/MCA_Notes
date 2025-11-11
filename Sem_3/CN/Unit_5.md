# **Topic: Application Layer – Basic Concepts**

### 🟩 **1. Domain Name System (DNS)**

- 2021 — Sec C: Q7(b) (Purpose of DNS; three classifications of domain name space)  
- 2023 — Sec B: (e) (short note on DNS)  
- 2024 — Sec C: Q7(b)(i) (short note on DNS)

#### **Definition:**

DNS (Domain Name System) is a **naming service** that converts **human-readable domain names** (like `www.google.com`) into **IP addresses** (like `142.250.183.132`), which computers use to communicate.

#### **Purpose:**

* To make the Internet user-friendly by avoiding the need to remember numeric IP addresses.
* To map domain names ↔ IP addresses.

#### **Working of DNS:**

1. User enters a domain name in browser.
2. DNS resolver sends a query to DNS server.
3. Server responds with the IP address of that domain.
4. Browser connects to that IP to open the website.

#### **Classifications of Domain Name Space:**

DNS uses a **hierarchical structure**, divided into:

1. **Root Domain (.)** – top level of DNS hierarchy.
2. **Top-Level Domains (TLDs):**

   * Generic TLDs (gTLD): `.com`, `.org`, `.net`
   * Country code TLDs (ccTLD): `.in`, `.us`, `.uk`
3. **Second-Level Domains:** e.g., `google.com`, `amazon.in`
4. **Subdomains:** e.g., `mail.google.com`, `blog.microsoft.com`

#### **Example:**

`www.microsoft.com`
→ `www` = subdomain, `microsoft` = second-level domain, `.com` = top-level domain

#### **Key Points:**

* Works on **UDP port 53**
* Used in both IPv4 and IPv6
* Core DNS records: **A, AAAA, MX, CNAME, NS**

---

### 🟦 **2. World Wide Web (WWW)**

- 2022 — Sec C: Q7(a) (option a: URL — WWW concept)  
- 2024 — Sec C: Q7(b)(iii) (short note on WWW)

#### **Definition:**

The **World Wide Web (WWW)** is a **system of interlinked documents and multimedia content** accessible via the Internet using browsers.

#### **Main Components:**

1. **Web Clients (Browsers):** Chrome, Firefox, Edge
2. **Web Servers:** Host and deliver web content
3. **Protocols:** Mainly HTTP and HTTPS
4. **Resources:** Web pages, images, videos, etc., identified by **URLs**

#### **Concept of URL:**

A **Uniform Resource Locator (URL)** is the **address of a resource** on the web.
Example:
`https://www.amazon.in/product`

* `https` → protocol
* `www.amazon.in` → domain
* `/product` → resource path

#### **Working:**

When a user enters a URL:

1. Browser requests web page using HTTP/HTTPS.
2. Server sends the page content.
3. Browser displays it to the user.

#### **Features:**

* Supports hyperlinks for easy navigation.
* Uses multimedia content (text, audio, video).
* Accessible through web browsers globally.

---

### 🟨 **3. HyperText Transfer Protocol (HTTP)**

- 2024 — Sec C: Q7(b)(ii) (short note on HTTP)  
- 2022 — Sec C: Q7(a) (Cookies — HTTP/Web context)

#### **Definition:**

HTTP (HyperText Transfer Protocol) is an **application layer protocol** used to **transfer web data** between a client (browser) and a web server.

#### **Function:**

* Enables **communication between browser and web server.**
* Uses **request–response model.**

#### **HTTP Operation Steps:**

1. **Client sends HTTP Request** (GET, POST, PUT, DELETE).
2. **Server processes request** and sends HTTP Response with status code (e.g., 200 OK, 404 Not Found).

#### **Features:**

* Uses **port 80** (HTTP) or **port 443** (HTTPS for secure communication).
* **Stateless protocol** – each request is independent.
* Uses **Cookies** to maintain session info.

#### **HTTP Example:**

```
GET /index.html HTTP/1.1
Host: www.example.com
```

#### **Cookies in HTTP:**

* Small data files stored on the client’s device.
* Used for **session management, personalization, and tracking.**

---

### 🧩 **Summary Table:**

| **Concept** | **Full Form / Meaning**     | **Purpose / Function**                                  |
| ----------- | --------------------------- | ------------------------------------------------------- |
| **DNS**     | Domain Name System          | Converts domain names to IP addresses                   |
| **WWW**     | World Wide Web              | Platform to access interlinked web pages and multimedia |
| **HTTP**    | HyperText Transfer Protocol | Transfers web data between client and server            |

---

### 🖼️ **Simple Diagram – How the Web Works**

```
[User] → (URL) → [DNS Server] → (IP Address) → [Web Server] → (HTTP Response) → [Browser Displays Page]
```

Perfect 💫 here’s your complete and clear **Application Layer Services notes** — written exactly in the same easy-to-learn and structured style 👇

---

### 🟩 **4. Electronic Mail (E-mail)**

- 2019 — Sec C: Q7(b) (message format, message transfer, mail reader)  
- 2021 — Sec A: (j) (which application layer protocol supports electronic mail?)  
- 2021 — Sec C: Q7(a) (E‑mail components; E‑mail architectures)  
- 2023 — Sec A: (i) (role of SMTP in email)  
- 2023 — Sec C: Q7(b) (E‑mail architectures with components)

#### **Definition:**

**E-mail (Electronic Mail)** is a method of exchanging **digital messages** between users through electronic devices using the **Internet**.

It is one of the most widely used **application layer services** in networking.

---

#### **Components of E-mail System:**

1. **User Agent (Mail Reader):**

   * Interface for users to read, write, send, and organize emails.
   * Examples: Outlook, Gmail, Thunderbird.

2. **Mail Transfer Agent (MTA):**

   * Responsible for **sending and receiving** emails between servers.
   * Uses **SMTP** protocol.

3. **Mail Delivery Agent (MDA):**

   * Delivers received messages to the recipient’s mailbox.

---

#### **E-mail Architecture:**

There are **two main models** of e-mail communication:

1. **Client–Server Model:**

   * The sender uses a **mail client** (User Agent) to send messages.
   * The message passes through **Mail Transfer Agents (MTAs)** and reaches the **recipient’s mail server**.
   * The recipient’s **Mail User Agent (MUA)** retrieves the message.

2. **Store-and-Forward Model:**

   * Emails are temporarily stored on intermediate servers before being forwarded to the final destination.

---

#### **Message Transfer Protocols:**

| **Protocol** | **Full Form**                    | **Function**                                                             |
| ------------ | -------------------------------- | ------------------------------------------------------------------------ |
| **SMTP**     | Simple Mail Transfer Protocol    | Used to send mail from sender to mail server and between mail servers.   |
| **POP3**     | Post Office Protocol v3          | Used to retrieve emails from server (downloads and deletes from server). |
| **IMAP**     | Internet Message Access Protocol | Used to read and manage emails directly on the server.                   |

---

#### **E-mail Message Format:**

1. **Header:**
   Contains control information like `From:`, `To:`, `Subject:`, `Date:`.
2. **Body:**
   Actual text or content of the message.

Example:

```
From: john@example.com
To: dev@example.com
Subject: Project Update
Body: Please check the attached file.
```

---

#### **Role of SMTP:**

* Works on **port 25** (or 587 for secure).
* Transfers messages **from sender’s mail client to mail server** or between mail servers.
* Uses **TCP** for reliable delivery.

---

#### **Diagram: Basic Email Communication Flow**

```
[Sender] → SMTP → [Mail Server] → Internet → [Recipient Mail Server] → POP3/IMAP → [Recipient]
```

---

### 🟦 **2. File Transfer Protocol (FTP)**

- 2021 — Sec B: (e) (short note on FTP)  
- 2023 — Sec B: (e) (short note on FTP)

#### **Definition:**

**FTP (File Transfer Protocol)** is an **application layer protocol** used to **transfer files** between a client and a remote server over a TCP/IP network.

#### **Purpose:**

To **upload**, **download**, **rename**, or **delete** files remotely.

---

#### **Key Components:**

1. **FTP Client:**
   User interface to connect to the server (e.g., FileZilla, WinSCP).
2. **FTP Server:**
   Stores files and handles client requests.

---

#### **Operation:**

* Uses **two connections**:

  * **Control Connection (Port 21):** For sending commands.
  * **Data Connection (Port 20):** For transferring files.

#### **Working Steps:**

1. User connects to FTP server using a username and password.
2. Control connection is established.
3. File transfer occurs through data connection.
4. Connection closes after completion.

---

#### **Modes of FTP:**

1. **Active Mode:** Server initiates data connection to client.
2. **Passive Mode:** Client initiates both control and data connections (used in firewalls).

---

#### **Advantages:**

* Reliable file transfer over TCP.
* Supports resume and batch transfers.
* Widely used in website hosting and data backup.

---

#### **Diagram:**

```
[FTP Client] ⇄ (Control Port 21) ⇄ [FTP Server]
[FTP Client] ⇄ (Data Port 20) ⇄ [FTP Server]
```

---

### 🟨 **3. Remote Login (Telnet / NVT)**

- 2021 — Sec B: (e) (short note on TELNET)  
- 2022 — Sec C: Q7(a) (option d: NVT — Telnet)  
- 2023 — Sec B: (e) (short note on Telnet)  
- 2024 — Sec C: Q7(b)(iv) (short note on TELNET)

#### **Definition:**

**Telnet (Telecommunication Network)** is a **protocol used for remote login** that allows users to **access and manage a remote computer** over a network as if they were locally connected.

It is one of the earliest Internet protocols for **remote command execution**.

---

#### **Purpose:**

* Enables remote access to computers for configuration, administration, and troubleshooting.
* Uses **TCP port 23**.

---

#### **Key Components:**

1. **Telnet Client:** Installed on the user’s device to initiate connection.
2. **Telnet Server:** Accepts connection requests and provides a command-line interface.
3. **NVT (Network Virtual Terminal):**

   * A **standard format** for data exchange between client and server.
   * Ensures both systems can communicate regardless of their hardware/software differences.

---

#### **Working:**

1. User runs Telnet client and connects to remote server.
2. Authentication (username/password) is performed.
3. Commands entered on client are executed on the remote server.
4. Output is sent back to the client’s screen.

---

#### **Advantages:**

* Allows full control over remote systems.
* Lightweight and simple to use.

#### **Limitations:**

* **Not secure** — transmits data (including passwords) in plain text.
* Replaced by **SSH (Secure Shell)** for secure remote login.

---

# Introduction to Cryptography

### 🔐 **Topic: Introduction to Cryptography**

- 2024 — Sec A: (i) (Define security goals of information)  
- 2019 — Sec C: Q7(a) (What is security goals?)

---

### 🟩 **1. Definition**

**Cryptography** is the **science of securing information** by converting it into a **coded format** so that only authorized users can understand it.
It ensures **data confidentiality, integrity, authentication,** and **non-repudiation** during communication.

---

### 🟦 **2. Goals of Cryptography (Security Goals)**

The main goals are known as the **CIA triad**, along with a few additional ones:

1. **Confidentiality:**

   * Ensures that information is **accessible only to authorized users**.
   * Achieved using **encryption**.

2. **Integrity:**

   * Ensures that data is **not altered** or tampered with during transmission.
   * Verified using **hashing** or **digital signatures**.

3. **Authentication:**

   * Confirms the **identity of the sender and receiver**.
   * Example: digital certificates, login credentials.

4. **Non-Repudiation:**

   * Prevents any party from **denying** that they sent or received a message.
   * Implemented using **digital signatures**.

5. **Availability:**

   * Ensures that information and resources are **available whenever required** by authorized users.

---

### 🟨 **3. Applications of Cryptography**

- 2023 — Sec C: Q7(a) (Define network security; discuss network security services)  
- 2019 — Sec C: Q7(a) (types of network attacks — related to cryptographic application)


Cryptography plays a major role in securing digital communications and data.

**Common Applications:**

1. **Secure Communication:**
   Used in **emails, messaging apps, VPNs, and HTTPS websites**.
2. **Data Protection:**
   Encrypts sensitive files and databases (like bank data or health records).
3. **Digital Signatures:**
   Verifies authenticity and ensures no tampering.
4. **E-Commerce:**
   Protects transactions and payment details during online shopping.
5. **User Authentication:**
   Used in password protection, biometrics, and access control systems.

---

### 🟧 **4. Attacks in Cryptography**

- 2019 — Sec C: Q7(a) (Explain different types of network attacks)

Cryptographic systems can face several **types of attacks** by malicious users trying to break security.

| **Type of Attack**                | **Description**                                                      | **Example**                           |
| --------------------------------- | -------------------------------------------------------------------- | ------------------------------------- |
| **Passive Attack**                | Attacker only **monitors** the communication without altering it.    | Eavesdropping, traffic analysis       |
| **Active Attack**                 | Attacker **modifies or injects data** into communication.            | Man-in-the-middle, message alteration |
| **Ciphertext-only Attack**        | Attacker has only the encrypted data and tries to decrypt it.        | Cracking encrypted files              |
| **Known-Plaintext Attack**        | Attacker has some plaintext and its corresponding ciphertext.        | Pattern matching                      |
| **Brute Force Attack**            | Attacker tries **all possible keys** until the correct one is found. | Password cracking                     |
| **Replay Attack**                 | Reuses previously captured valid data packets.                       | Reusing login tokens                  |
| **Phishing / Social Engineering** | Tricks user into revealing information.                              | Fake login pages                      |

---

### 🟫 **5. Encryption and Decryption**

- 2024 — Sec C: Q7(a) (Significance of cryptography; compare public‑key and private‑key cryptography)
- 2024 — Sec C: Q7(b) (encryption/decryption — covered within significance/comparison)
- 2019 — Sec C: Q7(a) (cryptography basics — referenced in topics covered)

#### **Encryption:**

* The process of **converting plaintext into ciphertext** using an algorithm and a key.
* Purpose: To keep data confidential.
* Example:

  ```
  Plaintext: HELLO
  Encrypted (Ciphertext): KHOOR
  ```

#### **Decryption:**

* The process of **converting ciphertext back to plaintext** using the key.
* Example:

  ```
  Ciphertext: KHOOR
  Decrypted: HELLO
  ```

#### **Encryption Formula:**

```
Ciphertext = Encrypt(Plaintext, Key)
Plaintext = Decrypt(Ciphertext, Key)
```

---

### 🟪 **6. Types of Cryptography**

#### **(A) Private Key (Symmetric Key) Cryptography**

* Uses **one single key** for both encryption and decryption.
* Fast and suitable for large data volumes.
* Main drawback: **key must be shared secretly** between sender and receiver.

**Examples:**
DES, AES, Blowfish.

**Diagram:**

```
[Sender]
  ↓ (Encrypt using Key K)
[Ciphertext]
  ↓ (Decrypt using same Key K)
[Receiver]
```

---

#### **(B) Public Key (Asymmetric Key) Cryptography**

* Uses **two keys**:

  * **Public Key** → used for encryption
  * **Private Key** → used for decryption
* More secure but **slower** than symmetric encryption.

**Examples:**
RSA, Diffie-Hellman, ECC.

**Diagram:**

```
[Sender]
  ↓ (Encrypt using Receiver’s Public Key)
[Ciphertext]
  ↓ (Decrypt using Receiver’s Private Key)
[Receiver]
```

---

### 🔷 **Comparison: Public Key vs Private Key Cryptography**

| **Basis**          | **Private Key (Symmetric)**    | **Public Key (Asymmetric)**      |
| ------------------ | ------------------------------ | -------------------------------- |
| **Number of Keys** | One (shared)                   | Two (public and private)         |
| **Speed**          | Fast                           | Slower                           |
| **Security**       | Less secure (key sharing risk) | More secure                      |
| **Used For**       | Bulk data encryption           | Digital signatures, key exchange |
| **Example**        | AES, DES                       | RSA, ECC                         |

---

### 🧩 **7. Significance of Cryptography**

* Protects **data privacy** and ensures **secure communication**.
* Prevents **unauthorized access** and **information theft**.
* Essential for **online banking, secure browsing, and data integrity**.
* Foundation for **cybersecurity and digital trust**.

---

### ✅ **In Short:**

> **Cryptography** ensures secure data transmission by using encryption and decryption techniques.
> It protects against attacks, maintains privacy, and supports authentication through public and private key systems.

---