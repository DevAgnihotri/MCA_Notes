## 🧩 **1. Basic Concept of Software Design**

- What is software design? Describe levels of software design. [2020, Section B Q3(c)]
- What is software design? Explain the various principles and design concepts of software design. [2024, Section B Q(c)]
- What are the elements/components of design model? [2021, Section A (c)]
- Discuss risk management (adjacent topic). Explain how to select the best risk reduction technique. [2023, Section B (e)]

### ✳️ What is Software Design?

Software design is a process to transform user requirements into some suitable form, which helps the programmer in software coding and implementation.

It involves the **process of defining the architecture, components, interfaces, and data** for a software system to satisfy specified requirements.
It bridges the gap between **requirements specification** and **implementation**.

---

### 🧱 Levels of Software Design

There are **three main levels**:

1. **Architectural Design:**

   * Defines the system structure — major modules and their relationships.
   * Output: **Architecture diagram**.
2. **High-Level Design (HLD):**

   * Describes module-level functionality and interfaces.
   * Defines how modules interact.
3. **Low-Level Design (LLD):**

   * Focuses on internal logic, algorithms, and data structures of individual modules.

---

### ⚙️ Principles of Good Software Design

1. **Modularity:** Divide system into manageable components.
2. **Abstraction:** Focus on essential features, hide complexity.
3. **Encapsulation:** Keep data and logic safe within modules.
4. **Cohesion & Coupling:** Aim for **high cohesion**, **low coupling**.
5. **Simplicity:** Avoid unnecessary complexity, while desinging the softawre
6. **Reusability:** Encourage reuse of components.
7. **Maintainability:** Design for easy modification.

---

### 🧩 Design Concepts

* **Design Model:** A representation of software from different viewpoints — data, architecture, interface, and components.

### **Elements of Design Model**

1. **Data Design** — It shows how data is arranged, stored, and used in the system. It helps in planning how information will move between different parts of the program. Proper data design makes it easier to handle and update the data whenever required.

2. **Architectural Design** — It explains the overall structure or layout of the software. This design shows how different modules are linked and how they work together to form the complete system. It acts as a guide for developers to build the system in a clear and organized way.

3. **Interface Design** — It defines how users and system components will communicate with each other. This design helps in creating a smooth connection between user and system. A good interface makes it easier for users to use the system.

4. **Component-Level Design** — It focuses on the inner details of each part of the software. It describes what each component will do and how it will perform its task. This helps in breaking the system into smaller units that are easier to develop, test, and maintain.

5. **Procedural Design** — It explains the step-by-step working of the program. This design helps to show the order in which tasks are done to get the final output. It makes the coding process simple and helps developers understand the exact flow of operations.
---

## 🏗️ **2. Architectural Design**

- Differentiate architectural design and procedural design. [2024, Section C Q5(b)]

### 🧠 Definition

Architectural design is the **blueprint of the software system** that defines major components and their interaction.
It answers **“What are the main parts and how do they work together?”**

It explains the overall structure or layout of the software. This design shows how different modules are linked and how they work together to form the complete system. It acts as a guide for developers to build the system in a clear and organized way.

---

### 🔀 Architectural vs. Procedural Design
| **No.** | **Architectural Design**                                            | **Procedural Design**                                 |
| :-----: | :------------------------------------------------------------------ | :---------------------------------------------------- |
|  **1**  | Shows the overall structure of the software.                        | Shows the step-by-step working of the program.        |
|  **2**  | Focuses on how modules or parts are connected.                      | Focuses on how each part performs its task.           |
|  **3**  | It is a high-level design.                                          | It is a low-level design.                             |
|  **4**  | Helps to understand how the system is divided.                      | Helps to understand how the system actually works.    |
|  **5**  | Describes relationships between different modules.                  | Describes the logic and flow inside a module.         |
|  **6**  | Acts as a blueprint of the whole system.                            | Acts as a guide for coding and implementation.        |
|  **7**  | Gives a broad view of the system’s structure.                       | Gives a detailed view of the system’s procedures.     |
|  **8**  | Used in the early stage of design.                                  | Used after the architectural design is complete.      |
|  **9**  | Focuses more on connections and data flow between modules.          | Focuses more on control flow and processing steps.    |
|  **10** | Example: dividing software into input, process, and output modules. | Example: writing algorithm steps for data processing. |


---

## ⚙️ **3. Low-Level Design — Modularization**

- What are the advantages of Modularization? [2021, Section A (j)]
- What do you mean by function oriented design? Discuss the advantages of modular system. [2020, Section C Q5(a)]

Detailed design deals with the implementation part of sub-systems in the previous two designs.

It is more detailed towards modules and their implementations. It defines logical structure of each module and their interfaces to communicate with other modules.

### 🧩 What is Modularization?

**Modularization** is the process of **dividing a system into smaller, independent modules** that can be developed and tested separately.

Modularization is a technique to divide a software system into multiple discrete and independent modules, which are expected to be capable of carrying out task(s) independently.
---

### ✅ Advantages of Modularization

1. **Simplicity:** Each module is easier to work with.
2. **Reusability:** Modules can be reused in other projects.
3. **Maintainability:** Easy to isolate and fix bugs.
4. **Parallel Development:** Teams can work on different modules simultaneously.
5. **Scalability:** System can be easily expanded.
6. **Testing Ease:** Each module can be unit tested separately.

---

### 🧩Coupling & Cohesion (2024 — Q5(b))

- Explain various types of coupling with the help of an example. [2020, Section C Q5(b)]
- Explain the types of coupling and cohesion. [2021, Section B (d)]
- Define Cohesion. What is Functional Cohesion? Does Functional Cohesion within a module bring about good software design? Give an example. What type of coupling and cohesion is preferred? [2023, Section C Q5(a)]
- What is meant by the term cohesion in the context of software design? [2024, Section C Q5(b)]

- What is meant by the term cohesion in the context of software design? [2024, Section C Q5(b)]

When a software program is modularized, its tasks are divided into several modules based on some characteristics.

There are measures by which the quality of a design of modules and their interaction among each other can be measured. These measures are called coupling and cohesion.

**Coupling** means how much one module in a software system depends on another.
It shows the level of connection between modules.
If coupling is high, modules depend too much on each other.
If coupling is low, modules work more independently, which is better for software design.
**(DSCECC)**

![Coupling Illustration](https://media.licdn.com/dms/image/v2/C5612AQE3VK4whXDp9w/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1520234740041?e=2147483647&v=beta&t=K-dNJioqi7OjATK0NFaSDh4G7TE6lBw7wi-bKVluqBQ)

| **Type of Coupling**                             | **Explanation (Easy and Clear)**                                                                                                                                                         |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Content Coupling**                          | In **content coupling**, one module directly uses or changes the content of another module. This makes them tightly connected, and any change in one can break the other.                |
| **2. Common Coupling**                           | In **common coupling**, two or more modules share the same common data or global variables. Because of this shared data, changing one module’s value can affect all others using it.     |
| **3. External Coupling**                         | **External coupling** happens when modules depend on external systems like files, devices, or communication links. If the external part changes, the modules may stop working correctly. |
| **4. Control Coupling**                          | In **control coupling**, one module controls the behavior of another by passing control information like flags or commands. The control of one module depends on another.                |
| **5. Stamp Coupling (Data-Structured Coupling)** | **Stamp coupling** means that modules share a data structure or record, but each module only uses part of it. So, they are linked through a common structured group of data.             |
| **6. Data Coupling**                             | **Data coupling** occurs when modules share only necessary data through parameters. It is the best type of coupling because modules stay independent and easy to modify.                 |

#### Cohesion (FSCPTLC)

**Cohesion** means how closely the elements or parts inside a single module are related to each other.
It shows how well the tasks within a module work together to perform one purpose.
Higher cohesion is good because it means the module does one clear job.
Lower cohesion is bad because the module tries to do many unrelated things.

![module_cohesion](https://cdn.botpenguin.com/assets/website/software_engineering_coupling_and_cohesion7_d0cacade52.webp)

| **Type of Cohesion**            | **Explanation (Easy and Clear)**                                                                                                                                             |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Coincidental Cohesion**    | In **coincidental cohesion**, the elements in a module are grouped randomly without any proper relation. The tasks do not depend on each other and are just placed together. |
| **2. Logical Cohesion**         | **Logical cohesion** happens when elements in a module perform similar types of tasks, like input or output operations, but are chosen by control flags or conditions.       |
| **3. Temporal Cohesion**        | In **temporal cohesion**, elements are grouped because they are executed at the same time. For example, tasks done during program start-up or shutdown belong together.      |
| **4. Procedural Cohesion**      | **Procedural cohesion** means the elements are grouped because they follow a specific sequence of execution. The tasks are related by order, not by the same purpose.        |
| **5. Communicational Cohesion** | In **communicational cohesion**, elements work on the same data or contribute to the same output. They are grouped because they share common data.                           |
| **6. Sequential Cohesion**      | **Sequential cohesion** means the output of one element becomes the input for another element in the same module. The tasks are connected in a clear sequence.               |
| **7. Functional Cohesion**      | **Functional cohesion** is the best type of cohesion. It means all elements in the module work together to perform one single, well-defined function.                        |

---

### 📊 Structure Chart (2023 — A (e))

- Describe structure chart. [2023, Section A (e)]

A **structure chart** is a diagram that shows the **organization and relationship** between different modules of a system.
It is used in the **design phase** of software development to represent how the system is divided into smaller parts.
A structure chart helps in understanding how data moves and how control is passed between modules.

A **structure chart** uses simple symbols like boxes and arrows —

* **Boxes** represent modules.
* **Arrows** show the flow of data or control between them.

Structure charts make it easier to see the **hierarchy** (which module controls which) and how all modules fit together to form the complete system.

---

### **Features/Adv of Structure Charts**

1. **Hierarchical View:**
   A structure chart shows modules in a **top-down hierarchy**, with the main module at the top and smaller modules below it.

2. **Modular Representation:**
   Each module in the structure chart represents one specific function or task of the system.

3. **Clear Relationships:**
   It clearly shows how one module is connected or linked to another through arrows or lines.

4. **Control and Data Flow:**
   Structure charts show both **control signals** and **data flow** between modules using different arrow styles.

5. **Improves Understanding:**
   By using a structure chart, developers can easily understand how the system works and how tasks are divided.

## 🧮 **1. Pseudocodes and Flowcharts**

### ✳️ Pseudocode

Pseudocode is a **high-level, human-readable description of an algorithm** that uses simple language constructs to represent logic.
It helps in bridging the gap between **program logic** and **actual coding**.

**Key Features:**

* Uses keywords like `IF`, `ELSE`, `FOR`, `WHILE`, `BEGIN`, `END`.
* Focuses on **logic**, not syntax.
* Easily converts into any programming language.

**Example:**

```
BEGIN
   INPUT num
   IF num % 2 == 0 THEN
        PRINT "Even"
   ELSE
        PRINT "Odd"
   ENDIF
END
```

---

### 🌀 Flowchart

A **Flowchart** is a **graphical representation of an algorithm** showing the flow of control using **standard symbols**.

**Common Symbols:**

| Symbol | Meaning        |
| ------ | -------------- |
| ⭘      | Start / End    |
| ⬛      | Process        |
| ⧉      | Input / Output |
| ◆      | Decision       |
| ⬇️     | Flow line      |

**Advantages:**

* Easy visualization of process flow.
* Helps in debugging and documentation.
* Makes logic easier to communicate.

---

---

## 🧭 **3. Design Strategies**

- Function-Oriented Design
    - What do you mean by function oriented design? Discuss the advantages of modular system. [2020, Section C Q5(a)]
    - Compare the object oriented and function-oriented design. [2021, Section C Q5 (one part)]
- Object-Oriented Design
    - What are the main advantages of using an object-oriented design approach over a function-oriented approach? [2024, Section C Q5(a)]
    - Compare the object oriented and function-oriented design. [2021, Section C Q5 (one part)]
- Top-Down and Bottom-Up Design
    - (No explicit TD/BU question in provided papers; related conceptual items appear under basic/architectural topics.)


Software Design Strategies define **how a system is broken down and developed**, guiding overall structure and logic flow.

---

### ⚙️ Function-Oriented Design (FOD)

**Definition:**
A top-down approach where the system is designed **around the functions or processes** that it performs.

**Features:**

* Uses **Data Flow Diagrams (DFDs)**.
* Emphasizes *what functions are performed* and *how data moves*.
* Each function becomes a separate module.

**Advantages:**

1. Promotes **modularity and reusability**.
2. **Easier to understand** for procedural systems.
3. **Good for small to medium projects.**

**Limitations:**

* Less focus on data structure.
* Harder to maintain in complex, data-driven systems.

![FOP](data:image/jpeg;base64,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)
---

### 🧱 Object-Oriented Design (OOD)

**Definition:**
System is modeled as a collection of **objects** that encapsulate both **data and behavior**.

**Core Concepts:**

1. **Encapsulation** — bind data + functions together.
2. **Inheritance** — reuse and extend existing classes.
3. **Polymorphism** — same operation behaves differently on different objects.
4. **Abstraction** — focus on essential features only.

**Advantages:**

* Promotes **reusability and scalability**.
* **Easier maintenance** and **real-world mapping**.
* Supports **data integrity** and **code extensibility**.

![OOP](https://media.geeksforgeeks.org/wp-content/uploads/20231017190331/Object-Oriented-Paradigm.png)
---

### 🔄 FOD vs OOD Comparison
Perfect 👍 here’s a **clear, exam-ready table** comparing **Function-Oriented Design** and **Object-Oriented Design** — written in **simple, easy-to-learn language**, no jargon, just the core theory 👇

---

### **Function-Oriented Design vs Object-Oriented Design**

| **No.** | **Function-Oriented Design**                                    | **Object-Oriented Design**                                             |
| :-----: | :-------------------------------------------------------------- | :--------------------------------------------------------------------- |
|  **1**  | Focuses on functions or procedures that perform tasks.          | Focuses on objects that combine data and functions together.           |
|  **2**  | The main aim is to break the system into smaller functions.     | The main aim is to break the system into classes and objects.          |
|  **3**  | Data is given less importance and kept separate from functions. | Data and functions are combined inside objects.                        |
|  **4**  | Functions can directly access data from other functions.        | Data is hidden inside objects and accessed through methods only.       |
|  **5**  | Reusability is low because functions depend on global data.     | Reusability is high because objects and classes can be reused easily.  |
|  **6**  | Changes in data may affect many functions.                      | Changes are easier to manage because data is protected inside objects. |
|  **7**  | Uses a top-down design approach.                                | Uses a bottom-up design approach.                                      |
|  **8**  | Suitable for small and simple programs.                         | Suitable for large and complex systems.                                |
|  **9**  | Examples: Structured programming using C.                       | Examples: Object-oriented programming using Java, C++, Python.         |
|  **10** | Focus is on “what actions to perform.”                          | Focus is on “who performs the action” (the object).                    |

---

### 🧭 Top-Down and Bottom-Up Design

#### **Top-Down Design**

* Start from the **highest-level system** and break it into smaller components.
* Used in **function-oriented** approach.
* Focuses on **decomposition** first.
  **Advantages:**
* Clear structure, easy to trace requirements.
* Early detection of missing functionality.

#### **Bottom-Up Design**

* Start from **low-level modules or components** and integrate them into a complete system.
* Used in **object-oriented** systems.
* Focuses on **composition** first.
  **Advantages:**
* Promotes reusability.
* Early testing of modules possible.

Perfect, dear 🌟 — here are your **detailed, clear, and exam-ready notes** on
**Software Measurement and Metrics**, covering:
**Halstead’s Software Science, Function Point (FP) Based Measures, and Cyclomatic Complexity (Control Flow Graphs)** — written in **simple, learnable English** like our earlier ones 👇

---

# 🧩 **Software Measurement and Metrics — Overview**

- Halstead’s Software Science
    - What is Halstead’s software science metric? Define. [2021, Section C Q6 (part b)(a)]
    - Calculate Halstead metrics (Volume and Difficulty) for given code. [2023, Section C Q6(a)]
- Function Point (FP) Based Measures
    - Explain about function point metric in detail. [2021, Section C Q6 (part b)(b)]
- Cyclomatic Complexity / Control Flow Graphs
    - What is cyclomatic complexity? Calculate the cyclomatic complexity of the following code: [largest() { ... }]. [2020, Section C Q6(a)]
    - How to compute the cyclomatic complexity? [2021, Section A (f)]
    - What is Cyclomatic Complexity? [2024, Section A (e)]
- Coding-to-metrics items (code-based cyclomatic/Halstead problems referenced above). [2020, 2021, 2023, 2024 as listed]


### ✳️ What are Software Metrics?

Software Metrics are **quantitative measures** that help us **analyze, evaluate, and improve** software quality, size, complexity, and performance.

**Purpose of Software Metrics:**

1. To **measure software productivity**.
2. To **estimate effort, time, and cost**.
3. To **analyze software quality and complexity**.
4. To **compare projects** and **improve future design**.

---

## 📘 **1. Halstead’s Software Science**

### 💡 Definition

Halstead’s Software Science is a **size-oriented software metric** developed by **Maurice Halstead** to measure software’s complexity and effort based on the **number of operators and operands** in a program.

It helps to **predict effort, time, and errors** in software development.

---

### 📊 **Halstead’s Parameters**

| Symbol | Meaning                        | Description               |
| ------ | ------------------------------ | ------------------------- |
| **n₁** | Number of unique operators     | e.g. +, -, if, return     |
| **n₂** | Number of unique operands      | e.g. variables, constants |
| **N₁** | Total occurrences of operators | Count all operators used  |
| **N₂** | Total occurrences of operands  | Count all operands used   |

---

### 📐 **Formulas**

| **Measure**                | **Formula**              | **Meaning**                |
| -------------------------- | ------------------------ | -------------------------- |
| **Program Vocabulary (n)** | n = n₁ + n₂              | Total unique elements      |
| **Program Length (N)**     | N = N₁ + N₂              | Total elements used        |
| **Volume (V)**             | V = N × log₂(n)          | Size of the program        |
| **Difficulty (D)**         | D = (n₁ / 2) × (N₂ / n₂) | Effort to understand code  |
| **Effort (E)**             | E = D × V                | Total mental effort        |
| **Time (T)**               | T = E / 18 sec           | Time to code or understand |
| **Bugs (B)**               | B = E^(2/3) / 3000       | Estimated errors           |

---

### 🧠 **Interpretation**

* **Higher Volume → More code to understand**
* **Higher Difficulty → More complex code**
* **Higher Effort → More development or debugging time**

✅ **Example Question:**
“Calculate Halstead Volume and Difficulty for the given code.”
👉 Use formulas with the given operator/operand counts.

---

## ⚙️ **2. Function Point (FP) Based Measures**

### 💡 Definition

**Function Point (FP)** is a **functionality-oriented metric** used to measure the **size of software** based on the **features delivered to the user**, not lines of code.

Developed by **Allan Albrecht (IBM)**, it focuses on **what the software does**, not how it’s implemented.

---

### 📊 **Five Major Components**

| **Component**                         | **Description**                | **Example**       |
| ------------------------------------- | ------------------------------ | ----------------- |
| **1. External Inputs (EI)**           | User inputs that update data   | Forms, data entry |
| **2. External Outputs (EO)**          | Outputs generated              | Reports, messages |
| **3. External Inquiries (EQ)**        | Input-output combinations      | Search forms      |
| **4. Internal Logical Files (ILF)**   | Internal data stores           | Database tables   |
| **5. External Interface Files (EIF)** | Shared data with other systems | Linked databases  |

---

### 🧾 **Computation Steps**

1. **Identify & Count** the above five components.
2. **Assign Weights** (low, average, high complexity).
3. **Calculate Unadjusted Function Points (UFP):**
   [
   UFP = \sum ({count of each component × its weight})
   ]
4. **Calculate Value Adjustment Factor (VAF):**
   [
   VAF = 0.65 + 0.01 × \sum ({complexity adjustment values})
   ]
5. **Final Function Points (FP):**
   [
   FP = UFP × VAF
   ]

---

### 💬 **Advantages**

* Independent of programming language.
* Measures user functionality.
* Useful for **early estimation** before coding starts.

---

### 📘 **Example**

A system with:

* 10 Inputs (avg weight = 4)
* 5 Outputs (avg weight = 5)
* 2 Files (avg weight = 10)

Then,
UFP = (10×4) + (5×5) + (2×10) = 40 + 25 + 20 = **85 FP**

---

## 🧮 **3. Cyclomatic Complexity (CC)**

### 💡 Definition

Cyclomatic Complexity is a **control flow-based metric** proposed by **Thomas McCabe**.
It measures the **number of linearly independent paths** in a program.

👉 **It indicates the logical complexity of a program.**

---

### 📊 **Formula**

[
V(G) = E - N + 2P
]
where:

* **E =** Number of edges in Control Flow Graph
* **N =** Number of nodes in Control Flow Graph
* **P =** Number of connected components (usually 1 for a single function)

---

### 🧠 **Alternate Method**

Count the **number of decision points (like if, while, for, case)**:
[
V(G) = \text{Number of decision nodes} + 1
]

---

### 🧾 **Example**

```c
if (a > b)
   x = a;
else
   x = b;
printf("%d", x);
```

👉 There is 1 decision point →
Cyclomatic Complexity = 1 + 1 = **2**

---

### 📈 **Interpretation**

| **Cyclomatic Complexity** | **Meaning**         | **Remarks**              |
| ------------------------- | ------------------- | ------------------------ |
| 1 – 10                    | Simple, low risk    | ✅ Easy to test           |
| 11 – 20                   | Moderate complexity | ⚠️ Needs careful testing |
| 21 – 50                   | Complex             | ❌ Hard to test           |
| > 50                      | Very complex        | 🚫 Re-design needed      |

---

### 📘 **Control Flow Graph (CFG)**

A **graphical representation** of the control flow of a program:

* **Nodes** → Statements or blocks of code
* **Edges** → Control paths between them

Helps in **visualizing program logic** and **calculating CC**.

---

### 🧩 **Importance**

* Identifies complex areas of code.
* Helps in **unit testing and debugging**.
* Reduces risk of logical errors.
* Guides **modular design** decisions.

---

