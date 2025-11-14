### **The Link Layer and LANs - Introduction**
The link layer is responsible for transferring datagrams over a **single communication link** between adjacent nodes (hosts, routers, switches) along the end-to-end path.
**Key Questions for this Chapter:**
- How are network-layer datagrams encapsulated into link-layer frames?
- How are transmission conflicts on shared/broadcast links resolved?
- How does link-layer addressing work and how does it relate to network-layer (IP) addressing?
- What is the difference between a switch and a router?

**Two Fundamental Types of Link-Layer Channels:**
1. **Broadcast Channels:** Connect multiple hosts (e.g., wireless LANs, HFC cable access networks). Require a **Medium Access Control (MAC) protocol** to coordinate transmissions and avoid collisions.
2. **Point-to-Point Links:** Connect two individual nodes (e.g., a long-distance router link, a computer to an Ethernet switch). Coordination is simpler.
![[Pasted image 20251114183257.png]]

**Transportation Analogy:**
- **Tourist = Datagram**
- **Transportation Segment (e.g., limo, plane, train) = Link**
- **Transportation Company/Mode = Link-Layer Protocol**
- **Travel Agent = Routing Protocol**
#### **The Services Provided by the Link Layer**
Link-layer protocols can offer several key services:
- **Framing:** Encapsulates the network-layer datagram within a link-layer frame for transmission. The frame includes a data field (for the datagram) and header fields.
- **Link Access:** A **Medium Access Control (MAC) protocol** governs the rules for transmitting a frame onto the link. This is crucial for **multiple access** links where multiple nodes share a single broadcast channel.
- **Reliable Delivery:** Guarantees the movement of each datagram across the link without error, using acknowledgments and retransmissions. Often used for error-prone links (like wireless) but considered overhead for reliable wired links (like fibre).
- **Error Detection and Correction:** The transmitting node adds **error-detection bits** to the frame. The receiving node checks these bits to detect if bit errors have occurred during transmission. **Error correction** goes a step further by also determining and fixing the exact location of the errors.
#### **Where Is the Link Layer Implemented?**
The link layer is implemented in a combination of **hardware and software**, and is the point in the protocol stack where software meets hardware.
- **Hardware (Network Adapter / NIC):** The primary implementation. A dedicated chip (the network adapter or Network Interface Controller - NIC) handles most link-layer services in hardware:
    - Framing
    - Link access
    - Error detection
    - Signal transmission/reception
- **Software (Host CPU):** Implements higher-level link-layer functionality:
    - Assembling link-layer addressing information.
    - Activating the controller hardware.
    - Handling controller interrupts (e.g., frame received).
    - Passing datagrams up to the network layer.
![[Pasted image 20251114183318.png]]
### **Error-Detection and -Correction Techniques**
The link layer often provides services to detect and sometimes correct bit errors introduced during transmission. These techniques involve the sender adding extra **Error-Detection and -Correction (EDC)** bits to the data (D). The receiver uses these bits to determine if the received data (D') is error-free.
![[Pasted image 20251114183327.png]]

**Key Trade-off:** More robust error detection/correction techniques reduce the probability of **undetected errors** but incur a higher overhead (more EDC bits and more computation).
#### **Parity Checks**
**Single Parity Bit:**
- The sender adds one extra bit so that the total number of 1s in the `d+1` bits is either **even** (even parity) or **odd** (odd parity).
- The receiver counts the 1s. If the count doesn't match the expected parity (e.g., an odd number found with even parity), an error is detected. (INSERT FIGURE 6.4, ONE-BIT EVEN PARITY, HERE)
- **Limitation:** Can only detect an **odd number of bit errors**. If an even number of bits are flipped, the error goes **undetected**. This is problematic with burst errors.

**Two-Dimensional Parity:**
- A generalization that provides **error correction** capability.
- The `d` data bits are arranged in an `i x j` matrix.
- A parity bit is computed for each **row** and each **column**. The `i + j + 1` parity bits are sent as EDC. (INSERT FIGURE 6.5, TWO-DIMENSIONAL EVEN PARITY, HERE)
- **Capabilities:**
    - Can **detect and correct** any **single-bit error**. The intersection of the row and column with parity errors identifies the corrupted bit.
    - Can **detect (but not correct)** any combination of **two errors**.
#### **Forward Error Correction (FEC)**
- The ability of the receiver to **detect and correct errors** without needing the sender to retransmit the data.
- **Advantages:**
    - Reduces the number of retransmissions required.
    - Provides immediate correction, which is crucial for **real-time applications** (e.g., VoIP, video streaming) and links with **long propagation delays** (e.g., satellite, deep-space).
### **Checksumming Methods**
- **Concept:** The data (D) is treated as a sequence of k-bit integers. These integers are summed, and the resulting sum (or its complement) is used as the error-detection bits.
- **Internet Checksum:** Used at the **transport layer** (TCP, UDP) and **network layer** (IP header).
    - Data is treated as 16-bit integers.
    - The 1s complement of the sum is taken to form the checksum.
    - The receiver calculates the 1s complement of the sum (including the checksum); a result of all 0s indicates no error.
- **Characteristics:**
    - **Low Overhead:** Typically only 16 bits.
    - **Relatively Weak Protection:** Compared to CRC.
    - **Implemented in Software:** Used at the transport layer because it is simple and fast to compute in software on a host's CPU.
### **Cyclic Redundancy Check (CRC)**
CRC is a powerful error-detection technique widely used in the **link layer**, implemented in hardware on network adapters.
- **Operation:**
    1. Sender and receiver agree on a generator (G), an `r+1`-bit pattern.
    2. For data (D) of `d` bits, the sender selects `r` additional bits (R) such that the `d+r` bit pattern is **divisible by G** (using modulo-2 arithmetic).
    3. The receiver divides the received `d+r` bits by G. A **non-zero remainder indicates an error**.
- **Modulo-2 Arithmetic:** The core of CRC calculations. It is binary arithmetic without carries or borrows.
    - Addition and subtraction are both equivalent to the **bitwise XOR** operation.
    - Example: `1011 XOR 0101 = 1110`.
- **Calculating R (the CRC bits):** `R = remainder( (D • 2^r) / G )` (INSERT FIGURE 6.7, A SAMPLE CRC CALCULATION, HERE)
- **Strengths:**
    - Can detect all **burst errors** shorter than `r+1` bits.
    - Can detect any **odd number** of bit errors.
    - Very robust; a burst error longer than `r+1` bits is detected with a probability of `1 - 0.5^r`.

**Why Checksum at Transport, CRC at Link?**
- **Transport Layer:** Implemented in **software** on the host CPU. Needs a simple, fast algorithm like checksum.
- **Link Layer:** Implemented in **hardware** on the network adapter. Can perform the more complex but powerful CRC operations rapidly.
### **Multiple Access Links and Protocols**

This section addresses the problem of coordinating access to a **shared broadcast channel** (e.g., Ethernet, wireless LANs), where multiple nodes are connected to the same communication medium.
- **The Multiple Access Problem:** How to coordinate the transmissions of multiple sending and receiving nodes to a single, shared broadcast channel to avoid, or recover from, **collisions**.
- **Collision:** When two or more nodes transmit at the same time, their signals "collide," become intertwined, and the frames are **lost**, wasting channel bandwidth. (INSERT FIGURE 6.8, VARIOUS MULTIPLE ACCESS CHANNELS, HERE)

**Ideally, a multiple access protocol should have the following characteristics:**
1. **High throughput when only one node is active:** A single active node should be able to use the full channel rate, R bps.
2. **Fairness when multiple nodes are active:** When M nodes are active, each should get an average throughput of R/M bps.
3. **Decentralized:** No master node to create a single point of failure.
4. **Simple:** Inexpensive to implement.

**Three Broad Categories of Multiple Access Protocols:**
1. **Channel Partitioning Protocols:** Divide the channel (by time, frequency, or code) to avoid collisions.
2. **Random Access Protocols:** Nodes transmit at full rate, but if a collision occurs, they wait a random time before retransmitting.
3. **Taking-Turns Protocols:** Nodes take turns transmitting, coordinating in a structured way.

### **Channel Partitioning Protocols**
These protocols divide the broadcast channel's resources to avoid collisions entirely.
**1. Time-Division Multiplexing (TDM)**
- **Concept:** Time is divided into **frames**, and each frame is divided into **N time slots** (one for each of N nodes). Each node can only transmit during its assigned slot in each repeating frame.
- **Advantages:**
    - **Collision-free.**
    - **Perfectly fair:** Each node gets a dedicated rate of **R/N bps**.
- **Disadvantages:**
    - **Inefficient:** A node is limited to R/N bps **even if it is the only node with data to send**.
    - **Fixed Delay:** A node must always wait for its turn, even if the channel is idle. (INSERT FIGURE 6.9, TDM AND FDM EXAMPLE, HERE)

**2. Frequency-Division Multiplexing (FDM)**
- **Concept:** The channel's frequency spectrum is divided into **N different frequency bands**, each with a bandwidth of R/N. Each node is assigned its own dedicated frequency band.
- **Advantages & Disadvantages:** Shares the same pros and cons as TDM: collision-free and fair, but inefficient for a single active node (limited to R/N bps).

**3. Code Division Multiple Access (CDMA)**
- **Concept:** Assigns a **unique code** to each node. All nodes can transmit **simultaneously** over the entire frequency spectrum. A receiver can correctly decode a specific sender's data if it knows that sender's code, effectively filtering out other transmissions.
- **Use Cases:** Widely used in military systems (for anti-jamming) and in **cellular telephony**.
### **Random Access Protocols**
In random access protocols, a node transmits at the **full channel rate (R bps)** when it has data. If a **collision** occurs, the node waits a **random delay** before retransmitting. This avoids the channel waste of partitioning protocols when only one node is active.
#### **Slotted ALOHA**
This is a simple random access protocol with specific assumptions to make analysis easier.
**Assumptions:**
- Time is divided into equal **slots** (the size of one frame transmission time).
- Nodes are **synchronized** and can only start transmission at the beginning of a slot.
- All frames are the same size.
- Nodes can detect a collision before the slot ends.

**Protocol Operation:**
1. When a node has a new frame, it transmits at the beginning of the next slot.
2. If no collision occurs, the transmission is successful. The node is done.
3. If a collision occurs, the node detects it. The node then **retransmits the frame in each subsequent slot with probability `p`** until it is successful. (INSERT FIGURE 6.10, SLOTTED ALOHA OPERATION, HERE)

**Advantages:**
- **Single Active Node:** A single node can use the **full channel rate, R bps**.
- **Highly decentralized:** No central coordinator is needed.
- **Simple** to implement.

**Disadvantage: Efficiency**
- **Efficiency:** The long-run fraction of **successful slots** (slots where exactly one node transmits) when many nodes are active.
- **Analysis:** The maximum efficiency of slotted ALOHA is **1/e ≈ 0.37**.
- **Interpretation:** This means that at best, only **37% of the channel's capacity** is used for successful transmissions. The rest is wasted on **collisions (26%)** and **empty slots (37%)**.
### **ALOHA**
**Pure ALOHA (Unslotted ALOHA)**
- **Operation:** A fully decentralized protocol. When a frame first arrives, the node **immediately transmits** it in its entirety.
- **Collision Handling:** If a collision occurs, the node **immediately retransmits the frame with probability `p`** after the transmission is complete. Otherwise, it waits one frame transmission time and tries again.
- **Vulnerability Period:** For a frame starting at time `t₀` to be successful, no other node can start transmitting in the interval `[t₀ - 1, t₀ + 1]`. This is a **2-unit time** window. (INSERT FIGURE 6.11, INTERFERING TRANSMISSIONS IN PURE ALOHA, HERE)
- **Efficiency:** The maximum efficiency of pure ALOHA is **1/(2e) ≈ 0.18**. This is **half the efficiency of slotted ALOHA**, which is the price paid for being completely unslotted and decentralized.
### **Carrier Sense Multiple Access (CSMA)**
CSMA protocols introduce two simple, polite rules to reduce the chance of collisions, inspired by human conversation:
1. **Carrier Sensing: "Listen before speaking."** A node listens to the channel (**senses the carrier**) before transmitting. If the channel is busy, it waits.
2. **Collision Detection: "If someone else starts talking at the same time, stop talking."** A node listens to the channel **while it is transmitting**. If it detects that another node's transmission is interfering (a collision), it **stops transmitting** immediately.

**Why Do Collisions Still Occur in CSMA?**
- Due to **channel propagation delay**. A signal takes time to travel across the medium.
- **Scenario:** Node B starts transmitting. Its signal hasn't reached Node D yet. Node D senses the channel as idle and starts transmitting, leading to a collision. (INSERT FIGURE 6.12, CSMA WITH COLLIDING TRANSMISSIONS, HERE)
### **CSMA with Collision Detection (CSMA/CD)**
This is the protocol used in **Ethernet**. It combines carrier sensing with collision detection to improve efficiency by not wasting time transmitting corrupted frames in full.
**CSMA/CD Operation:**
1. The adapter gets a datagram and prepares a frame.
2. If the channel is idle, it starts transmitting. If busy, it waits until idle.
3. **While transmitting,** the adapter monitors the channel for collisions.
4. If the entire frame is transmitted without a collision, the process is done.
5. If a collision is detected **during transmission**, the adapter **immediately aborts** the transmission. (INSERT FIGURE 6.13, CSMA WITH COLLISION DETECTION, HERE)
6. After aborting, the adapter waits a **random** amount of time before returning to step 2.

**Binary Exponential Backoff:**
- This is the algorithm used to determine the random wait time after a collision. It ensures stability by adapting the wait time based on how many collisions a frame has experienced.
- **Algorithm:** After the *n*th collision, the adapter chooses a value **K** at random from the set `{0, 1, 2, ..., 2ⁿ-1}`. The wait time is **K × 512 bit times**.
- **Effect:** The **more collisions** a frame experiences, the **larger the range** from which K is chosen. This helps to separate the retransmission attempts of colliding nodes.
- The exponent `n` is capped (at 10 for Ethernet), so the wait time doesn't grow infinitely.
### **CASE HISTORY: Norm Abramson and ALOHAnet**
- Norm Abramson designed the **ALOHAnet** in Hawaii in 1969 to solve the problem of packet switching over radio across mountainous islands.
- This was the first example of a radio packet network.
- The **pure ALOHA** protocol was developed for this network to handle collisions on the shared upstream channel.
- ALOHAnet's design later **inspired Bob Metcalfe**, who modified it to create the **CSMA/CD protocol** and, ultimately, **Ethernet**.
### **CSMA/CD Efficiency**
The efficiency of CSMA/CD (as used in Ethernet) is defined as the long-run fraction of time the channel is used for **successful frame transmissions** without collisions.
- **Efficiency Formula:** `Efficiency = 1 / (1 + 5 * d_prop / d_trans)`
    - **`d_prop`:** The **maximum propagation delay** for a signal to travel between the two farthest nodes.
    - **`d_trans`:** The **time to transmit a maximum-size frame**.
**Interpretation:**
- If **`d_prop → 0`**, efficiency approaches **1**. With no propagation delay, collisions are detected instantly, and no channel capacity is wasted.
- If **`d_trans` becomes very large**, efficiency approaches **1**. A single frame holds the channel for a long time, making productive use of it.
### **Taking-Turns Protocols**
These protocols aim to provide the high efficiency of a single active node using the full rate (R bps) while also providing fair, collision-free access when multiple nodes are active (each getting ~R/M bps).

**1. Polling Protocol:**
- **Operation:** A designated **master node** polls the other nodes in a round-robin fashion. It asks each node in turn if it has data to send, granting it permission to transmit up to a maximum number of frames.
- **Advantages:**
    - **Eliminates collisions and empty slots**, leading to high efficiency.
- **Disadvantages:**
    - **Polling Delay:** The time spent notifying nodes introduces latency.
    - **Single Point of Failure:** If the master node fails, the entire network fails.
    - **Example:** Bluetooth.

**2. Token-Passing Protocol:**
- **Operation:** A special frame called a **token** is passed from node to node in a fixed, circular order. A node can only transmit when it is holding the token.
- **Advantages:**
    - **Decentralized** (no master node).
    - **Highly efficient** and collision-free.
- **Disadvantages:**
    - **Token Loss:** If a node fails, the token can be lost, crashing the network.
    - **Token Holding:** A faulty or malicious node might hold the token indefinitely.
    - **Examples:** FDDI, IEEE 802.5 Token Ring.
### **DOCSIS: The Link-Layer Protocol for Cable Internet Access**
DOCSIS is the protocol used in cable internet access networks. It provides a fascinating **case study** because it combines elements from **all three classes** of multiple access protocols.
**Network Context:**
- The **Cable Modem Termination System (CMTS)** at the headend communicates with thousands of residential **cable modems**.
- **Downstream (CMTS → Modems):** A pure broadcast channel from a single sender (the CMTS), so no multiple access problem.
- **Upstream (Modems → CMTS):** A shared broadcast channel where multiple modems can transmit, requiring a multiple access protocol.

**How DOCSIS Works (Upstream Channel):** (INSERT FIGURE 6.14, DOCSIS UPSTREAM AND DOWNSTREAM, HERE)
1. **TDM-like Structure:** The upstream channel is divided into time intervals containing **mini-slots**.
2. **Centralized Allocation (Taking-Turns):** The CMTS sends a **MAP message** (downstream) to explicitly grant specific mini-slots to specific cable modems for data transmission. This **prevents collisions** for data frames.
3. **Random Access for Requests:** To tell the CMTS it has data to send, a modem transmits a **mini-slot-request frame** during a special set of mini-slots reserved for this purpose. These requests are sent using a **random access** method and **can collide**.
4. **Collision Handling:** Modems cannot sense the channel. They infer a collision if they don't receive a grant in response to their request. They then use **binary exponential backoff** to retransmit the request.

**Summary:** DOCSIS is a hybrid protocol using:
- **FDM** to create separate upstream/downstream channels.
- **TDM** to structure the upstream channel into mini-slots.
- **Taking-Turns** for collision-free data transmission via central allocation.
- **Random Access** with binary exponential backoff for initial bandwidth requests.

### **Switched Local Area Networks**
**Core Concept:** A network where hosts and routers are connected by **link-layer switches**. These switches operate at the link layer, forwarding **frames** (not datagrams) based on **MAC addresses**, not IP addresses.
### **Link-Layer Addressing and ARP**
#### **MAC Addresses**
- **What they are:** A unique, 6-byte (48-bit) identifier assigned to a device's network adapter (interface).
    - Also called a **LAN address**, **physical address**, or **MAC address**.
- **Key Properties:**
    1. **Flat Structure:** Unlike hierarchical IP addresses, a MAC address does not change, no matter where the device connects.
    2. **Globally Unique:** Managed by IEEE, which allocates blocks of addresses (first 24 bits) to manufacturers.
- **Analogy:**
    - **MAC Address:** Like a Social Security Number (flat, permanent).
    - **IP Address:** Like a postal address (hierarchical, changes with location).
- **Frame Handling:** An adapter only processes a frame and passes the datagram up the protocol stack if the frame's destination MAC address matches its own or is the **broadcast address** (`FF-FF-FF-FF-FF-FF`).
#### **Why Both IP and MAC Addresses? (Layered Independence)**
1. **Protocol Neutrality:** LANs must support various network-layer protocols (IP, IPX), not just IP.
2. **Independence:** To keep layers as independent building blocks, each needs its own addressing scheme.
#### **Address Resolution Protocol (ARP)**
- **Purpose:** To resolve a **network-layer IP address** to a **link-layer MAC address** for a destination on the **same subnet**.
- **Analogy:** ARP is to IP/MAC resolution as **DNS** is to hostname/IP resolution, but ARP only works within a local subnet.

**How ARP Works:**
1. **ARP Table:** Each host and router maintains a table that maps IP addresses to MAC addresses. Each entry has a **Time-To-Live (TTL)**.
2. **The ARP Process:**
    - A sending host checks its ARP table for the destination IP address.
    - If the mapping **exists**, it uses the MAC address to send the frame.
    - If the mapping **does not exist**, it initiates an ARP query:
        - **Query:** The sender creates an **ARP query packet** and sends it inside a **broadcast frame** (destination MAC = `FF-FF-FF-FF-FF-FF`) to all devices on the subnet.
        - **Response:** The device whose IP address matches the query responds by sending an **ARP response packet** back to the sender inside a **standard, unicast frame**.
    - The sender receives the response, updates its ARP table, and can now send the original data frame.

- **Key Characteristics of ARP:**
    - **Plug-and-Play:** ARP tables are built automatically; no manual configuration is needed.
    - **Architectural Placement:** ARP straddles the boundary between the link and network layers, as it uses link-layer framing but contains network-layer addresses.
### **Sending a Datagram Off the Subnet**
**The Scenario:** A host needs to send a datagram to a destination on a **different subnet**. This requires traversing a router.
**Key Insight:** The host does **not** use the final destination's MAC address. Instead, it uses the MAC address of the **first-hop router** (the "default gateway").
**The Process (using Figure 6.19 as an example):**
1. **Host Decision:** Host 111.111.111.111 determines that the destination (222.222.222.222) is on a different network.
2. **First Hop:** The host concludes it must send the datagram to its configured **router interface** (111.111.111.110).
3. **ARP for Router:** The host uses **ARP** to find the **MAC address** of the router interface 111.111.111.110.
4. **Frame to Router:** The host creates a frame with the **destination MAC address of the router** but the **destination IP address of the final host**. It sends this frame.
5. **Router's Job:** The router's adapter receives the frame, passes the IP datagram up, and the router's network layer consults its forwarding table.
6. **Second Hop:** The forwarding table dictates the datagram should be sent out the interface with IP 222.222.222.220.
7. **ARP for Final Host:** The router's second interface uses **ARP** to find the **MAC address** of the final destination host (222.222.222.222).
8. **Final Delivery:** The router creates a _new_ frame with the **destination MAC address of the final host** and sends it onto Subnet 2.
### **Ethernet**
**Dominance:** Ethernet is the dominant wired LAN technology due to its early deployment, simplicity, low cost, and constant evolution to higher data rates.
**Evolution of Topology:**
- **Past:** Bus topology (coaxial cable), which was a broadcast LAN.
- **Then:** Star topology with a **hub**. A hub is a physical-layer device that repeats bits to all other ports, making it also a **broadcast LAN** where collisions occur.
- **Now:** Star topology with a **switch**. A switch is a link-layer device that is "collision-less" and can forward frames intelligently.

#### **Ethernet Frame Structure**
The Ethernet frame has several key fields:
- **Preamble (8 bytes):** The first 7 bytes (10101010) synchronize the receiver's clock. The last byte (10101011) alerts the receiver that the frame is starting.
- **Destination Address (6 bytes):** The MAC address of the destination adapter.
- **Source Address (6 bytes):** The MAC address of the sending adapter.
- **Type Field (2 bytes):** Essential for **multiplexing/demultiplexing**. It indicates which network-layer protocol (e.g., IP, ARP) is contained in the data field. This is the link-layer equivalent of the transport-layer port number or network-layer protocol field.
- **Data Field (46 to 1,500 bytes):** Carries the IP datagram (or other network-layer packet). This defines the Ethernet **MTU (Maximum Transmission Unit)**. If the data is less than 46 bytes, it is "stuffed" to meet the minimum.
- **CRC (Cyclic Redundancy Check) (4 bytes):** Used for **error detection**. The receiving adapter discards the frame if an error is detected.
#### **Ethernet Services**
- **Connectionless:** No handshake is performed before sending a frame.
- **Unreliable:** The receiving adapter does **not** send acknowledgments for correctly received frames. It simply discards frames that fail the CRC check.
**Implication for Higher Layers:**
- If a frame is dropped, there is no Ethernet-level retransmission.
- **UDP:** The application would see a gap in the data.
- **TCP:** TCP would notice the missing data (via lack of ACK) and retransmit it. The retransmitted data would be sent in a new Ethernet frame, so reliability is achieved at a higher layer.
### **Ethernet Technologies**
Ethernet is not a single standard but a family of technologies standardized by IEEE 802.3. The naming convention provides key information:
- **Speed:** The first number (10, 100, 1000, 10G, 40G) indicates the data rate in Mbps or Gbps.
- **BASE:** Stands for "baseband," meaning the physical medium carries only Ethernet traffic.
- **Media:** The final letter(s) indicates the physical medium (e.g., **T** for twisted-pair copper wire, various codes for fiber like LX, SX).
**Evolution and Key Characteristics:**
- **Original Ethernet:** Used a **bus topology** with coaxial cable (10BASE-2, 10BASE-5). It was a true broadcast LAN requiring the CSMA/CD protocol.
- **Modern Ethernet:** Uses a **star topology** with switches connected via twisted-pair copper or fiber-optic cables.
- **Backward Compatibility:** A key to Ethernet's success is that each new, faster standard (like Gigabit Ethernet) maintains the same **frame format** as the original. This allows for easy integration with existing equipment.
- **The Changing Role of MAC Protocol:** In modern, **switched, full-duplex** Ethernet networks, collisions are eliminated. Therefore, the **CSMA/CD protocol is often unnecessary**, even though the frame format remains unchanged.
### **Link-Layer Switches**
Switches are core components of modern LANs. They are **transparent** to hosts and routers—devices communicate with each other, not with the switch.
#### **Core Switch Functions**
1. **Forwarding:** Moving a frame received on one interface to the appropriate output interface(s) to reach its destination.
2. **Filtering:** Deciding whether to drop a frame (if it's on the correct segment) or to forward it.
3. **Buffering:** Temporarily storing frames when the output link is busy, preventing frame loss.
These functions are performed using a **switch table**.
#### **The Switch Table**
The switch table contains mappings to guide frame forwarding. Each entry typically includes:
- A **MAC Address**
- The **switch interface** that leads toward that MAC address
- A **timestamp** of when the entry was created
**Forwarding Logic:** When a frame arrives on interface `x` with destination MAC address `DD-DD-DD-DD-DD-DD`:
- **No Table Entry:** The switch **broadcasts** the frame to all interfaces _except `x`_.
- **Entry Matches Interface `x`:** The switch **filters** (discards) the frame, as the destination is already on the same LAN segment from which the frame came.
- **Entry Points to Interface `y` (different from `x`):** The switch **forwards** the frame only to the output buffer for interface `y`.
#### **Self-Learning (How the Table is Built)**
Switch tables are built **automatically**; they are **plug-and-play** devices with no need for manual configuration. The process is:
1. The switch table is initially empty.
2. For every incoming frame, the switch examines the **source MAC address** and:
    - Records that address in the table.
    - Notes the **interface** the frame arrived on.
    - Updates the **timestamp** for that entry.
3. The switch **ages out** entries that have not been refreshed after a period (the aging time). This purges addresses of devices that have been disconnected.
**Full-Duplex Operation:** Modern switches can send and receive on an interface simultaneously without interference.

### **Properties of Link-Layer Switching**
Using switches (instead of hubs or buses) provides significant advantages:
- **Elimination of Collisions:** Switches buffer frames, allowing each link to operate at its full speed without collisions. The maximum total throughput is the sum of all interface rates.
- **Heterogeneous Links:** Different switch interfaces can operate at different speeds (e.g., 1 Gbps, 100 Mbps) and over different media (copper, fiber), making it easy to mix old and new equipment.
- **Management:** Switches simplify network management. They can automatically detect and isolate malfunctioning adapters ("jabbering") and gather statistics for debugging and planning.
**Focus on Security: Switch Poisoning**
- In a normal switched LAN, a host only receives frames addressed to it, making sniffing difficult.
- **Switch Poisoning** is an attack where an attacker floods the switch with frames containing bogus source MAC addresses. This fills the switch table, causing it to **broadcast** most traffic, which the attacker can then sniff.
### **Switches vs. Routers**
This is a fundamental comparison between layer-2 and layer-3 packet forwarding devices.

|Feature|Switches (Layer-2)|Routers (Layer-3)|
|---|---|---|
|**Addressing**|Uses flat MAC addresses|Uses hierarchical IP addresses|
|**Plug-and-Play?**|**Yes** (self-learning)|**No** (requires IP configuration)|
|**Traffic Isolation**|Yes (via VLANs)|Yes (by default)|
|**Optimal Routing**|**No** (restricted to a spanning tree)|**Yes** (can use best path)|
|**Broadcast Storms**|Susceptible (broadcasts are forwarded)|Protects against them (blocks layer-2 broadcasts)|
|**Processing Speed**|Faster (processes up to layer-2)|Slower (processes up to layer-3)|

**When to Use Which?**
- **Switches** are ideal for **smaller networks** (a few hundred hosts) due to their plug-and-play nature and simplicity.
- **Routers** are necessary within **larger networks** (thousands of hosts) to provide robust traffic isolation, prevent broadcast storms, and enable intelligent routing.
### **Virtual Local Area Networks (VLANs)**
VLANs solve several problems in a large switched network by creating **logical broadcast domains** over a single physical switch infrastructure.
**Drawbacks of a Single Large Switched LAN:**
1. **Lack of Traffic Isolation:** Broadcast traffic (ARP, DHCP) must traverse the entire network, hurting performance and security.
2. **Inefficient Use of Switches:** A small group requires its own physical switch.
3. **Managing Users:** Moving a user to a different group requires physically reconnecting them to a different switch.
**How VLANs Work:**
- In a **port-based VLAN**, the network manager configures the switch's ports into separate groups. Each group is a separate VLAN (a separate broadcast domain).
- Frames are only delivered between ports belonging to the **same VLAN**.
**Connecting VLANs and Scaling**
- **Communication Between VLANs:** To allow communication between different VLANs (e.g., EE and CS), traffic must be routed between them. This is often done with a router or a layer-3 switch.
- **VLAN Trunking:** To connect VLANs that span **multiple physical switches**, a special **trunk port** is used.
    - A trunk port belongs to **all VLANs**.
    - The **802.1Q protocol** is used, which adds a **VLAN tag** to the Ethernet frame to identify which VLAN it belongs to as it crosses the trunk link. The tag is added by the sending switch and removed by the receiving switch.
**Other VLAN Types:**
- **MAC-based VLANs:** VLAN membership is based on a device's MAC address, not the physical port it is connected to.
- VLANs can also be defined by network-layer protocol (IP, IPv6) and can be extended across routers.
### **Link Virtualization: A Network as a Link Layer**
**Core Concept:** The Internet can treat an entire, complex network (like the telephone system or an MPLS network) as a single **virtual link**. From the perspective of Internet hosts and routers, this complex network appears to be a simple link-layer channel.
### **Multiprotocol Label Switching (MPLS)**
MPLS is a packet-switched, virtual-circuit network that blends concepts from circuit-switched networks with IP routing. From an Internet perspective, it is often viewed as a **link-layer technology** that interconnects IP devices.
#### **How MPLS Works**
- **The MPLS Header:** An MPLS-capable router adds a short MPLS header between the layer-2 and layer-3 (IP) headers. This header contains a **label**, which is used for forwarding.
- **Label-Switched Routers (LSRs):** MPLS-capable routers are called LSRs. They forward frames by looking up the **MPLS label** in a table, not by performing a longest-prefix match on the IP address. This makes forwarding simpler and faster.
- **The Path (Label-Switched Path - LSP):** A path through the MPLS network is pre-established, and labels are distributed using a signalling protocol (like RSVP-TE). Routers along the path have a table that maps an incoming label on one interface to an outgoing label on another.
#### **Key Advantages and Uses of MPLS**
The main value of MPLS is not raw speed but advanced **traffic management** and **traffic engineering**:
1. **Traffic Engineering:** MPLS allows network operators to override standard IP routing. It can force traffic to specific paths based on policy or performance, enabling **load balancing** across multiple paths that standard IP routing would not use.
2. **Fast Restoration:** MPLS can quickly reroute traffic over pre-computed backup paths in case of a link failure, improving network reliability.
3. **Virtual Private Networks (VPNs):** MPLS is widely used to implement VPNs, allowing an ISP to securely connect a customer's multiple networks while isolating their traffic from other users on the same infrastructure.
**Relationship to SDN:** MPLS provides many traffic engineering capabilities that can also be achieved using **Software-Defined Networking (SDN)** and generalized forwarding. The two technologies currently co-exist.
### **Data Center Networking**
**Purpose of Data Centers:**
- Deliver content (web pages, video) to users.
- Act as a massively-parallel computing infrastructure (e.g., for search indexing).
- Provide **cloud computing** services to other companies.
#### **Data Center Architectures**
**Basic Components:**
- **Hosts (Blades):** Commodity servers stacked in **racks** (20-40 per rack).
- **Top of Rack (TOR) Switch:** A switch at the top of each rack that interconnects its hosts and connects the rack to the rest of the data center network.
- **Border Router:** Connects the data center to the public Internet.
- **Load Balancer:** A critical piece of infrastructure that distributes incoming external requests to internal hosts.
**The Role of the Load Balancer:**
- Distributes requests to hosts to balance the load.
- Acts as a "layer-4 switch," making decisions based on IP address and port number.
- Provides a **NAT-like function**, translating between a public VIP (Virtual IP) and the private IPs of internal hosts. This hides the internal network structure for security.
**Hierarchical Architecture:**  
To scale to hundreds of thousands of hosts, data centers use a multi-tiered hierarchy of switches:
- **Border Router** -> **Access Routers** -> **Tier-1 Switches** -> **Tier-2 Switches** -> **TOR Switches (Tier-3)** -> **Hosts**.
- This design includes **redundancy** in links and equipment for high availability.
- The network is partitioned into **VLANs** containing a few hundred hosts to limit the scope of broadcast traffic (like ARP).
#### **The Host-to-Host Capacity Problem**
**The Bottleneck:** In a simple hierarchy, the links between switches (e.g., 100 Gbps) can become a bottleneck for traffic between hosts in different racks, even if each host has a fast (e.g., 10 Gbps) connection to its TOR switch. Many simultaneous cross-rack flows must share the capacity of the uplink connections.
**Solutions to the Capacity Problem:**
1. **Use Higher-Rate Switches:** This is very expensive.
2. **Locality:** Co-locate services and data that communicate frequently in the same rack or nearby racks. This is not always possible due to the need for flexible resource allocation.
3. **Increased Connectivity (The Primary Solution):** Provide multiple parallel paths between tiers.
    - For example, connect each TOR switch to _multiple_ Tier-2 switches, and each Tier-2 switch to _multiple_ Tier-1 switches.
    - This creates **path diversity**, increasing both **aggregate capacity** and **reliability**.
**Consequence: Multi-Path Routing**  
With multiple paths, data centres rely heavily on **multi-path routing**.
- **ECMP (Equal Cost Multi Path):** A common technique that performs a randomized next-hop selection for flows, spreading traffic across multiple paths.
- More advanced schemes can perform finer-grained load balancing, sometimes even routing packets from the _same flow_ across different paths.
### **Trends in Data Center Networking**
Data center design is driven by the goals of reducing cost, improving performance, and increasing flexibility. Key trends include:
#### **1. Hierarchical, Multi-Tiered Interconnection Networks**
- The standard architecture uses a hierarchy of switches (TOR, Tier-2, Tier-1) to create a massive, interconnected fabric.
- This is a realization of a **Clos network**, which provides multiple paths between any two hosts.
- **Benefits:** This design offers superior **capacity** (through multipath routing) and **reliability** (through path diversity) compared to a single, massive switch.
#### **2. Commodity Switches and Centralized (SDN) Control**
- Large operators often build their own switches using **commodity, off-the-shelf components** ("merchant silicon") to drastically reduce costs.
- Management is simplified by adopting an **SDN-like, logically centralized control plane**. This separates the simple data-plane switches from the intelligent software-based controller, enabling automated configuration and management at a massive scale.
#### **3. Virtualization and the "Single Switch" Abstraction**
- **Virtual Machines (VMs)** can be migrated between physical servers for load balancing and maintenance.
- To support this seamlessly, the entire data center network is often treated as a **single, flat layer-2 network**.
- **How it works:** Standard ARP broadcast is replaced with a **centralized directory service** (like DNS) that keeps track of which physical switch a VM's IP address is currently connected to. This creates the illusion that all hosts are connected to one giant switch.
#### **4. Addressing Physical Constraints**
- Data centers have **extremely high capacity** (40/100 Gbps links) and **microsecond-level delays**.
- This environment breaks traditional TCP, which reacts too slowly and suffers from inefficiencies in low-loss regimes.
- **Solutions include:**
    - **Data Center-specific TCP variants** that react faster to congestion.
    - **Remote Direct Memory Access (RDMA)** over Ethernet for ultra-low-latency communication.
    - **Advanced flow scheduling** techniques that separate scheduling from rate control.
#### **5. Hardware Modularity and Customization**
- **Modular Data Centers (MDCs):** Data centers are built from pre-fabricated shipping containers, each a "mini data center" with a few thousand hosts. This allows for rapid deployment.
- **Full Customization:** Large cloud providers now design and build their own hardware, including **network adapters, switches, and routers**, and develop their own software and protocols for optimal performance and cost.
- **Availability Zones:** To improve fault tolerance, providers replicate data centers in separate, nearby buildings. This allows for synchronous data replication while protecting against facility-level failures.
### **Retrospective: A Day in the Life of a Web Page Request**
This section provides an integrated view of how all the protocols from the link layer up to the application layer work together to perform a simple task: downloading a web page.
#### **Phase 1: Getting an IP Address (DHCP)**
Before anything else, Bob's laptop needs an IP address. This is done via DHCP.
1. **DHCP Discovery:** Bob's laptop creates a **DHCP request** message.
2. **Encapsulation:** The message is placed inside a **UDP** segment (ports 67/68), then an **IP** datagram (source: `0.0.0.0`, destination: `255.255.255.255`), and finally an **Ethernet** frame (destination: `FF:FF:FF:FF:FF:FF`).
3. **Broadcast:** The switch broadcasts the Ethernet frame. The router, which runs the DHCP server, receives it.
4. **DHCP Offer:** The DHCP server allocates an IP address (`68.85.2.101`) and sends a **DHCP ACK** back. This message also contains the IP addresses of the **DNS server** and the **default gateway**.
5. **Delivery:** The router sends the ACK in a frame addressed directly to Bob's laptop's MAC address. The switch, having learned Bob's MAC address, forwards it correctly.
6. **Configuration:** Bob's laptop records its IP address and configures its network settings.
#### **Phase 2: Finding the Web Server's IP Address (DNS & ARP)**
To connect to `www.google.com`, Bob's laptop needs its IP address, which requires DNS.
7. **DNS Query:** The OS creates a **DNS query** for `www.google.com`.
8. **Encapsulation:** The query is placed inside a **UDP** segment (port 53), then an **IP** datagram (destination: DNS server `68.87.71.226`).
9. **The ARP Problem:** To send this datagram, the laptop needs the **MAC address** of the default gateway (`68.85.2.1`), which it doesn't know.
10. **ARP Request:** The laptop broadcasts an **ARP query** frame asking "Who has `68.85.2.1`?"
11. **ARP Reply:** The gateway router replies with its MAC address (`00:22:6B:45:1F:1B`).
12. **Sending the DNS Query:** Bob's laptop can now send the DNS query frame to the gateway router's MAC address.
13. **Routing the Query:** The school router forwards the IP datagram through its network (using intra-domain routing protocols like OSPF) to the Comcast DNS server.
14. **DNS Reply:** The DNS server looks up the name and returns a **DNS reply** containing the IP address for `www.google.com` (`64.233.169.105`).
#### **Phase 3: Web Client-Server Interaction (TCP & HTTP)**
With the web server's IP address, Bob's browser can now fetch the page.
15. **TCP Handshake:** The browser creates a **TCP socket** and initiates a **three-way handshake** with `www.google.com`.
    - A **TCP SYN** segment is sent. It is encapsulated in an IP datagram and routed through the school, Comcast, and Google networks (using BGP for inter-domain routing).
    - The Google server responds with a **TCP SYNACK**.
    - Bob's laptop sends a **TCP ACK**. The connection is now established.
16. **HTTP Request/Response:**
    - The browser writes an **HTTP GET** request into the TCP socket.
    - The request is sent to the web server, which processes it.
    - The server sends back an **HTTP response** message containing the HTML of the web page.
17. **Rendering:** The datagram containing the HTTP response is routed back to Bob's laptop. His browser extracts the HTML and finally **displays the web page**.
### **Summary**
This chapter examined the **link layer**, which is responsible for moving a network-layer datagram from one node to an **adjacent node** over a single communication link.
#### **Core Concepts and Services**
- The fundamental service is **framing**: encapsulating a network-layer datagram within a link-layer frame for transmission.
- The specific services provided (e.g., link access, reliable delivery) vary greatly depending on the link type, such as:
    - **Point-to-point links:** A single sender and receiver.
    - **Broadcast (Multiple Access) links:** Shared by many senders, requiring a **Multiple Access Protocol** to coordinate access and avoid collisions.
    - **Virtual Links:** An entire network (like the telephone system or MPLS) can be treated as a single link-layer channel.
#### **Key Principles and Protocols**
1. **Error Detection and Correction:** Techniques like **Cyclic Redundancy Check (CRC)** add bits to the frame header to allow the receiver to detect, and sometimes correct, bit-level errors introduced during transmission.
2. **Multiple Access Protocols:** These protocols manage access to a shared broadcast channel and fall into three categories:
    - **Channel Partitioning:** Divides the channel (by time (TDM) or frequency (FDM)).
    - **Random Access:** Allows collisions and uses random backoff to recover (e.g., **ALOHA**, **CSMA/CD**).
    - **Taking Turns:** Coordinates nodes to avoid collisions (e.g., **polling**, **token-passing**).
3. **Link-Layer Addressing:** Devices have **MAC addresses**—flat, permanent physical addresses—unlike hierarchical, changeable IP addresses. The **Address Resolution Protocol (ARP)** is used to discover the MAC address associated with a given IP address on the same subnet.
4. **Switched Local Area Networks (LANs):**
    - **Ethernet** is the dominant wired LAN technology, using a simple, connectionless, and unreliable frame delivery service.
    - **Link-layer switches** are self-learning, plug-and-play devices that build forwarding tables to selectively forward frames, eliminating collisions and increasing aggregate throughput.
    - **Virtual LANs (VLANs)** allow a single physical switched network to be partitioned into multiple logical broadcast domains, providing traffic isolation and management flexibility.
5. **Link Virtualization:** Networks like **MPLS** can be used to interconnect IP routers, providing a virtual link-layer service with advanced capabilities like traffic engineering.
6. **Data Centre Networking:** Massive data centres use highly interconnected, hierarchical networks of commodity switches to connect hundreds of thousands of hosts, employing load balancers, multi-path routing, and SDN-like centralized control for scalability and performance.
#### **Holistic View**
The chapter concluded with a "day in the life" example, tracing a web page request through **DHCP, ARP, DNS, TCP, and HTTP**. This integrated the link layer with the network, transport, and application layers, demonstrating how all protocols work together to accomplish a common task.