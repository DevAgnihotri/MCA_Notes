# Data Link Layer: Error Detection, Correction, Flow & Error Control

## Error Detection and Error Correction

### Types of Errors

- **Single-bit error:** Only one bit in the data unit changes (for example, 1001 becomes 1101). This is easy to detect and fix.
- **Burst error:** Two or more bits in the data unit change (for example, 1001 becomes 1110). Burst errors are harder to detect and fix because they affect more bits at once.

### Error Detection Techniques

**2019, Section B: What is cyclic code and explain Cyclic Redundancy Check (CRC) code?**
**2023, Section B: CRC Example**
**2021, Section C: List out various error detection techniques? Discuss Hamming code with suitable example.**
**2023, Section C: Error handling at data link layer? Discuss Hamming code with suitable example.**

### Error Handling at Data Link Layer

- The data link layer uses error detection and correction techniques to make sure data is received correctly. If an error is found, it can ask for retransmission (send the data again) or fix the error using codes like Hamming code. This keeps communication reliable and accurate.

- **Parity Check (VRC - Vertical Redundancy Check):**

  - Adds a parity bit to each data unit to make the number of 1s either even (even parity) or odd (odd parity).
  - If the number of 1s is not as expected, an error is detected.
  - Simple and fast, but only detects single-bit errors. It cannot fix errors, only detect them.

- **LRC (Longitudinal Redundancy Check):**

  - Arranges data in a table and adds a parity bit for each column.
  - Can detect burst errors better than VRC because it checks both rows and columns.

- **Checksum:**

  - Adds all data units together and sends the sum (checksum) with the data.
  - The receiver adds received data and compares with the checksum. If they match, data is correct; if not, there is an error.
  - Used in network protocols like TCP/IP.

- **CRC (Cyclic Redundancy Check):**

  - CRC is a way to check if data has errors when it is sent from one computer to another.
  - It works by using math called polynomial division. The sender uses a special formula (called a generator polynomial) to divide the data and gets a remainder. This remainder is called the CRC bits.
  - The sender adds these CRC bits to the end of the data before sending it.
  - When the receiver gets the data, it uses the same formula to check the data and the CRC bits together. If the remainder is zero, the data is correct. If it is not zero, there is an error.

  - **Cyclic Code:** This means that if you move the bits of a code word in a circle (cyclic shift), you still get a valid code word. CRC uses this idea to make error checking stronger.

  - **Example (2023, Section B):**

    - [https://www.youtube.com/watch?v=UhMqF0e6Ueg]

    - Suppose you want to send the bit stream: 10011101.
    - The generator polynomial is x^3 + 1, which is written as 1001 in binary.
    - Steps:
      1. Add 3 zeros to the end of the data (because the generator is 4 bits): 10011101000.
      2. Divide this new bit stream by 1001 using binary division.
      3. The remainder you get is the CRC bits. Attach these bits to the original data before sending.
      4. If any bit changes during transmission, the receiver will divide the received bits by 1001. If the remainder is not zero, it means there was an error in the data.

- **Hamming Code:**

  - [https://www.youtube.com/watch?v=KoK6APJ7_LI]

  - Hamming code is a method used to find and fix errors in data. It does not just detect errors, it can also correct them.
  - It works by adding extra bits to the data. These extra bits are called parity bits. They help check if the data is correct.
  - Parity bits are placed at positions that are powers of 2 (like 1, 2, 4, 8, ...). Each parity bit checks a different group of data bits.
  - When the data is received, the receiver checks all the parity bits. If there is a mistake in one bit, the parity bits will show exactly which bit is wrong. The receiver can then fix the error by changing that bit back.
  - Hamming code can fix single-bit errors and can tell if there are two-bit errors (but cannot fix two-bit errors).

  - **How it works:**

    - For example, if you want to send the data 1011, you add parity bits at positions 1, 2, and 4.
    - You fill in the parity bits so that each group of bits has the correct parity (even or odd number of 1s).
    - The final code might look like 0110011 (the parity bits are calculated to protect the data).
    - If one bit changes during transmission, the receiver checks the parity bits and finds out which bit is wrong. It can then fix the error.

  - Hamming code is useful because it makes communication more reliable and helps computers fix mistakes automatically.

---

## Flow Control and Error Control

**2021, Section C: Discuss sliding window-based flow control techniques at data link layer.**
**2023, Section C: Explain Selective Reject and Go-Back-N ARQ with reference to sliding window protocol.**
**2021, Section A: Maximum window size for selective reject protocol with n-bit frame sequence numbers?**

### Flow Control

- **Purpose:** Flow control helps make sure that the sender does not send data too fast for the receiver to handle. If the sender sends too much data at once, the receiver might get confused or lose some data. Flow control keeps both sides working smoothly together.

- **Stop and Wait Protocol:**

  - The sender sends one frame (a small chunk of data) and then waits for the receiver to say "I got it!" (an acknowledgment).
  - Only after getting the acknowledgment does the sender send the next frame.
  - This method is easy to understand and use, but it can be slow, especially if the sender and receiver are far apart or the network is very fast. The sender spends a lot of time waiting.

- **Sliding Window Protocol:** (PYQ)
  - The sender can send several frames in a row before needing an acknowledgment. The number of frames it can send is called the "window size."
  - The receiver can accept frames within this window and send back acknowledgments for them.
  - This makes sending data much faster and more efficient because the sender does not have to wait after every single frame.
  - **Example:** If the window size is 4, the sender can send 4 frames one after another before waiting for an acknowledgment. This helps use the network better and saves time.

### Error Control (ARQ Protocols) (PYQ)

Error control makes sure that the data sent from one computer to another arrives correctly. If something goes wrong, error control helps fix it.

- **Go-Back-N ARQ:**

  - The sender can send several frames (up to the window size) before waiting for an acknowledgment.
  - If the receiver finds an error in a frame, it throws away that frame and all the frames that come after it.
  - The sender then goes back and sends the wrong frame again, along with all the frames that came after it.
  - This method is simple, but if there are lots of errors, it can waste time and network space because many frames might have to be sent again.

- **Selective-Repeat ARQ (Selective Reject):**
  - Only the frames that have errors are sent again, not all the frames after the error.
  - The receiver keeps the frames that are correct and only asks for the missing or wrong frames to be sent again.
  - This method is more efficient than Go-Back-N, especially if errors do not happen very often.
  - **Maximum Window Size:** If the sequence numbers for frames use n bits, the largest window size is 2^(n-1) frames.
    - **Example:** If n = 3, the window size is 2^(3-1) = 4 frames. This means the sender can send up to 4 frames before needing an acknowledgment.

---

## Channel Allocation Protocols

**2021, Section B: What do you mean by ALOHA? Consider a situation, where a large population of ALOHA users manages to generate 50 requests/sec, including both originals and retransmissions. Time is slotted in units of 40 msec.**

### ALOHA Protocol

ALOHA is a simple random access protocol where users send data whenever they have something to send. If two users send at the same time, their data collides and must be resent. Slotted ALOHA improves efficiency by dividing time into slots, and users can only send at the start of a slot.

Given:
- Requests/sec (G) = 50
- Slot duration = 40 ms = 0.04 sec
- Average number of requests per slot:  
    \( G = 50 \times 0.04 = 2 \)

#### (a) Chances of success on the first attempt

For slotted ALOHA, the probability of success in a slot is:
\[
P_{success} = G \times e^{-G}
\]
But for a single transmission, the probability that no other user transmits in the same slot is:
\[
P_{success} = e^{-G} = e^{-2} \approx 0.135
\]
So, the chance of success on the first attempt is **about 13.5%**.

#### (b) Probability of exactly k collisions and then a success

The probability of k failures (collisions) followed by a success is:
\[
P = (1 - e^{-G})^k \times e^{-G}
\]
Where \( e^{-G} \) is the probability of success in a slot.

#### (c) Expected number of transmission attempts needed

The expected number of attempts is the reciprocal of the probability of success:
\[
E = \frac{1}{e^{-G}} = e^{G} = e^{2} \approx 7.39
\]
So, on average, **about 7.39 attempts** are needed for a successful transmission.


**2023, Section A: Discuss CSMA/CD.**

**2019, Section C: Define controlled access and list three protocols in this category.**

---

### Introduction to Channel Allocation Protocols

- Channel allocation protocols are rules and methods used to decide how multiple devices share the same communication channel (like a wire or radio frequency) so that data can be sent without too many collisions (data getting mixed up).
- There are three main types:
  1. **Random Access Protocols**
  2. **Controlled Access Protocols**
  3. **Channelization Protocols**

---

### 1. Random Access Protocols

- Devices send data whenever they want, but if two devices send at the same time, their data collides and must be resent.
- These protocols are simple and work well when there are not too many users.

#### ALOHA (PYQ)

- **Definition:**  
    ALOHA is a simple way for computers or devices to send data over a shared channel. In ALOHA, any device can send data whenever it wants. If two devices send data at the same time, their messages crash into each other (this is called a collision), and the data is lost. When a collision happens, the device waits for a random amount of time and then tries to send the data again. This helps reduce the chance of another collision.

- **Types of ALOHA:**  
    1. **Pure ALOHA:**  
         - Devices can send data at any moment, without waiting for a special time.
         - Collisions can happen often because there is no control over when devices send data.
         - After sending, the device waits to see if the data was received. If not, it tries again after a random delay.
    2. **Slotted ALOHA:**  
         - Time is split into equal slots (like turns).
         - Devices can only send data at the start of a slot.
         - This reduces the chance of collisions because devices are more organized about when they send data.
         - Slotted ALOHA is more efficient than Pure ALOHA.

- **Success Probability (2021, Section B):**  
    - (a) **Chance of Success on First Attempt:**  
        - For slotted ALOHA, the chance that a device sends data and no other device sends at the same time is given by the formula:  
            \( P_{success} = G \times e^{-G} \)  
            where G is the average number of requests per slot.
        - For a single transmission, the chance that no other device sends in the same slot is:  
            \( P_{success} = e^{-G} \)
        - This means if there are many devices, the chance of success goes down.
    - (b) **Probability of Exactly k Collisions and Then a Success:**  
        - Sometimes, a device may have to try several times before its data is sent successfully.
        - The chance of having k failures (collisions) before a success is:  
            \( P = (1 - p)^k \times p \)  
            where p is the probability of success in a slot.
        - This formula helps us know how many tries might be needed.
    - (c) **Expected Number of Transmission Attempts Needed:**  
        - On average, the number of tries needed to send data successfully is:  
            \( E = \frac{1}{p} \)
        - If the chance of success is low, the device will need more tries.

---

#### CSMA (Carrier Sense Multiple Access)

- **Definition:**  
    CSMA is a method where devices listen to the channel before sending data. If the channel is busy (someone else is sending), the device waits until the channel is free. This helps avoid collisions.

- **Types of CSMA:**  
    1. **CSMA/CD (Carrier Sense Multiple Access with Collision Detection) (PYQ):**  
         - Used in wired networks like Ethernet.
         - Devices listen to the channel before sending data.
         - If two devices send at the same time and a collision happens, they stop sending as soon as they notice the collision.
         - After a collision, each device waits for a random time before trying again. This reduces the chance of another collision.
         - This method helps keep the network running smoothly and avoids wasting time sending data that will be lost.
    2. **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance):**  
         - Used in wireless networks like Wi-Fi.
         - Devices try to avoid collisions by waiting and sending special signals before sending data.
         - If the channel is busy, the device waits for it to become free.
         - This method is important for wireless networks because it is harder to detect collisions in the air.

---

### 2. Controlled Access Protocols (PYQ)

- **Definition:**  
    Controlled access means that devices take turns using the channel, so only one device sends data at a time. This helps prevent collisions and makes communication more organized.

- **Three Main Controlled Access Protocols:**  
    1. **Reservation:**  
         - Devices reserve time slots ahead of time to send their data.
         - Each device knows when it can send, so there are no collisions.
         - This is like booking a time to use a computer in a lab.
    2. **Polling:**  
         - A central controller (like a teacher) asks each device one by one if it wants to send data.
         - Only the device that is asked can send data at that time.
         - This keeps things orderly and avoids collisions.
    3. **Token Passing:**  
        - A special message called a "token" is passed around the network.
        - **What is a token?**  
          - A token is a small data packet that acts as a permission slip for sending data. It circulates among devices in a fixed order.
        - Only the device that has the token is allowed to send data.
        - After sending, the device passes the token to the next device.
        - This method is like passing a talking stick in a group discussion—only the person with the stick can talk.

- **Summary:**  
    Controlled access protocols make sure that devices do not talk over each other. They help keep the network organized and reduce the chance of data getting lost.

### 3. Channelization Protocols

    Channelization protocols are methods that allow multiple devices to share the same communication channel at the same time, but without interfering with each other. These protocols divide the channel in different ways so that everyone can send and receive data smoothly.

- **TDMA (Time Division Multiple Access):**
    - In TDMA, time is split into small slots, like turns in a game.
    - Each device is given its own time slot to send data, so only one device uses the channel at a time during its slot.
    - This prevents collisions because devices wait for their turn.
    - For example, if there are 4 devices, each one gets a turn to send data in a repeating cycle.

- **FDMA (Frequency Division Multiple Access):**
    - FDMA divides the channel into different frequency bands, like different radio stations.
    - Each device is assigned a unique frequency to use for sending data.
    - Devices can send data at the same time, but on different frequencies, so their signals do not mix.
    - This is commonly used in radio and TV broadcasting, where each station has its own frequency.

- **CDMA (Code Division Multiple Access):**
    - In CDMA, all devices use the same channel at the same time, but each device uses a special code to separate its data from others.
    - The codes are unique for each device, like secret passwords.
    - The receiver uses the same code to pick out the correct data from the mixed signals.
    - This allows many devices to communicate at once without interfering, and is used in mobile phone networks.

    These channelization protocols help make communication faster and more efficient, especially when many devices need to share the same network.

---