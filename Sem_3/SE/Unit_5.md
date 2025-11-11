## 🧩 **Software as an Evolutionary Entity**

* Software is not static — it **evolves continuously** due to **changing user needs, environments, technologies, and errors found post-deployment**.
* This continuous evolution is called **Software Evolution**.

### **Reasons for Evolution:**

1. **Changing requirements** (new features or user demands).
2. **Platform changes** (new OS, databases, devices).
3. **Error corrections** (bugs found after release).
4. **Performance improvement** (speed, security, efficiency).

✅ *Example:* Updating an e-commerce website to support UPI payments or improve load time.

---

## ⚙️ **Need for Maintenance**

📘 *(2023 — A(i): “Define need of maintenance”)*

**Definition:**
Software Maintenance is the **process of modifying and updating software after its delivery** to correct faults, improve performance, or adapt it to a changed environment.

### **Need/Importance:**

1. **Error Correction:** Fix bugs not discovered during testing.
2. **Adaptation:** Make software compatible with new hardware, OS, or tools.
3. **Enhancement:** Add new features or modify existing ones.
4. **Performance Improvement:** Optimize speed, memory, and efficiency.
5. **Security Updates:** Patch vulnerabilities to protect data.

✅ *In short:* Maintenance keeps software **reliable, usable, and up-to-date**.

---

## 🧱 **Categories of Software Maintenance**

📘 *(2021 — C Q6(a); 2020 — A(g))*
* [2021 — Section C Q6(a)] "Explain the maintenance activities and maintenance problems. How is the cost of maintenance estimated?"
* [2020 — Section A (g)] "Discuss two fundamental sources of change." (context: drivers of maintenance)


There are **three major categories** of software maintenance, often remembered as **the “3P” types** — *Preventive, Corrective, Perfective.*

---

* [2021 — Section C Q6(a)] "Explain the maintenance activities and maintenance problems. How is the cost of maintenance estimated?"
* [2020 — Section A (g)] "Discuss two fundamental sources of change." (context: drivers of maintenance)


### **1. Preventive Maintenance**

* Done to **prevent future problems**.
* Focuses on **code restructuring, documentation improvement**, and removing unused modules.
* Helps make software easier to maintain in the long run.

✅ *Example:* Refactoring old code to improve readability.

---

### **2. Corrective Maintenance**

* Performed to **fix errors or defects** found after deployment.
* These may include **logic errors, runtime bugs, or design flaws**.

✅ *Example:* Fixing a crash bug that appears when users upload a large file.

---

### **3. Perfective Maintenance**

* Focuses on **enhancing performance or adding new features**.
* Based on user feedback and evolving business goals.

✅ *Example:* Adding a new “dark mode” option to a mobile app.

---

### **(Bonus — Adaptive Maintenance)**

Some sources include a fourth category:

* **Adaptive Maintenance:** Adjusting software to run in a new environment (new OS, hardware, database, etc.)

✅ *Example:* Updating a Windows app to work on macOS.

---

## 💰 **Cost of Maintenance**

📘 *(2021 — C Q6(a): “How is cost of maintenance estimated?”)*

**Definition:**
Cost of maintenance includes all **effort, time, and resources** spent after delivery to keep software functional and relevant.

### **Factors Affecting Maintenance Cost:**

1. **Software Complexity:** Complex code is harder and costlier to maintain.
2. **Documentation Quality:** Poor or outdated documentation increases time and cost.
3. **Staff Skill Level:** Skilled developers reduce maintenance time.
4. **Testing Effort:** Retesting after every change adds to cost.
5. **Change Frequency:** More frequent updates = higher cost.
6. **Age of Software:** Older systems cost more due to outdated tools or dependencies.

---

### **Maintenance Cost Estimation:**

* Usually calculated as a **percentage of the original development cost**.
* On average, **60–80% of total software cost** is spent on maintenance over its lifetime.
* Formula (approx.):
  [
  \text{Maintenance Cost} = \text{Development Cost} \times \text{Maintenance Rate (%)}
  ]

✅ *Example:*
If development cost = ₹10 lakh and maintenance rate = 70%,
then maintenance cost ≈ ₹7 lakh.

Perfect 👍 here are your **well-organized, exam-ready notes** on

📘 **Software Re-Engineering, Reverse Engineering, SCM Activities, Change Control, and Version Control**
(Structured just like before — short, clear, and mapped to your question set 👇)

---

## 🧩 **Software Re-Engineering**

📘 *(2024 — C Q7(b): “Explain the role of CASE tools in Software Re-engineering in detail.”)*

### **Definition:**

Software Re-Engineering is the **process of analyzing and modifying existing software** to improve its **functionality, performance, maintainability, or adaptability**, without completely rewriting it.

It focuses on **upgrading legacy systems** using modern technologies while preserving business logic.

---

### **Steps in Software Re-Engineering:**

1. **Inventory Analysis:** Identify which systems need re-engineering.
2. **Document Restructuring:** Update or create missing documentation.
3. **Reverse Engineering:** Extract design and structure from old code.
4. **Code Restructuring:** Clean, optimize, and refactor code.
5. **Data Restructuring:** Modify or migrate databases if needed.
6. **Forward Engineering:** Rebuild or regenerate software using new tools and design.

---

### **Role of CASE Tools (Computer-Aided Software Engineering):**

CASE tools **automate re-engineering activities** and **improve quality**.

| CASE Tool Function            | Role in Re-Engineering                                 |
| ----------------------------- | ------------------------------------------------------ |
| **Reverse Engineering Tools** | Extract design and structure from source code          |
| **Code Analysis Tools**       | Detect dead code, unused variables, or code smells     |
| **Data Dictionary Tools**     | Help understand database structure                     |
| **Refactoring Tools**         | Automate code restructuring and optimization           |
| **Forward Engineering Tools** | Generate design and code in modern platforms           |
| **Version Control Tools**     | Track all software modifications during re-engineering |

✅ *Example:* Using **Eclipse, Rational Rose, or Visual Paradigm** to model and regenerate components of an old system.

---

### **Benefits:**

* Extends life of legacy systems
* Improves maintainability and performance
* Reduces future maintenance cost
* Enables migration to new tech stack

---

## 🔍 **Reverse Engineering**

📘 *(2024 — B (e): “What is Reverse Engineering? Describe the reverse engineering process.”)*

### **Definition:**

Reverse Engineering is the process of **analyzing an existing system to identify its components and design information** — usually done when source documentation is missing.

It moves **from code → design → specification** (the reverse of development).

---

### **Objectives:**

* Understand system logic and structure
* Recover lost design documents
* Support re-engineering and debugging
* Migrate or integrate legacy software

---

### **Process of Reverse Engineering:**

1. **Information Extraction:** Collect code, databases, and files.
2. **Parsing and Analysis:** Analyze control flow, data flow, and structure.
3. **Abstraction:** Identify modules, functions, and data relationships.
4. **Documentation Generation:** Produce design diagrams, flowcharts, and reports.
5. **Re-documentation:** Create updated design/specification documents.

✅ *Example:* Using tools like *Understand* or *Sourcetrail* to generate UML diagrams from code.

---

### **Output of Reverse Engineering:**

* Design models
* UML diagrams
* Data flow diagrams (DFDs)
* Updated documentation

---

## ⚙️ **Software Configuration Management (SCM) Activities**

📘 *(2023 — C Q7(b); 2020 — B (e); 2020 — A (f))*

### **Definition:**

Software Configuration Management (SCM) is the **process of systematically managing changes** in software to maintain its **integrity and traceability** throughout the SDLC.

It ensures that only **authorized and recorded changes** are made.

---

### **Objectives:**

* Control and record changes to software items
* Prevent unauthorized modifications
* Maintain consistency between versions
* Track evolution of software components

---

### **Key SCM Activities:**

| Activity                               | Description                                                                     |
| -------------------------------------- | ------------------------------------------------------------------------------- |
| **1. Configuration Identification**    | Identify configuration items (CIs) — e.g., source files, test data, design docs |
| **2. Configuration Control**           | Manage and approve proposed changes                                             |
| **3. Configuration Status Accounting** | Record and report all changes and current status                                |
| **4. Configuration Auditing**          | Verify that changes are properly implemented and documented                     |

---

### **Configuration Items (CIs):**

📘 *(2020 — A (f): “Name two configuration items.”)*
Items managed under SCM — like:

* Source code files
* Test plans
* Requirement documents
* Database schemas

✅ *Examples:* “login.java”, “system_design.docx”

---

### **Benefits of SCM:**

* Ensures consistency across versions
* Improves project coordination
* Simplifies rollback if errors occur
* Increases accountability and traceability

---

## 🔄 **Change Control Process**

* [2020 — Section C Q7(a)] "What do you mean by Change Control? Explain the process of change control with the help of a diagram."
* [2020 — Section B (e)] "State Baseline. Discuss the process of modification of baseline."
* [2020 — Section A (g)] "Discuss two fundamental sources of change."

📘 *(2020 — C Q7(a); 2020 — B (e); 2020 — A (g))*

### **Definition:**

Change Control is the **systematic process of managing software modifications** to ensure that only authorized and evaluated changes are implemented.

---

### **Steps in Change Control:**

1. **Change Request Initiation:**
   A developer, tester, or user raises a Change Request (CR).

2. **Impact Analysis:**
   Assess technical and financial effects of change.

3. **Approval/Review:**
   Change Control Board (CCB) evaluates and approves or rejects the request.

4. **Implementation:**
   Apply approved changes to code and documentation.

5. **Verification and Validation:**
   Test changes for correctness.

6. **Baseline Update:**
   Update baseline after successful implementation.

---

### **Diagram (Text Form):**

```
Change Request → Impact Analysis → Approval → Implementation → Testing → Baseline Update
```

---

### **Baseline:**

📘 *(2020 — B (e): “State Baseline. Discuss the process of modification of baseline.”)*

**Baseline** = A formally approved version of a software component or document that serves as a **reference point** for further development.

**Modification Process:**

* A change request is submitted → evaluated → approved → change applied → new baseline created.

✅ *Example:* “Version 1.0” becomes a new baseline after accepted updates.

---

### **Fundamental Sources of Change:**

📘 *(2020 — A (g))*

1. **New Requirements:** Evolving business or user needs.
2. **Defects/Errors:** Bugs or design flaws requiring correction.

---

## 🗂️ **Software Version Control**

* [2020 — Section A (f)] "Name two configuration items."
* [2020 — Section B (e)] "State Baseline. Discuss the process of modification of baseline."

📘 *(2020 — A (f); 2020 — B (e))*

### **Definition:**

Version Control is the process of **tracking and managing different versions of software artifacts** such as code, documents, and test cases.

It allows **multiple developers to work concurrently** without overwriting each other’s work.

---

### **Key Functions:**

* Track all versions and changes
* Enable rollback to previous stable versions
* Record who made which change and when
* Support branching and merging

---

### **Tools for Version Control:**

* **Centralized:** CVS, Subversion (SVN)
* **Distributed:** Git, Mercurial

✅ *Example:* Using **GitHub** to manage multiple releases (v1.0, v1.1, v2.0).

---

### **Relation to Baseline:**

Every approved version can become a **baseline**, serving as a foundation for further changes.

---

Perfect 💯 here’s your **final full, exam-focused, neatly structured notes** on

📘 *CASE Tools, Software Estimation (Cost–Effort–Schedule–COCOMO–Resource Models), and Risk Analysis & Management*

formatted **exactly like before** — with definitions, key points, and tables 👇

---

## 🧰 **An Overview of CASE Tools**

* [2023 — Section C Q7(a)] "Categorize the use of CASE tools in software engineering with their advantages and disadvantages."
* [2024 — Section C Q7(b)] "Explain the role of CASE tools in Software Re-engineering in detail."

📘 *(2023 — C Q7(a); 2024 — C Q7(b))*

### **Definition:**

CASE (Computer-Aided Software Engineering) tools are **automated software tools** that assist in **various phases of the software development life cycle (SDLC)** — from requirement analysis to maintenance.
They help in **reducing development time, improving accuracy, and ensuring consistency** across the project.

---

### **Categories of CASE Tools:**

| Type                               | Function                                              | Example                               |
| ---------------------------------- | ----------------------------------------------------- | ------------------------------------- |
| **Upper CASE Tools**               | Support early phases — *requirement analysis, design* | Rational Rose, ERwin                  |
| **Lower CASE Tools**               | Support later phases — *coding, testing, maintenance* | Eclipse, JUnit                        |
| **Integrated CASE Tools (I-CASE)** | Cover *entire SDLC*                                   | Enterprise Architect, Visual Paradigm |

---

### **Advantages:**

✅ Improved software quality through standardization
✅ Faster development and reduced human errors
✅ Better documentation and maintainability
✅ Enhanced team collaboration and productivity

---

### **Disadvantages:**

❌ High initial cost and training requirement
❌ Tool incompatibility or platform dependency
❌ Overreliance on automation can reduce creativity
❌ May not suit small-scale projects

---

### **Role in Software Re-engineering (2024 – C Q7b):**

CASE tools assist in **automating code analysis, documentation, and transformation** during re-engineering.

| Function              | CASE Tool Role                              |
| --------------------- | ------------------------------------------- |
| Reverse Engineering   | Extract design from existing code           |
| Code Refactoring      | Improve structure without changing behavior |
| Data Dictionary Tools | Manage schema and metadata                  |
| Forward Engineering   | Generate code from models                   |
| Version Control       | Track re-engineering changes                |

✅ *Example:* Using tools like Rational Rose or StarUML for converting legacy systems into modern architectures.

---

## 💰 **Estimation of Various Parameters**

📘 *(2021 — C Q6(a); additional theory from standard SE models)*

### **1️⃣ Cost Estimation:**

It is the **process of predicting the total cost** of software development — including human, hardware, and software resources.

**Formula (Basic):**
[
\text{Cost} = \text{Effort} \times \text{Cost per Person-Month}
]

---

### **2️⃣ Effort Estimation:**

Effort = total amount of work (in **person-months**) required to develop the project.

Depends on:

* Size of project (LOC or Function Points)
* Complexity
* Developer experience
* Technology used

---

### **3️⃣ Schedule/Duration Estimation:**

Schedule is the **time required to complete** the project.

[
\text{Schedule} = f(\text{Effort}, \text{Team Size})
]
Often, *larger teams* do **not** linearly reduce schedule because of communication overhead.

---

### **4️⃣ Constructive Cost Model (COCOMO):**

* [2021 — Section C Q6(a)] "How is the cost of maintenance estimated?"
* No direct questions found on COCOMO or Resource Allocation Models in the uploaded papers.


Developed by **Barry Boehm**, COCOMO estimates **effort and cost** based on project size in **KLOC (thousand lines of code).**

[
E = a \times (KLOC)^b
]
[
D = c \times (E)^d
]

Where:

* **E** = Effort in person-months
* **D** = Duration in months
* **a, b, c, d** = constants depending on project type (Organic, Semi-detached, Embedded)

| Mode              | a   | b    | Example                              |
| ----------------- | --- | ---- | ------------------------------------ |
| **Organic**       | 2.4 | 1.05 | Simple, small projects               |
| **Semi-detached** | 3.0 | 1.12 | Medium complexity                    |
| **Embedded**      | 3.6 | 1.20 | Complex, hardware/software dependent |

✅ *Example:* For a 10 KLOC organic project:
Effort = 2.4 × (10)^1.05 ≈ 27 person-months

---

### **5️⃣ Resource Allocation Models:**

Used to determine **how human, hardware, and software resources** are distributed across SDLC phases.

| Phase                    | Typical % Effort |
| ------------------------ | ---------------- |
| Requirements + Design    | 40%              |
| Coding                   | 20%              |
| Testing + Integration    | 30%              |
| Documentation + Delivery | 10%              |

📘 *Helps project managers plan manpower, time, and cost effectively.*

---

## ⚠️ **Software Risk Analysis and Management**

* [2024 — Section C Q7(a)] "What do you understand by Software Risk Analysis and how Risk Analysis is important in Software Engineering?"
* [2021 — Section B (c)] "Explain the process of Risk Analysis and Management."
* [2020 — Section C Q7(b)] "Discuss the various activities of Risk Assessment."
* [2023 — Section B (e)] "Discuss risk management? Explain how to select the best risk reduction technique when there are many ways of reducing a risk."
* [2023 — Section A (j)] "Discuss the ways to avoid risk."
* [2024 — Section A (i)] "Differentiate between reactive risk and proactive risk strategies."

📘 *(2020, 2021, 2023, 2024 — multiple questions)*

---

### **Definition:**

Software Risk Analysis and Management is the process of **identifying, assessing, and controlling potential problems** that may threaten project success.

Risk = *Uncertain event that may affect cost, time, quality, or performance.*

---

### **Types of Risk:**

| Type                | Description                          | Example                          |
| ------------------- | ------------------------------------ | -------------------------------- |
| **Project Risks**   | Affect project schedule or resources | Missed deadlines                 |
| **Technical Risks** | Related to technology or tools       | Software bugs, new tech failures |
| **Business Risks**  | Affect organizational goals          | Budget cuts, policy changes      |

---

### **Risk Management Process (2021 — B (c)):**

1. **Risk Identification:**
   List all possible risks. (e.g., delay in delivery, key member leaving)

2. **Risk Analysis (Assessment):**
   Estimate *probability* and *impact* of each risk.
   [
   \text{Risk Exposure (RE)} = P \times I
   ]
   (P = Probability, I = Impact)

3. **Risk Prioritization:**
   Classify into High, Medium, Low priority.

4. **Risk Planning / Mitigation:**
   Develop strategies to minimize or eliminate the impact.

5. **Risk Monitoring:**
   Continuously track risk indicators during the project.

---

### **Risk Assessment Activities (2020 — C Q7(b)):**

* Identify potential hazards
* Analyze causes and effects
* Estimate likelihood and severity
* Develop control actions
* Maintain risk register

---

### **Risk Reduction Techniques (2023 — B (e)):**

When multiple reduction methods exist, select based on:

* Cost-benefit ratio
* Feasibility
* Long-term impact

**Techniques include:**

* *Avoidance* → Change plan to remove risk source
* *Reduction* → Lower probability or impact
* *Transfer* → Shift risk (e.g., outsourcing)
* *Acceptance* → Live with it, but prepare contingency plans

---

### **Ways to Avoid Risk (2023 — A (j)):**

✅ Use experienced teams
✅ Adopt proven technologies
✅ Review designs regularly
✅ Maintain strong documentation
✅ Conduct regular audits

---

### **Reactive vs Proactive Risk Strategies (2024 — A (i)):**

| Strategy      | Meaning                                          | Example                                       |
| ------------- | ------------------------------------------------ | --------------------------------------------- |
| **Reactive**  | Deal with risks *after* they occur               | Fix bugs after release                        |
| **Proactive** | Anticipate and prevent risks *before* they occur | Conduct early code reviews, prototype testing |

---

### **Importance of Risk Analysis (2024 — C Q7(a)):**

* Prevents project delays and budget overruns
* Ensures preparedness for uncertainties
* Improves decision-making and planning
* Builds stakeholder confidence

---