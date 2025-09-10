# Cloud Computing Notes

## Table of Contents

- [Definition of Cloud Computing](#definition-of-cloud-computing)
- [Evolution of Cloud Computing](#evolution-of-cloud-computing)
- [Underlying Principles of Parallel and Distributed Computing](#underlying-principles-of-parallel-and-distributed-computing)
- [History of Cloud Computing](#history-of-cloud-computing)
- [Characteristics and Features of Cloud Computing](#characteristics-and-features-of-cloud-computing)
- [Cloud Architectures](#cloud-architectures)
- [Business Models Around Clouds](#business-models-around-clouds)
- [Major Players in Cloud Computing](#major-players-in-cloud-computing)
- [Issues in Clouds](#issues-in-clouds)
- [Eucalyptus, Nimbus, OpenNebula, CloudSim](#eucalyptus-nimbus-opennebula-cloudsim)

---

## Definition of Cloud Computing

**PYQ: What do you mean by Cloud Computing? (2023 Section C)**

Cloud Computing means using computer resources (like servers and storage) from a provider over the internet. You can access your files and programs from anywhere, anytime. It is flexible and saves money because you only pay for what you use.

## Evolution of Cloud Computing

Cloud computing did not start suddenly. It grew from older ways of using computers:

- In the 1960s, big computers called mainframes were used by many people at once.
- In the 1980s, client-server computing let smaller computers connect to big servers.
- In the 1990s, grid computing allowed many computers to work together on big problems.
- Utility computing made computer power available like electricity—use as much as you need.
- Today, cloud computing lets you use computer resources over the internet, easily and quickly.

Cloud computing started with ideas from the 1960s. Over time, new ways to share computer power were invented. In 2006, Amazon started Amazon Web Services (AWS), which made cloud computing popular. Now, many companies use cloud computing for their work.

---

## Underlying Principles of Parallel and Distributed Computing

**PYQ: 2024 Section A: Compare parallel computing and distributed computing.**
**PYQ: 2023 Section A: Explain underlying principles of parallel and distributed computing.**
**PYQ: 2021 Section A: Differentiate between Cloud computing and Distributed computing.**
**PYQ: 2018 Section A: Differentiate between Grid Computing and Distributed computing.**

Cloud computing works because of two main ideas:

- **Parallel Computing:** This principle involves multiple processors or computers working on different parts of a problem at the same time. Tasks are divided into smaller pieces and processed simultaneously, which speeds up computation and improves performance. Parallel computing is useful for handling large-scale data processing and scientific simulations.

- **Distributed Computing:** In distributed computing, computers located in different places are connected through a network and collaborate to complete tasks. Each computer (node) shares resources and workload, increasing reliability and scalability. If one node fails, others can continue working, making the system fault-tolerant.

These principles allow cloud computing to:

- Handle lots of users and big jobs
- Be available all the time (high availability)
- Grow or shrink as needed (scalability)

### Difference Table: Parallel vs Distributed Computing

| Point | Parallel Computing                          | Distributed Computing                                 |
| ----- | ------------------------------------------- | ----------------------------------------------------- |
| 1     | Uses many processors in one computer        | Uses many computers connected by a network            |
| 2     | All processors share memory                 | Each computer has its own memory                      |
| 3     | Works on one big problem together           | Each computer can work on different problems          |
| 4     | Fast communication between processors       | Communication is slower over a network                |
| 5     | Easier to manage (one system)               | Harder to manage (many systems)                       |
| 6     | Good for tasks needing lots of calculations | Good for tasks needing sharing of resources           |
| 7     | If one processor fails, others may stop     | If one computer fails, others keep working            |
| 8     | Used in supercomputers                      | Used in cloud computing and web services              |
| 9     | Needs special hardware                      | Can use normal computers                              |
| 10    | All processors are close together           | Computers can be far apart (even in different cities) |

---

## Characteristics and Features of Cloud Computing

Cloud computing has many special features that make it useful and popular.

**PYQ: List out and discuss the innovative characteristics of cloud computing. (2024 Section C)**
**PYQ: Explain several properties & characteristics exhibited by Cloud Computing. (2022 Section C)**
**PYQ: Describe the characteristics of cloud computing environments. (2018 Section B)**
**PYQ: State the basic features of cloud computing. (2021 Section A)**

### Main Characteristics

1. **On-demand self-service:** Computer resources are available whenever needed, without requiring human interaction with the service provider.
2. **Broad network access:** Cloud services are accessible from various devices such as phones, tablets, or computers, over the internet.
3. **Resource pooling:** Multiple users share the same resources, with each user receiving the required allocation.
4. **Rapid elasticity:** Resources can be quickly added or removed as demand changes.
5. **Measured service:** Usage is monitored and billed based on consumption, similar to utilities like water or electricity.
6. **Scalability:** The cloud infrastructure can efficiently handle varying workloads.
7. **Reliability:** Services are highly available and capable of recovering from failures.
8. **Security:** Data is protected and privacy is maintained.
9. **Cost efficiency:** Expensive hardware purchases are avoided, reducing overall costs.
10. **Flexibility:** Services can be accessed from any device and location.

---

## Cloud types

Cloud computing uses different ways to organize and deliver services. These are called cloud architectures.

**PYQ: Discuss any one of the cloud . (2023 Section C)**

### Types of Cloud 

#### 1. Public Cloud

- **Definition:** Public cloud means services are offered to anyone over the internet. Anyone can sign up and use these services.
- **Points:**
  - Managed by companies like Amazon, Google, or Microsoft.
  - You do not own the hardware; the provider takes care of everything.
  - You pay only for what you use, like renting space or computer power.
  - Good for small businesses or people who want to start quickly.
  - Example: Amazon Web Services (AWS), Google Cloud Platform.

#### 2. Private Cloud

- **Definition:** Private cloud is used by one company or group. The services are not shared with others.
- **Points:**
  - Managed by the company itself or by a special provider.
  - More control over security and data.
  - Can be set up in the company’s own building or at a provider’s place.
  - Good for big companies with strict rules about data.
  - Example: A bank using its own cloud for customer data.

#### 3. Hybrid Cloud

- **Definition:** Hybrid cloud is a mix of public and private clouds. It shares data and applications between them.
- **Points:**
  - Lets you keep important data in the private cloud and use public cloud for other tasks.
  - More flexibility and better use of resources.
  - Can save money and improve security.
  - Good for companies that want both privacy and the power of public cloud.
  - Example: A hospital storing patient records privately but using public cloud for email.

#### 4. Community Cloud

**PYQ Section A**

- **Definition:** Community cloud is shared by several organizations with similar needs.
- **Points:**
  - Managed by the organizations or a third party.
  - Used by groups like schools, hospitals, or government offices.
  - Helps share costs and resources.
  - Good for organizations with common goals or rules.
  - Example: Universities sharing a cloud for research data.

---

## Business Models Around Clouds

Cloud computing supports different business models, which means companies use the cloud in different ways to make money or save costs. Here are some common models:

### Common Cloud Business Models

#### 1. Software as a Service (SaaS)
- **Definition:** Software is delivered over the internet. Users access applications through a web browser, without installing anything locally.
- **Features:**
    - No need to manage hardware or software updates.
    - Pay-as-you-go or subscription pricing.
    - Accessible from any device with internet.
- **Examples:** Google Docs, Microsoft Office 365, Salesforce.
- **Benefits:**
    - Easy collaboration and sharing.
    - Automatic updates and maintenance.
    - Lower upfront costs.

#### 2. Platform as a Service (PaaS)
- **Definition:** Provides a platform for developers to build, test, and deploy applications. The provider manages infrastructure, operating systems, and runtime environments.
- **Features:**
    - Includes tools for coding, testing, and deploying.
    - Scalable resources for applications.
    - Supports multiple programming languages.
- **Examples:** Google App Engine, Microsoft Azure, Heroku.
- **Benefits:**
    - Faster development and deployment.
    - No need to manage servers or operating systems.
    - Built-in scalability and security.

#### 3. Infrastructure as a Service (IaaS)
- **Definition:** Offers virtualized computing resources like servers, storage, and networking over the internet. Users control operating systems and applications.
- **Features:**
    - Flexible and scalable hardware resources.
    - Pay only for what you use.
    - Full control over the infrastructure.
- **Examples:** Amazon Web Services (AWS), Google Cloud Platform, Microsoft Azure.
- **Benefits:**
    - No need to buy physical hardware.
    - Easily scale up or down as needed.
    - Suitable for hosting websites, databases, and custom applications.

---

## Major Players in Cloud Computing

Many companies provide cloud services. The biggest ones are:

- **Amazon Web Services (AWS):** Offers many cloud services like storage, computing, and databases. (PYQ: Write short notes on Amazon Web Services. 2021 Section C)
- **Microsoft Azure:** Provides cloud solutions for businesses and developers.
- **Google Cloud Platform:** Offers cloud services for data storage, computing, and machine learning.
- **IBM Cloud:** Focuses on business and AI solutions.
- **Alibaba Cloud:** Popular in Asia for cloud services.
---

## Issues in Clouds

Cloud computing has some challenges and issues:

1. **Security:** Protecting data from hackers and unauthorized users.
2. **Privacy:** Keeping personal and sensitive information safe.
3. **Downtime:** Cloud services may stop working sometimes, causing interruptions.
4. **Data Loss:** There is a risk of losing files if something fails.
5. **Compliance:** Following rules and laws about storing and handling data.
6. **Vendor Lock-in:** It can be hard to switch from one cloud provider to another.
7. **Limited Control:** Users have less control over hardware and software.
8. **Internet Dependency:** Cloud services need a good internet connection to work.
9. **Hidden Costs:** Extra charges may appear for storage, data transfer, or special features.
10. **Performance Issues:** Sometimes cloud services can be slow if many people use them at once.

---

## Eucalyptus, Nimbus, OpenNebula, CloudSim

### Eucalyptus

Eucalyptus is a free, open-source software that helps companies build their own cloud systems. It is mainly used for creating private clouds (for one company) or hybrid clouds (mix of private and public). Eucalyptus lets organizations set up cloud services similar to Amazon Web Services (AWS), but with more control over their own data and resources.

**Key Points:**
- **Open-source:** Anyone can use and change the software for free.
- **IaaS Support:** Eucalyptus provides Infrastructure as a Service, which means users can get virtual machines, storage, and networks on demand.
- **AWS Compatibility:** It works with tools and services from AWS, so companies can use both Eucalyptus and AWS together.
- **Security and Control:** Organizations can keep their data safe and manage their own cloud setup.
- **Scalability:** Eucalyptus can grow or shrink as needed, handling more users or bigger workloads.

**How it Works:**
Eucalyptus lets you create virtual computers (VMs), store files, and manage networks, all inside your own company. You can add or remove resources easily, and only pay for what you use if you connect to public clouds.

---

### Nimbus

Nimbus is another open-source toolkit for building cloud computing environments. It is popular in universities and research labs because it helps scientists and researchers run experiments using virtual machines on remote computers.

**Key Points:**
- **Open-source and Free:** Anyone can use Nimbus without paying.
- **Virtual Machine Management:** Users can create, start, stop, and manage virtual machines easily.
- **Customizable:** Nimbus can be changed and adapted to fit different needs.
- **Integration:** It works with other cloud tools and systems.
- **Focus on Science:** Designed for research and scientific computing.

**Features of Nimbus (PYQ 2023 Section A):**
- Easy to set up and use for managing virtual machines.
- Supports scientific and research projects.
- Can be connected with other cloud platforms.
- Flexible and can be customized for different users.

**Nimbus Architecture (PYQ 2022 Section C):**
Nimbus has several important parts:
- **Cloud Client:** The tool that users use to access and control the cloud.
- **Workspace Service:** Manages virtual machines and resources.
- **Resource Pool:** A group of computers or virtual machines that provide the computing power.
- **Context Broker:** Helps set up and configure virtual machines.
- **Other Components:** Includes security, monitoring, and networking tools.

| Component         | Meaning (Simple English)               |
| ----------------- | -------------------------------------- |
| Cloud Client      | Tool for users to access the cloud     |
| Workspace Service | Manages virtual machines and resources |
| Resource Pool     | Group of computers or VMs              |
| Context Broker    | Sets up and configures VMs             |

Nimbus helps researchers run experiments without needing expensive hardware. They can use remote computers and test their ideas easily.

---

### OpenNebula

OpenNebula is a free, open-source platform that helps companies and organizations manage their own data centers and private clouds. It is used by businesses, universities, and research labs to control their cloud infrastructure.

**Key Points:**
- **Open-source:** Free to use and change.
- **Data Center Management:** Helps manage servers, storage, and networks in one place.
- **Virtualization:** Lets users create and control virtual machines.
- **Automation:** Many tasks can be automated, saving time and effort.
- **Scalability:** Can handle small or large setups, growing as needed.
- **User Control:** Organizations have full control over their cloud and data.

**How it Works:**
OpenNebula lets users create virtual computers, store files, and manage networks. It supports different types of virtualization (like VMware, KVM, and Xen) and can connect with public clouds if needed. It is easy to use and helps companies save money by using their own hardware.

---

### CloudSim

CloudSim is a toolkit used by researchers and students to simulate cloud computing environments. Instead of using real computers and networks, CloudSim lets users create models and test how cloud systems would work.

**Key Points:**
- **Simulation Tool:** CloudSim is not a real cloud, but a program for testing ideas.
- **Open-source:** Free to use for anyone.
- **Performance Testing:** Users can see how cloud resources (like servers and storage) work under different conditions.
- **Cost and Resource Management:** Helps study how much resources are needed and how much it might cost.
- **Saves Money and Time:** No need to buy expensive hardware for experiments.

**How it Works:**
Researchers use CloudSim to create models of cloud systems. They can change settings, add users, and test different scenarios. This helps them understand how real clouds would behave, find problems, and improve designs before building actual systems.

**PYQ: Write short notes on CloudSim (2021 Section C):**
- CloudSim lets users create models of cloud systems.
- It helps test how cloud resources work under different conditions.
- Saves money and time by avoiding real-world experiments.

---

These four tools—Eucalyptus, Nimbus, OpenNebula, and CloudSim—are important for building, managing, and testing cloud computing systems. They help organizations and researchers use cloud technology in safe, flexible, and cost-effective ways.

---
