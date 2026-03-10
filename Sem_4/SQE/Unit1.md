# UNIT 1 – SOFTWARE QUALITY ASSURANCE (Deep Notes for 10–15 Marks)

# Software Quality and Its Measurable Characteristics

## Software Quality

**2. Explain the term Software Quality. (Section A – Q1b)**

### Definition

Software quality is a degree that tells how well a software product meets users’ needs and how correctly and reliably it works in the situations it is meant for.

### Explanation

Software quality does not only mean that the software is working.
It means that the software:

- Produces correct output
- Works without failure
- Is secure
- Is easy to use
- Uses minimum resources
- Can be easily modified in future

Thus, software quality ensures both:

- **Functional correctness** (what the system does)
- **Non-functional performance** (how well the system performs)

Software that satisfies user expectations over time is said to be of high quality.

# Software Quality Engineering (SQE)

## Definition

Quality engineering (QE) is a systematic approach that integrates testing and quality assurance throughout the entire software development lifecycle (SDLC), rather than just at the end. 

It focuses on preventing defects through automation, collaboration, and process optimization to deliver high-quality, reliable, and user-centric software efficiently.

## Meaning of the Term

The term **Software Quality Engineering** combines three concepts:

* **Software** → The computer programs and related documentation
* **Quality** → Degree that tells how well a software meets user requirements
* **Engineering** → Application of systematic methods and scientific principles

Thus, **Software Quality Engineering means applying engineering principles to ensure high software quality during development and maintenance.**

---

## Explanation

Software Quality Engineering focuses on **building quality into the software from the beginning**, rather than trying to fix defects later.

It includes activities such as:

* Defining quality standards
* Preventing defects during development
* Measuring software quality
* Performing reviews and inspections
* Monitoring reliability and performance

SQE covers **both quality assurance and quality control**.

| Aspect            | Focus              |
| ----------------- | ------------------ |
| Quality Assurance | Preventing defects |
| Quality Control   | Detecting defects  |

Together they ensure that software meets required quality levels.

---

# Key Activities in Software Quality Engineering

Software Quality Engineering involves several important activities that help maintain product quality.

### Major SQE Activities

| Activity               | Explanation                            |
| ---------------------- | -------------------------------------- |
| Quality Planning       | Defining quality goals and standards   |
| Quality Assurance      | Ensuring development follows standards |
| Quality Control        | Detecting defects through testing      |
| Quality Measurement    | Using metrics to evaluate quality      |
| Continuous Improvement | Improving development processes        |

---

### Mnemonic to Remember SQE Activities

👉 **PAQMI**

* **P** – Planning
* **A** – Assurance
* **Q** – Quality Control
* **M** – Measurement
* **I** – Improvement

Think:
To engineer quality in software → follow **PAQMI activities**.

---

# Importance of Software Quality Engineering / Objectives of Software Quality Engineering

Sofware quality enginerring is important as it helps.. /The main objectives of Software Quality Engineering are:

**DUCRM - Defects, User Requirements, Customer Satisfaction, Reliability, Maintainability**

1. To ensure that software meets user requirements
2. To reduce defects in software products
3. To improve reliability and performance
4. To enhance maintainability and usability
5. To improve customer satisfaction

By achieving these objectives, SQE helps produce **high-quality and dependable software systems**.

**5. Demonstrate Software Quality Attributes and Specification in detail. _(Section C – Q3a)_**

## Software Quality Attributes

Software quality is evaluated based on certain measurable characteristics known as **Quality Attributes**.

### Definition

Software Quality Attributes are the properties or characteristics that determine how effectively and efficiently a software system performs its intended functions.

These attributes describe the overall performance level of software.

### Major Software Quality Attributes

Here it is in **PERFICIUM order** (P → E → R → F → I → C → I → U → M):

| Attribute        | Explanation                                 |
| ---------------- | ------------------------------------------- |
| Portability      | Can run on different platforms              |
| Efficiency       | Uses system resources effectively           |
| Reliability      | Works without failure for a given time      |
| Flexibility      | Easy to adapt to new changes                |
| Integrity        | Protects system from unauthorized access    |
| Correctness      | Software performs according to requirements |
| Interoperability | Works with other systems                    |
| Usability        | Easy to learn and operate                   |
| Maintainability  | Easy to repair and modify                   |

---

## Software Quality Specification

Quality must be defined before development starts.

### Definition

Software Quality Specification is a document that contains set of quality standards and requirements that a software system must meet during development and operation.

### Explanation

It clearly defines:

- Performance requirements
- Security needs
- Reliability level
- Usability standards
- System behavior expectations

It helps in:

- Guiding developers during development
- Assisting testers in validation
- Measuring quality level by management

Without quality specification:

- Developers may interpret quality differently
- Testing becomes inconsistent
- Final product may not satisfy users

# Software Defect

A Defect is a flaw in the software system caused by a fault that may lead to incorrect results.
It indicates that the software does not behave as intended.

## Causes of Defects (Mnemonic: **DEFECT**)

| Letter | Cause               | Meaning                                                              |
| ------ | ------------------- | -------------------------------------------------------------------- |
| **D**  | Design Errors       | Mistakes made while designing system architecture or logic.          |
| **E**  | Environment Issues  | Problems caused by hardware, operating system, or development tools. |
| **F**  | Faulty Requirements | Incorrect, incomplete, or misunderstood requirements.                |
| **E**  | Execution Mistakes  | Errors made by programmers while writing or implementing code.       |
| **C**  | Communication Gaps  | Miscommunication between developers, testers, and clients.           |
| **T**  | Testing Weakness    | Inadequate or improper testing that fails to detect defects early.   |

## Defect Management Process

### Definition

The **Defect Management Process** is a systematic process used to identify, record, track, fix, and verify defects in software.
It ensures that defects are properly handled so that the software product maintains good quality and reliability.

### Common Example Used

Suppose an **online shopping system calculates the total bill incorrectly**.
Instead of **Total Price = Quantity × Price**, the system calculates the wrong amount.

This same example will be used for all levels below.

## Levels in the Defect Management Process

## 1. Detection

### Definition

Detection is the stage where a defect is discovered during testing, review, or by users while using the software.
It is the first step where the problem in the system is identified.

### Example

While testing the shopping website, the tester notices that the **total bill shown to the customer is incorrect**.

---

## 2. Logging

### Definition

Logging is the process of recording the detected defect in a defect tracking system with proper details.
Information such as defect description, severity, and steps to reproduce the problem are documented.

### Example

The tester reports the defect in a defect tracking tool and writes:
*"Total bill is calculated incorrectly when the user adds multiple products."*

---

## 3. Assignment

### Definition

Assignment is the stage where the reported defect is assigned to a developer or development team for fixing.
The project manager or team lead usually assigns the defect.

### Example

The team leader assigns the **billing calculation defect** to a developer who is responsible for the payment module.

---

## 4. Resolution (Fixing)

### Definition

Resolution is the process where the developer analyzes the defect and corrects the problem in the program code.
The faulty logic or incorrect code is modified to remove the defect.

### Example

The developer finds that the formula in the code is wrong and corrects it to:

Total Price = Quantity × Price

---

## 5. Verification

### Definition

Verification is the stage where the tester checks the software again to confirm that the defect has been fixed correctly.
Testing ensures that the defect no longer exists and the system works properly.

### Example

The tester tests the shopping system again and confirms that the **total bill is now calculated correctly**.

---

## 6. Closure

### Definition

Closure is the final stage where the defect is marked as closed after successful verification.
This means the defect has been resolved and no further action is required.

### Example

After confirming the correct bill calculation, the tester marks the defect as **closed in the defect tracking system**.

## Software Defects and Their Effect on Quality

Software quality is mainly affected by errors that occur during development.

**Discuss error, fault & failure with respect to Software Quality. _(Section A – Q1a)_**

---

## Terminologies in Software Engineering

**Bug, Wrong (Error), Fault, Defect, Failure**

### Common Example Used

A developer writes the billing formula incorrectly in an online shopping system.
Instead of **Total Price = Quantity × Price**, the programmer writes **Quantity − Price**.

## Wrong (Error)

**Definition:**
A Wrong (Error) is a human mistake made during software development such as misunderstanding requirements or writing incorrect logic.
It usually occurs during requirement analysis, design, or coding.

**Example:**
The programmer misunderstands the billing logic and thinks subtraction should be used instead of multiplication.

## Fault

**Definition:**
A Fault is the incorrect statement or logic written in the program due to a human error.
It exists inside the software code or design.

**Example:**
The programmer writes **Total = Quantity − Price** in the program code.

## Defect

**Definition:**
A Defect is a flaw in the software system caused by a fault that may lead to incorrect results.
It indicates that the software does not behave as intended.

**Example:**
Because of the wrong formula in the system, the billing module contains incorrect calculation logic.

## Failure

**Definition:**
A Failure occurs when the software does not perform its intended function during execution.
It is the visible incorrect behavior of the system.

**Example:**
When a customer places an order, the system calculates the total price incorrectly.

## Bug

**Definition:**
A Bug is a defect discovered during software testing or after software release.
It is the commonly used term for reporting software problems.

**Example:**
The tester reports that the billing system is calculating the total price incorrectly.

## Relationship Between the Terms

Simple Example of the Full Chain

1. Developer misunderstands requirement (Error)
2. Writes wrong calculation in code (Fault)
3. Billing module contains wrong logic (Defect)
4. Software calculates wrong bill during execution (Failure)

Tester reports the issue (Bug)

Error (Wrong)
→ Fault
→ Defect
→ Failure
→ Bug

# Cost of Quality (CoQ)

Maintaining quality involves certain costs.

### Definition

Cost of Quality is the total cost invested in preventing defects and the cost arising due to defects present in the system.

It includes both:

- Cost of achieving good quality
- Cost of poor quality

---

## Types of Cost of Quality
| Type                  | Definition                                                                 | Examples / Explanation |
| --------------------- | -------------------------------------------------------------------------- | ---------------------- |
| Prevention Cost       | Prevention Cost is the money spent to prevent defects from happening.      | Training, better requirements, design reviews, coding standards, tooling, process improvements. |
| Appraisal Cost        | Appraisal Cost is the money spent to find and detect defects.              | Testing, inspections, code reviews, test automation, audits, QA environment costs. |
| Internal Failure Cost | Internal Failure Cost is the money spent because defects were found after development but before delivery. | Rework, debugging, retesting, wasted developer time, scrap of faulty components. |
| External Failure Cost | External Failure Cost is the money spent because defects were found after devlopment and delivery. | Customer support, patches, hotfixes, refunds, legal costs, lost sales and reputation. |

---

### Mnemonic to Remember:

👉 **PAIE** (sounds like “Pay”)
We _pay_ for quality in four ways:

- **P** – Prevention Cost
- **A** – Appraisal Cost
- **I** – Internal Failure Cost
- **E** – External Failure Cost

External Failure is usually the highest cost because it affects customer trust and reputation.

---

# Defect Management Techniques

To maintain software quality, defects must be controlled.

- Defect management techniques are simple steps used to handle bugs in software.
- They include finding and reporting defects, recording details, and tracking their progress.
- Teams decide which defects to fix first, assign them to developers, and retest after fixes.
- The process also checks causes to stop the same bugs from happening again and improves quality.

---

## Defect Prevention

**Explain Defect Prevention and its activities. Mention the steps involved in Defect Prevention Techniques and Practices.**

![DPT](https://media.geeksforgeeks.org/wp-content/uploads/20200908155423/D132.png)

**Defect Prevention (DP)** means stopping defects from happening again in the future.
If a defect has already been found, the goal is to make sure that the **same type of defect does not occur again**.

In a team, a **Coordinator** manages defect prevention activities. The coordinator:

* Leads defect prevention work
* Organizes meetings
* Helps communication between team members and management
* Helps create defect prevention guidelines

A **Defect Prevention (DP) Board** usually makes a **quarterly plan** for the organization.
This plan sets goals to reduce defects. Different methods and activities are used to achieve these goals.

### Methods of Defect Prevention

There are several methods used to prevent defects in software.

#### 1. Software Requirement Analysis

Many defects happen because of **wrong or unclear requirements and design**.

Software requirements describe:

* Features of the software
* Functions of the software
* What users expect from the software

Requirements are an important part of the **Software Development Life Cycle (SDLC)**.

If developers and testers **do not understand the requirements properly**, defects may occur later in development.

Therefore, requirements must be **carefully analyzed and clearly understood** to prevent defects.

#### 2. Review and Inspection

**Reviews and inspections** are powerful techniques used to find defects early.

They help detect defects **before the software goes into production**.

These activities are used during **software development and maintenance**.

Types of review:

* **Self Review** – A developer checks their own work.
* **Peer Review** – Team members review each other’s work.

Finding defects early saves **time, cost, and effort**.

#### 3. Defect Logging and Documentation

After defects are found, they should be **properly recorded and documented**.

The defect record should include:

* Description of the defect
* Where it occurred
* When it occurred

This documentation helps teams:

* Understand defects better
* Analyze patterns of defects
* Take actions to prevent them in future phases

#### 4. Root Cause Analysis (RCA)

**Root Cause Analysis** means finding the **main reason why a defect occurred**.

It answers questions like:

* Why did the defect happen?
* What caused it?
* How can we stop it from happening again?

Once the root cause is identified, the team can take **corrective actions** to prevent similar defects in the future.

---

✅ **Quick Memory Trick: R³D**

* **R** – Requirement Analysis
* **R** – Review & Inspection
* **D** – Defect Logging
* **R** – Root Cause Analysis

---

## Defect Reduction

### Definition

Defect Reduction is the process of identifying and removing defects before the software is delivered to the customer.

### Methods:

- Testing
- Code reviews
- Inspections
- Static analysis

Goal: Reduce number of existing defects.

---

## Defect Containment

### Definition

Defect Containment is the process of minimizing the impact of defects so that they do not cause system failure during operation.

### Methods:

- Exception handling
- Backup systems
- Fault-tolerant design
- Redundancy techniques

Goal: Prevent system failure even if defects exist.

---

### Mnemonic to Remember Defect Control Strategies:

👉 **PRC**

- **P** – Prevention
- **R** – Reduction
- **C** – Containment

additionaly... we can look over this

![Detect Managment Process](https://www.slideteam.net/media/catalog/product/cache/1280x720/d/e/defect_management_process_in_software_development_slide01.jpg)

# Software Reviews, Measurement, Inspection, Documents and Metrics

---

# Software Reviews: Ensuring Quality Before Testing

During software development, errors can occur at any stage such as requirement gathering, design, coding, or documentation.
To detect these errors early, **Software Reviews** are conducted.

---

## Software Review

### Definition

A Software Review is a systematic examination of software work products such as requirements, design, code, and documents to identify defects and improve quality.

### Meaning

Review means checking or evaluating something carefully.
So, software review means checking software components before execution.

### Explanation

Software review is a **static verification technique**, which means:

- Software is examined without executing it.
- Focus is on identifying faults early.
- Helps in improving product quality.

Benefits:

- Early defect detection
- Reduced development cost
- Improved software reliability
- Better communication among team members

---

## Types of Software Reviews

There are several types of reviews based on the level of formality involved.

### Major Types of Reviews:

| Type              | Explanation                               |
| ----------------- | ----------------------------------------- |
| Informal Review   | Casual checking without strict procedure  |
| Walkthrough       | Author explains product to team members   |
| Technical Review  | Experts examine technical correctness     |
| Inspection        | Formal and structured defect detection    |
| Management Review | Management evaluates progress and quality |
| Audit Review      | Independent evaluation for standards      |

---

### Mnemonic to Remember Types of Reviews:

👉 **IWTIMA** (sounds like “I Will Take Inspection, Manager, Auditor”)

- **I** – Informal Review
- **W** – Walkthrough
- **T** – Technical Review
- **I** – Inspection
- **M** – Management Review
- **A** – Audit Review

![A](https://media.geeksforgeeks.org/wp-content/uploads/20240625143606/Types-Software-Technical-Review.png)

---

# Measurement and Inspection Process

Software quality cannot be improved unless it is measured and inspected properly.

---

## Software Measurement

### Definition

Software Measurement is the process of assigning numerical values to software attributes or characteristics in order to evaluate its quality.

### Meaning

Measurement means determining size or amount.
So, software measurement determines quality-related factors in numerical form.

### Explanation

It helps in:

- Estimating software complexity
- Evaluating performance
- Measuring defect rate
- Predicting reliability
- Improving development process

Software measurement provides objective data for decision-making.

---

## Software Inspection

Inspection is a **formal type of review** used to detect defects in software work products.

### Definition

Software Inspection is a structured process in which a team examines software artifacts such as design documents or code to identify defects systematically.

It is the most effective review technique for defect detection.

---

## Inspection Process Steps

Inspection follows a structured approach.

### Steps Involved:

| Step               | Explanation                                |
| ------------------ | ------------------------------------------ |
| Planning           | Selection of inspection team and materials |
| Overview           | Author explains product to team            |
| Preparation        | Reviewers examine documents individually   |
| Inspection Meeting | Team identifies defects collectively       |
| Rework             | Author fixes identified defects            |
| Follow-up          | Verification of defect removal             |

---

### Mnemonic to Remember Inspection Steps:

👉 **POPRIF**

- **P** – Planning
- **O** – Overview
- **P** – Preparation
- **I** – Inspection Meeting
- **R** – Rework
- **F** – Follow-up

Think:
To inspect software → **POPRIF** process is followed.

![B](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQesZYxc9QtjRj5QJYoRS6CkkbCJIYARyLvXg&s)

---

# Software Documents

Software development involves several documents that help in maintaining quality and communication.

---

## Software Documents

### Definition

Software Documents are written records that describe software requirements, design, implementation, testing, and maintenance details.

### Explanation

They help in:

- Understanding system functionality
- Supporting future maintenance
- Improving communication
- Providing reference for testing

---

## Types of Software Documents

| Document             | Purpose                       |
| -------------------- | ----------------------------- |
| Requirement Document | Defines user needs            |
| Design Document      | Describes system architecture |
| Test Document        | Contains test plans and cases |
| User Manual          | Guides end-users              |
| Maintenance Document | Helps in software updates     |

---

### Mnemonic to Remember Documents:

👉 **RDTUM**

- **R** – Requirement Document
- **D** – Design Document
- **T** – Test Document
- **U** – User Manual
- **M** – Maintenance Document

---

# Software Metrics

Measurement in software is achieved using metrics.

---

## Functional vs Non‑Functional Requirements

**Demonstate functional and Non Functional Requirements with example**

### Definitions

- Functional Requirements: Specify what the system must do — features, behaviors, inputs/outputs and business rules.
- Non‑Functional Requirements (NFRs): Specify how the system performs those functions — qualities like performance, security, usability, reliability, and maintainability.

### Key Differences

| Aspect            |                            Functional Requirements | Non‑Functional Requirements                                         |
| ----------------- | -------------------------------------------------: | :------------------------------------------------------------------ |
| Purpose           |         Describe system behavior and functionality | Describe quality attributes and constraints                         |
| Example statement | "The system shall allow users to create accounts." | "The system shall respond to search queries within 2 seconds."      |
| Measurability     |       Often binary (implemented / not implemented) | Usually quantitative or subject to SLAs (performance, availability) |
| Testability       |            Verified by functional/acceptance tests | Verified by performance, load, security, usability tests            |
| Impact            |                     Affects features and use-cases | Affects architecture, design, operations                            |
| Priority change   |                     May change with business needs | Typically stable but may change with scale or risk posture          |
| Stakeholders      |       Product owners, business analysts, end users | Architects, operations, QA, security teams                          |
| Documentation     |          Use cases, user stories, functional specs | NFR checklist, system quality specifications, SLOs/SLAs             |

### Why both matter

- Functional requirements deliver user value (what to build).
- NFRs ensure the delivered value is usable, reliable, secure, and maintainable (how well it works).  
  Balancing both is essential for perceived software quality.

### Quick checklist to write NFRs

- Be specific and measurable (e.g., numbers, thresholds).
- Attach test criteria and monitoring method.
- State environment/conditions and acceptable tolerance.
- Link to functional requirements they constrain.

### Simple examples of Functional and Non‑Functional Requirements

#### Functional requirements (what the system must do)
- Users can create an account using an email and password.
- Users can log in and log out.
- The system allows users to add items to a shopping cart and checkout.
- The system sends an order confirmation email after purchase.
- Admins can add, edit, or remove product listings.

#### Non‑functional requirements (how the system performs)
- The website responds to user actions within 2 seconds under normal load.
- The system is available 99.9% of the time per month.
- Passwords are stored using secure hashing (e.g., bcrypt).
- The application supports at least 500 concurrent users.
- Search results are returned within 1 second for typical queries.
- All pages should render correctly on mobile and desktop screens.
- Data backups are performed daily and retained for 30 days.
- Sensitive data is transmitted only over HTTPS.

These pair together: functional requirements define features; non‑functional requirements define quality, performance, security, and reliability.


## Software Metrics

### Definition

Software Metrics are quantitative measures used to evaluate the quality, performance, and complexity of software products or processes.

### Meaning

Metric means a standard of measurement.

---

## Types of Software Metrics

| Metric Type     | Explanation                      |
| --------------- | -------------------------------- |
| Product Metrics | Measure software characteristics |
| Process Metrics | Measure development process      |
| Project Metrics | Measure project performance      |

---

### Product Metrics

Measure:

- Size
- Complexity
- Performance
- Reliability

---

### Process Metrics

Measure:

- Development efficiency
- Defect removal rate
- Testing effectiveness

---

### Project Metrics

Measure:

- Cost
- Schedule
- Productivity
- Resource utilization

---

### Mnemonic to Remember Metric Types:

👉 **PPP**

- **P** – Product Metrics
- **P** – Process Metrics
- **P** – Project Metrics

Think:
Software quality measurement uses **PPP Metrics**.

## Measuring Software Quality

![Software Quality Image](https://appsierra-site.s3.ap-south-1.amazonaws.com/menskool_Blog_4b895f464c.jpg)

Measuring software quality uses objective metrics and indicators to track, compare, and improve product fitness.

### Key Metrics and Indicators

- Defect Density  
   Number of defects / size (e.g., defects per KLOC). Lower = better.

- Defect Rate  
   Number of defects found per unit time or per release cycle.

- Mean Time Between Failures (MTBF)  
   Total operational time / number of failures — higher is better.

- Mean Time To Repair (MTTR)  
   Total downtime / number of repairs — lower is better.

- Availability  
   Availability = MTBF / (MTBF + MTTR)

- Reliability  
   Probability the system performs without failure for a specified period (measured via failure rates, MTBF).

- Test Coverage  
   % of code, requirements, or paths exercised by tests — higher coverage improves confidence.

- Escaped Defects (Customer-reported)  
   Defects found in production per release — used to measure release quality.

- Requirement Coverage  
   % of requirements verified by tests or acceptance criteria.

- Performance Metrics  
   Response time, throughput, resource utilization under expected loads.

- Maintainability Metrics  
   Cyclomatic complexity, code churn, modularity — indicate ease of change.

- Security Metrics  
   Number/severity of vulnerabilities, time-to-patch, successful penetration test findings.

### Guidance

- Use a balanced set of metrics (process, product, and outcome).
- Track trends over time and set thresholds/targets.
- Interpret metrics in context; correlate metrics to identify root causes.
- Combine automated collection (CI/CD, telemetry) with periodic reviews for action.

---

## Defect Rate

### Definition

Defect Rate is the number of defects identified in software per unit size (e.g., per 1000 lines of code) or per unit time.

### Formula:

Defect Rate = Number of Defects / Size of Software

### Explanation

- High Defect Rate = Low Quality
- Low Defect Rate = High Quality

Defect rate helps in:

- Comparing development performance
- Evaluating software stability
- Predicting reliability

---

## Reliability

### Definition

Reliability is the probability that software will function without failure for a specified period under specified operating conditions.

### Explanation

Reliable software:

- Works continuously
- Does not crash
- Produces correct output consistently

Reliability depends on:

- Fewer defects
- Proper testing
- Good system design

As defect rate decreases, reliability increases.
