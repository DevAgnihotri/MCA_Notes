# UNIT 2 — Software Quality Metrics (Product Quality Metrics)

Software quality cannot be improved unless it is **measured objectively**. Product quality metrics help organizations measure how good a software product is by analyzing defects, customer experience, and system functionality.

# Product Quality Metrics

## Meaning of Product Quality Metrics

### Definition

Product Quality Metrics are quantitative measures used to evaluate the quality and reliability of a software product.

### Explanation

These metrics focus on the **final software product**, rather than the development process. They help determine whether the product satisfies quality expectations.

They measure aspects such as:

* Number of defects
* Customer problems
* Customer satisfaction
* Functional size of software

Product quality metrics help organizations:

* Evaluate software performance
* Improve reliability
* Reduce defects
* Improve user experience

### Main Product Quality Metrics

The important product quality metrics include:

| Metric                       | Purpose                                    |
| ---------------------------- | ------------------------------------------ |
| Defect Density               | Measures defects relative to software size |
| Customer Problems Metric     | Measures problems reported by users        |
| Customer Satisfaction Metric | Measures how satisfied users are           |
| Function Points              | Measures functional size of software       |

### Mnemonic to Remember Product Quality Metrics

👉 **DCCF**

* **D** – Defect Density
* **C** – Customer Problems
* **C** – Customer Satisfaction
* **F** – Function Points

Think:
To judge product quality → **DCCF metrics**

---

# Defect Density

Defect density is one of the most widely used quality metrics.

### Definition

Defect Density is the number of confirmed defects found in a software product divided by the size of the software.

### Formula

Defect Density =
Number of Defects / Size of Software

Software size is often measured in:

* Lines of Code (LOC)
* Function Points

---

### Explanation

Defect density helps measure **how many defects exist relative to software size**.

Example:

If a program contains:

* 50 defects
* 10,000 lines of code

Defect Density = 50 / 10,000

Lower defect density indicates **better software quality**.

---

### Importance of Defect Density

It helps in:

1. Evaluating software quality
2. Comparing different software systems
3. Measuring testing effectiveness
4. Predicting software reliability

If defect density decreases over time, it means the development process is improving.

---

### Factors Affecting Defect Density

* Complexity of software
* Developer experience
* Testing effectiveness
* Development process maturity

Highly complex systems usually have higher defect density.

---

# Customer Problems Metric

After software is delivered, users may report problems. These issues help evaluate real-world software quality.

### Definition

Customer Problems Metric measures the number of problems reported by customers after the software has been released.

### Explanation

These problems may include:

* Software defects
* System crashes
* Performance issues
* Usability difficulties

This metric helps determine how the software behaves in the **actual user environment**.

---

### Types of Customer Problems

Customer problems can be categorized into several types:

| Type                 | Explanation                            |
| -------------------- | -------------------------------------- |
| Defects              | Errors in the software                 |
| Usability Problems   | Difficulty in using the software       |
| Documentation Issues | Incorrect or missing user instructions |
| Performance Problems | Slow response time                     |

---

### Mnemonic to Remember Customer Problem Types

👉 **DUPP**

* **D** – Defects
* **U** – Usability Issues
* **P** – Performance Problems
* **P** – Poor Documentation

---

### Importance of Customer Problems Metric

This metric helps organizations:

* Understand user difficulties
* Improve future versions
* Identify hidden defects
* Improve product reliability

If customer problems increase, it indicates **poor software quality or inadequate testing**.

---

# Customer Satisfaction Metrics

Customer satisfaction measures how happy users are with the software product.

### Definition

Customer Satisfaction Metrics measure the degree to which users are satisfied with the software product and its performance.

### Explanation

Software quality is ultimately judged by **users**.
Even if software is technically correct, it is not successful if customers are not satisfied.

Customer satisfaction can be measured using:

* Surveys
* Feedback forms
* Product ratings
* Support requests

---

### Methods to Measure Customer Satisfaction

| Method           | Explanation                         |
| ---------------- | ----------------------------------- |
| Surveys          | Customers rate product experience   |
| Feedback Reports | Users report issues and suggestions |
| Support Calls    | Number of customer support requests |
| Product Ratings  | Reviews and ratings given by users  |

---

### Mnemonic to Remember Methods

👉 **SFSP**

* **S** – Surveys
* **F** – Feedback
* **S** – Support Calls
* **P** – Product Ratings

---

### Importance of Customer Satisfaction Metrics

Customer satisfaction metrics help in:

1. Evaluating product success
2. Improving software usability
3. Understanding user expectations
4. Enhancing customer loyalty

A product with **high satisfaction ratings** is considered successful and reliable.

---

# Function Points

Function points are used to measure the **functional size of software**.

---

## Function Points (FP)

### Definition

Function Points are a software measurement technique used to estimate the functional size of software based on the number of user functions the system provides.

### Meaning

Instead of measuring software size using **lines of code**, function points measure the **functionality delivered to users**.

---

### Explanation

Function point analysis evaluates the system by counting different types of user-visible functions.

These include:

| Component                | Explanation                    |
| ------------------------ | ------------------------------ |
| External Inputs          | Data entering the system       |
| External Outputs         | Data leaving the system        |
| External Inquiries       | Interactive user requests      |
| Internal Logical Files   | Data stored inside system      |
| External Interface Files | Data shared with other systems |

---

### Mnemonic to Remember Function Point Components

👉 **EOEIF**

* **E** – External Inputs
* **O** – External Outputs
* **E** – External Inquiries
* **I** – Internal Logical Files
* **F** – External Interface Files

Think:

Software functions come from **EOEIF components**.

---

### Importance of Function Points

Function points are useful because they:

1. Measure software size independent of programming language
2. Help estimate development effort
3. Help predict development cost
4. Help measure productivity

---

### Advantages of Function Points

* Technology independent
* Useful in early project estimation
* Helps compare different projects
* Supports cost estimation

---

### Difference Between LOC and Function Points

| LOC                             | Function Points               |
| ------------------------------- | ----------------------------- |
| Measures number of code lines   | Measures system functionality |
| Depends on programming language | Language independent          |
| Hard to estimate early          | Can be estimated early        |

Thus, function points provide a **better estimation of software size and complexity**.

Perfect 👍 Dev.
We’ll continue **Unit 2 – Software Quality Metrics**, now focusing on **In-Process Quality Metrics**.
Same style: **connected flow, deeper explanation (10–15 marks ready), definitions, formulas, and single-word mnemonics**.

---

# In-Process Quality Metrics

## Meaning of In-Process Quality Metrics

### Definition

In-Process Quality Metrics are measurements used during the software development process to monitor and control the quality of the product before it is completed.

### Explanation

Unlike product metrics (which evaluate the final software), **in-process metrics evaluate quality during development**.

They help answer questions like:

* Are defects increasing or decreasing?
* Which development phase introduces the most defects?
* How effective is the testing process?

By monitoring quality during development, organizations can **detect problems early and improve development efficiency**.

---

### Major In-Process Quality Metrics

| Metric                             | Purpose                                                 |
| ---------------------------------- | ------------------------------------------------------- |
| Defect Arrival Pattern             | Shows how defects are discovered over time              |
| Phase-Based Defect Removal Pattern | Shows how defects are removed in each development phase |
| Defect Removal Effectiveness       | Measures efficiency of defect detection                 |

---

### Mnemonic to Remember

👉 **ADR**

* **A** – Arrival Pattern
* **D** – Defect Removal Pattern
* **R** – Removal Effectiveness

Think:
To control in-process quality → **ADR metrics**

---

# Defect Arrival Pattern

Software testing usually reveals defects gradually over time. Observing how defects appear during testing helps assess software stability.

---

## Definition

Defect Arrival Pattern describes the rate at which defects are discovered during the testing phase of software development.

---

## Explanation

During testing:

* Initially many defects are found.
* Over time the number decreases.
* Eventually very few defects appear.

This pattern helps determine:

* Progress of testing
* Stability of software
* Remaining defect risk

The pattern is usually represented using a **defect discovery curve**.

---

## Typical Defect Arrival Behavior

Defect discovery often follows three stages:

| Stage        | Explanation                                 |
| ------------ | ------------------------------------------- |
| Early Stage  | Few defects discovered while testing begins |
| Middle Stage | Large number of defects detected            |
| Final Stage  | Defects gradually decrease                  |

---

### Mnemonic for Defect Discovery Stages

👉 **EMF**

* **E** – Early Stage
* **M** – Middle Stage
* **F** – Final Stage

Think:

Testing progress follows **EMF pattern** of defect discovery.

---

## Importance of Defect Arrival Pattern

This metric helps teams:

1. Monitor testing progress
2. Identify unstable modules
3. Estimate remaining defects
4. Decide software release readiness

If defects continue appearing at a high rate near the end of testing, it indicates **poor software quality or insufficient testing**.

---

# Phase-Based Defect Removal Pattern

Defects can be introduced during different stages of development such as requirements, design, or coding.
This metric tracks **where defects originate and where they are removed**.

---

## Definition

Phase-Based Defect Removal Pattern measures how many defects are detected and removed in each phase of the software development life cycle.

---

## Explanation

Software development typically includes several phases:

* Requirements
* Design
* Coding
* Testing

Defects introduced in early phases should ideally be detected early.
However, sometimes defects remain hidden and are detected only during later phases.

Tracking defect removal patterns helps identify **weak phases in development**.

---

### Typical Development Phases

| Phase             | Explanation                         |
| ----------------- | ----------------------------------- |
| Requirement Phase | Defects due to unclear requirements |
| Design Phase      | Architecture or logic errors        |
| Coding Phase      | Programming mistakes                |
| Testing Phase     | Remaining defects discovered        |

---

### Mnemonic to Remember Development Phases

👉 **RDCT**

* **R** – Requirement
* **D** – Design
* **C** – Coding
* **T** – Testing

Think:
Software development moves through **RDCT phases**.

---

## Importance of Phase-Based Defect Removal Pattern

This metric helps organizations:

1. Identify which phase introduces the most defects
2. Improve early-stage development practices
3. Reduce testing workload
4. Improve overall process quality

Example insight:

If many defects from requirements are discovered during testing, it indicates **poor requirement analysis**.

---

# Defect Removal Effectiveness (DRE)

Defect Removal Effectiveness measures how efficiently defects are removed during development before software delivery.

---

## Definition

Defect Removal Effectiveness (DRE) is the percentage of defects removed during development compared to the total defects found both before and after release.

---

## Formula

DRE =

Defects Removed Before Release
------------------------------------ × 100
Total Defects (Before + After Release)

---

## Explanation

DRE indicates **how effective the development and testing process is at removing defects**.

If most defects are found before release, the DRE value will be high.

Example:

Defects found before release = 90
Defects found after release = 10

Total defects = 100

DRE = (90 / 100) × 100 = **90%**

Higher DRE means better defect detection during development.

---

## Interpretation of DRE Values

| DRE Value | Quality Interpretation   |
| --------- | ------------------------ |
| 90–100%   | Excellent defect removal |
| 80–90%    | Good quality process     |
| 70–80%    | Moderate quality         |
| Below 70% | Poor defect detection    |

---

## Importance of Defect Removal Effectiveness

DRE helps organizations:

1. Evaluate testing effectiveness
2. Improve defect detection methods
3. Reduce customer-reported defects
4. Improve software reliability

A high DRE means **most defects are removed before customers encounter them**.

---

# Relationship Between In-Process Quality Metrics

These metrics work together to monitor development quality.

* **Defect Arrival Pattern** → shows how defects are discovered during testing
* **Phase-Based Defect Removal Pattern** → shows where defects originate and are removed
* **Defect Removal Effectiveness** → measures efficiency of the defect removal process

Together they help organizations **monitor, control, and improve software quality during development**.

Great Dev 👍
We’ll continue **Unit 2 – Software Quality Metrics**, now focusing on **Metrics for Software Maintenance**.

Same structure as before:
✔ connected headings
✔ deeper explanation (10–15 marks ready)
✔ definitions
✔ formulas where needed
✔ single-word mnemonics where possible

---

# Metrics for Software Maintenance

After software is delivered to users, it enters the **maintenance phase**. During this phase, developers fix bugs, improve performance, and adapt the system to new requirements.
To evaluate how effectively maintenance activities are performed, **software maintenance metrics** are used.

---

## Meaning of Software Maintenance Metrics

### Definition

Software Maintenance Metrics are quantitative measures used to evaluate the efficiency, responsiveness, and quality of maintenance activities performed after software release.

### Explanation

Maintenance metrics help organizations monitor:

* How quickly defects are fixed
* How many issues are pending
* Whether fixes introduce new defects
* Overall stability of the software system

These metrics ensure that software continues to operate reliably even after deployment.

---

### Major Maintenance Metrics

| Metric                      | Purpose                                              |
| --------------------------- | ---------------------------------------------------- |
| Backlog Management Index    | Measures how effectively pending issues are resolved |
| Fix Response Time           | Measures how quickly defects are fixed               |
| Fix Quality                 | Evaluates quality of defect fixes                    |
| Software Quality Indicators | Overall indicators of system health                  |

---

### Mnemonic to Remember Maintenance Metrics

👉 **BFQS**

* **B** – Backlog Management Index
* **F** – Fix Response Time
* **Q** – Fix Quality
* **S** – Software Quality Indicators

Think:
Maintenance quality is evaluated using **BFQS metrics**.

---

# Backlog Management Index (BMI)

During maintenance, many defect reports and change requests accumulate. These unresolved issues are known as the **backlog**.

---

## Definition

Backlog Management Index (BMI) measures how effectively a team resolves the backlog of reported defects and change requests.

---

## Formula

BMI =

Number of Problems Closed in a Period
------------------------------------------ × 100
Number of Problems Arrived in the Same Period

---

## Explanation

The BMI value shows whether the maintenance team is keeping up with incoming issues.

Example:

Problems reported in a month = 120
Problems fixed in the same month = 100

BMI = (100 / 120) × 100 = **83.3%**

---

## Interpretation of BMI

| BMI Value | Meaning                          |
| --------- | -------------------------------- |
| 100%      | All reported issues are resolved |
| >100%     | Backlog is decreasing            |
| <100%     | Backlog is increasing            |

---

## Importance of Backlog Management Index

BMI helps organizations:

1. Monitor maintenance workload
2. Control accumulation of unresolved defects
3. Evaluate maintenance efficiency
4. Ensure timely resolution of issues

If BMI remains below 100% for long periods, it indicates **growing backlog and maintenance problems**.

---

# Fix Response Time

Users expect problems to be fixed quickly after they are reported.

---

## Definition

Fix Response Time is the average time taken by the maintenance team to respond to and resolve a reported defect or issue.

---

## Formula

Fix Response Time =

## Total Time Taken to Fix Issues

Total Number of Issues Fixed

---

## Explanation

This metric measures the **speed of maintenance support**.

Example:

If 10 issues take a total of 50 hours to fix:

Fix Response Time = 50 / 10 = **5 hours per issue**

---

## Importance of Fix Response Time

It helps organizations evaluate:

* Maintenance responsiveness
* Customer support efficiency
* Developer productivity

Shorter fix response time indicates **faster and more efficient maintenance**.

---

# Fix Quality

Sometimes fixing a defect introduces new errors. Therefore, it is important to evaluate the **quality of fixes**.

---

## Definition

Fix Quality measures how effectively defects are fixed without introducing new defects into the system.

---

## Explanation

A fix is considered high quality if:

* The defect is completely resolved
* No new defects are introduced
* System stability is maintained

Poor fix quality may result in **regression defects**, where fixing one problem causes another.

---

## Measuring Fix Quality

Fix quality is usually evaluated by measuring:

* Number of defects caused by fixes
* Percentage of successful fixes
* Number of reopened defect reports

---

### Mnemonic for Fix Quality Factors

👉 **RSP**

* **R** – Reopened defects
* **S** – Successful fixes
* **P** – Problems caused by fixes

Think:
Fix quality depends on **RSP factors**.

---

# Software Quality Indicators

Software quality indicators provide a broader view of the **overall health and stability of the software system**.

---

## Definition

Software Quality Indicators are measurable factors used to evaluate the overall performance, reliability, and maintainability of software.

---

## Explanation

These indicators combine multiple metrics to assess the **general quality level** of the system.

They help managers and developers understand whether the software system is improving or degrading over time.

---

## Major Software Quality Indicators

| Indicator                  | Explanation                        |
| -------------------------- | ---------------------------------- |
| Defect Density             | Number of defects per unit size    |
| Customer Reported Problems | Issues reported by users           |
| System Reliability         | Ability to run without failure     |
| Maintenance Effort         | Resources required for maintenance |
| Response Time for Fixes    | Speed of problem resolution        |

---

### Mnemonic to Remember Quality Indicators

👉 **DCRMR**

* **D** – Defect Density
* **C** – Customer Problems
* **R** – Reliability
* **M** – Maintenance Effort
* **R** – Response Time

Think:
Software health can be judged using **DCRMR indicators**.

---

# Role of Maintenance Metrics in Software Quality

Maintenance metrics play an important role in ensuring long-term software quality.

They help organizations:

1. Monitor post-release defects
2. Improve maintenance efficiency
3. Reduce system downtime
4. Increase customer satisfaction
5. Maintain software reliability

By analyzing maintenance metrics, organizations can ensure that the software system remains **stable, reliable, and efficient throughout its lifecycle**.