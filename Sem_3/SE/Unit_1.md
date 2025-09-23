# Software Engineering: Detailed Notes

## Introduction to Software

**2020 SECTION B Q2(a): What is software? Explain characteristics of software.**

**Answer:**
Software is a collection of programs, procedures, and related documentation that enables computers to perform specific tasks. It acts as an interface between the user and the hardware. Software is intangible (cannot be touched) and is developed by writing code, not by assembling physical parts.

## Software Characteristics

**2020 SECTION B Q2(a): What is software? Explain characteristics of software.**
**2021 SECTION A Q1(a): What are the characteristics of the software?**

**Answer:**
Characteristics of software include:

1. **Intangible (cannot be touched):** Software is not a physical product.
2. **Developed, not manufactured:** Software is created by writing code, not by assembling parts.
3. **Easy to modify:** Changes can be made easily compared to hardware.
4. **No wear and tear:** Software does not degrade physically over time.
5. **Customizable:** Can be tailored to meet specific user needs.
6. **Complexity:** Software can be very complex, with millions of lines of code.
7. **Functionality:** Software provides specific functions to solve problems or perform tasks.
8. **Reusability:** Parts of software (modules) can be reused in other programs.
9. **Quality depends on design:** Good design leads to reliable and efficient software.

## Software Components

**Answer:**
Software components are the individual parts or modules that make up a software system. Each component performs a specific function and can interact with other components.

**Examples of Software Components:**

- **User Interface (UI):** The part users interact with.
- **Database:** Stores and manages data.
- **Business Logic:** The rules and calculations that drive the software.
- **Data Access Layer:** Connects the software to databases or files.
- **Utility Components:** Provide supporting functions (like logging, error handling).

## Software Crisis

**2023 SECTION A Q1(a): List 2 reasons for software crisis.**

**Answer:**
The software crisis refers to the problems faced during the development and maintenance of software, especially as systems became larger and more complex.

Two reasons for software crisis:

1. **Increasing complexity:** Software systems became too large and complicated to manage easily.
2. **Poor quality and reliability:** Many software projects failed to meet user needs or had frequent errors (bugs).

Other reasons include projects running over budget or time, difficulty in maintaining and updating software, and lack of skilled professionals.

## Introduction to Software Engineering

**2023 SECTION A Q1(b): "Software is developed or engineered; it is not manufactured in classical sense". Explain.**

**Answer:**
Unlike physical products (like cars or phones), software is not made by assembling parts in a factory. Software is created by designing and writing code, which is a creative and intellectual process. Each software product can be unique, and changes can be made easily without physical constraints. There is no physical production line; instead, software is built through planning, designing, coding, and testing.

**2024 SECTION B Q2(a): What is software engineering? Explain the layered approach to software engineering.**

**Answer:**

Software engineering is the process of designing, building, and maintaining computer programs.
It uses rules and methods to make sure software works well.
The goal is to create reliable, easy-to-use programs.
It combines coding, planning, and problem-solving.

**Layered Approach to Software Engineering:**
Software engineering uses a layered approach, which means it is organized into different levels or layers:

1. **Quality Focus:**

- Every organization rest on its commitment to quality.
- There are many Quality attributes of software(Correctness, Usability, Integrity, Maintainability
  etc.)

2. **Process Layer:**

- It defines a framework that includes different activities and tasks.
- In short, it covers all activities, actions and tasks required to be carried out for software development

3. **Methods Layer:** Provides technical methods for tasks (like coding, modeling, analysis).  
   Methods are like instructions or techniques for doing each task.  
   They help developers solve problems and build software correctly.

4. **Tools Layer:** Software tools that help automate and support the process and methods (like IDEs, testing tools).  
   Tools make work faster and easier by handling repetitive tasks.  
   Examples include code editors, testing programs, and project management software.

## Software Engineering Processes

**Answer:**
A software engineering process is a set of activities and steps followed to develop software. It helps ensure that software is built in a structured and efficient way.

**Main Processes:**

1. **Requirement Analysis:** Understanding what the user needs.
2. **Design:** Planning how the software will work and look.
3. **Implementation (Coding):** Writing the actual code.
4. **Testing:** Checking for errors and making sure the software works as expected.
5. **Deployment:** Releasing the software for use.
6. **Maintenance:** Updating and fixing the software after release.

## Similarity and Differences from Conventional Engineering Processes

**2020 SECTION C Q3(a): Differentiate between software engineering and traditional engineering.**
**2022 SECTION C Q3(a): What are the major differences between System Engineering and Software Engineering?**

**Answer:**
| Aspect | Software Engineering | Conventional Engineering (System Engineering) |
|-----------------------|---------------------------------------|-----------------------------------------------|
| Product Nature | Intangible (cannot be touched) | Tangible (physical products) |
| Changes | Easy to modify and update | Harder to change once built |
| Production | Developed by coding | Manufactured in factories |
| Wear and Tear | No physical wear | Physical wear over time |
| Complexity | Can be highly complex | Usually less complex than large software |
| Reusability | Modules can be reused easily | Parts may not be reusable |
| Cost of Change | Low | High |
| Testing | Can be automated | Often manual and physical |
| Maintenance | Frequent updates possible | Maintenance is physical and less frequent |

Major differences:

- Software engineering deals with logic and code, while system engineering deals with physical systems.
- Software can be distributed instantly (like downloads), but physical products need shipping.
- Errors in software can be fixed quickly; physical errors may need expensive repairs.

## Software Quality Attributes

**Definition:**
Software quality attributes are the features or properties that determine how good software is. These attributes help measure the performance, reliability, and usability of software.

**Key Software Quality Attributes:**

1. **Reliability:** The ability of software to perform its required functions under stated conditions for a specified period (works correctly without failing).
2. **Usability:** How easy it is for users to learn and use the software (user-friendly).
3. **Efficiency:** How well software uses system resources (like memory and CPU) to perform its tasks.
4. **Maintainability:** How easy it is to fix bugs, update, or improve the software.
5. **Portability:** The ability of software to run on different hardware or operating systems without modification.
6. **Functionality:** The range of operations that the software can perform (features provided).
7. **Security:** Protection of software from unauthorized access and threats.
8. **Scalability:** Ability to handle increased workload or users without performance loss.
9. **Testability:** How easily software can be tested to find errors.
10. **Reusability:** (2022 SECTION A) The extent to which parts of the software (modules, code) can be used in other applications or systems.

**2022 SECTION A: What is reusability in Software Engineering?**

- Reusability means using existing software components in new applications, which saves time and effort, improves reliability, and reduces cost.

---

## Software Development Life Cycle (SDLC)

**What is SDLC?**

SDLC stands for Software Development Life Cycle. It is a step-by-step process that software developers follow to create software applications. Think of it like a recipe for making software - it tells you what to do first, second, third, and so on.

**Why do we need SDLC?**

- Makes software development organized and systematic
- Helps avoid mistakes and confusion
- Ensures quality software is produced
- Helps manage time and money better
- Makes it easier for teams to work together

**SDLC Steps in Detail:**

### **1. Planning and Requirement Analysis**

**What it means:** Understanding what the customer wants and planning the project.

**Activities:**

- Talk to customers to understand their needs
- Write down all requirements clearly
- Study if the project is possible (feasibility study)
- Plan budget, time, and resources needed

**Example:** A school wants software to manage student records. In this step, we ask questions like:

- What information about students do you want to store?
- Who will use this software?
- How many students will it handle?
- What is your budget?

### **2. System Analysis and Design**

**What it means:** Planning how the software will work and look.

**Activities:**

- Create the software architecture (overall structure)
- Design user interfaces (screens that users will see)
- Plan the database (where data will be stored)
- Decide what technology to use

**Example:** For the school software, we design:

- Login screen for teachers and admin
- Student registration form
- Report generation screens
- Database tables for student information

### **3. Implementation (Coding/Development)**

**What it means:** Actually writing the computer code to build the software.

**Activities:**

- Write code in programming languages (like Java, Python, etc.)
- Create database structures
- Build user interfaces
- Connect different parts of the software

**Example:** Programmers write code to:

- Create login functionality
- Build forms to add new students
- Program report generation features
- Set up the database

### **4. Testing**

**What it means:** Checking if the software works correctly and finding errors (bugs).

**Activities:**

- Test individual parts (unit testing)
- Test how parts work together (integration testing)
- Test the complete system (system testing)
- Let users test it (user acceptance testing)

**Example:** For school software, test:

- Can users login correctly?
- Does student registration work?
- Are reports generated properly?
- Can multiple users use it at the same time?

### **5. Deployment (Installation)**

**What it means:** Installing the software where it will be used.

**Activities:**

- Install software on user computers/servers
- Set up databases
- Train users how to use the software
- Provide user manuals

**Example:**

- Install the school software on school computers
- Train teachers and office staff
- Provide help documentation

### **6. Maintenance**

**What it means:** Keeping the software working and improving it over time.

**Activities:**

- Fix bugs found after deployment
- Add new features as requested
- Update software for security
- Provide technical support

**Example:**

- Fix any problems teachers report
- Add new features like parent login
- Update for new academic year requirements
- Provide help when users have questions

**Real-World Example: Online Shopping Website**

1. **Planning:** Understand customer needs - they want to buy products online
2. **Design:** Plan website layout, shopping cart, payment system
3. **Coding:** Build the website with product pages, cart functionality, payment processing
4. **Testing:** Check if users can browse, add items to cart, and make payments
5. **Deployment:** Launch the website for public use
6. **Maintenance:** Fix bugs, add new products, update security features

**Simple Summary:**
SDLC is like building a house - you first plan what you want, design it, build it step by step, check if everything works, move in, and then maintain it over time.

## Software Development Life Cycle (SDLC) Models

#### **PYQ**

- **2022 SECTION B** - Explain the need of Software life cycle models in Software Engineering.
- **2024 SECTION C** - Explain the need of software life cycle models in Software Engineering.

### Need for Software Life Cycle Models

SDLC (Software Development Life Cycle) models are important because they provide a clear, step-by-step way to build software. These models show the order of activities, from planning and designing to coding, testing, and maintaining the software.

**Why do we need SDLC models?**

- **Organized Process:** SDLC models help teams follow a structured process, so everyone knows what to do and when. This reduces confusion and makes teamwork easier.
- **Quality Assurance:** They make sure the software is high quality and meets what users want. Each step includes checks to catch mistakes early.
- **Error Reduction:** By following steps, teams can avoid mistakes and find problems early. Testing is done at different stages to make sure everything works.
- **Time and Cost Management:** SDLC models help save time and money by planning work and resources well. Teams can estimate how long each step will take and how much it will cost.
- **Easy Project Management:** They make it easier to manage big projects and track progress. Managers can see which step the project is in and what needs to be done next.
- **Clear Documentation:** SDLC models require teams to write down requirements, designs, and plans. This helps everyone understand the project and makes future updates easier.
- **Risk Management:** By planning each step, teams can find risks early and solve them before they become big problems.
- **Customer Satisfaction:** SDLC models involve users at different stages, so their feedback can be included. This makes sure the final software meets their needs.

---

### Waterfall Model

**PYQ**

- **2020 SECTION C** - Discuss the Waterfall Model with advantages and disadvantages.
- **2021 SECTION B** - Write the advantages and disadvantages of classic waterfall life cycle model?
- **2022 SECTION A** - Write two advantages of Waterfall model of Software life cycle.
- **2022 SECTION C** - Explain Water fall Model. What are the problems that are sometimes encountered when the waterfall model is applied?
- **2024 SECTION C** - What is waterfall model? Describe the activities of waterfall model and also mention its drawbacks

**Definition:**

The Waterfall Model is a basic way to make software by following a series of steps, one after another. You must finish each step before moving to the next. It is called "waterfall" because the process flows downwards, like water falling from one level to the next.

In this model, you start by finding out what the user wants (requirements), then plan how the software will work (design), write the code (implementation), check for mistakes (testing), give the software to users (deployment), and finally fix problems or make updates (maintenance). You cannot go back to a previous step easily, so it works best when everything is clear from the beginning.

The Waterfall Model is easy to understand and manage, but it is not flexible if changes are needed later.

**Steps in Waterfall Model:**

1. **Requirement Analysis:**

   - Find out what the user wants.
   - Write down all requirements.

2. **System Design:**

   - Plan how the software will work.
   - Decide what parts are needed.

3. **Implementation (Coding):**

   - Write the code for the software.

4. **Testing:**

   - Check for mistakes (bugs).
   - Make sure everything works.

5. **Deployment:**

   - Give the software to users.

6. **Maintenance:**
   - Fix problems and update the software.

**Advantages:**

- Easy to understand and use.
- Each step is clear and organized.
- Good for small projects with clear goals.
- Simple to manage.

**Disadvantages:**

- Not flexible; hard to go back to earlier steps.
- Not good if requirements change often.
- Mistakes may be found late (during testing).
- Users see the software only at the end.

**Code space for image:**

```
![Waterfall Model Diagram](https://media.geeksforgeeks.org/wp-content/uploads/20231030183557/waterfall.jpg)
```

---

### Prototype Model

**PYQ**

- **2021 SECTION A** - What are the benefits of prototyping?
- **2023 SECTION B** - Discuss the prototype model. What is the effect of designing a prototype on the overall cost of the software project?

The Prototype Model is a way to build software by first making a simple version called a "prototype." This prototype shows the basic look and features of the software. Users try out the prototype and tell the developers what they like, what needs to change, and what is missing. The developers then improve the prototype based on this feedback. This process is repeated several times until everyone is happy and the requirements are clear. After that, the final software is built using what was learned from the prototype.

This model is helpful when it is hard to know exactly what users want at the beginning. By letting users see and use early versions, their needs and ideas become clearer, and the final software is more likely to meet their expectations.

**Steps in Prototype Model:**

1. Gather basic requirements.
2. Build a quick prototype.
3. Show it to users and get feedback.
4. Improve the prototype.
5. Build the final software.

**Benefits:**

- Helps users explain what they want.
- Users see and use the software early.
- Reduces mistakes about requirements.
- Makes users happier with the final product.

**Effect on Cost:**

- Making a prototype costs more at first.
- But it saves money later by avoiding big changes and mistakes.

**Code space for image:**

```
![Prototype Model Diagram](https://i.ytimg.com/vi/fWEZFH8lwag/maxresdefault.jpg)
```

---

### Spiral Model

**PYQ**
**2023 SECTION C** - What is Software development life cycle? Discuss the process for Spiral model.

**Definition:**  
The Spiral Model mixes the Waterfall and Prototype models. It repeats steps in cycles (spirals). Each cycle adds more features and checks for risks.

**Steps in Spiral Model:**

1. **Communication:**

   - Interact with users to gather requirements and understand their needs.

2. **Planning:**

   - Define objectives, identify risks, and plan the next phase.

3. **Modeling:**

   - Design and outline how the software will function.

4. **Construction:**

   - Build and test the software incrementally.

5. **Deployment:**
   - Deliver the software to users, collect feedback, and prepare for the next cycle.

- These steps repeat, making the software better each time.

**Advantages:**

- Good for big and risky projects.
- Finds and fixes problems early.
- Allows changes and feedback during development.

**Code space for image:**

```
![Spiral Model Diagram](https://www.gtu-paper-solution.com/upload/2160701/W2016/Q2B_OR.png)
```

---

### Evolutionary and Iterative Models

#### PYQ

- **2023 SECTION C** - Current trends in Software Engineering are moving away from the waterfall model… Explain.

**Answer:**  
Current trends in Software Engineering favor evolutionary and iterative models over the traditional waterfall model. Unlike the waterfall model, which follows a rigid, linear sequence of steps, evolutionary and iterative models allow software to be developed in small increments, with frequent user feedback and continuous improvement. This approach is more flexible and adaptive to changing requirements, enabling teams to deliver working software quickly, fix issues early, and respond to user needs throughout the development process. Agile and Scrum are popular examples of these modern methods, reflecting the industry's shift toward faster, more responsive software development.

**Definition:**  
These models build software in small steps. Each step adds new features or improves the software. Users can give feedback after each step.

- **Evolutionary Model:**

  - Software grows in stages.
  - Each stage adds new parts.

- **Iterative Enhancement Model:**
  - Software is improved again and again.
  - Each cycle adds changes based on feedback.

**Current Trends:**

- Most teams now use these models because they are flexible.
- Users get working software quickly.
- Mistakes and changes are fixed fast.
- Examples: Agile and Scrum methods.

**Code space for image:**

```
![Evolutionary](https://d8it4huxumps7.cloudfront.net/uploads/images/652f8424328d0_4.jpg?d=2000x2000)
```

## [Iterative Model Diagram](https://codilime.com/img/sdlc-iterative-model-.png)

### V-Model

- The major drawback of waterfall model is we move to the next stage only when the previous one is finished and there was no chance to go back if something is found wrong in later stages.
- V-Model provides means of testing of software at each stage in reverse manner.
- At every stage, test plans and test cases are created to verify and validate the product according to the requirement of that stage.
- This makes both verification and validation go in parallel. This model is also known as verification and validation model.