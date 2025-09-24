# Requirement Engineering and Feasibility Study

## Requirement Engineering

**2021, Sec A: What is Software Requirement Engineering?**
**2023, Sec C: Significance of Requirement Engineering & Steps**
**2024, Sec A: Steps in Requirement Engineering Process**

- **Definition:**
  - Software Requirement Engineering (SRE) is the process of finding out, analyzing, documenting, and managing what users need from a software system. It helps make sure the software will solve the right problems and work as expected.
- **Significance:**
  - Requirement engineering is important because it helps avoid mistakes, saves time and money, and makes sure the software meets user needs.
  - It helps everyone (users, developers, managers) understand what the software should do.
- **Steps in Requirement Engineering:**
  1. **Elicitation:** Gathering information from users and stakeholders (people interested in the project) about what they need. Methods: Interviews, surveys, observation, brainstorming.
  2. **Analysis:** Studying the gathered information to find out what is possible and what is needed. Sorting out conflicts and making requirements clear.
  3. **Documentation:** Writing down the requirements in a clear and organized way, usually in a Software Requirements Specification (SRS) document.
  4. **Review:** Checking the requirements with users and team members to make sure they are correct and complete.
  5. **Management:** Keeping track of changes to requirements and making sure everyone knows the latest version.

**2022, Sec C: Software Requirement Analysis and Specification & Methods for Requirement Gathering**
**2022, Sec C: Requirement Elicitation and Analysis Process**

- **Requirement Analysis:** Understanding and organizing user needs. Making sure requirements are clear, complete, and possible.
- **Specification:** Writing requirements in detail so developers know what to build.
- **Methods for Requirement Gathering:** Interviews, questionnaires, workshops, observation, document analysis.

- **Elicitation:** Collecting requirements from users using different methods. This involves interacting with stakeholders through interviews, surveys, workshops, and observations to understand their needs and expectations.
- **Analysis:** Studying and refining requirements to remove confusion and conflicts. This step ensures that all requirements are clear, consistent, and feasible, resolving any ambiguities or contradictions among stakeholder inputs.

**2021, Sec B: Risk Analysis and Management**

- **Definition:** Risk analysis is finding out what could go wrong in the project and how to handle it.
- **Process:**
  1. Identify risks (like unclear requirements, technical problems).
  2. Analyze how likely and serious each risk is.
  3. Plan how to avoid or reduce risks.
  4. Monitor risks during the project.

**2020, Sec A: Define Functional Requirement**
**2024, Sec B: Differentiate between functional and non-functional requirements**

| Aspect           | Functional Requirements                       | Non-Functional Requirements                       |
| ---------------- | --------------------------------------------- | ------------------------------------------------- |
| Definition       | What the system should do                     | How the system should be                          |
| Focus            | Features, tasks, and behaviors                | Quality attributes and constraints                |
| Example          | "User can log in"                             | "System responds within 2 seconds"                |
| Specification    | Described in use cases or user stories        | Described as system properties                    |
| Measurement      | Can be tested by executing functions          | Measured by metrics (speed, reliability, etc.)    |
| User Interaction | Directly visible to users                     | Often invisible to users                          |
| Change Frequency | Changes with business needs                   | Changes with technology or standards              |
| Documentation    | Listed in functional specification            | Listed in quality or performance specification    |
| Impact on Design | Determines system architecture and modules    | Influences system architecture and infrastructure |
| Examples         | Data entry, report generation, authentication | Security, scalability, usability, maintainability |

**2023, Sec A: Two characteristics of SRS**

- **SRS (Software Requirements Specification):** A document that lists all requirements for the software.
- **Characteristics:**
  1. **Clear and precise:** Requirements should be easy to understand and not confusing.
  2. **Complete:** All necessary requirements should be included.

---

## Feasibility Study (STOLE)

**2020, Sec C: Role of Feasibility Study & Two Types**
**2023, Sec B: What is feasibility study? Contents of feasibility report**
**2024, Sec C: Important activities during feasibility study phase**

- **Definition:** A feasibility study checks if a project is possible and worth doing. It looks at whether the software can be built with the available time, money, and technology.
- **Role:** Helps decide if the project should go ahead. Finds possible problems early.
- **Types of Feasibility:**
  1. **Technical Feasibility:** Checks if the technology needed is available and can be used.
  2. **Economic Feasibility:** Checks if the project is affordable and worth the cost.
  3. **Operational Feasibility:** Checks if the solution will work in the organization.
  4. **Legal Feasibility:** Checks if the project follows laws and regulations.
  5. **Schedule Feasibility:** Checks if the project can be completed on time.
- **Contents of Feasibility Report:**
  1. Project overview
  2. Goals and objectives
  3. Types of feasibility (technical, economic, operational, legal, schedule)
  4. Findings and recommendations
- **Important Activities:**
  1. Study current system
  2. Identify problems and needs
  3. Analyze possible solutions
  4. Evaluate alternatives
  5. Recommend best solution

---

## Information Modelling (DFD, ER Diagram, Structure Chart)

**2020, Sec A & 2024, Sec A: What does data flow diagram level 0 represent?**
**2020, Sec B: Draw Context level and Level-1 DFD for Attendance Monitoring System.**
**2023, Sec B: Draw a DFD for result preparation automation system of MCA Courses.**
**2022, Sec B: Explain in detail about DFD and Structure Chart.**
**2023, Sec A: Describe structure chart.**
**2023, Sec A: Describe ER Diagram.**

### Data Flow Diagram (DFD):**

- **What is a Data Flow Diagram (DFD)?**
    - A DFD is a simple diagram that shows how data moves through a system. It helps you see where data comes from, where it goes, and how it is processed.
    - DFDs use easy-to-understand symbols:
        - **Circle:** A process that changes or uses data (e.g., "Calculate Results").
        - **Arrow:** Shows how data moves from one place to another.
        - **Rectangle:** An outside person or system (external entity) that interacts with your system (e.g., "Student").
        - **Open-ended Rectangle:** A place where data is stored (data store), like a database.

- **Level 0 DFD (Context Diagram):**
    - This is the simplest DFD. It shows the whole system as one big process and how it connects to outside entities.
    - **Example:** For an Attendance Monitoring System, the Level 0 DFD would show:
        - The system as one circle labeled "Attendance Monitoring System".
        - Arrows going to and from "Student", "Teacher", and "Database".
        - It only shows the main inputs and outputs, not the details inside the system.

    ```
    [Student] ---> [Attendance Monitoring System] <--- [Teacher]
                                                |
                                        [Database]
    ```

- **Level 1 DFD:**
    - This DFD breaks the main system into smaller steps or processes. It shows more detail about what happens inside the system.
    - **Example:** For Attendance Monitoring System, Level 1 DFD might show:
        - Processes like "Mark Attendance", "View Attendance", "Generate Report".
        - Data stores like "Attendance Records".
        - Entities like "Student" and "Teacher".
        - Arrows showing how data moves between these parts.

    ```
    [Student] ---> (Mark Attendance) ---> [Attendance Records]
    [Teacher] ---> (View Attendance) ---> [Attendance Records]
    (Generate Report) ---> [Attendance Records] ---> [Teacher]
    ```

- **DFD for Result Preparation System:**
    - **Context Level:** Shows the system as one process interacting with "Student", "Exam Cell", and "Database".
    - **Level 1:** Breaks it into steps like "Enter Marks", "Calculate Results", "Generate Report".
    - Example points:
        - "Student" gives marks to "Enter Marks" process.
        - "Calculate Results" uses data from "Database".
        - "Generate Report" sends results to "Exam Cell" and "Student".

- **Why use DFDs?**
    - DFDs make it easy for everyone (students, teachers, developers) to understand how a system works.
    - They help find mistakes, improve design, and explain ideas clearly.
    - DFDs are simple, use basic shapes, and do not need technical language.

- **Quick Points:**
    - DFDs show data movement, not how things are done.
    - Level 0 = big picture, Level 1 = more details.
    - Useful for planning, explaining, and documenting systems.
    
### Structure Chart:

- A structure chart is a simple diagram that shows how a software system is broken into smaller parts called modules. It looks like a tree, with the main module at the top and submodules below it.
- Each box in the chart represents a module (a part of the program that does a specific job).
- Lines connect modules to show which modules call (use) other modules. The flow goes from top (main module) to bottom (submodules).
- Structure charts help programmers see how the system is organized, plan the code, and understand which parts depend on others. This makes building and fixing the software easier.

- **Key Points:**
    - Shows the overall structure of the system.
    - Makes it easy to see which modules work together.
    - Helps divide work among programmers.
    - Useful for designing, coding, and maintaining software.

        - **Simple Example Diagram:**

            ```
            +-------------------+
            |   Main Module     |
            +-------------------+
                         /      \
                        /        \
            +-----------+  +-----------+
            | Module A  |  | Module B  |
            +-----------+  +-----------+
                     |              |
            +-----------+  +-----------+
            |Module A1  |  |Module B1  |
            +-----------+  +-----------+
            ```

            - The "Main Module" calls "Module A" and "Module B".
            - "Module A" calls "Module A1".
            - "Module B" calls "Module B1".

        - In real systems, there can be many levels and modules, but the idea stays the same: show how everything is connected in a simple, easy-to-understand way.

- **Entity Relationship Diagram (ER Diagram):**
  - An ER diagram is used to design databases. It shows entities (like Student, Course) and relationships (like "enrolls in") between them. Entities are rectangles, relationships are diamonds, and attributes are ovals.
  - ER diagrams help organize data and make sure the database structure matches real-world needs.

---

## SRS Document & IEEE Standards for SRS

- **Software Requirements Specification (SRS):**
  - SRS is a document that completely describeswhat the proposed s/w should do without describing how the software will do it.
  - An SRS is a detailed document that lists all the requirements for a software system. It helps developers know what to build and users know what to expect.
  - A good SRS is clear, complete, and easy to understand. It includes sections like Introduction, Overall Description, Specific Requirements, and Appendices.
- **IEEE Standards for SRS:**
  - IEEE 830 is a standard that guides how to write an SRS. It helps make SRS documents organized and professional, so everyone understands the requirements.

---

## Software Quality Assurance (SQA), SEI-CMM, ISO 9000

**2024, Sec C: What is software quality assurance? What are the various quality concepts of SQA? Explain.**

- **Software Quality Assurance (SQA):**

  - SQA is a set of activities to make sure software meets quality standards and works as expected. It includes planning, checking, and improving software quality throughout the project.

  - **Quality Concepts:**
    1. **Verification:** Making sure the software is built correctly ("Are we building the product right?"). This means checking if the software follows the design and requirements.
    2. **Validation:** Making sure the software solves the user's problem and works in real life ("Are we building the right product?").
    3. **Quality Frameworks:** Organized ways to ensure quality, like ISO 9000 and SEI-CMM.
    4. **SQA Plans:** Documents that describe how quality will be managed and checked during the project.

**2020, Sec C: Explain the CMM with the help of diagram. Differentiate between ISO and CMM.**  
**2021, Sec C: Describe the levels of CMM.**  
**2024, Sec A: List the process maturity levels in SEI’s CMM.**  
**2020, Sec C: Explain the CMM with the help of diagram. Differentiate between ISO and CMM.**

---

### SEI-CMM (Capability Maturity Model)

- **Definition:**  
    The Capability Maturity Model (CMM) is a framework developed by the Software Engineering Institute (SEI) to assess and improve the maturity of software development processes in organizations. It provides a structured way to move from ad-hoc, chaotic processes to disciplined, mature processes that deliver high-quality software.

- **Purpose:**  
    - Helps organizations evaluate their current software process maturity.
    - Guides step-by-step improvement of processes.
    - Reduces risks, improves quality, and increases productivity.

---

#### **Levels of CMM (Process Maturity Levels in SEI’s CMM):**

1. **Initial (Level 1):**
     - Processes are unpredictable, poorly controlled, and reactive.
     - Very few or no processes are defined and followed.
     - Since software production processes are not defined, different engineers follow their own process and as a result development efforts become chaotic
     - The success of projects depends on individual efforts. 

2. **Repeatable (Level 2):**
     - At this level, the basic project management practices such as tracking cost and schedule are established.
     - Past successes can be repeated on similar projects.
     - Planning and tracking are introduced.

3. **Defined (Level 3):**
     - At this level the processes for both management and development activities are defined and documented.
     - Processes are documented, standardized, and integrated into a standard process for the organization.
     - All projects use approved, tailored versions of these processes.

4. **Managed (Level 4):**
     - Processes are measured and controlled using quantitative metrics.
     - Detailed understanding of process performance is achieved.
     - **Two types of metrics are collected:**
      - **Product Metrics:** Measure characteristics of the product being developed, such as size, reliability, time complexity, and understandability.
      - **Process Metrics:** Reflect the effectiveness of the process being used, such as average defect correction time, productivity, average number of defects found per hour of inspection, and average number of failures detected during testing per lines of code (LOC).

5. **Optimizing (Level 5):**
     - Focus on continuous process improvement.
     - Innovative ideas and technologies are adopted to improve processes.
     - Such an organization organization identifies identifies the bestsoftware engineering practices andinnovations which may be tools, methods, or processes

---

#### **Diagram: CMM Staircase**

```
     +-------------------+
     |   Level 5         |  Optimizing
     +-------------------+
                     ^
     +-------------------+
     |   Level 4         |  Managed
     +-------------------+
                     ^
     +-------------------+
     |   Level 3         |  Defined
     +-------------------+
                     ^
     +-------------------+
     |   Level 2         |  Repeatable
     +-------------------+
                     ^
     +-------------------+
     |   Level 1         |  Initial
     +-------------------+
```

![CMM Levels Diagram](https://geekflare.com/wp-content/uploads/2023/03/cmm-levels.png)

- Each step represents a higher maturity level, with improved processes and better results.

---

#### **Key Points and Subpoints:**

- **Benefits of CMM:**
    - Provides a roadmap for process improvement.
    - Helps organizations deliver software on time and within budget.
    - Improves product quality and customer satisfaction.

- **Application:**
    - Used by software organizations to assess and improve their development processes.
    - Basis for other models like CMMI (Capability Maturity Model Integration).

---


- **ISO 9000:**

  - ISO 9000 is a set of international standards for quality management. It helps organizations make sure their products and services meet customer needs and regulations. ISO 9000 applies to all industries, not just software.

#### **Difference between ISO and CMM:**

| Aspect                | ISO 9000                                      | CMM (Capability Maturity Model)                   |
|-----------------------|-----------------------------------------------|---------------------------------------------------|
| Focus                 | Quality management for all industries         | Software process improvement                      |
| Industry Applicability| Applies to manufacturing, services, software  | Primarily for software organizations              |
| Approach              | Sets standards for quality systems            | Defines maturity levels for process improvement   |
| Certification         | Organizations can be certified                | Organizations are assessed, not certified         |
| Scope                 | Covers entire organization’s quality system   | Focuses on software development processes         |
| Structure             | Series of standards (ISO 9001, 9002, etc.)    | Five maturity levels (Initial to Optimizing)      |
| Documentation         | Requires documented procedures and records    | Requires defined and measured processes           |
| Audit/Assessment      | External audits for certification             | Appraisals for maturity level determination       |
| Improvement           | Emphasizes consistency and compliance         | Emphasizes continuous process improvement         |
| Global Recognition    | Internationally recognized standard           | Widely used in software industry                  |

---

- **Summary:**  
    SEI-CMM helps organizations improve their software development processes through five maturity levels, each building on the previous one. ISO 9000 focuses on quality management for all industries, while CMM is specific to software process improvement.


**2021, Sec C: Differentiate between Validation and Verification of a Software Product.**

**Validation vs. Verification of a Software Product:**

| Aspect            | Verification                                   | Validation                                    |
|-------------------|------------------------------------------------|-----------------------------------------------|
| Definition        | Checks if software meets specified requirements | Checks if software fulfills user needs        |
| Focus             | "Are we building the product right?"           | "Are we building the right product?"          |
| Timing            | Done during development                        | Done after development                        |
| Methods           | Reviews, inspections, walkthroughs, testing    | User acceptance testing, field trials         |
| Basis             | Based on design documents and specifications   | Based on actual user requirements             |
| Responsibility    | Developers and testers                         | End users and stakeholders                    |
| Output            | Detects errors in design and implementation    | Detects gaps in meeting user expectations     |
| Nature            | Objective, technical                           | Subjective, user-oriented                     |
| Frequency         | Performed throughout development               | Performed at the end or after major releases  |
| Goal              | Ensure correctness and completeness            | Ensure usefulness and satisfaction            |
