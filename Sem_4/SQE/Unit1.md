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

---

**5. Demonstrate Software Quality Attributes and Specification in detail. _(Section C – Q3a)_**

## Software Quality Attributes

Software quality is evaluated based on certain measurable characteristics known as **Quality Attributes**.

### Definition

Software Quality Attributes are the properties or characteristics that determine how effectively and efficiently a software system performs its intended functions.

These attributes describe the overall performance level of software.

---

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

---

# Software Defects and Their Effect on Quality

Software quality is mainly affected by errors that occur during development.

**Discuss error, fault & failure with respect to Software Quality. _(Section A – Q1a)_**

---

## Fault, Defect, and Failure

### Fault

A Fault is an incorrect step, logic mistake, or wrong instruction written in the program code.

Example: Using incorrect formula in interest calculation.

---

### Defect

A Defect is a flaw in the software system that occurs due to the presence of a fault and may cause incorrect behavior.

Example: Wrong interest amount displayed.

---

### Failure

A Failure occurs when the system does not perform its intended function during execution.

Example: Application crashes when interest is calculated.

---

### Relationship:

Fault (Coding Error)
→ leads to
Defect (System Flaw)
→ causes
Failure (Incorrect System Behavior)

Failure occurs only when defective code is executed.

![Fault, Defect, and Failure Relationship](https://media.geeksforgeeks.org/wp-content/uploads/20230818110304/defect_-bug-and-failure.png)

---

# Measuring Software Quality

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

---

# Cost of Quality (CoQ)

Maintaining quality involves certain costs.

### Definition

Cost of Quality is the total cost invested in preventing defects and the cost arising due to defects present in the system.

It includes both:

- Cost of achieving good quality
- Cost of poor quality

---

## Types of Cost of Quality

| Type                  | Explanation                     |
| --------------------- | ------------------------------- |
| Prevention Cost       | Cost to avoid defects           |
| Appraisal Cost        | Cost to detect defects          |
| Internal Failure Cost | Cost of defects before delivery |
| External Failure Cost | Cost of defects after delivery  |

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
