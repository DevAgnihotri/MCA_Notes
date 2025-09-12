# Computer Networks Unit 1 Notes

## Table of Contents

- [Data Communications](#data-communications)
- [Networks and Classification](#networks-and-classification)
- [Network Topologies](#network-topologies)
- [Protocols and Standards](#protocols-and-standards)
- [Network Connecting Devices](#network-connecting-devices)
- [Transmission Media](#transmission-media)

---

## Data Communications

### Introduction to Data Communication

**What is Data Communication?**

Data communication is the process of sending and receiving data (information) between two or more devices through a transmission medium (pathway for data). This allows computers and other devices to share information over short or long distances.

### Components of Data Communication System

**PYQ: List out components of data communication system. (2023, Section A)**

A data communication system has five main components:

1. **Message:** The information or data that needs to be sent (text, images, videos, etc.)
2. **Sender:** The device that sends the message (computer, phone, etc.)
3. **Receiver:** The device that receives the message (another computer, phone, etc.)
4. **Transmission Medium:** The pathway through which data travels (cables, wireless signals)
5. **Protocol:** Rules and standards that control how data is sent and received (like traffic rules for data)

| Component | Simple Meaning      | Example              |
| --------- | ------------------- | -------------------- |
| Message   | Information to send | Email, photo, video  |
| Sender    | Device sending data | Your computer        |
| Receiver  | Device getting data | Friend's computer    |
| Medium    | Path for data       | Internet cable, WiFi |
| Protocol  | Rules for sending   | HTTP, TCP/IP         |

### Characteristics of Data Communication

- **Accuracy:** Data should reach without errors
- **Timeliness:** Data should arrive on time
- **Delivery:** Data should reach the correct destination
- **Jitter:** Delay between data packets should be minimal

### Data Representation

Data can be represented in different forms:

- **Analog:** Continuous signals (like sound waves)
- **Digital:** Discrete signals (0s and 1s)

### Data Flow

Data can flow in three ways:

- **Simplex:** Data can only move in one direction. One device always sends, and the other always receives. For example, a radio station sends music, and your radio only receives it. You cannot send anything back to the radio station.
- **Half-duplex:** Data can move in both directions, but not at the same time. Devices take turns to send and receive information. For example, with a walkie-talkie, you have to press a button to talk, and then let go to listen. Only one person can talk at a time.
- **Full-duplex:** Data can move in both directions at the same time. Both devices can send and receive information together. For example, during a phone call, you and your friend can talk and listen at the same time without waiting for the other to stop.

---

## Networks and Classification

### What is a Network?

**PYQ: What is Network? Explain different types of Networks. (2019, Section B)**
**PYQ: Discuss network classification based on geographical scale. (2021, Section B)**

A network is a collection of computers and other devices connected together to share resources and information. Networks allow devices to communicate with each other and share files, printers, internet connections, and more.

### Applications of Computer Networks

**PYQ: What are the applications of computer network? (2019, Section A)**

Computer networks have many useful applications:

1. **Resource Sharing:** Share printers, files, and software among multiple users
2. **Communication:** Send emails, messages, and make video calls
3. **Data Storage:** Store data on remote servers (cloud storage)
4. **Internet Access:** Browse websites and use online services
5. **Entertainment:** Stream movies, play online games
6. **Business Operations:** Online banking, e-commerce, remote work
7. **Education:** Online learning, digital libraries
8. **Information Sharing:** Access to databases and research materials

### Types of Networks Based on Geographical Scale

Networks are classified based on their size and coverage area:

### Difference Between LAN, MAN, and WAN

| Feature             | LAN (Local Area Network)          | MAN (Metropolitan Area Network)  | WAN (Wide Area Network)               |
| ------------------- | --------------------------------- | -------------------------------- | ------------------------------------- |
| Coverage Area       | Small (room, building, campus)    | Medium (city, metropolitan area) | Large (country, continent, globe)     |
| Ownership           | Private (single organization)     | Public/private (multiple orgs)   | Public/private (multiple orgs)        |
| Speed               | Very high (100 Mbps – 10 Gbps)    | High (up to 1 Gbps)              | Moderate (1 Mbps – 100 Mbps)          |
| Cost                | Low                               | Medium                           | High                                  |
| Setup Complexity    | Simple                            | Moderate                         | Complex                               |
| Maintenance         | Easy                              | Moderate                         | Difficult                             |
| Example             | Office network, home WiFi         | Cable TV network, city WiFi      | Internet, telephone networks          |
| Transmission Medium | Ethernet cables, WiFi             | Fiber optics, copper cables      | Satellite, fiber optics, leased lines |
| Security            | High (controlled access)          | Moderate                         | Lower (more vulnerable)               |
| Typical Use         | File sharing, printers, LAN games | City-wide services, public WiFi  | Global communication, remote access   |

---

## Network Topologies

### What are Network Topologies?

**PYQ: Explain various network topologies along with their relative advantages and disadvantages. (2021, Section C)**
**PYQ: Discuss various computer network topologies with suitable diagrams. (2023, Section B)**

Network topology refers to the physical or logical arrangement of devices in a network. It shows how computers and other devices are connected to each other.

### Types of Network Topologies

Network topology is the way computers and devices are arranged and connected in a network. Each topology has its own structure, working method, advantages, disadvantages, and examples.

#### 1. Bus Topology

**Definition:**  
All devices are connected to a single central cable called the backbone.

**How it works:**  
Data sent by a device travels along the backbone and is received by all devices. Only the intended device accepts the data.

**Example:**  
Small office networks, early Ethernet networks.

**Advantages:**

- Simple to set up and understand.
- Uses less cable compared to other topologies.
- Cost-effective for small networks.

**Disadvantages:**

- If the backbone cable fails, the whole network stops working.
- Difficult to find and fix problems.
- Limited cable length and number of devices.
- Data collisions can happen when many devices send data at once.

---

#### 2. Star Topology

**Definition:**  
All devices are connected to a central hub or switch.

**How it works:**  
Each device communicates through the central hub. The hub manages and forwards data to the correct device.

**Example:**  
Home WiFi networks, most modern office networks.

**Advantages:**

- Easy to add or remove devices without affecting the network.
- If one cable fails, only that device is affected.
- Simple to troubleshoot problems.
- Good performance for medium-sized networks.

**Disadvantages:**

- If the central hub fails, the whole network goes down.
- Requires more cable than bus topology.
- More expensive due to the cost of the hub or switch.

---

#### 3. Ring Topology

**Definition:**  
Devices are connected in a circular pattern, forming a ring.

**How it works:**  
Data travels in one direction around the ring, passing through each device until it reaches the destination.

**Example:**  
Token Ring networks, some office networks.

**Advantages:**

- Each device has equal access to the network.
- No data collisions because data moves in one direction.
- Can handle high traffic loads.

**Disadvantages:**

- If one device or connection fails, the whole network may stop working.
- Adding or removing devices is difficult.
- Troubleshooting is complex.

---

#### 4. Mesh Topology

**Definition:**  
Every device is connected directly to every other device.

**How it works:**  
Data can take multiple paths to reach its destination, making the network very reliable.

**Example:**  
Internet backbone, military communication networks.

**Advantages:**

- Very reliable; if one connection fails, data can use another path.
- Fast data transmission due to multiple routes.
- Easy to find and fix problems.

**Disadvantages:**

- Very expensive; needs lots of cables and network cards.
- Complex to install and manage.
- Not practical for small networks.

---

#### 5. Tree Topology (Hierarchical Topology)

**Definition:**  
Combines star and bus topologies. Groups of star networks are connected to a main bus backbone.

**How it works:**  
Devices are arranged in a hierarchy, like branches of a tree.

**Example:**  
Large organizations with different departments, school networks.

**Advantages:**

- Easy to expand by adding more branches.
- Can separate and prioritize different parts of the network.
- Supported by many hardware and software vendors.

**Disadvantages:**

- If the backbone fails, the whole network fails.
- More expensive than bus or star topology.
- Wiring and configuration can be complex.

---

#### Comparison Table

| Topology | Reliability | Cost      | Ease of Installation | Performance | Example                 |
| -------- | ----------- | --------- | -------------------- | ----------- | ----------------------- |
| Bus      | Low         | Low       | Easy                 | Moderate    | Small office, labs      |
| Star     | Moderate    | Moderate  | Easy                 | Good        | Home WiFi, offices      |
| Ring     | Moderate    | Moderate  | Moderate             | Good        | Token Ring networks     |
| Mesh     | Very High   | Very High | Difficult            | Excellent   | Internet backbone       |
| Tree     | Moderate    | High      | Moderate             | Good        | School, large companies |

---

All topologies have their own uses, strengths, and weaknesses. Choosing the right topology depends on the size, budget, and needs of the network.

---

## Protocols and Standards

### What are Protocols?

Protocols are rules and standards that define how devices communicate in a network. Think of protocols like traffic rules that help cars move safely on roads. Similarly, protocols help data move safely between computers.

### Need for Layered Architecture

**PYQ: What is need of layered architecture in ISO/OSI model. (2021, Section A)**

Layered architecture breaks down complex network communication into smaller, manageable parts. Each layer has specific responsibilities:

1. **Simplicity:** Complex problems are divided into smaller, easier-to-solve parts
2. **Modularity:** Each layer can be developed and updated independently
3. **Standardization:** Common rules for all manufacturers to follow
4. **Troubleshooting:** Problems can be isolated to specific layers
5. **Flexibility:** Changes in one layer don't affect other layers
6. **Interoperability:** Different devices from different companies can work together

### ISO-OSI Model

**PYQ: Explain responsibilities each layer in ISO/OSI Model with suitable diagrams. (2023, Section C)**

The Open Systems Interconnection (OSI) model has 7 layers. Each layer performs specific functions:

#### Layer 7: Application Layer

- **Purpose:** Interface between user and network
- **Functions:** Provides network services to applications
- **Examples:** Web browsers, email clients, file transfer
- **Protocols:** HTTP, FTP, SMTP, DNS

#### Layer 6: Presentation Layer

- **Purpose:** Data formatting and encryption
- **Functions:** Converts data into readable format, handles encryption/decryption
- **Examples:** JPEG, GIF, SSL encryption
- **Simple meaning:** Translates data so different computers can understand

#### Layer 5: Session Layer

- **Purpose:** Manages communication sessions
- **Functions:** Establishes, maintains, and terminates connections
- **Examples:** SQL sessions, RPC (Remote Procedure Calls)
- **Simple meaning:** Controls conversations between computers

#### Layer 4: Transport Layer

- **Purpose:** Reliable data delivery
- **Functions:** Error detection, flow control, data segmentation
- **Examples:** TCP, UDP
- **Simple meaning:** Makes sure data arrives correctly and completely

#### Layer 3: Network Layer

- **Purpose:** Routing and addressing
- **Functions:** Finds best path for data, logical addressing
- **Examples:** IP, routers
- **Simple meaning:** Decides which route data should take

#### Layer 2: Data Link Layer

- **Purpose:** Node-to-node delivery
- **Functions:** Error detection, MAC addressing, frame formation
- **Examples:** Ethernet, switches, bridges
- **Simple meaning:** Handles data transfer between directly connected devices

#### Layer 1: Physical Layer

- **Purpose:** Physical transmission
- **Functions:** Electrical signals, cables, connectors
- **Examples:** Cables, hubs, repeaters
- **Simple meaning:** The actual wires and signals that carry data

| Layer | Name         | Function              | Device                | Protocol        |
| ----- | ------------ | --------------------- | --------------------- | --------------- |
| 7     | Application  | User interface        | Computer applications | HTTP, FTP       |
| 6     | Presentation | Data formatting       | None specific         | SSL, JPEG       |
| 5     | Session      | Session management    | None specific         | SQL, RPC        |
| 4     | Transport    | Reliable delivery     | Gateway               | TCP, UDP        |
| 3     | Network      | Routing               | Router                | IP              |
| 2     | Data Link    | Local delivery        | Switch, Bridge        | Ethernet        |
| 1     | Physical     | Physical transmission | Hub, Repeater         | Cables, signals |

### TCP/IP Model

**PYQ: Explain the TCP/IP reference model with neat diagram. (2019, Section B)**
**PYQ: Discuss architecture and responsibilities of each layer in TCP/IP model. (2021, Section C)**

The TCP/IP model has 4 layers and is the foundation of the modern internet:

#### Layer 4: Application Layer

- **Purpose:** Combines OSI layers 5, 6, and 7
- **Functions:** User applications, data formatting, session management
- **Protocols:** HTTP, HTTPS, FTP, SMTP, DNS, DHCP
- **Examples:** Web browsing, email, file transfer

#### Layer 3: Transport Layer

- **Purpose:** Same as OSI Transport layer
- **Functions:** Reliable data delivery, error control, flow control
- **Protocols:**
  - **TCP (Transmission Control Protocol):** Reliable, connection-oriented
  - **UDP (User Datagram Protocol):** Fast, connectionless
- **Simple meaning:** Ensures data arrives correctly

#### Layer 2: Internet Layer

- **Purpose:** Same as OSI Network layer
- **Functions:** Routing, logical addressing, packet forwarding
- **Protocols:** IP (Internet Protocol), ICMP, ARP
- **Simple meaning:** Finds the best path for data across networks

#### Layer 1: Network Access Layer

- **Purpose:** Combines OSI Physical and Data Link layers
- **Functions:** Physical transmission, local addressing
- **Protocols:** Ethernet, WiFi, PPP
- **Simple meaning:** Handles the actual sending of data over physical networks

| TCP/IP Layer   | OSI Equivalent                     | Main Function         | Key Protocols   |
| -------------- | ---------------------------------- | --------------------- | --------------- |
| Application    | Application, Presentation, Session | User services         | HTTP, FTP, SMTP |
| Transport      | Transport                          | Reliable delivery     | TCP, UDP        |
| Internet       | Network                            | Routing               | IP, ICMP        |
| Network Access | Data Link, Physical                | Physical transmission | Ethernet, WiFi  |

---

## Network Connecting Devices

**PYQ: Describe internetworking connecting devices in reference to layers. (2019, Section C)**

Network connecting devices help connect different parts of a network and operate at different OSI layers:

### 1. Hub (Physical Layer - Layer 1)

- **Definition:** A basic device that connects multiple devices in a star topology
- **Function:** Repeats incoming data to all connected devices
- **Characteristics:**
  - Creates one large collision domain (area where data collisions occur)
  - All devices share the same bandwidth
  - Cannot filter or process data
  - Cheaper but less efficient

**Advantages:**

- Simple and inexpensive
- Easy to install

**Disadvantages:**

- Creates network congestion
- No security (data goes to all devices)
- Half-duplex communication only

### 2. Bridge (Data Link Layer - Layer 2)

- **Definition:** Connects two or more network segments and filters traffic
- **Function:** Learns MAC addresses and forwards data only to intended devices
- **Characteristics:**
  - Divides network into separate collision domains
  - Reduces network traffic
  - Can connect different types of networks

**Advantages:**

- Reduces collisions
- Improves network performance
- Can connect different network types

**Disadvantages:**

- More expensive than hubs
- Limited number of ports

### 3. Switch (Data Link Layer - Layer 2)

- **Definition:** An intelligent device that connects multiple devices and manages data flow
- **Function:** Creates separate collision domains for each port and learns MAC addresses
- **Characteristics:**
  - Each port is a separate collision domain
  - Full-duplex communication
  - Maintains MAC address table
  - Can implement VLANs (Virtual LANs)

**Advantages:**

- High performance and speed
- Reduces collisions completely
- Better security than hubs
- Supports full-duplex communication

**Disadvantages:**

- More expensive than hubs
- Requires more configuration

### 4. Router (Network Layer - Layer 3)

- **Definition:** Connects different networks and finds the best path for data
- **Function:** Routes data between different networks using IP addresses
- **Characteristics:**
  - Creates separate broadcast domains
  - Uses routing tables to make decisions
  - Can connect different network types
  - Provides security features

**Advantages:**

- Connects different networks
- Provides security through access control
- Reduces network traffic
- Can choose best paths for data

**Disadvantages:**

- More expensive and complex
- Slower than switches for local traffic
- Requires configuration

### 5. Gateway (All Layers)

**PYQ: What is Gateway? (2019, Section A)**

- **Definition:** A device that connects networks using different protocols or architectures
- **Function:** Translates between different network protocols and formats
- **Characteristics:**
  - Works at all OSI layers
  - Can translate between different protocol stacks
  - Often includes firewall and security features
  - Can connect networks with different addressing schemes

**Examples:**

- Email gateway (connects different email systems)
- Internet gateway (connects LAN to internet)
- Protocol gateway (converts between TCP/IP and other protocols)

**Advantages:**

- Connects incompatible networks
- Provides protocol translation
- Often includes security features

**Disadvantages:**

- Most expensive and complex
- Can create bottlenecks
- Requires significant configuration

### Device Comparison Table

| Device  | OSI Layer     | Function               | Collision Domains | Broadcast Domains | Cost      |
| ------- | ------------- | ---------------------- | ----------------- | ----------------- | --------- |
| Hub     | Physical (1)  | Signal repetition      | 1                 | 1                 | Low       |
| Bridge  | Data Link (2) | MAC-based forwarding   | Multiple          | 1                 | Medium    |
| Switch  | Data Link (2) | Intelligent forwarding | One per port      | 1                 | Medium    |
| Router  | Network (3)   | IP-based routing       | One per port      | Multiple          | High      |
| Gateway | All layers    | Protocol translation   | Varies            | Varies            | Very High |

---

## Transmission Media

Transmission media are the physical channels through which data travels between devices. They are like roads for your data. There are two main types:

### Guided Media (Wired Media)

- **Definition:** These are physical cables or wires that guide the data along a fixed path. (Guided means data follows a specific route.)
- **Examples:**
  - **Twisted Pair Cable:** Pair of insulated copper wires twisted together.
  - **Coaxial Cable:** Has a central conductor and a shielding layer.
  - **Fiber Optic Cable:** Uses light to transmit data, offering high speed and low interference.

### Types of Transmission Media

**PYQ What is transmission medium? What are the different types of transmission medium? (2019, Section C)**
**PYQ Discuss various types of transmission media with their applications areas. (2023, Section C)**


Transmission media are the physical or wireless paths that carry data from one device to another in a network. They are divided into two main types: **Guided (Wired) Media** and **Unguided (Wireless) Media**.

---

#### 1. Guided Media (Wired Media)

**Definition:**  
Guided media use physical cables or wires to transmit data along a fixed path.

**Types and Applications:**

- **Twisted Pair Cable**
    - *Description:* Two insulated copper wires twisted together.
    - *Application:* Used in telephone lines, Ethernet LANs.
    - *Advantages:* Cheap, easy to install.
    - *Disadvantages:* Limited speed and distance, affected by interference.

- **Coaxial Cable**
    - *Description:* Has a central copper conductor, insulating layer, and shielding.
    - *Application:* Used for cable TV, older computer networks.
    - *Advantages:* Better shielding, supports higher speeds than twisted pair.
    - *Disadvantages:* Bulkier, more expensive.

- **Fiber Optic Cable**
    - *Description:* Uses thin glass or plastic fibers to transmit data as light signals.
    - *Application:* Used for high-speed internet, long-distance communication.
    - *Advantages:* Very high speed, immune to electrical interference, long distance.
    - *Disadvantages:* Expensive, fragile, harder to install.

---

#### 2. Unguided Media (Wireless Media)

**Definition:**  
Unguided media transmit data through air or space without physical cables.

**Types and Applications:**

- **Radio Waves**
    - *Description:* Electromagnetic waves used for wireless communication.
    - *Application:* WiFi, FM radio, mobile phones.
    - *Advantages:* Can cover large areas, supports mobility.
    - *Disadvantages:* Prone to interference, less secure.

- **Microwaves**
    - *Description:* High-frequency radio waves.
    - *Application:* Satellite communication, long-distance telephone calls.
    - *Advantages:* Can transmit over long distances, high bandwidth.
    - *Disadvantages:* Needs line-of-sight, affected by weather.

- **Infrared**
    - *Description:* Uses infrared light for short-range communication.
    - *Application:* TV remote controls, some wireless keyboards/mice.
    - *Advantages:* Simple, cheap, no interference with radio signals.
    - *Disadvantages:* Short range, needs direct line-of-sight.

---
**PYQ What are the criteria used to evaluate transmission medium? (2021, Section A)**

### Criteria for Choosing Transmission Media

When selecting a transmission medium, consider:

- **Bandwidth:** How much data can be sent at once.
- **Attenuation:** How much signal is lost over distance.
- **Interference:** How easily the signal is affected by noise.
- **Cost:** Price of buying, installing, and maintaining.
- **Security:** How safe the data is from being intercepted.

---

**Summary Table:**

| Media Type      | Example           | Application Area         | Advantages           | Disadvantages         |
|-----------------|-------------------|-------------------------|----------------------|----------------------|
| Twisted Pair    | Ethernet cable    | LAN, telephones         | Cheap, easy install  | Limited speed/distance|
| Coaxial Cable   | Cable TV cable    | TV, older networks      | Good shielding       | Bulky, expensive     |
| Fiber Optic     | Fiber cable       | Internet, long distance | High speed, secure   | Expensive, fragile   |
| Radio Waves     | WiFi, FM radio    | Wireless networks       | Mobility, coverage   | Interference, security|
| Microwaves      | Satellite link    | Long-distance comm.     | High bandwidth       | Needs line-of-sight  |
| Infrared        | Remote control    | Short-range devices     | Simple, no radio int.| Short range, direct  |


## Classification and Arrangement: Wired LANs and Wireless LANs

Networks are often classified based on how devices are connected.

### Wired LANs

- **Definition:** Local Area Networks where devices communicate through physical cables (e.g., Ethernet).
- **Features:**
  - High speed and reliability
  - Less interference
  - Limited to a specific area (like an office or school)
- **Examples:** Office networks, home LANs.

### Wireless LANs

- **Definition:** Networks that use wireless signals (like WiFi) to connect devices without cables.
- **Features:**
  - Offers mobility and easy setup
  - Can cover larger areas than wired LANs
  - May face interference or security challenges
- **Examples:** Home wireless networks, public WiFi hotspots.

**Interconnection:**

- Wired LANs use guided media (like cables) which are fixed routes for data. Wireless LANs use unguided media (like radio waves) that allow flexible movement of data.

---
