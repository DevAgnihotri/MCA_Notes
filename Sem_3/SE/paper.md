# Question 1

## **Black Box Testing vs White Box Testing (10 Easy Points)**

| **#**  | **Black Box Testing**            | **White Box Testing**                   |
| ------ | -------------------------------- | --------------------------------------- |
| **1**  | Tester **does NOT see code**     | Tester **can see and understand code**  |
| **2**  | Focus on **output/behavior**     | Focus on **internal logic + structure** |
| **3**  | Checks **what** the system does  | Checks **how** the system works         |
| **4**  | Test cases from **requirements** | Test cases from **code flow**           |
| **5**  | Good for **user-level testing**  | Good for **developer-level testing**    |
| **6**  | No need for coding knowledge     | Requires **strong coding skills**       |
| **7**  | Can miss hidden code errors      | Can catch **hidden logical errors**     |
| **8**  | Slower for deep logic issues     | Faster for finding logic mistakes       |
| **9**  | Examples: UI, forms, login page  | Examples: loops, conditions, paths      |
| **10** | Done by **testers** mostly       | Done by **developers** mostly           |

---

# Question 2

## 1. Functional Point Analysis (FPA)

### Definition
**Function Point (FP)** is a **functionality-oriented metric** used to measure the **size of software** based on the **features delivered to the user**, not lines of code.

Developed by **Allan Albrecht (IBM)**, it focuses on **what the software does**, not how it’s implemented.

### Key Components (The 5 Parameters)
To calculate FPA, you classify the software's functions into five distinct types. These are often called the "information domain values."

1.  **External Inputs (EI):**
    * Data entering the application from the outside (user or another system) that updates internal logical files.
    * *Example:* User registration forms, login screens.
2.  **External Outputs (EO):**
    * Data leaving the system that contains derived information (calculated or processed data).
    * *Example:* Reports, calculated receipts, error messages.
3.  **External Inquiries (EQ):**
    * An input-output combination that results in data retrieval.
    * *Example:* Search functionality, viewing a bank balance.
4.  **Internal Logical Files (ILF):**
    * Data that resides within the application and is maintained through External Inputs.
    * *Example:* A database table storing customer details.
5.  **External Interface Files (EIF):**
    * Data that resides *outside* the application and is read only.
    * *Example:* A payment gateway database accessed by your app.

### How to Calculate (The Formula)
The final Functional Point (FP) count is calculated using the **Unadjusted Function Points (UFP)** and the **Value Adjustment Factor (VAF)**.

The formula is:
FP = UFP * VAF

* **UFP:** The sum of all the weighted counts of the 5 parameters above.
* **VAF:** A factor derived from 14 General System Characteristics (like performance, security, or reusability needs).

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

## 2. Cyclomatic Complexity

Cyclomatic Complexity is a **control flow-based metric** proposed by **Thomas McCabe**.
It measures the **number of linearly independent paths** in a program.

👉 **It indicates the logical complexity of a program.**

* **Low Complexity:** Easier to test and maintain.
* **High Complexity:** Harder to test; higher probability of defects.

### Formulas
There are three standard ways to calculate Cyclomatic Complexity, denoted as $V(G)$:

**Method 1: Graph Formula**
$$V(G) = E - N + 2P$$
* $E$ = Number of Edges (lines/arrows in the flow graph)
* $N$ = Number of Nodes (circles/states in the flow graph)
* $P$ = Number of connected components (usually 1 for a single program)

**Method 2: Predicate Node Formula**
$$V(G) = P + 1$$
* $P$ = Number of Predicate Nodes (nodes that contain a condition/decision like `if`, `while`, `for`).

**Method 3: Region Formula**
$$V(G) = R$$
* $R$ = Number of enclosed regions in the graph + 1 (the outer region).

---

### Steps to Calculate Cyclomatic Complexity

For exams, you are usually given a code snippet and asked to find the complexity. Follow these steps:

**Step 1: Construct the Control Flow Graph (CFG)**
* Translate the code into a diagram.
* Represent sequential statements as **Nodes** (circles).
* Represent the flow of control (sequences, jumps) as **Edges** (arrows connecting circles).
* Any statement that makes a decision (`if`, `while`, `for`) creates a branching node.

**Step 2: Count the Elements**
Count the number of Nodes ($N$) and the number of Edges ($E$) in your drawing.

**Step 3: Apply the Formula**
Plug your counts into the formula: $V(G) = E - N + 2$.

> **Example Calculation:**
> * If your graph has **10 Edges** and **8 Nodes**:
> * $$V(G) = 10 - 8 + 2$$
> * $$V(G) = 4$$
> * **Result:** The complexity is 4, meaning there are 4 independent paths to test.

**Step 4 (Shortcut Method):**
If you do not have time to draw the graph, simply count the decision keywords (`if`, `for`, `while`, `case`, `&&`, `||`) in the code and add 1.
$$V(G) = \text{Number of Conditions} + 1$$

***

# Question 3

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

![Coupling Illustration](https://media.licdn.com/dms/image/v2/C5612AQE3VK4whXDp9w/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1520234740041?e=2147483647&v=beta&t=K-dNJioqi7OjATK0NFaSDh4G7TE6lBw7wi-bKVluqBQ)

| **Type of Coupling**                             | **Explanation (Easy and Clear)**                                                                                                                                                         |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Content Coupling**                          | In **content coupling**, one module directly uses or changes the content of another module. This makes them tightly connected, and any change in one can break the other.                |
| **2. Common Coupling**                           | In **common coupling**, two or more modules share the same common data or global variables. Because of this shared data, changing one module’s value can affect all others using it.     |
| **3. External Coupling**                         | **External coupling** happens when modules depend on external systems like files, devices, or communication links. If the external part changes, the modules may stop working correctly. |
| **4. Control Coupling**                          | In **control coupling**, one module controls the behavior of another by passing control information like flags or commands. The control of one module depends on another.                |
| **5. Stamp Coupling (Data-Structured Coupling)** | **Stamp coupling** means that modules share a data structure or record, but each module only uses part of it. So, they are linked through a common structured group of data.             |
| **6. Data Coupling**                             | **Data coupling** occurs when modules share only necessary data through parameters. It is the best type of coupling because modules stay independent and easy to modify.                 |

#### Cohesion

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

# Question 4

## 🧩 **Alpha and Beta Testing of Products**

- Distinguish between alpha and beta testing. (2021 A(h))
📘 *(2021 — A(h))*

### **Definition:**

Both **Alpha** and **Beta testing** are **acceptance testing techniques** conducted **before final product release** to ensure quality from the user’s perspective.

### **1. Alpha Testing:**

* Conducted **in-house** by the **developer’s team** and a few selected internal users.
* Takes place **at the developer’s site**.
* Focuses on identifying **bugs, usability issues, and functional gaps** before external release.
* Environment is **controlled** (not real-world).

✅ *Example:* Internal employees testing a new app version before it’s released publicly.

---

### **2. Beta Testing:**

* Performed by **actual end-users** in a **real-world environment**.
* Conducted **after Alpha testing** and before final launch.
* Helps find issues that occur **in practical usage** on different systems or conditions.
* Feedback is collected to refine the product further.

✅ *Example:* Releasing a “Beta version” of software to customers for trial use.

---

### **Difference Between Alpha and Beta Testing:**

| Feature          | Alpha Testing                 | Beta Testing                    |
| ---------------- | ----------------------------- | ------------------------------- |
| **Performed by** | Developers & internal testers | Real end-users                  |
| **Environment**  | Controlled (lab setup)        | Real-world (user systems)       |
| **Purpose**      | Detect internal bugs early    | Gather user feedback            |
| **Stage**        | Before Beta testing           | After Alpha testing             |
| **Access**       | Closed (limited users)        | Open/limited public release     |
| **Outcome**      | Product refinement            | Final validation & improvements |

---

# Question 5 **Testing**

### **Definition:**

Testing is the process of **executing a program with the intent of finding errors**.
It ensures that the software product meets the **requirements**, works as intended, and is **defect-free**.

### **Purpose:**

* To **detect defects** early before deployment.
* To **verify** and **validate** software functionality.
* To ensure **quality, reliability, and performance**.

---

## 🎯 **Testing Objectives**

📘 *(2021 – Section A (d))*
- What are the objectives of testing? (2021 A(d))

### **Main Objectives:**

1. **Verification & Validation (V&V):**
   Ensure the product is built correctly and meets user needs.
2. **Error Detection:**
   Identify defects, bugs, or deviations from requirements.
3. **Quality Assurance:**
   Ensure performance, usability, and reliability standards.
4. **Risk Reduction:**
   Helps prevent failures and reduces post-release issues.
5. **Compliance:**
   Confirms adherence to organizational or legal standards.

---

## 🧪 **Unit Testing**

- Explain how Unit testing of a Software System is performed? (2021 B(a))
- Describe the errors commonly found during Unit Testing. (2024 C Q6(a))

📘 *(2021 – Section B (a); 2024 – Section C Q6(a))*

### **Definition:**

Testing individual components or modules of a program in isolation to verify their correctness.

### **How It’s Performed:**

1. Write **test cases** for each function/method.
2. Use **drivers** (to call the unit) and **stubs** (to simulate missing modules).
3. Verify outputs against expected results.
4. Use tools like **JUnit**, **PyTest**, etc.

### **Common Errors Found:**

* Logical errors in computation
* Incorrect variable initialization
* Faulty control structures
* Boundary condition failures
* Interface or parameter mismatches

### **Goal:**

To ensure that **each unit performs as designed** and integrates smoothly later.

---

## 🔗 **Integration Testing**

- What is integration testing? Explain different types of integration testing. (2020 C Q6(b))
- Explain in detail about integration testing? How integration testing is different from system testing? (2021 C Q7(b))
- What is integration testing? Explain different types of integration testing. (2023 B(d))
- What is integration testing? Differentiate between top-down and bottom-up integration testing. (2024 B(d))
- Explain the Integration-testing process and system-testing process and discuss their outcomes. (2024 C Q6(b))

📘 *(2020 – C Q6(b); 2021 – C Q7(b); 2023 – B(d); 2024 – B(d), C Q6(b))*

### **Definition:**

Integration Testing checks the **interaction between integrated modules** to detect interface defects.

### **Types:**

1. **Top-Down Integration Testing:**

   * Testing starts from top-level modules to lower-level.
   * Uses *stubs* for unimplemented modules.
   * Advantage: Major design flaws found early.

2. **Bottom-Up Integration Testing:**

   * Testing begins with lower-level modules and moves upward.
   * Uses *drivers* for higher modules.
   * Advantage: Easier defect isolation at lower levels.

3. **Sandwich/Hybrid Integration Testing:**

   * Combines both top-down and bottom-up approaches.

4. **Big-Bang Integration Testing:**

   * All modules integrated at once and tested together.
   * Quick but difficult to debug errors.

### **Integration vs System Testing:**

| Aspect    | Integration Testing            | System Testing                  |
| --------- | ------------------------------ | ------------------------------- |
| Focus     | Interfaces between modules     | Entire system as a whole        |
| Scope     | Limited                        | Broad                           |
| Objective | Verify data flow & interaction | Validate complete functionality |

---

## ✅ **Acceptance Testing**

- List the levels or phases of testing. (Unit, Integration, System, Acceptance) (2021 C Q4(b))

📘 *(2021 – C Q4(b))*

### **Definition:**

Final testing phase performed to ensure the system is ready for **delivery and use by end-users**.

### **Types:**

1. **Alpha Testing:**
   Conducted by internal users/developers in a controlled environment.
2. **Beta Testing:**
   Done by external users/customers in the real environment.

### **Purpose:**

* Verify that software meets **business requirements**.
* Ensure **usability and customer satisfaction**.

---

## ♻️ **Regression Testing**

- What are the two main activities of regression testing? (2023 A(g))

📘 *(2023 – A (g))*

### **Definition:**

Testing done after modifications to ensure that **new changes haven’t affected existing functionality**.

### **Main Activities:**

1. **Re-execute test cases** after updates or bug fixes.
2. **Compare new results** with previous outputs to detect side effects.

### **Importance:**

* Maintains software **stability**.
* Prevents **re-introduction of old bugs**.
* Often automated using tools (e.g., Selenium, Jenkins).

# Question 6 

Software Maintenance is the **process of modifying and updating software after its delivery** to correct faults, improve performance, or adapt it to a changed environment.

### **Need/Importance:**

1. **Error Correction:** Fix bugs not discovered during testing.
2. **Adaptation:** Make software compatible with new hardware, OS, or tools.
3. **Enhancement:** Add new features or modify existing ones.
4. **Performance Improvement:** Optimize speed, memory, and efficiency.
5. **Security Updates:** Patch vulnerabilities to protect data.

## 🧱 **Categories of Software Maintenance**

📘 *(2021 — C Q6(a); 2020 — A(g))*
* [2021 — Section C Q6(a)] "Explain the maintenance activities and maintenance problems. How is the cost of maintenance estimated?"
* [2020 — Section A (g)] "Discuss two fundamental sources of change." (context: drivers of maintenance)


### 🧱 **Categories of Software Maintenance**

**Software maintenance** means changing or improving software after it is given to users.
It helps the software keep working properly, stay useful, and meet new needs over time.
There are four main categories of software maintenance.

---

1. **Corrective Maintenance**
   Corrective maintenance is done to correct mistakes found in the software.
   It helps to remove errors so that the program gives the right results.
   The main goal of corrective maintenance is to maintain the correct working of the system.
   It is performed after users report faults or problems during use.

2. **Adaptive Maintenance**
   Adaptive maintenance is done to make the software **adapt** to a new environment.
   It helps the system continue working when conditions or settings change.
   The aim of adaptive maintenance is to maintain the use of the software in a new setup.
   It lets the software adapt smoothly without changing its main purpose.

3. **Perfective Maintenance**
   Perfective maintenance is done to **perfect** the software and make it better.
   It includes small improvements that help maintain good performance and user comfort.
   The goal of perfective maintenance is to make the system more perfect in its working.
   It focuses on making the software better, not on fixing errors.

4. **Preventive Maintenance**
   Preventive maintenance is done to prevent future errors before they occur.
   It helps maintain the software in good condition for a long time.
   The aim of preventive maintenance is to find and fix small issues early.
   It ensures the software stays stable and reliable in the future.
