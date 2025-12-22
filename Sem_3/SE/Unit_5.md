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

---

## 💰 **Cost of Maintenance**

📘 *(2021 — C Q6(a): “How is cost of maintenance estimated?”)*

**Cost of maintenance** means the total amount of money spent to maintain a software system after it is delivered.
It includes all the efforts, time, and resources needed to keep the software working properly.
The cost of maintenance is often high because software must be changed and improved regularly.
It continues throughout the life of the software and can even be higher than the original development cost.

The formula for cost of maintenance is:
**Maintenance Cost = Development Cost × Maintenance Rate (%)**

The main goal of calculating the cost of maintenance is to plan the budget and resources needed for the long-term working of the software.

---

### ⚙️ **Factors Affecting the Cost of Maintenance**

1. **Type of Maintenance**
   The cost of maintenance depends on which type of maintenance is being done.
   Corrective maintenance may cost less, while adaptive or perfective maintenance can cost more.
   The more complex the type, the higher the cost of maintenance becomes.

2. **Quality of Design**
   If the software design is poor, the cost of maintenance increases.
   A good design makes it easier to understand and change the system.
   So, better design helps reduce the overall cost of maintenance.

3. **Code Quality**
   The cost of maintenance depends on how well the code is written.
   Simple and well-structured code is easy to maintain.
   Bad or unorganized code increases the cost of maintenance because it takes more time to fix.

4. **Documentation**
   Clear and complete documentation helps in understanding the system easily.
   When documentation is missing or unclear, maintenance becomes difficult.
   So, poor documentation increases the cost of maintenance.

5. **Staff Skills**
   The cost of maintenance also depends on the skill of the people doing it.
   Skilled staff can find and fix issues faster, reducing extra cost.
   Less experienced staff may take more time, increasing the cost of maintenance.

6. **Size and Age of Software**
   Large and old software systems are harder to maintain.
   As software grows or becomes outdated, changes take more time and effort.
   Hence, older systems usually have a higher cost of maintenance.

7. **Technology Used**
   The technology or tools used in the software also affect maintenance cost.
   If the technology is old or unsupported, it becomes costly to maintain.
   Modern and common technologies reduce the cost of maintenance.

8. **Frequency of Changes**
   The more often the software needs changes, the more the cost of maintenance increases.
   Regular updates or modifications add extra work.
   Stable software with fewer changes has a lower cost of maintenance.

9. **User Requirements**
   When users keep asking for new features or improvements, maintenance costs go up.
   Each new requirement needs coding, testing, and documentation updates.
   So, changing user needs increase the cost of maintenance.

10. **Testing and Validation Effort**
    Every maintenance activity needs testing to check if the system still works correctly.
    More testing means more effort and higher cost.
    Proper testing, however, helps maintain software quality over time.

---

### **Maintenance Cost Estimation:**

* Usually calculated as a **percentage of the original development cost**.
* On average, **60–80% of total software cost** is spent on maintenance over its lifetime.
* Formula (approx.):
  [
`Maintenance Cost = Development Cost × Maintenance Rate (%)`
  ]

✅ *Example:*
If development cost = ₹10 lakh and maintenance rate = 70%,
then maintenance cost ≈ ₹7 lakh.

## 🧩 **Software Re-Engineering**

📘 *(2024 — C Q7(b): “Explain the  Software Re-engineering in detail.”)*

### **Definition:**

**Software Re-engineering** means improving an old software system so that it becomes more useful, easy to maintain, and fits current needs. It focuses on understanding the existing system, finding problems, and then improving it without fully rebuilding from scratch.


### **Steps in Software Re-Engineering:**

1. **Inventory Analysis:** Identify which systems need re-engineering.
2. **Document Restructuring:** Update or create missing documentation.
3. **Reverse Engineering:** Extract design and structure from old code.
4. **Code Restructuring:** Clean, optimize, and refactor code.
5. **Data Restructuring:** Modify or migrate databases if needed.
6. **Forward Engineering:** Rebuild or regenerate software using new tools and design.

🧩 **Use of CASE Tools in Software Engineering — with Advantages and Disadvantages**

* [2023 — Section C Q7(a)] "Categorize the use of CASE tools in software engineering with their advantages and disadvantages."
* [2024 — Section C Q7(b)] "Explain the role of CASE tools in Software Re-engineering in detail."

**CASE tools** (Computer-Aided Software Engineering tools) are special software programs that help in developing and maintaining other software systems.
They support the whole **software engineering** process — from planning and designing to coding and testing.
CASE tools help engineers make their work more accurate, better organized, and easier to manage.

---

### 🔹 **Categories of CASE Tools**

#### 1. **Upper CASE Tools**

Upper CASE tools are used in the early stages of software development. They help in planning, requirement analysis, and system design. These tools focus on the **upper** or starting phase of software engineering.

**Examples:** Diagram creators, modeling tools, data-flow and ER diagram tools.

#### 2. **Lower CASE Tools**

Lower CASE tools are used in later stages like coding, testing, and implementation. They help in writing code, checking errors, and managing test cases. These tools work on the **lower** or ending phase of software engineering.

**Examples:** Code generators, testing tools, debugging tools.

#### 3. **Integrated CASE Tools**

Integrated CASE tools combine both upper and lower CASE tools. They support the complete software development process in one environment.
These tools help maintain smooth connection between design, coding, and testing stages.

**Examples:** Rational Rose, Enterprise Architect.

⚖️ **Advantages of CASE Tools**

1. **CASE tools improve accuracy** by reducing manual work in designing and coding.
2. **CASE tools maintain consistency** because every part of the project follows the same design rules.
3. **CASE tools save time** by automating steps like diagram creation, code generation, and testing.
4. **CASE tools improve communication** between team members using shared diagrams and documents.
5. **CASE tools make maintenance easier** since design and code are properly organized and documented.

---

⚠️ **Disadvantages of CASE Tools**

1. **CASE tools can be costly** to buy and set up, especially for small projects.
2. **CASE tools may need training** because some tools are complex to use.
3. **CASE tools depend on proper input** — if the design or data is wrong, the tool gives wrong results.
4. **CASE tools may not fit all projects**, as some small or simple systems do not need such tools.
5. **CASE tools can reduce creativity** if engineers rely only on the tool instead of their own design thinking.


✅ *Example:* Using **Eclipse, Rational Rose, or Visual Paradigm** to model and regenerate components of an old system.


## 🔄 **Reverse Engineering — Meaning and Process**

**Reverse Engineering** means studying an existing software system to understand how it works.
It is called *reverse* because instead of developing software from requirements to code, we go **backward** from code to design or model.
The main goal of reverse engineering is to **understand**, **analyze**, and **improve** a system — especially when the original design documents are missing.
It helps in maintenance, re-engineering, and system improvement without rebuilding everything from the start.

---

### ⚙️ **Reverse Engineering Process**

The **reverse engineering process** involves several steps that move from program code to high-level understanding.
Each step uses the idea of going “reverse” — from detailed implementation back to the original structure and logic.

---

#### 1. **Information Extraction**

In this step, the reverse engineering process begins by collecting information from the existing software.
All available data such as code, files, and documentation are studied.
This helps engineers see what the system does and how it behaves.

---

#### 2. **Code Analysis**

Here, the reverse engineering process focuses on understanding the actual program code.
The logic, functions, and dependencies between modules are examined.
This helps in identifying how different parts of the system connect and work together.

---

#### 3. **Data Structure Recovery**

In this step, the reverse engineering process finds how data is stored, used, and linked.
It helps in building data models such as entity-relationship diagrams.
This makes it easier to see the flow of data inside the system.

---

#### 4. **Design Recovery**

The reverse engineering process now moves from low-level code to higher-level design.
It recreates design diagrams like flowcharts or structure charts that show the overall architecture.
This step helps understand how the original system was designed before it was built.

---

#### 5. **Documentation Generation**

Finally, the reverse engineering process creates proper documentation for future use.
This includes design reports, data flow diagrams, and other notes.
Good documentation ensures that the re-engineered or maintained system can be understood by others later.

---

## ⚙️ **Software Configuration Management (SCM) Activities**

📘 *(2023 — C Q7(b); 2020 — B (e); 2020 — A (f))*

### **Definition:**

Software Configuration Management (SCM) is the **process of systematically managing changes** in software to maintain its **integrity and traceability** throughout the SDLC.

It ensures that only **authorized and recorded changes** are made.

### **Objectives:**

* Control and record changes to software items
* Prevent unauthorized modifications
* Maintain consistency between versions
* Track evolution of software components

### ⚙️ **Key Activities of Software Configuration Management (SCM)**

**Software Configuration Management (SCM)** is the process of controlling and managing all changes made to a software system.
It makes sure that every part of the software is clearly identified, tracked, and updated properly.
The main **SCM activities** help in maintaining the stability, accuracy, and organization of the software throughout its life.

#### 🔹 **1. Configuration Identification**

In **configuration identification**, all important parts of the software are clearly listed and labeled.
These parts are called *configuration items* (CIs), which include source code, documents, test data, and design files.
This activity helps everyone know exactly what items exist and what versions are being used.

#### 🔹 **2. Configuration Control**

In **configuration control**, the main goal is to manage and approve all proposed changes.
Whenever someone wants to update or modify a configuration item, this process checks and approves it first.
This activity helps prevent confusion and keeps the software changes under proper control.

#### 🔹 **3. Configuration Status Accounting**

**Configuration status accounting** means keeping detailed records of all changes made to the software.
It tracks which version is current, what changes have been made, and who approved them.
This activity helps in reporting the exact status of every software item at any time.

#### 🔹 **4. Configuration Auditing**

**Configuration auditing** checks whether all approved changes are correctly applied and documented.
It ensures that the actual software matches the approved design and that no unauthorized changes exist.
This activity helps maintain the quality and correctness of the software configuration.

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

Change Control is the **systematic process of managing all changes made in a software** it takes care of who's and what of all modifaications in the system. like who made the change and what change is made.
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

COCOMO stands for Constructive Cost Model. It is a software cost estimation model developed by Barry Boehm. COCOMO is used to estimate the effort, time, and cost required to develop a software project. This model helps managers and developers plan projects in a better and more realistic way.

The main idea of COCOMO is that the size of the software decides how much effort and time will be needed. The size of software is usually measured in Lines of Code (LOC)(uses a metric KLOC). Based on this size, COCOMO calculates how many person-months of effort will be required to complete the project.
MODES OF COCOMO

COCOMO also classifies software projects into three modes:

- Organic Mode: Small, simple projects with experienced teams.
- Semi-Detached Mode: Medium-sized projects with mixed experience teams.
- Embedded Mode: Large, complex projects with strict requirements.

```
[
E = a * (KLOC)^b
]
[
D = c * (E)^d
]
```

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