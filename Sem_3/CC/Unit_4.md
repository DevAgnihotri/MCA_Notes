# 🌩️ **Virtualization for Cloud: Need for Virtualization**

### 🔹 **Meaning**

**Virtualization** is the technique of creating a **virtual (non-physical)** version of a computing environment such as a server, operating system, storage, or network.
It allows one physical system to run **multiple virtual systems**, each working independently as if it were a real computer.

This is done using special software known as a **Virtual Machine Monitor (VMM)** or **Hypervisor**, which manages the virtual machines (VMs) and allocates resources like CPU, memory, and storage to them.

---

### 💡 **Why Virtualization is Needed in Cloud Computing**

- 2023 (A g): What is the usage of virtualization platform in implementing cloud?
- 2022 (A h): Determine the reasons used for adopting Virtual Machine Monitors.

Virtualization is the **backbone of cloud computing** — without it, cloud services like AWS, Azure, or Google Cloud could not exist in their flexible form. It provides the environment where **one physical server acts like many**.

1. **Efficient Resource Utilization**

   - Physical systems often remain underused, but virtualization allows dividing one system into multiple VMs, ensuring every bit of hardware is put to work efficiently.
   - For example, a single powerful server can host many smaller virtual servers instead of buying multiple physical ones.

2. **Cost Reduction**

   - Organizations save money on hardware, maintenance, electricity, and cooling since multiple systems run on one machine.

3. **Isolation and Security**

   - Each virtual machine runs separately. A failure or attack on one VM does not affect others, improving system safety.

4. **Scalability and Flexibility**

   - Cloud providers can easily create, modify, or delete VMs based on user demand. This flexibility makes scaling up or down simple and fast.

5. **Simplified Management**

   - Virtual machines can be cloned, backed up, or moved (migrated) between physical servers easily, helping administrators manage large systems centrally.

6. **Multi-Tenancy Support**

   - In public clouds, many users share the same infrastructure. Virtualization ensures proper separation and security among users’ data and operations.

7. **Testing and Development Environments**

   - Developers can create multiple OS environments (like Windows, Linux) on a single system for testing applications safely.

8. **Disaster Recovery and Maintenance**

   - Virtualization allows easy **snapshotting** — saving the exact state of a VM. It helps in quick recovery during system crashes or maintenance.

---

### 🧠 **Role of Virtual Machine Monitors**

The **Virtual Machine Monitor (VMM)**, also called a **Hypervisor**, is the controlling software layer that creates and manages virtual machines.
It ensures:

- Each VM gets fair access to hardware,
- Complete isolation between machines, and
- Smooth performance even when multiple OS run simultaneously.

Cloud data centers use hypervisors like **VMware, KVM, Xen, and Microsoft Hyper-V** to manage thousands of VMs across large clusters of physical machines.

VMMs are adopted because they make the system more efficient, safer, and easier to manage. They also support migration of virtual machines between servers without downtime, helping in load balancing and maintenance.

---

### 💬 **In Simple Words:**

Virtualization is needed in cloud computing because it **turns one physical computer into many logical computers**, allowing **cost savings**, **resource efficiency**, **security**, and **flexible management** — all of which are essential to run modern cloud services.

---

# ⚖️ **Pros and Cons of Virtualization (Including Pitfalls)**

- 2024 (C Q5b): Analyze the pros and cons of virtualization in detail.
- 2018 (B h / 2021 C Q4(b)): Enlist and explain some of the common pitfalls that come with virtualizations.

### ✅ **Advantages / Benefits of Virtualization**

1. **Better Hardware Utilization**

   - One physical system can run many virtual systems, using CPU, memory, and storage to the fullest.

2. **Cost Efficiency**

   - Reduces the need for physical hardware, cutting down purchase, power, and maintenance costs.

3. **Isolation Between Systems**

   - Each VM works independently. Problems or malware in one system don’t affect others.

4. **Easier Backup and Recovery**

   - Snapshots and cloning make it easy to recover from crashes or errors quickly.

5. **Scalability**

   - Creating a new server in a virtualized setup takes minutes instead of hours or days.

6. **Improved Flexibility**

   - Virtual machines can be easily moved between servers or adjusted for more or fewer resources.

7. **Eco-Friendly**

   - Fewer physical servers mean lower energy use and carbon footprint.

8. **Testing and Experimentation**

   - Developers can safely test software, system updates, or configurations in virtual environments.

---

### ❌ **Disadvantages / Drawbacks of Virtualization**

1. **Performance Overhead**

   - Because there’s a layer between hardware and software (the hypervisor), performance may slightly reduce compared to a dedicated physical machine.

2. **Complex Setup and Management**

   - Virtualization environments require powerful hardware and skilled administrators.

3. **Security Risks**

   - If a hacker gains access to the hypervisor, they could reach all virtual machines on that host.

4. **Resource Contention**

   - If too many virtual machines share one host, they may compete for CPU or memory, slowing each other down.

5. **Licensing Costs**

   - Each virtual machine may need its own software or OS license, increasing costs.

6. **Compatibility Issues**

   - Some hardware devices or older software might not work correctly in virtualized environments.

---

## ☁️ **Types of Virtualization**

### 🔹 **Definition**

**Virtualization types (or levels)** refer to the **different ways or layers** at which a system can be virtualized — from hardware level up to the application level.
Each type focuses on **which part of the system** is being virtualized (hardware, OS, server, storage, etc.).

---

## 🧩 **Main Types / Levels of Virtualization**

**Types of Virtualization / Levels**

- 2024 (A e): Express the levels of virtualization.
- 2022 (B d): Differentiate between Hardware Virtualization and Server Virtualization.
- 2023 (C Q6b): Describe in detail about hardware virtualization and server virtualization with diagram and examples.
- 2023 (A h) / 2023 (A h) & 2023 (A h): Differentiate between Para virtualization and Full virtualization. (2023 A h, 2022 C Q6b)

# **Types of Virtualization(HONDASS)**

## **1. Hardware Virtualization**

Hardware virtualization is a type of virtualization in which **physical hardware such as CPU, memory, storage, and devices are virtualized using a hypervisor**.
- The hypervisor creates multiple **virtual machines**, and each virtual machine runs its **own operating system** independently.
- Hardware virtualization is widely used in cloud computing because it allows many users to share the same physical hardware safely.

![Image](https://www.researchgate.net/publication/280095977/figure/fig7/AS:667718932000783@1536208007208/Hardware-virtualization.png)
---

## **2. Server Virtualization**

Server virtualization is a type of virtualization in which **a physical server is divided into multiple virtual servers**.
- Each virtual server works independently and can run different applications or services.
- This type of virtualization improves **server efficiency**, reduces **wastage of resources**, and makes server management easier.

![Image](https://www.researchgate.net/figure/Figure1-Architecture-of-Server-Virtualization_fig1_339749899)
---

## **3. Operating System Virtualization**

Operating system virtualization is a type of virtualization in which **multiple virtual environments are created on a single operating system**.
- All virtual systems share the **same OS kernel**, but they work as separate systems.
- This type of virtualization is lightweight, fast, and commonly used for running applications in isolated environments.

---
![Image](https://media.geeksforgeeks.org/wp-content/uploads/20250408150440048447/1.webp)

## **4. Storage Virtualization**

Storage virtualization is a type of virtualization in which **multiple physical storage devices are combined into one virtual storage system**.
- Users do not see the actual physical disks and access storage as a single unit.
- This makes storage management simple and improves storage performance and reliability.

![Image](https://www.interviewbit.com/blog/wp-content/uploads/2022/05/Storage-Virtualization-877x1024.png)
---

## **5. Network Virtualization**

Network virtualization is a type of virtualization in which **network resources such as switches, routers, and connections are created virtually**.
It allows multiple virtual networks to operate on the same physical network.
Network virtualization improves **network security**, **flexibility**, and **control** in cloud environments.

---

## **6. Desktop Virtualization**

Desktop virtualization is a type of virtualization in which **desktop operating systems run on a central server instead of local computers**.
Users access their desktop using the internet from any device.
This type of virtualization helps in **centralized control**, **easy maintenance**, and **secure access**.

---

## **7. Application Virtualization**

Application virtualization is a type of virtualization in which **applications run in a virtual environment without being directly installed on the operating system**.
The application is isolated from the system, which prevents conflicts with other software.
This improves system stability and makes application deployment easier.

#### **Difference Between Paravirtualization and Full Virtualization**

| No. | Paravirtualization                   | Full Virtualization                          |
| --- | ------------------------------------ | -------------------------------------------- |
| 1   | Guest OS **knows** it is virtualized | Guest OS **does not know** it is virtualized |
| 2   | Guest OS is **modified**             | Guest OS is **not modified**                 |
| 3   | Works with **special OS support**    | Works with **any OS**                        |
| 4   | OS talks **directly to hypervisor**  | OS talks to **virtual hardware**             |
| 5   | **Faster performance**               | **Slightly slower** performance              |
| 6   | Less hardware emulation              | Full hardware emulation                      |
| 7   | Better efficiency                    | More resource usage                          |
| 8   | Example: Xen (paravirtual mode)      | Example: VMware, VirtualBox                  |
| 9   | Harder to install                    | Easy to install                              |
| 10  | Less compatible                      | Highly compatible                            |

---

# **What is a Virtual Machine (VM)?**

A **Virtual Machine (VM)** is a **virtual software-based computer** that works like a real physical computer.
It has its own **operating system, CPU, memory, and storage**, but it runs on a **physical machine using virtualization technology**.

## ⚙️ **System Virtual Machines (System VMs)**

### 🔹 **Definition**

A System Virtual Machine is a type of virtual machine that allows a full operating system to run as if it were installed on a real physical computer. System VMs are mainly used to run multiple operating systems on one machine.

### 🔹 **Features:**

1. Provides full hardware abstraction (CPU, memory, I/O).
2. Each system VM is **completely isolated** from others.
3. Can run different OSs on the same host.

### 🔹 **Example:**

- VMware Workstation
- VirtualBox
- Microsoft Hyper-V

### 🔹 **Structure:**

```
Physical Hardware
   ↓
Virtual Machine Monitor (Hypervisor)
   ↓
System Virtual Machines
   ↓
Guest OS + Applications
```

### 🔹 **Use Case:**

Used in **server consolidation**, **testing environments**, and **cloud infrastructure (IaaS)**.

---

## ⚙️ **Process Virtual Machines (Process VMs)**

### 🔹 **Definition**

A **Process Virtual Machine** is a VM that is designed to run **a single process or program** as an independent environment.
It **exists only while that process is running** and disappears after the program ends.

### 🔹 **Example:**

- **Java Virtual Machine (JVM)** → runs Java programs.
- **.NET CLR (Common Language Runtime)** → runs .NET applications.

### 🔹 **Features:**

1. Supports platform-independent code execution.
2. Provides runtime services like garbage collection, security, and memory management.
3. Offers portability — the same program runs on different operating systems.

### 🔹 **Structure:**

```
Application Code
   ↓
Process Virtual Machine (e.g., JVM)
   ↓
Host Operating System
   ↓
Hardware
```

## **Difference Between System VM and Process VM**

| No. | System Virtual Machine                 | Process Virtual Machine                   |
| --- | -------------------------------------- | ----------------------------------------- |
| 1   | Virtualizes **entire hardware system** | Virtualizes **a single process**          |
| 2   | Runs a **full operating system**       | Runs **one application**                  |
| 3   | Exists as long as the VM is running    | Exists only while program runs            |
| 4   | Uses a **hypervisor**                  | Uses a **runtime environment**            |
| 5   | Heavier and uses more resources        | Lightweight and uses fewer resources      |
| 6   | Used for system-level virtualization   | Used for application-level virtualization |
| 7   | Can run different OS types             | OS-independent applications               |
| 8   | Starts before applications             | Starts with the application               |
| 9   | Example: VirtualBox, VMware            | Example: Java Virtual Machine (JVM)       |
| 10  | Common in cloud infrastructure         | Common in software execution              |

---

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20200728155828/SystemVM.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20200728160724/ProcessVM1.png)
---

## ⚙️ **Virtual Machine Monitor (VMM) / Hypervisor**

### 🔹 **Definition**

A **Virtual Machine Monitor (VMM)** — also known as a **Hypervisor** — is the **core software layer** that enables virtualization.
It manages multiple VMs and allocates resources like CPU, RAM, and I/O devices to them.

### 🔹 **Functions of a VMM:**

1. **Creation and Management of VMs**

   - Creates, starts, pauses, and deletes virtual machines.

2. **Resource Allocation**

   - Distributes physical resources (CPU, memory) among VMs.

3. **Isolation**

   - Ensures each VM runs independently.

4. **Performance Monitoring**

   - Tracks resource usage and performance.

5. **Security Control**

   - Prevents VMs from interfering with each other.

---

#### **Type 1 Hypervisor (Bare-Metal) – Definition**

A **Type 1 Hypervisor** runs **directly on the physical hardware** without any host operating system.
It controls hardware resources and is mainly used in **servers and cloud data centers**.

---

#### **Type 2 Hypervisor (Hosted) – Definition**

A **Type 2 Hypervisor** runs **on top of a host operating system** like a normal software.
It is mainly used for **learning, testing, and personal use**.

---

#### **Difference Between Type 1 and Type 2 Hypervisor**

| No. | Type 1 Hypervisor               | Type 2 Hypervisor                       |
| --- | ------------------------------- | --------------------------------------- |
| 1   | Runs directly on hardware       | Runs on host OS                         |
| 2   | No host operating system needed | Host OS is required                     |
| 3   | Faster performance              | Slightly slower                         |
| 4   | More secure                     | Less secure                             |
| 5   | Used in cloud computing         | Used on personal computers              |
| 6   | Handles hardware directly       | Uses OS to access hardware              |
| 7   | More complex to set up          | Easy to install                         |
| 8   | Better resource efficiency      | Lower efficiency                        |
| 9   | Example: VMware ESXi, Xen       | Example: VirtualBox, VMware Workstation |
| 10  | Production-level use            | Learning and testing use                |


![Image](https://miro.medium.com/v2/resize:fit:1400/0*r7b1FbiZM3bdTZDf.png)
---

### 🔹 **Host VMM vs Native VMM vs Process VM**

### Process VM

- 2018 (B e): What is the difference between process virtual machines, host VMMs and native VMMs?

## ⚙️ **Interpretation and Binary Translation**

- 2018 (A e): What do you mean by full virtualization?
- 2022 (C Q6b): Binary Translation is a method for achieving Full Virtualization. Discuss. Also compare Binary Translation with Para Virtualization.

### 🔹 **Purpose**

Both _Interpretation_ and _Binary Translation_ are **techniques used by the hypervisor** to execute guest OS instructions safely — especially when running **unmodified operating systems** in **Full Virtualization**.

---

### 🧩 **1. Interpretation**

- In **interpretation**, the VMM **reads and executes guest instructions one by one**.
- Privileged instructions (like hardware access) are **trapped** and handled by the VMM safely.

**Example:**
If a guest OS tries to access hardware directly, the VMM intercepts that instruction and simulates the behavior safely.

**Advantage:**

- Simple and flexible.

**Disadvantage:**

- Very slow because each instruction is executed separately.

---

### 🧩 **2. Binary Translation**

- **Binary Translation** improves performance by translating the guest OS code **before execution**.
- The VMM **scans and replaces** unsafe or privileged instructions with **safe versions** that run under control of the hypervisor.

**Steps:**

1. Guest code is analyzed.
2. Privileged instructions are replaced.
3. Translated code is cached for reuse.

**Advantage:**

- Much faster than interpretation.
- Allows **Full Virtualization** even when guest OS is unmodified.

**Example:** VMware Workstation uses binary translation.

### ⚖️ **Comparison: Binary Translation vs Para Virtualization**

| Aspect          | Binary Translation                           | Para Virtualization                    |
| :-------------- | :------------------------------------------- | :------------------------------------- |
| **Guest OS**    | Unmodified                                   | Modified                               |
| **Method**      | Replaces privileged instructions dynamically | Uses hypercalls (direct communication) |
| **Performance** | Slightly slower                              | Faster                                 |
| **Complexity**  | Complex translation layer                    | Requires modified OS                   |
| **Example**     | VMware                                       | Xen                                    |

## ⚙️ **2️⃣ Xen Hypervisor**

### 🔹 **Type:** Type-1 (Bare-Metal) Hypervisor

### 🔹 **Developer:** Originally by **University of Cambridge**, now maintained by **Xen Project (Linux Foundation)**

- Xen is a Type 1 (Bare-Metal) hypervisor that runs directly on hardware. It's Open Source and Lightweight
- Its main purpose is to run many virtual machines safely and efficiently in cloud systems.
- It works by controlling hardware directly and sharing resources among virtual machines.

---

## ⚙️ **3️⃣ KVM (Kernel-based Virtual Machine)**

### 🔹 **Type:** Type-1 Hypervisor (integrated into Linux Kernel)

### 🔹 **Developer:** Red Hat / Open-source Linux community

- KVM is a Type 1 (Bare-Metal) hypervisor built into the Linux kernel. Open Source
- Its purpose is to turn a Linux system into a virtual machine manager.
- It works by using the Linux kernel to manage hardware and run virtual machines.
---

## ⚙️ **4️⃣ VMware**

### 🔹 **Type:** Available as both Type-1 and Type-2

### 🔹 **Developer:** VMware Inc. (a part of Broadcom, formerly Dell Technologies)

- VMware (like VMware ESXi) is a Type 1 (Bare-Metal) hypervisor used in enterprise and cloud environments.
- Its purpose is to create and manage virtual machines easily and securely.
- It works by virtualizing hardware and providing strong management tools.

### 🔹 **Use Cases:**

- Widely used in **corporate data centers**, **testing labs**, and **cloud setups**.

---

## ⚙️ **5️⃣ VirtualBox**

### 🔹 **Type:** Type-2 (Hosted) Hypervisor

### 🔹 **Developer:** Oracle Corporation (open-source edition available)

### 🔹 **Definition:**

- VirtualBox is a Type 2 (Hosted) hypervisor that runs on top of an operating system.
- Its purpose is learning, testing, and running different operating systems on personal computers.
- It works like normal software that creates virtual machines using the host OS.

---

## ⚙️ **6️⃣ Microsoft Hyper-V**

### 🔹 **Type:** Type-1 (Native / Bare-Metal)

### 🔹 **Developer:** Microsoft Corporation

### 🔹 **Definition:**

- Microsoft Hyper-V is a Type 1 (Bare-Metal) hypervisor developed by Microsoft.
- Its purpose is to run virtual machines on Windows servers and data centers.
- It works by directly controlling hardware and managing multiple virtual machines.

---
