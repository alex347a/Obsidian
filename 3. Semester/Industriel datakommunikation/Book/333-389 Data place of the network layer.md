IP

DHCP

NAT

### Overview of Network Layer

The network layer provides **host-to-host** communication service, unlike the transport layer's process-to-process service. This layer exists in **every host and router** in the network, making it complex and distributed.

#### Forwarding and Routing: Data Plane vs. Control Plane

The network layer is decomposed into two interacting parts:

1. **Data Plane (Forwarding):** The **router-local** action of transferring a packet from an input link to the appropriate output link. This happens at nanosecond timescales and is typically implemented in hardware.
    
    - **Analogy:** Getting through a single highway interchange.
        
2. **Control Plane (Routing):** The **network-wide** process that determines the end-to-end paths packets take from source to destination. This happens at second timescales and is often implemented in software.
    
    - **Analogy:** Planning the entire trip from Pennsylvania to Florida.
        

**Forwarding Tables:** Routers use **forwarding tables** to determine where to send packets. The router examines header fields in arriving packets, uses them to index into its forwarding table, and finds the appropriate output link interface. (INSERT FIGURE 4.2 HERE)

#### Control Plane Approaches

**Traditional Approach:**

- Each router has its own **routing component** that communicates with other routers' routing components using **routing protocols**.
    
- The routing algorithms determine the contents of the forwarding tables.
    
- Both forwarding (data plane) and routing (control plane) functions are contained within each router.
    

**SDN Approach (Software-Defined Networking):**

- A **physically separate, remote controller** computes and distributes forwarding tables to all routers.
    
- Routers only perform forwarding; the control logic is centralized in the remote controller.
    
- This separation allows for more flexible, software-based control of network functionality. (INSERT FIGURE 4.3 HERE)
    

#### Network Service Model

The network service model defines the characteristics of end-to-end packet delivery. Possible services include:

- Guaranteed delivery
    
- Guaranteed delivery with bounded delay
    
- In-order packet delivery
    
- Guaranteed minimal bandwidth
    
- Security (encryption/decryption)
    

**Internet's Service Model: Best-Effort Service**

- The Internet provides only **best-effort service** - packets are not guaranteed to arrive, arrive in order, or have bounded delay.
    
- Despite this minimal service model, when combined with adequate bandwidth and adaptive applications (like DASH for video streaming), it has proven sufficient for most applications including streaming video and real-time conferencing.

### **Terminology: Forwarding, Switching, Routers, and Switches**

The terms **forwarding** and **switching** are used interchangeably in networking.

However, it's important to distinguish between types of packet-switching devices:

- **Packet Switch:** A general term for any device that transfers a packet from an input link to an output link based on header fields.
    
- **Link-Layer Switch (Layer 2):** A packet switch that bases its forwarding decision on fields in the **link-layer** frame (e.g., an Ethernet MAC address).
    
- **Router (Layer 3):** A packet switch that bases its forwarding decision on fields in the **network-layer** datagram (e.g., an IP address).
    

Since this chapter focuses on the network layer, we will primarily use the term **router**.

### **What’s Inside a Router?**

A router's primary job is to forward packets from an incoming link to the appropriate outgoing link. Its architecture consists of four main components: (INSERT FIGURE 4.4, ROUTER ARCHITECTURE, HERE)

1. **Input Ports:** This is where an incoming physical link connects. It performs several key functions:
    
    - **Physical and Link-Layer Processing:** Terminates the physical link and handles the data link protocol (e.g., Ethernet).
        
    - **Lookup Function:** The most critical step. Here, the **forwarding table** is consulted to determine the output port for an arriving packet. This decision must be made in nanoseconds.
        
    - Control packets (e.g., for routing protocols) are sent to the routing processor.
        
2. **Switching Fabric:** The "network inside the router" that connects the input ports to the output ports. It is responsible for moving packets across the router internally.
    
3. **Output Ports:** This component receives packets from the switching fabric and transmits them onto the outgoing link. It stores packets in a queue if they arrive faster than the transmission rate and performs the necessary link-layer and physical-layer functions.
    
4. **Routing Processor:** This executes the **control-plane** functions.
    
    - In traditional routers, it runs routing protocols, maintains routing tables, and computes the **forwarding table**.
        
    - In SDN routers, it communicates with a remote controller to receive forwarding table entries.
        
    - These functions operate on a much slower timescale (milliseconds/seconds) and are typically implemented in software.
        

**Hardware vs. Software:** The data plane (input ports, switching fabric, output ports) is implemented in hardware to achieve nanosecond-speed operations. The control plane is implemented in software on the routing processor.

### **Input Port Processing and Destination-Based Forwarding**

A detailed view of input port processing shows the steps: line termination, data-link processing, and the crucial lookup/forwarding function. (INSERT FIGURE 4.5, INPUT PORT PROCESSING, HERE)

The forwarding table is copied from the routing processor to the input ports, allowing them to make local, high-speed forwarding decisions without creating a central bottleneck.

**The Lookup Problem**  
A brute-force forwarding table with an entry for every possible IP address (over 4 billion) is not feasible. Instead, routers use **prefixes** to represent ranges of addresses.

**Longest Prefix Matching (LPM)**  
The forwarding table contains entries for network prefixes. A packet's destination address is matched against these prefixes. The key rule is **longest prefix matching**: the router forwards the packet based on the entry with the _longest_ (i.e., most specific) matching prefix.

- **Example:** A packet with destination address `11001000 00010111 00010110 10100001` is matched against the table. It matches the first entry (`/21`) and the third entry (`/16`). The **longest prefix match** is the first entry (`/21`), so the packet is forwarded to link interface 0. (INSERT A TABLE ILLUSTRATING LONGEST PREFIX MATCHING, LIKE THE ONE IN THE TEXT, HERE)
    

This lookup must be done in nanoseconds. Routers use specialized hardware and algorithms, such as **Ternary Content Addressable Memories (TCAMs)**, which can perform a lookup in constant time.

**Other Input Port Actions**  
Besides lookup, input ports also:

- Verify and update checksums.
    
- Decrement the Time-To-Live (TTL) field.
    
- Update network management counters.
    

**The "Match Plus Action" Abstraction**  
The input port operation—matching a header field and then taking an action (like forwarding, dropping, or modifying)—is a powerful, general abstraction used in many network devices, including switches, firewalls, and NATs. This is central to **generalized forwarding**.

### **Switching**

The switching fabric is the "heart" of the router, physically moving packets from an input port to an output port. There are three primary ways to implement switching: (INSERT FIGURE 4.6, THREE SWITCHING TECHNIQUES, HERE)

1. **Switching via Memory:**
    
    - The earliest routers were essentially computers. The routing processor (CPU) directly controlled the switch.
        
    - When a packet arrived, it was copied into the main memory of the router. The CPU would then extract the destination address, look up the output port, and copy the packet to the output port's buffer.
        
    - **Limitation:** The switching speed is limited by the memory bandwidth, and only one packet can be moved at a time.
        
    - In modern routers that use this method, the lookup and switching are handled by processors on the input line cards, making it more like a shared-memory multiprocessor.
        
2. **Switching via a Bus:**
    
    - The input port transfers a packet directly to the output port over a shared bus, without the routing processor's intervention.
        
    - The input port pre-pends an internal "switch label" (header) to the packet indicating the desired output port. All output ports see the packet, but only the one matching the label keeps it.
        
    - **Limitation:** The **bus speed becomes the bottleneck**, as only one packet can cross the bus at a time. This is like a roundabout that can only hold one car.
        
3. **Switching via an Interconnection Network:**
    
    - To overcome the bandwidth limit of a single bus, a **crossbar switch** can be used. It is a network of `2N` busses connecting `N` input ports to `N` output ports.
        
    - **Advantage:** It is **non-blocking**, meaning it can forward multiple packets in parallel simultaneously, as long as they are destined for _different_ output ports.
        
    - If two packets from different inputs are destined for the _same_ output, one will be blocked because only one packet can be sent over an output bus at a time.
        
    - High-end routers use even more sophisticated multi-stage interconnection networks to increase capacity.
        

### **Output Port Processing**

Output port processing takes packets that have been switched through the fabric and transmits them onto the outgoing link. Its key functions are:

- **Queuing:** Storing packets that have arrived faster than the transmission rate.
    
- **Scheduling:** Selecting which packet to transmit next from the queue.
    
- **Link & Physical Layer Processing:** Performing the necessary operations to send the packet out on the wire. (INSERT FIGURE 4.7, OUTPUT PORT PROCESSING, HERE)
    

### **Where Does Queuing Occur?**

Queuing happens when the rate of incoming packets exceeds the rate at which they can be processed. The location of the queues is critical for performance and can lead to **packet loss** if buffers become full.

**A. Input Queuing**

- **Scenario:** The switching fabric is slower than the combined input line speeds.
    
- **Problem: Head-of-the-Line (HOL) Blocking:** This occurs when a packet at the front of an input queue is blocked because it is destined for a busy output port. This single blocked packet also prevents _other packets behind it_ in the same queue from being forwarded, even if _their_ destined output ports are free. (INSERT FIGURE 4.8, HOL BLOCKING, HERE)
    
- HOL blocking can severely limit a switch's throughput.
    

**B. Output Queuing**

- **Scenario:** The switching fabric is faster than the individual output line speeds.
    
- **Problem:** Packets arriving simultaneously from _multiple_ input ports and destined for the _same_ output port must be queued at that output port. If the queue (buffer) fills up, packets must be dropped.
    
- **Packet-Dropping Policies:**
    
    - **Drop-tail:** Simply drops an arriving packet if the queue is full.
        
    - **Active Queue Management (AQM):** Proactively drops or marks packets _before_ the buffer is completely full to signal congestion to the sender. Examples include **Random Early Detection (RED)** and more modern algorithms like **PIE** and **CoDel**. (INSERT FIGURE 4.9, OUTPUT PORT QUEUING, HERE)