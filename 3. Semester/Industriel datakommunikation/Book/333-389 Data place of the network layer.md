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
### **How Much Buffering is "Enough"?**
The amount of buffering (memory) in a router is a critical design choice. While more buffering can absorb traffic bursts and reduce packet loss, it also increases queuing delay.
- **Old Rule of Thumb:** The buffer size (B) should be equal to the link capacity (C) multiplied by the average round-trip time (RTT). For a 10 Gbps link with a 250 ms RTT, this would be **B = RTT * C = 2.5 Gbits**.
- **Modern Understanding:** This rule was based on a small number of TCP flows. With a large number of independent flows (N) passing through a core router link, the needed buffer size is much smaller: **B = (RTT * C) / √N**.
- **The Double-Edged Sword of Buffering:** More buffering decreases packet loss but increases delay. For interactive applications like gaming and video conferencing, increased delay is very harmful. Too much buffering can also make TCP congestion control less responsive.
### **Bufferbloat**
This is a problem where excessively large buffers in network links (often at the network edge, like in home routers) cause persistently high delays, even when the network is not heavily congested.
- **Scenario:** Imagine a home gamer with a slow uplink. A burst of packets fills the home router's large buffer. Due to TCP's "ACK clocking" mechanism, a new packet arrives to refill the buffer every time a packet is transmitted, maintaining a constant, large queue.
- **Result:** The link is fully utilized, but packets experience a consistently high queuing delay, making interactive applications unusable, even though there is no "congestion" in the traditional sense. (INSERT FIGURE 4.10, BUFFERBLOAT, HERE)
- **Solution:** Active Queue Management (AQM) algorithms like PIE and CoDel are designed to combat bufferbloat by keeping queuing delays short.
### **Packet Scheduling**
The packet scheduler at the output port determines the order in which queued packets are transmitted. Different disciplines provide different services.

**First-In-First-Out (FIFO)**
- The simplest method. Packets are transmitted in the exact order they arrive.
- If the queue is full, the packet-discarding policy (e.g., drop-tail) determines which packet is lost. (INSERT FIGURE 4.11 & 4.12, FIFO QUEUING, HERE)

**Priority Queuing**
- Packets are classified into priority classes upon arrival, each with its own queue.
- The scheduler _always_ transmits a packet from the highest-priority queue that has a packet. Only when that queue is empty does it serve the next lower-priority queue.
- **Non-preemptive:** Once a packet starts transmission, it is not interrupted, even if a higher-priority packet arrives. (INSERT FIGURE 4.13 & 4.14, PRIORITY QUEUING, HERE)

**Round Robin and Weighted Fair Queuing (WFQ)**
- **Round Robin:** The scheduler cycles through the class queues, serving one packet from each class in turn. It is **work-conserving**, meaning it will skip an empty queue and move to the next. (INSERT FIGURE 4.15, ROUND ROBIN QUEUING, HERE)
- **Weighted Fair Queuing (WFQ):** A generalized form of round robin. Each class `i` is assigned a weight `w_i`.
    - WFQ guarantees that each class `i` will receive a _minimum_ fraction of the link bandwidth equal to `w_i / (sum of all weights of classes with packets)`.
    - This allows an Internet Provider to give different service guarantees to different traffic types or customers. (INSERT FIGURE 4.16, WEIGHTED FAIR QUEUING, HERE)
### **PRINCIPLES IN PRACTICE: Net Neutrality**
Packet scheduling mechanisms (like Priority Queuing and WFQ) allow ISPs to provide different levels of service to different "classes" of traffic. This capability is at the heart of the **net neutrality** debate.
**What is Net Neutrality?**  
The principle that an Internet Service Provider (ISP) should treat all data on the internet the same, without discriminating or charging differently based on user, content, website, or platform.
**Key Rules often associated with Net Neutrality:**
- **No Blocking:** ISPs cannot block lawful content, applications, or services.
- **No Throttling:** ISPs cannot deliberately slow down (throttle) specific internet traffic.
- **No Paid Prioritization:** ISPs cannot create "fast lanes" for companies that pay extra, while leaving others in a "slow lane."

**The Debate:**
- **Pro-Neutrality:** Argues it promotes innovation and prevents ISPs from abusing their power as gatekeepers.
- **Against Strict Regulation:** Argues that it reduces investment and prevents ISPs from managing their networks efficiently or offering new service tiers.

The legal and regulatory landscape for net neutrality continues to evolve.
### **The Internet Protocol (IP): IPv4, Addressing, IPv6, and More**

This section focuses on the specific protocols of the Internet's network layer, primarily the **Internet Protocol (IP)**. The two main versions are **IPv4** (the currently dominant version) and **IPv6** (its successor).
### **IPv4 Datagram Format**
The Internet's network-layer packet is called a **datagram**. The IPv4 datagram format is crucial to understand. Its key fields are as follows: (INSERT FIGURE 4.17, IPV4 DATAGRAM FORMAT, HERE)
- **Version (4 bits):** Specifies the IP protocol version (4 for IPv4). This allows routers to know how to interpret the rest of the datagram.
- **Header Length (4 bits):** Indicates where the header ends and the data begins, as the IP header can be variable length due to options. A typical header with no options is 20 bytes.
- **Type of Service (TOS) (8 bits):** Originally intended to allow different types of datagrams (e.g., real-time vs. non-real-time) to be distinguished. Two bits are now used for **Explicit Congestion Notification (ECN)**.
- **Datagram Length (16 bits):** The total length of the datagram (header + data) in bytes. The maximum size is 65,535 bytes, but most are around 1,500 bytes to fit inside an Ethernet frame.
- **Identifier, Flags, Fragmentation Offset (16 + 3 + 13 bits):** These fields are used for **IP fragmentation**, where a large datagram is broken into smaller pieces for transmission and reassembled at the destination. (IPv6 does not allow fragmentation).
- **Time-to-Live (TTL) (8 bits):** Prevents datagrams from circulating forever. Each router decrements this field by one. If it reaches zero, the router discards the datagram.
- **Protocol (8 bits):** Indicates the specific transport-layer protocol to which the data should be passed (e.g., 6 for TCP, 17 for UDP). This "glues" the network layer to the transport layer.
- **Header Checksum (16 bits):** Aids a router in detecting bit-level errors in the received IP datagram header. It is recomputed at every router because fields like TTL change.
- **Source and Destination IP Addresses (32 bits each):** The fundamental addresses that define the sending and receiving hosts.
- **Options (variable length):** Allows the header to be extended for special features. Used rarely, as they complicate processing. They were removed in IPv6.
- **Data (Payload):** The primary purpose of the datagram! This typically contains a transport-layer segment (TCP or UDP).

A typical IP datagram carrying a TCP segment has 40 bytes of header (20 bytes of IP header + 20 bytes of TCP header) before the application data.
### **IPv4 Addressing**
IP addressing is a subtle and central topic for understanding the Internet.
**Interfaces and Addresses**
- A host or router connects to a physical link via an **interface**.
- A host typically has one interface; a router has multiple interfaces (one for each link).
- An **IP address is associated with an interface**, not the host or router itself.
- Every interface on the global Internet must have a globally unique IP address (with some exceptions like NAT).

**IP Address Structure**
- An IPv4 address is **32 bits long** (about 4 billion possible addresses).
- They are written in **dotted-decimal notation** (e.g., `193.32.216.9`), where each number represents one byte (8 bits) of the address.

**Subnets**  
A **subnet** (or "IP network") is a group of interconnected interfaces that can communicate directly without passing through a router.
- **How to identify a subnet:** Interfaces on the same subnet have a common prefix of bits in their IP addresses.
- **Subnet Address:** A subnet is given an address, written as `a.b.c.d/x`, where `/x` (the **subnet mask**) indicates the number of bits in the common prefix.
- **Example:** In the diagram, the hosts and router interface with addresses `223.1.1.1`, `223.1.1.2`, `223.1.1.3`, and `223.1.1.4` all share the leftmost 24 bits. They form the subnet `223.1.1.0/24`. (INSERT FIGURE 4.18, IP ADDRESSING AND INTERFACES, HERE)

**Subnets Beyond Simple LANs**  
Subnets are not just for Ethernet LANs. A point-to-point link between two routers also forms a subnet, typically with a `/24` or `/30` prefix. (INSERT FIGURES 4.19 & 4.20, ILLUSTRATING SUBNETS IN MORE COMPLEX TOPOLOGIES, HERE)

**The General Rule for Defining Subnets:**  
To find the subnets in an interconnected system, detach each interface from its host or router, creating isolated "islands" of networks. Each of these islands is a subnet.
### **Classless Inter-Domain Routing (CIDR)**
The original IP addressing scheme, known as **classful addressing**, required subnets to be 8, 16, or 24 bits long (Class A, B, and C). This was inflexible and wasted addresses.
**CIDR** (Classless Inter-Domain Routing) was introduced to solve this. It has two key features:
1. The prefix length (`/x`) in a subnet address is arbitrary, not just 8, 16, or 24.
2. It enables **address aggregation** (or route summarization), which dramatically reduces the size of routing tables in the Internet.

**How Address Aggregation Works:**
- An ISP is allocated a large block of addresses (e.g., `200.23.16.0/20`).
- The ISP can then divide this block into smaller, contiguous sub-blocks for its customer organizations (e.g., `200.23.18.0/23` for Organization 1).
- The ISP then **advertises to the rest of the Internet** only the single, aggregated prefix `200.23.16.0/20`.
- This means routers outside the ISP only need one entry to reach all eight organizations, instead of eight separate entries. (INSERT FIGURE 4.21, HIERARCHICAL ADDRESSING AND ROUTE AGGREGATION, HERE)

**The Exception: Longest Prefix Matching**  
Aggregation works perfectly when addresses are allocated hierarchically. But what if an organization changes ISPs and keeps its old IP addresses?
- In this case, the organization's original ISP (ISPs-R-Us) must advertise a _more specific route_ to that organization's block (e.g., `200.23.18.0/23`).
- Other routers in the Internet will use the **longest prefix matching** rule. A packet destined for this organization will be sent to ISPs-R-Us because its `/23` advertisement is a longer (more specific) match than the original ISP's `/20` advertisement. (INSERT FIGURE 4.22, ILLUSTRATING THIS SCENARIO, HERE)

**Special Address: IP Broadcast**
- The address `255.255.255.255` is the **limited broadcast address**. A datagram sent to this address is delivered to all hosts on the same subnet. Routers typically do not forward these packets.
### **Obtaining a Block of Addresses**
- An organization gets its block of IP addresses from an **Internet Service Provider (ISP)**.
- The ISP, in turn, gets a larger block from a **Regional Internet Registry (RIR)**.
- The ultimate global authority responsible for managing the IP address space, DNS root servers, and domain names is **ICANN** (Internet Corporation for Assigned Names and Numbers).
### **Obtaining a Host Address: The Dynamic Host Configuration Protocol (DHCP)**
Manually configuring IP addresses on hosts is impractical. **DHCP** automates this process and is known as a **plug-and-play** or **zero-configuration** protocol.

**What DHCP Provides:**  
A DHCP server can provide a host with:
- Its **IP address**.
- Its **subnet mask**.
- The address of its **first-hop router** ("default gateway").
- The address of its **local DNS server**.

**DHCP Operation (Client-Server Protocol):**
- A newly connected host (the client) needs to obtain an IP address.
- In the simplest case, each subnet has its own DHCP server.
- If no server is on the subnet, a **DHCP relay agent** (typically a router on the subnet) knows the address of a DHCP server and will forward DHCP messages between the client and server. (INSERT FIGURE 4.23, DHCP CLIENT-SERVER SCENARIO, HERE)
### **DHCP Protocol Operation**
DHCP is a four-step process that allows a client to automatically obtain an IP address and other network configuration parameters. The client and server exchange the following messages, often using broadcast addresses since the client doesn't have an IP address initially: (INSERT FIGURE 4.24, DHCP CLIENT-SERVER INTERACTION, HERE)
1. **DHCP Discover:** The client broadcasts a **DHCPDISCOVER** message to find available DHCP servers. The source IP is `0.0.0.0` and the destination is `255.255.255.255`.
2. **DHCP Offer:** A DHCP server that receives the discover message responds with a **DHCPOFFER** message. This message is broadcast back to the client and contains the offered IP address, subnet mask, lease time (how long the address is valid), and other parameters.
3. **DHCP Request:** The client chooses one of the offers and broadcasts a **DHCPREQUEST** message, specifying the server it has selected.
4. **DHCP ACK:** The chosen server responds with a **DHCPACK** message, confirming the assignment. The client can now use the IP address for the duration of the lease.

**Shortcoming:** DHCP is not well-suited for mobility. When a host moves to a new subnet, it gets a new IP address, breaking any ongoing TCP connections.
### **Network Address Translation (NAT)**
NAT is a technique that allows a single device (like a home router) to act as an agent between a private local network and the public Internet. This enables multiple devices in a private network to share a single, public IP address.

**How NAT Works:**
- **Private Addresses:** Devices within the home network use IP addresses from a **private address space** (e.g., `10.0.0.0/8`, `192.168.0.0/16`). These addresses are not globally unique and are only meaningful within the local network.
- **Public Address:** The NAT router has a single public IP address on its WAN side (e.g., `138.76.29.7`), which is used for all communication with the outside world.
- **The NAT Translation Table:** This is the key to the operation. The router maintains a table that maps `(private IP, private port)` to `(public IP, public port)` for every ongoing connection. (INSERT FIGURE 4.25, NETWORK ADDRESS TRANSLATION, HERE)

**The NAT Process (Step-by-Step):**
1. A host inside the network (e.g., `10.0.0.1:3345`) sends a packet to a web server (`128.119.40.186:80`).
2. The NAT router intercepts the packet, creates a new source port (e.g., `5001`), and rewrites the packet header so the source is now `138.76.29.7:5001`. It adds an entry `(10.0.0.1, 3345) <-> (138.76.29.7, 5001)` to its translation table.
3. The web server replies to `138.76.29.7:5001`.
4. The NAT router receives the reply, looks up port `5001` in its table, and rewrites the destination header to `10.0.0.1:3345` before forwarding it into the home network.

**Arguments Against NAT:**
- **Violates Layering:** Routers are supposed to operate at the network layer, but NAT modifies port numbers, which are a transport-layer concept.
- **Breaks End-to-End Principle:** It interferes with the idea that hosts should be able to communicate directly. It can cause problems for peer-to-peer applications and servers running inside the private network.
### **IPv6**
The primary motivation for developing IPv6 was the imminent exhaustion of the 32-bit IPv4 address space. IPv6 uses **128-bit addresses**, creating an enormous address space.
**Key Changes in IPv6:**
- **Expanded Addressing:** 128-bit addresses, ensuring virtually unlimited addresses for the foreseeable future. It also introduces **anycast** addresses, which allow a packet to be delivered to any one member of a group of hosts.
- **Streamlined 40-Byte Header:** The IPv6 header has a fixed length of 40 bytes, making router processing faster. Several IPv4 fields (like header checksum, fragmentation fields) have been removed or made optional.
- **Flow Labelling:** A field to label packets belonging to the same "flow" (a series of packets from a source to a destination) for which special handling may be required.
### **FOCUS ON SECURITY: Firewalls and Intrusion Detection Systems**
To protect a network from malicious packets, administrators use:
- **Firewalls:** Sit at the network boundary and inspect packet headers. They can block packets based on IP addresses, port numbers, or even the state of TCP connections. They are a first line of defence.
- **Intrusion Detection Systems (IDS):** Perform **deep packet inspection**, examining the payload of packets for signatures of known attacks. They create alerts when a match is found.
- **Intrusion Prevention Systems (IPS):** Similar to an IDS, but can also actively block malicious packets.

These systems cannot protect against all attacks, especially new, unknown ones (zero-day exploits), but they are crucial for defending against known threats.
### **IPv6 Datagram Format**
The IPv6 datagram format was designed for efficiency and to accommodate the much larger 128-bit address space. Its key fields are: (INSERT FIGURE 4.26, IPV6 DATAGRAM FORMAT, HERE)
- **Version (4 bits):** Set to 6 for IPv6.
- **Traffic Class (8 bits):** Similar to IPv4's TOS field, used for distinguishing between different classes of traffic.
- **Flow Label (20 bits):** Used to identify packets belonging to the same "flow" (a series of packets from a source to a destination) that may require special handling.
- **Payload Length (16 bits):** The length of the data (payload) following the 40-byte header.
- **Next Header (8 bits):** Identifies the protocol (e.g., TCP, UDP) to which the payload will be delivered. It also replaces IPv4's Options field.
- **Hop Limit (8 bits):** Same as IPv4's TTL field. Decremented by each router; the packet is dropped if it reaches zero.
- **Source & Destination Addresses (128 bits each):** The new, much larger IP addresses.
- **Data:** The payload, e.g., a transport-layer segment.

**Fields Removed in IPv6:**  
To streamline the header and speed up router processing, IPv6 removed several IPv4 features:
- **Fragmentation/Reassembly:** IPv6 does **not** allow routers to fragment packets. If a packet is too large for a link, the router drops it and sends an ICMP error message back to the sender, which must then retransmit with a smaller size.
- **Header Checksum:** Removed to avoid the cost of recalculating it at every hop. Reliability is left to the data-link layer and the transport layer (e.g., TCP).
- **Options Field:** Replaced by the **Next Header** field, which can point to an optional "extension header," making the base header a fixed, simple 40 bytes.
### **Transitioning from IPv4 to IPv6**
A "flag day" where the entire Internet switches over at once is impossible. The most widely adopted transition technique is **tunneling**.
**Tunneling:**
- **Concept:** Allows IPv6 packets to travel over an IPv4 network by **encapsulating** the entire IPv6 datagram inside an IPv4 datagram as its payload.
- **Process:** The IPv6 node on the sending side of the tunnel places the IPv6 packet into the data field of an IPv4 packet. The IPv4 packet is addressed to the IPv6 node on the receiving end of the tunnel. The IPv4 routers in between forward this packet normally, unaware of the IPv6 packet inside. The receiving IPv6 node then extracts and processes the original IPv6 datagram. (INSERT FIGURE 4.27, TUNNELING, HERE)

**A Key Lesson:** Changing the network layer is extremely difficult and slow (like replacing a house's foundation), while deploying new application-layer protocols is fast and easy (like painting the house).
### **Generalized Forwarding and SDN**
The traditional "match-plus-action" model, where a router matches a destination IP address and forwards to an output port, is a specific case of a more powerful, **generalized forwarding** paradigm.

**The Generalized "Match-plus-Action" Abstraction:**
- **Match:** Can be performed on **multiple header fields** from different layers (e.g., source IP, destination IP, transport protocol, port numbers).
- **Action:** Can be much more than simple forwarding. Actions include:
    - Forward to one or more ports.
    - Drop (block) the packet (firewall).
    - Rewrite header fields (NAT).
    - Send to a special server for processing.

This abstraction is central to **Software-Defined Networking (SDN)**. In this model, a physically separate, **remote controller** computes, installs, and updates the forwarding tables in all the packet switches. (INSERT FIGURE 4.28, GENERALIZED FORWARDING, HERE)

**OpenFlow and Flow Tables**  
OpenFlow is a key SDN standard that implements this abstraction. Its forwarding table is called a **flow table**. Each entry in the flow table contains:
1. **A set of header field values to match** against incoming packets.
2. **A set of counters** to track the number of matched packets.
3. **A set of actions** to be taken on matching packets (e.g., forward, drop, modify).

This flow table is the API through which the behaviour of the entire network can be programmed.
### **Generalized Forwarding: Match and Action**
The power of generalized forwarding in SDN comes from its flexible "match-plus-action" abstraction, as implemented in standards like OpenFlow.
#### **Match**
OpenFlow allows a packet switch to match on a wide range of header fields from multiple layers, defying strict protocol layering to provide great flexibility. The matchable fields in OpenFlow 1.0 include: (INSERT FIGURE 4.29, PACKET MATCHING FIELDS, HERE)
- **Link Layer (Layer 2):**
    - **Source/Destination MAC Address:** The hardware addresses of the network interfaces.
    - **Ethernet Type:** Identifies the upper-layer protocol (e.g., IP).
    - **VLAN ID/Priority:** Fields related to Virtual LANs.
- **Network Layer (Layer 3):**
    - **Source/Destination IP Address:** The IP addresses.
    - **IP Protocol:** The transport-layer protocol (e.g., TCP, UDP).
    - **IP Type of Service (TOS):** The service type bits.
- **Transport Layer (Layer 4):**
    - **TCP/UDP Source/Destination Port:** The application-layer port numbers.
- **Ingress Port:** The physical input port on the switch where the packet arrived.

**Additional Features:**
- **Wildcards:** Can be used to match on prefixes (e.g., `128.119.*.*`).
- **Priority:** If a packet matches multiple flow table entries, the one with the highest priority is selected.

The set of matchable fields is a carefully chosen abstraction—powerful enough to implement many functions without being so complex it becomes unusable.
#### **Action**
When a packet matches a flow table entry, a set of actions is executed. Key actions include:
- **Forward:** Send the packet to a specific physical output port, broadcast it, or send it to the remote controller for further decision-making.
- **Drop:** Discard the packet (a fundamental firewall action).
- **Modify-field:** Rewrite the values in certain header fields (e.g., for Network Address Translation - NAT).
### **OpenFlow Examples of Match-plus-Action**
Let's see how match-plus-action rules can be used to implement different network-wide behaviors in a sample network. (INSERT FIGURE 4.30, OPENFLOW NETWORK, HERE)

**Example 1: Simple, Custom Forwarding**
- **Goal:** Route traffic from h5/h6 to h3/h4 via the path s3 -> s1 -> s2, avoiding the direct s3-s2 link.
- **Implementation:**
    - **s1's Flow Table:** Matches packets coming from ingress port 1 (from s3) with a source in `10.3.*.*` and a destination in `10.2.*.*`. The action is to **forward** them out port 4 (towards s2).
    - **s3's Flow Table:** Matches packets with the same IP criteria. The action is to **forward** them out port 3 (towards s1).
    - **s2's Flow Table:** Has specific entries to deliver the packets to the correct final host (h3 or h4) based on the destination IP.

**Example 2: Load Balancing**
- **Goal:** Balance traffic to `10.1.*.*` from h3 and h4 over different paths. Traffic from h3 should take the direct s2->s1 path, while traffic from h4 should take the s2->s3->s1 path.
- **Implementation:**
    - **s2's Flow Table:**
        - Match: Ingress port = 3 (from h3) AND IP Dst = `10.1.*.*` -> Action: **Forward(2)** (to s1).
        - Match: Ingress port = 4 (from h4) AND IP Dst = `10.1.*.*` -> Action: **Forward(1)** (to s3).
    - This demonstrates forwarding based on both the input port _and_ the destination address, which is impossible with traditional destination-based forwarding.

**Example 3: Firewalling**
- **Goal:** On s2, only allow incoming traffic that originates from hosts attached to s3 (`10.3.*.*`).
- **Implementation:**
    - **s2's Flow Table:** Contains entries that **forward** traffic only if the IP source is `10.3.*.*`. If there are no other permissive entries, all other traffic is effectively **dropped** by default.
### **Beyond Flow Tables: The P4 Language**
Flow tables represent a limited form of programmability. An even more advanced approach is to use a full programming language for defining how packets are processed.
- **P4 (Programming Protocol-independent Packet Processors):** This is a high-level language designed for programming the data plane of network devices.
- It allows network operators to define their own packet processing logic using variables, functions, and conditionals, providing ultimate flexibility beyond pre-defined match-action rules.