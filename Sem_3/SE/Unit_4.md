# 🧩 **Testing**

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

---

Here are your crisp, exam-focused notes on
**Testing for Functionality and Performance, Top-Down & Bottom-Up Testing Strategies, Test Drivers, and Test Stubs** —
written exactly in the same structured format as before 👇

---

## ⚙️ **Testing for Functionality and Testing for Performance**

- Define black-box testing strategy. (2024 A(g))
- What is equivalence partitioning? (Black-box testing technique) (2021 A(e))
- Write the difference between black-box testing and white-box testing; for a program computing square root of an integer between 0 and 5000 determine equivalence-class and boundary-value test cases. (2023 C Q6(b))


### **Functional Testing (Black-Box Testing)**

📘 *(2024 — Section A (g))*

#### **Definition:**

Functional testing — also called **black-box testing** — focuses on **what the system does**, not *how* it does it.
The internal logic or code is not visible to the tester.

#### **Key Idea:**

* Input → Processing → Output is tested purely based on **requirements**.
* Ensures that all **functions and features** behave as expected.

#### **Common Techniques:**

1. **Equivalence Partitioning (EP)** 📘 *(2021 — A (e))*

   * The input domain is divided into **equivalence classes** of valid and invalid data.
   * Only one test case from each class is used — minimizing redundancy.
     ✅ *Example:*
     For an input range 0–5000:
   * Valid class → [0–5000]
   * Invalid classes → <0 and >5000

2. **Boundary Value Analysis (BVA)**

   * Errors often occur at limits of input ranges.
     ✅ *Example (Square root program 0–5000):*
   * Test boundaries: `-1, 0, 1, 4999, 5000, 5001`
   * Ensures stability near edges of input domain.

#### **Black-Box vs White-Box Testing** 📘 *(2023 — C Q6(b))*

| Aspect           | Black-Box Testing             | White-Box Testing               |
| ---------------- | ----------------------------- | ------------------------------- |
| Focus            | Functionality                 | Internal logic/structure        |
| Based On         | Requirements                  | Source code                     |
| Tester Knowledge | No access to code             | Full access to code             |
| Example          | Equivalence partitioning, BVA | Path testing, condition testing |

---

### **Performance Testing**

Focuses on **non-functional attributes** — speed, stability, scalability, and responsiveness of the system.

#### **Types:**

1. **Load Testing** – Checks system under expected workload.
2. **Stress Testing** – Tests beyond limits to observe failure behavior.
3. **Volume Testing** – Evaluates performance with large data volume.
4. **Spike Testing** – Sudden increase in user load.

#### **Goal:**

To ensure that the system performs **efficiently and reliably** under real conditions.

---

## 🔼🔽 **Top-Down and Bottom-Up Testing Strategies**

- Write about drivers and stubs. (2021 A(g))
- Differentiate between test drivers and test stubs. (2023 A(h))
- Differentiate between top-down and bottom-up integration testing. (2024 B(d))


📘 *(2024 — B(d))*

### **1️⃣ Top-Down Testing**

#### **Definition:**

Integration testing approach where testing starts from the **top-level modules** and proceeds downward.

#### **Process:**

* Major control modules tested first.
* **Stubs** are used to simulate lower modules not yet developed.
* Lower modules integrated step-by-step.

#### **Advantages:**

* Design flaws found early.
* High-level logic verified first.

#### **Disadvantages:**

* Requires many stubs.
* Lower-level modules tested late.

---

### **2️⃣ Bottom-Up Testing**

#### **Definition:**

Integration testing begins with **lowest-level modules**, proceeding upward.

#### **Process:**

* Low-level components combined and tested as clusters.
* **Drivers** simulate higher-level modules that are not yet available.

#### **Advantages:**

* Easier error localization.
* Lower modules verified early.

#### **Disadvantages:**

* No early demonstration of full system behavior.
* Top-level logic tested late.

---

### **3️⃣ Comparison**

| Feature       | Top-Down               | Bottom-Up            |
| ------------- | ---------------------- | -------------------- |
| Start Point   | High-level modules     | Low-level modules    |
| Uses          | Stubs                  | Drivers              |
| Early Testing | High-level logic       | Low-level components |
| Drawback      | Many stubs needed      | Many drivers needed  |
| Example Use   | Control-driven systems | Data-driven systems  |

---

## 🧰 **Test Drivers and Test Stubs**

📘 *(2021 — A (g); 2023 — A (h))*

### **Test Drivers**

* Simulate the **caller module** (upper-level module).
* Provide inputs to and receive outputs from the module under test.
* Used mainly in **bottom-up testing**.
  ✅ *Example:* A main program that calls a function to test its output.

### **Test Stubs**

* Simulate the **called module** (lower-level module).
* Return dummy data to the module under test.
* Used mainly in **top-down testing**.
  ✅ *Example:* A stub returning pre-set output for a function that isn’t implemented yet.

### **Difference Between Drivers and Stubs**

| Basis   | Test Driver                   | Test Stub                                |
| ------- | ----------------------------- | ---------------------------------------- |
| Role    | Simulates higher-level module | Simulates lower-level module             |
| Used In | Bottom-Up Testing             | Top-Down Testing                         |
| Purpose | Invokes module under test     | Responds to calls from module under test |
| Example | Main() calling sub-function   | Dummy function returning fixed value     |


## ⚙️ **Structural Testing (White-Box Testing)**

- Differentiate between Structural testing and Functional testing. (White-box vs Black-box) (2021 C Q3(b))
- Write the difference between black-box testing and white-box testing. (2023 C Q6(b))


📘 *(2021 — C Q3(b); 2023 — C Q6(b))*

### **Definition:**

Structural Testing, also known as **White-Box Testing**, examines the **internal structure, logic, and code** of the software.
The tester has full knowledge of the code and designs tests based on **control paths, loops, and decisions** inside the program.

### **Purpose:**

To ensure that every **statement, condition, and path** in the program is tested at least once.

### **Common Techniques:**

1. **Statement Coverage** – Tests each line of code at least once.
2. **Branch Coverage** – Ensures every decision outcome (True/False) is executed.
3. **Path Coverage** – Covers all possible execution paths.
4. **Condition Coverage** – Checks each logical condition within a decision.

### **Advantages:**

* Detects hidden logic errors early.
* Ensures maximum code coverage.
* Helps optimize and refactor complex code.

### **Disadvantages:**

* Requires programming knowledge.
* Cannot detect missing functionality.

---

## 🎯 **Functional Testing (Black-Box Testing)**

- Differentiate between Structural testing and Functional testing. (White-box vs Black-box) (2021 C Q3(b))
- Define black-box testing strategy. (2024 A(g))
- What is equivalence partitioning? (Black-box testing technique) (2021 A(e))


📘 *(2021 — C Q3(b); 2024 — A(g); 2021 — A(e); 2023 — C Q6(b))*

### **Definition:**

Functional testing, also called **Black-Box Testing**, focuses on the **behavior** or **output** of the software, not the internal code.
The tester checks whether the system functions according to its **requirements**.

### **Purpose:**

To validate that the software performs the **intended tasks correctly** under all valid and invalid inputs.

### **Key Techniques:**

1. **Equivalence Partitioning (EP)** 📘 *(2021 — A(e))*

   * Divides input data into **equivalence classes** where test cases represent each class.
     ✅ *Example:*
     For input integer between 0 and 5000 →
   * Valid class: 0–5000
   * Invalid classes: <0 and >5000

2. **Boundary Value Analysis (BVA)**

   * Focuses on the **edges** of input ranges where errors often occur.
     ✅ *Example:*
     For the same square-root program: test values `-1, 0, 1, 4999, 5000, 5001`.

3. **Cause–Effect Graphing** – Links input conditions (causes) to expected outputs (effects).

### **Advantages:**

* Doesn’t need source code knowledge.
* Directly verifies functional requirements.

### **Disadvantages:**

* Limited coverage of internal logic.
* May miss hidden code errors.

---

### **🧩 Difference Between White-Box and Black-Box Testing**

| Feature          | White-Box (Structural)           | Black-Box (Functional)             |
| ---------------- | -------------------------------- | ---------------------------------- |
| Focus            | Internal logic & code paths      | External functionality & output    |
| Tester Knowledge | Full access to source code       | No knowledge of code               |
| Based On         | Design & implementation          | Requirements & specifications      |
| Main Techniques  | Statement, branch, path coverage | Equivalence partitioning, BVA      |
| Detects          | Logical, coding errors           | Missing or incorrect functionality |
| Example          | Testing loop logic               | Testing login validation form      |

---

## 🧪 **Test Data Suite Preparation**

- Determine the equivalence-class test cases and boundary-value test cases for a program that computes the square root of an input integer between 0 and 5000. (2023 C Q6(b))
- What is equivalence partitioning? (2021 A(e))


📘 *(2023 — C Q6(b); 2021 — A(e))*

### **Definition:**

A **test data suite** is a **collection of input test cases** designed to thoroughly test the behavior of a program under different conditions.

### **Steps to Prepare a Test Data Suite:**

1. **Analyze requirements** – Identify input domain and expected outputs.
2. **Partition input domain** – Use **Equivalence Partitioning** to group similar cases.
3. **Select boundary cases** – Apply **Boundary Value Analysis** for edge inputs.
4. **Prepare expected results** – Define what each input should produce.
5. **Record and execute tests** – Maintain test cases with expected vs actual outcomes.

### **Example:**

Program → *Compute square root of integer (0–5000)*

| Input Type | Test Values           | Expected Outcome                    |
| ---------- | --------------------- | ----------------------------------- |
| Valid      | 0, 1, 100, 4999, 5000 | Correct √ output                    |
| Invalid    | -1, 5001              | Display error/invalid input message |

✅ Thus, EP and BVA together ensure both **normal** and **extreme** cases are verified effectively.

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

## ⚙️ **Static Testing Strategies**

- Write a short note on Formal Technical Review and Code Inspection and compare them. (2020 B Q2(d))
- What is a formal technical review? What are the objectives of formal technical review? Give a comparative study of code inspection, reviews and walk-through. (2023 C Q5(b))
- Compliance with design and coding standards — (no explicit question in the provided set)


📘 *(2020 — B Q2(d); 2023 — C Q5(b))*

### **Definition:**

Static testing involves **reviewing documents, design, and code** *without executing the program*.
Its purpose is to find **errors early** in requirements, design, or code before dynamic testing begins.

---

### **1. Formal Technical Reviews (FTR)**

* A **structured peer review process** conducted by a team to evaluate software artifacts like design, code, or test plans.
* Focuses on **detecting defects**, ensuring **standards compliance**, and **improving quality**.

#### **Objectives:**

1. Detect errors in logic, design, or implementation.
2. Verify software meets its requirements.
3. Ensure consistency with design and coding standards.
4. Improve team understanding and knowledge sharing.

#### **FTR Process:**

1. **Preparation** – Reviewers study materials before meeting.
2. **Review Meeting** – Discussion led by a moderator.
3. **Issue Recording** – Defects and improvement suggestions are noted.
4. **Rework & Follow-up** – Author corrects and resubmits if needed.

✅ *Example:* Reviewing design documents for consistency before implementation.

---

### **2. Walkthroughs**

* An **informal review technique** led by the **author** of the document/code.
* The author explains the logic or design to peers for feedback.
* Focuses on **knowledge sharing** and finding **logical or structural errors**.

✅ *Example:* A developer explaining a module’s flowchart to the team for feedback.

---

### **3. Code Inspection**

* A **formal and detailed line-by-line examination** of code by trained reviewers (not necessarily the author).
* Focuses on finding **syntax errors, logic defects, and standard violations**.
* Typically uses **checklists** and **metrics**.

✅ *Example:* Reviewing C++ code using a checklist for variable naming and error handling standards.

---

### **Comparison — FTR, Walkthrough, and Code Inspection**

| Aspect        | FTR                         | Walkthrough         | Code Inspection            |
| ------------- | --------------------------- | ------------------- | -------------------------- |
| **Formality** | Formal                      | Informal            | Highly formal              |
| **Led by**    | Moderator                   | Author              | Moderator or lead reviewer |
| **Focus**     | Design, documentation, code | Logic understanding | Syntax & standards         |
| **Outcome**   | Defect report               | Learning & feedback | Defect list & code metrics |

---

### **4. Compliance with Design and Coding Standards**

* Ensures all project artifacts adhere to **established rules and conventions**.
* Covers **naming standards, indentation, commenting style, error handling, and documentation**.
* Reduces maintenance cost and increases code readability.

✅ *Example:* Following Google Java Style Guide or MISRA C coding rules.