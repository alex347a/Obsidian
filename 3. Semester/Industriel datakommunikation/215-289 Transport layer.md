### Introduction and Transport-Layer Services

The transport layer is a central piece of the network architecture, residing between the application and network layers. It provides communication services directly to application processes running on different hosts.

**Logical Communication:**  
The transport layer provides **logical communication** between application processes. From the application's perspective, it seems as if the hosts are directly connected, even if they are on opposite sides of the planet connected via numerous routers. This abstraction frees applications from worrying about the underlying physical infrastructure.
![[3.1.png]]

**Key Points:**
- Transport-layer protocols are implemented **only in end systems**, not in network routers.
- On the sending side, the transport layer:
    1. Receives application-layer messages.
    2. Breaks them into smaller chunks.
    3. Adds a transport-layer header to each chunk, creating a **transport-layer segment**.
    4. Passes the segment to the network layer for encapsulation into a datagram.
- Routers only examine network-layer fields in the datagram; they do not process the transport-layer segment inside.
- On the receiving side, the network layer extracts the transport-layer segment and passes it up to the transport layer, which then delivers the data to the receiving application.

**Available Protocols:**  
The Internet provides multiple transport-layer protocols, primarily:
- **TCP (Transmission Control Protocol)**
- **UDP (User Datagram Protocol)**

Each offers a different set of services to applications. This chapter will explore the principles behind these protocols, focusing on reliability and congestion control, and how they are implemented in UDP and TCP.
### Relationship Between Transport and Network Layers
The transport layer resides directly above the network layer. While both provide logical communication, their scope is fundamentally different:
- **Network Layer:** Provides logical communication **between hosts**.
- **Transport Layer:** Provides logical communication **between processes** (applications) running on those hosts.
#### Household Analogy
This relationship is illustrated with a household analogy (and in Figure 3.1):
- **Houses** = **Hosts** (End systems)
- **Cousins** in each house = **Application processes**
- **Letters** in envelopes = **Application messages**
- **Ann and Bill** (the mail handlers in each house) = **Transport-layer protocol**
- **Postal Service** = **Network-layer protocol**

**How it works:**
1. Ann collects letters from her siblings (processes) and gives them to the postal service (network layer).
2. The postal service moves the mail between the two houses (hosts), without concerning itself with which cousin (process) sent or should receive it.
3. When mail arrives, Bill distributes the letters to the correct siblings (processes).

**Key Insight from the Analogy:**
- Ann and Bill operate **only within their respective houses (end systems)**. They have no control over how the postal service (network layer) operates internally (e.g., at mail sorting centers or routers).
- Similarly, the **transport layer functions only in the end systems**. Intermediate routers do not use the information added by the transport layer; they only act on the network-layer header.
#### Service Model Constraints and Enhancements
The analogy also explains how the transport layer's capabilities are related to the network layer's service model.

**Constraint by the Network Layer:**  
If the postal service cannot guarantee a maximum delivery time, then Ann and Bill cannot promise their siblings a specific delivery deadline. Similarly, if the network layer cannot provide guarantees on delay or bandwidth, the transport layer cannot provide those guarantees to applications.

**Enhancement Beyond the Network Layer:**  
However, the transport layer can provide services that the underlying network layer does not. Two key examples are:
1. **Reliable Data Transfer:** A transport protocol (like TCP) can provide reliable communication to an application **even if the underlying network layer is unreliable** (loses, corrupts, or duplicates packets). It does this through mechanisms like acknowledgments and retransmissions.
2. **Security:** A transport protocol (using TLS/SSL) can provide encryption and data integrity **even if the network layer does not offer confidentiality**.

In summary, the transport layer builds upon the network layer's host-to-host service to create a more powerful process-to-process service for applications.

![[3.2.png]]
### Overview of the Transport Layer in the Internet
The Internet provides two primary transport-layer protocols to applications:
1. **UDP (User Datagram Protocol):** Provides an **unreliable, connectionless** service.
2. **TCP (Transmission Control Protocol):** Provides a **reliable, connection-oriented** service.

An application developer must choose one of these protocols when creating a network application (e.g., when creating sockets).

**Terminology Note:** In this book, we refer to the transport-layer packet as a **segment** for both TCP and UDP, reserving the term **datagram** for the network-layer packet.
#### The Internet Network Layer (IP)
The Internet's network-layer protocol is **IP (Internet Protocol)**. Its service model is **best-effort delivery**, meaning it is fundamentally **unreliable**. IP does not guarantee:
- Segment delivery
- Orderly delivery of segments
- Integrity of the data in segments

Every host has at least one **IP address**.
#### Services Provided by UDP and TCP
Both UDP and TCP build upon IP's host-to-host service to provide two fundamental services:
1. **Transport-Layer Multiplexing and Demultiplexing:** Extending IP's host-to-host delivery to **process-to-process delivery**. This is the core function.
2. **Error Checking:** Including error-detection fields in segment headers to verify data integrity.

**UDP's Service Model:**  
UDP provides **only** the two services listed above. Like IP, UDP is **unreliable**—it does not guarantee that data will arrive or arrive correctly. It is a minimal, lightweight protocol.

**TCP's Enhanced Service Model:**  
TCP provides several critical additional services:
1. **Reliable Data Transfer:** Using techniques like sequence numbers, acknowledgments, and retransmissions, TCP ensures data is delivered correctly and in order to the destination process. It transforms IP's unreliable service into a reliable data transport service.
2. **Congestion Control:** This is a service for the health of the network. TCP prevents any single connection from overwhelming links and routers by regulating the sender's transmission rate. It aims to give each TCP connection a fair share of bandwidth. UDP has no such regulation; a UDP application can send data at any rate.
### Multiplexing and Demultiplexing
Multiplexing and demultiplexing are the fundamental services that extend the network layer's **host-to-host** delivery to the transport layer's **process-to-process** delivery.

**Definitions:**
- **Demultiplexing:** At the receiving host, the job of delivering the data in a transport-layer segment to the correct **socket** (and thus the correct application process).
- **Multiplexing:** At the sending host, the job of gathering data chunks from different application processes (via their sockets), encapsulating each chunk with header information to create segments, and passing the segments to the network layer.

**The Role of Sockets:**  
The transport layer delivers data to **sockets**, not directly to processes. Each socket is a unique endpoint for communication. A host running multiple network applications (e.g., a web browser, an FTP client, and Telnet sessions) will have multiple sockets.
![[3.2.png]]

**How Demultiplexing Works: Port Numbers**  
Demultiplexing relies on two special fields in every transport-layer segment header:
1. **Source Port Number Field**
2. **Destination Port Number Field**

These fields are illustrated in Figure 3.3.
![[3.3.png]]
Each port number is a 16-bit number, ranging from 0 to 65535.

- **Well-Known Port Numbers (0-1023):** Reserved for use by well-known application-layer protocols (e.g., port 80 for HTTP, port 21 for FTP). A list is maintained by IANA.
- **Other Ports:** When developing a new application, it must be assigned a port number not already in use for a well-known service.

**The Basic Demultiplexing Process:**  
Each socket in a host is assigned a port number. When a segment arrives, the transport layer examines the **destination port number** in the segment and directs the segment to the socket that is bound to that port. The segment's data then passes through the socket to the attached process.

**Analogy Recap:**  
In the household analogy, Bill (the transport layer) demultiplexes incoming mail by looking at the recipient's name (the port number) on each envelope and delivering it to the correct sibling (the socket/process). Ann multiplexes outgoing mail by collecting letters from all siblings and giving the batch to the postal carrier (the network layer).

**Protocol Specifics:**  
The text notes that while this is basically how UDP performs demultiplexing, the process for TCP is more subtle, which will be explored next.



### Connection-Oriented Multiplexing and Demultiplexing (TCP)
TCP demultiplexing is more complex than UDP because it is connection-oriented. A **TCP socket is identified by a four-tuple**:
- **Source IP address**
- **Source port number**
- **Destination IP address**
- **Destination port number**

This four-tuple uniquely identifies each TCP connection. When a TCP segment arrives, the host uses **all four values** to direct (demultiplex) the segment to the correct socket.
![[3.4.png]]
#### How It Works: The TCP Server Example
Recall the TCP server programming example from Section 2.7.2:
1. **Welcoming Socket:** The server has a welcoming socket (`serverSocket`) listening on a well-known port (e.g., 12000) for connection requests.
2. **Client Connection Request:** A client creates a socket and sends a connection request segment to the server's IP and port 12000. This segment includes the client's chosen source port number.
3. **Creating a Connection Socket:** When the server's operating system receives the connection request, it locates the process waiting on port 12000. The server process then creates a **new socket** specifically for this client:
```python
connectionSocket, addr = serverSocket.accept()
```
4. **Four-Tuple Identification:** This new connection socket is identified by the four-tuple from the incoming segment:
    - Source IP (client's IP)
    - Source port (client's port)
    - Destination IP (server's IP)
    - Destination port (12000)

All subsequent segments from this client that match this four-tuple will be demultiplexed to this specific connection socket. The original welcoming socket remains open to accept new connections.
#### Illustration with Multiple Connections

This mechanism allows a server to handle many simultaneous connections from different clients. As shown in Figure 3.5:
![[3.5.png]]
- **Host C** can have two HTTP connections to **Server B**, using different source ports (e.g., 26145 and 7532). Server B distinguishes them by the different source ports.
- **Host A** can also have an HTTP connection to **Server B** using the same source port as one of Host C's connections (e.g., 26145). Server B can still distinguish them because the **source IP addresses are different** (A vs. C).

Thus, the four-tuple ensures each TCP connection is unique, even if multiple clients accidentally choose the same source port number.
#### Port Scanning
The fact that servers listen on specific ports has security implications. **Port scanning** is a technique to determine which ports are open on a target host, revealing which network applications are running. Tools like **nmap** systematically probe ports:
- For **TCP**, it looks for ports that accept connections.
- For **UDP**, it looks for ports that respond to segments.

This helps system administrators with network inventory but is also used by attackers to find vulnerable services (e.g., an application with a known security flaw listening on a specific port).

### Web Servers and TCP
Web servers use TCP sockets and port numbers in specific ways:
- A Web server listens on a well-known port (e.g., port 80 for HTTP).
- All client segments sent to the server have **destination port 80**.
- The server distinguishes between different clients using the **source IP address and source port number** from each segment, as illustrated in Figure 3.5.
![[3.5 1.png]]

**Server Implementation:**
- Traditional servers might spawn a **new process** for each connection, each with its own connection socket.
- Modern high-performance servers typically use **one process with multiple threads**, where each thread handles a client connection with its own socket.

**HTTP and Socket Lifespan:**
- **Persistent HTTP:** The same TCP connection (and server socket) is used for multiple request/response exchanges.
- **Non-persistent HTTP:** A new TCP connection and socket are created and closed for every single request/response, which can impact performance on busy servers.
### Connectionless Transport: UDP
UDP is a minimal, "no-frills" transport protocol that does little more than provide multiplexing/demultiplexing and error checking. It is **connectionless** - there is no handshaking before sending data.

**Why Use UDP Instead of TCP?**  
Despite TCP's reliability, UDP is preferred for certain applications because:
1. **Finer Application-Level Control:** UDP sends data immediately without TCP's congestion control throttling or retransmission delays. This is crucial for real-time applications that need a minimum sending rate and can tolerate some loss.
2. **No Connection Establishment:** UDP has no handshake delay, making it faster for simple request-response applications like DNS.
3. **No Connection State:** UDP doesn't maintain connection state (buffers, sequence numbers, etc.), allowing servers to support more active clients.
4. **Smaller Header Overhead:** UDP header is only 8 bytes vs. TCP's 20 bytes.

**Application Protocol Usage:**  
Figure 3.6 shows which applications use which transport protocols:
![[3.6.png]]
- **TCP:** Email (SMTP), remote access (Telnet/SSH), Web (HTTP), file transfer (FTP) - where reliability is critical.
- **UDP:** DNS, network management (SNMP), streaming multimedia - where speed/low latency is prioritized over reliability.
- **Both:** Some modern applications like streaming media may use either.

**Congestion Control Concern:**  
UDP's lack of congestion control can be problematic. Uncontrolled UDP senders can overwhelm routers and crowd out TCP traffic. Researchers have proposed mechanisms to add congestion control to UDP sources.

**Reliability with UDP:**  
Applications can implement their own reliability mechanisms on top of UDP (like Google's QUIC protocol), but this is complex to develop.
#### UDP Segment Structure
The UDP segment structure is simple, with only four header fields (each 16 bits/2 bytes):
![[3.7.png]]
1. **Source Port Number**
2. **Destination Port Number**
3. **Length** (header + data in bytes)
4. **Checksum**
#### UDP Checksum
The checksum provides **error detection** (not correction). The sender calculates the 1s complement of the sum of all 16-bit words in the segment. The receiver verifies the checksum; if errors are detected, the segment is typically discarded.

**Why UDP Needs Checksum When Link Layer May Have Error Checking:**  
This follows the **end-end principle** - since not all links guarantee error checking, and errors can occur in router memory, error detection must be implemented at the transport layer for true end-to-end reliability.
### **Principles of Reliable Data Transfer**
Reliable data transfer (RDT) is a fundamental networking problem, crucial not only for the transport layer (like TCP) but also for the link and application layers. The goal is to create a **reliable channel** from an unreliable one, ensuring no corrupted or lost data, and in-order delivery.

**Framework (Figure 3.8):**
![[3.8.png]]
- **Sender Side:** Invoked by `rdt_send(data)` from the upper layer. Sends packets into the channel using `udt_send(packet)`.
- **Receiver Side:** Invoked by `rdt_rcv(packet)` from the lower layer. Delivers data to the upper layer using `deliver_data(data)`.
- The protocol is developed for **unidirectional** data transfer, but requires **bidirectional** communication for control packets (ACKs/NAKs).
### **Building a Reliable Data Transfer Protocol**
The protocol is built incrementally, handling increasingly complex channel models.
**1. rdt1.0: Perfectly Reliable Channel**
- **Assumption:** The underlying channel is perfectly reliable.
- **Operation:** The sender creates a packet from the data and sends it. The receiver receives the packet and delivers the data. There is no need for feedback from the receiver.
- This is a trivial protocol with one state for both sender and receiver.
![[3.9.png]]
**2. rdt2.0: Channel with Bit Errors**
- **Assumption:** Packets can have bit errors, but are not lost and are delivered in order.
- **Mechanisms introduced:**
    - **Error Detection:** Using checksums (like UDP).
    - **Receiver Feedback:** The receiver sends positive acknowledgments (**ACK**) for correct packets and negative acknowledgments (**NAK**) for corrupted packets.
    - **Retransmission:** The sender resends the packet when a NAK is received.
- This is a **stop-and-wait** protocol: the sender sends one packet and then waits for an ACK or NAK before proceeding.
![[3.10.png]]
- **Flaw:** What if the ACK or NAK itself is corrupted? The sender wouldn't know if the data was received correctly.

**3. rdt2.1 & rdt2.2: Handling Corrupted ACKs/NAKs**
- The solution is to add a **sequence number** to data packets.
- For this stop-and-wait scenario, a **1-bit sequence number** (0 or 1) is sufficient.
- The receiver uses the sequence number to detect duplicate packets caused by the sender retransmitting on a lost or corrupted ACK.
- **rdt2.1 (Figures 3.11 & 3.12):** Explicitly uses ACKs and NAKs. The sender and receiver FSMs double in size to track the current sequence number.
![[3.11.png]]
![[3.12.png]]
- **rdt2.2 (Figures 3.13 & 3.14):** A NAK-free version. The receiver sends an ACK for the last _correctly received_ packet. If the sender receives a **duplicate ACK** (two ACKs for the same sequence number), it knows the next packet was not received correctly and retransmits. The ACK packets now also include the sequence number they are acknowledging.
![[3.13.png]]
![[3.14.png]]
**4. rdt3.0: Lossy Channel with Bit Errors**
- **Assumption:** The underlying channel can now both corrupt _and lose_ packets.
- **New Mechanism: Timer-based Retransmission.**
    - The sender starts a **countdown timer** each time it sends a packet (first time or retransmission).
    - If the sender's timer expires before an ACK is received, it assumes the packet (or its ACK) was lost and **retransmits**.
    - This approach handles lost data packets and lost ACK packets.
    - The sequence number handles the duplicate packets that result from premature timeouts (when a packet or ACK is merely delayed, not lost).
- rdt3.0 is known as the **Alternating-Bit Protocol**.
![[3.15.png]]
![[3.16.png]]
**Summary of Key Mechanisms:**
- **Checksums:** For error detection.
- **Sequence Numbers:** To detect duplicate packets.
- **Timers:** To recover from lost packets.
- **Acknowledgments (ACKs):** For positive receiver feedback.
- **Retransmission:** The core action for recovery from errors and loss.

These four mechanisms are the core building blocks for reliable data transfer, and are used extensively by TCP.
### **Pipelined Reliable Data Transfer Protocols**
**The Performance Problem of Stop-and-Wait (rdt3.0)**
- rdt3.0 is correct but has very poor performance because it is a **stop-and-wait** protocol.
- The sender must wait a full **Round-Trip Time (RTT)** for an ACK before sending the next packet.
- This leads to very low **sender utilization**: `U_sender = (L/R) / (RTT + L/R)`
    - **Example:** On a 1 Gbps link with a 30 msec RTT and 1KB packets, utilization is a dismal **0.027%**, yielding an effective throughput of only ~267 kbps.
- The solution is **pipelining**.

#### **Pipelining**
- The sender is allowed to send **multiple packets** before waiting for acknowledgments.
- This "fills the pipeline" and dramatically increases utilization, as shown in Figure 3.18(b).
![[3.17.png]]
![[3.18.png]]
- **Consequences of Pipelining:**
    1. **Increased Sequence Number Range:** Must be large enough to cover all in-flight packets.
    2. **Increased Buffering:** Sender and receiver must be able to buffer multiple packets.
    3. **New Error Recovery Strategies:** Two primary approaches: **Go-Back-N (GBN)** and **Selective Repeat (SR)**.
### **Go-Back-N (GBN)**
**Core Concept:**
- The sender can have up to **N** unacknowledged packets in the pipeline.
- This creates a **sliding window** of size N over the sequence number space.
![[3.19.png]]
- The window slides forward as cumulative acknowledgments are received.

**Sender Rules (Figure 3.20):**
![[3.20.png]]
- **Variables:**
    - `base`: Sequence number of the oldest unacknowledged packet.
    - `nextseqnum`: Sequence number of the next packet to be sent.
- **Three Main Events:**
    1. **Invocation from Above (`rdt_send`):** If the window is not full (`nextseqnum < base + N`), send the packet and increment `nextseqnum`. If the window is full, the sender refuses the data (or buffers it).
    2. **Receipt of an ACK:** ACKs are **cumulative**. An ACK for sequence number `n` acknowledges all packets up to and including `n`. The window slides so that `base = n + 1`.
    3. **Timeout:** The sender uses a **single timer** for the oldest unacknowledged packet. If a timeout occurs, it **retransmits all packets** from `base` to `nextseqnum - 1`. This is the "Go-Back-N" action.

**Receiver Rules (Figure 3.21):**
![[3.21.png]]
- The receiver only acknowledges **in-order** packets.
- If the expected packet (`expectedseqnum`) is received correctly, it is delivered and an ACK is sent.
- **All out-of-order packets are discarded**, and the receiver re-sends an ACK for the last correctly received in-order packet.
- **Advantage:** Receiver simplicity (no need to buffer out-of-order packets).
- **Disadvantage:** A single lost packet can cause the retransmission of many packets unnecessarily, which is inefficient on lossy or long-delay links.

**Operation:** Figure 3.22 shows GBN in action with a window size of 4. A single lost packet (pkt2) causes all subsequent packets (pkt3, pkt4, pkt5) to be discarded and retransmitted.
![[3.22.png]]
### **Selective Repeat (SR)**
**Core Concept:**
- GBN can be inefficient if the window size or error rate is high.
- **Selective Repeat** aims to have the sender **retransmit only the packets that are suspected of being lost or corrupted**.
- This requires the receiver to **individually acknowledge** each correctly received packet (non-cumulative ACKs) and to **buffer out-of-order packets**.

**How SR Works:**
![[3.23.png]]
![[3.24 and 3.25.png]]
- **Sender:**
    - Maintains a timer for each individual packet in the window.
    - Retransmits a packet only if its timer expires.
- **Receiver:**
    - Sends an **ACK for any correctly received packet**, whether in-order or not.
    - If a packet is received out-of-order but correctly, it is **buffered**.
    - Once all lower-sequence-number packets have been received, a batch of in-order data can be delivered to the upper layer.

**SR Advantages and Complexity:**
- **Advantage:** More efficient than GBN; only lost packets are retransmitted, preserving bandwidth.
- **Complexity:**
    - Requires more sophisticated logic and state at both sender and receiver.
    - The sender and receiver windows are no longer identical, requiring careful management to avoid sequence number confusion, especially when the sequence number space is limited.

**Operation:** Figure 3.26 shows SR in action. Packet 2 is lost, but packets 3, 4, and 5 are buffered at the receiver. When packet 2 is retransmitted and received, the receiver can deliver packets 2, 3, 4, and 5 in order to the upper layer.
![[3.26.png]]
**The Critical Issue: Window Size and Sequence Number Space**
- The sender and receiver windows are not always perfectly synchronized.
- With a finite sequence number range, an old, delayed packet from a previous cycle of sequence numbers can be mistaken for a new packet. (See Figure 3.27 for the classic dilemma).
- **Solution:** To prevent this ambiguity, the **window size (N) must be less than or equal to half the size of the sequence number space**.
    - Example: For a k-bit sequence number field (range 0 to 2^k - 1), the maximum window size is 2^(k-1).
![[3.27.png]]
![[Table 3.1.png]]
### **Summary of Reliable Data Transfer Mechanisms (Table 3.1)**

|Mechanism|Use and Comments|
|---|---|
|**Checksum**|Detects bit errors in a transmitted packet.|
|**Timer**|Used to trigger retransmission of a potentially lost packet. Can cause duplicate packets.|
|**Sequence Number**|Allows detection of lost packets (gaps) and duplicate packets (same number).|
|**Acknowledgment (ACK)**|Receiver tells sender a packet was received correctly. Can be individual or cumulative.|
|**Negative Ack (NAK)**|Receiver tells sender a packet was not received correctly.|
|**Window / Pipelining**|Allows multiple packets to be in flight, increasing sender utilization over stop-and-wait.|
### **Connection-Oriented Transport: TCP**
TCP is the Internet's connection-oriented, reliable transport protocol. It builds on the principles of reliable data transfer (RDT), using error detection, retransmissions, cumulative acknowledgments, timers, and sequence/acknowledgment numbers.

**TCP Connection**
**Connection-Oriented Service:**
- Before data exchange, the two processes must perform a **"handshake"** to establish connection parameters and initialize TCP state variables.
- The connection is **logical**, with state maintained only in the two end systems. Intermediate network elements (routers, switches) are unaware of TCP connections.

**Key Characteristics:**
- **Full-Duplex:** Data can flow in both directions simultaneously over the same connection.
- **Point-to-Point:** A connection is strictly between one sender and one receiver (no multicasting).

**Connection Establishment:**
- The process is known as the **three-way handshake**.
- The client initiates the connection.
- The first two segments carry no application data.

**TCP Buffers and Data Flow:**
- Data from the application process passes through a socket into the TCP **send buffer**.
![[3.28.png]]
- TCP grabs chunks of data from the send buffer, forms segments, and passes them to the network layer.
- The maximum amount of application data in a segment is the **Maximum Segment Size (MSS)**.
- **MSS is typically set as: MSS = MTU - (TCP/IP Header Size)**
    - A common MTU (Maximum Transmission Unit) for Ethernet is 1500 bytes.
    - With 40 bytes for TCP/IP headers, a typical MSS is **1460 bytes**.
- On the receiving end, data is placed in the TCP **receive buffer**, from which the application process reads.

**TCP Segment Structure**

The TCP segment consists of a header and a data field. The header is typically 20 bytes (without options).
![[3.29.png]]
**Key Header Fields:**
- **Source & Destination Port Numbers:** For multiplexing/demultiplexing.
- **Checksum:** For error detection.
- **Sequence Number (32-bit):** The byte-stream number of the first data byte in the segment.
- **Acknowledgment Number (32-bit):** The sequence number of the next byte the sender of this segment expects to receive. It is a **cumulative acknowledgment**.
- **Receive Window (16-bit):** Used for flow control (indicates the number of bytes the receiver is willing to accept).
- **Header Length (4-bit):** Length of the TCP header in 32-bit words.
- **Options Field (Variable-length):** Used for negotiating parameters like MSS.
- **Flag Fields (6 bits):**
    - **ACK:** Indicates that the acknowledgment number field is valid.
    - **SYN, FIN, RST:** Used for connection setup and teardown.
    - **PSH, URG:** Rarely used in practice.

**Sequence and Acknowledgment Numbers in Detail**

**How Sequence Numbers Work:**
- TCP views data as an **ordered stream of bytes**.
- The sequence number for a segment is the byte-stream number of the **first byte** in that segment's data field.
- **Example:** A 500,000-byte file with an MSS of 1,000 bytes would be broken into 500 segments. The first segment has sequence number 0, the second has 1000, the third has 2000, and so on.
![[3.30.png]]

**How Acknowledgment Numbers Work:**
- Because TCP is full-duplex, each segment also carries an acknowledgment for data flowing in the reverse direction.
- The acknowledgment number is the sequence number of the **next byte that the receiver expects to receive**. This is a **cumulative acknowledgment**.
- **Example 1:** If Host A has received all bytes from B up through byte 535, it will set the acknowledgment number to **536** in its next segment to B.
- **Example 2:** If Host A has received bytes 0-535 and then bytes 900-1000 (but is missing 536-899), it will still acknowledge up to the first missing byte, sending an ACK for **536**.

**Out-of-Order Segments:**
- The TCP RFCs allow implementers to decide how to handle out-of-order segments.
- The practical and efficient approach is for the receiver to **buffer out-of-order bytes** and wait for the missing data to fill the gaps, rather than discarding them.

**Initial Sequence Number (ISN):**
- Both sides of a connection **randomly choose an initial sequence number**.
- This prevents a segment from a previous, terminated connection from being mistaken for a segment in a new connection between the same hosts and ports.

### **Telnet: A Case Study for Sequence and Acknowledgment Numbers**
Telnet is an interactive application used for remote login. It runs over TCP and provides a clear example of how sequence and acknowledgment numbers work in practice.
**Key Telnet Behavior:**
- Each character typed by the client is sent to the server.
- The server **"echoes"** the character back to the client, which then displays it on the user's screen.
- This means every character makes a **round trip** across the network.

**Example: User types the letter 'C'**  
(Assume initial sequence numbers are 42 for client-to-server data and 79 for server-to-client data). 
![[3.31.png]]
1. **Client to Server Segment:**
    - **Data:** The single byte 'C'.
    - **Sequence Number:** 42 (the first byte of the client's data stream).
    - **Acknowledgment Number:** 79 (the client tells the server "I have received up to byte 78 and am expecting byte 79 next").

2. **Server to Client Segment (Piggybacking):**
    - **Purpose 1 (Acknowledgment):** Acknowledges the client's data. The ACK number is 43 ("I successfully received up to byte 42, send byte 43 next").
    - **Purpose 2 (Data):** Echoes the byte 'C' back to the client.
    - **Sequence Number:** 79 (the first byte of the server's data stream).
    - **Acknowledgment Number:** 43.
    - This is called **piggybacking**—the ACK for one direction is carried in a data segment going the other way.

3. **Client to Server Segment:**
    - **Purpose:** Acknowledges the server's echoed data.
    - **Data:** None (this segment is an ACK-only).
    - **Sequence Number:** 43 (the next sequence number the client would use for data; required even though there's no data).
    - **Acknowledgment Number:** 80 ("I successfully received your data up to byte 79, send byte 80 next").
### **Round-Trip Time Estimation and Timeout**
TCP uses a timeout/retransmit mechanism. Setting the timeout interval correctly is critical: too short causes unnecessary retransmissions; too long causes slow recovery from lost segments.
**1. Estimating the Round-Trip Time (RTT)**
- **SampleRTT:** The time from when a segment is sent until its acknowledgment is received.
    - TCP measures this **approximately once per RTT**, not for every single segment.
    - It is **not measured for retransmitted segments** (to avoid ambiguity).
- **EstimatedRTT:** A smoothed average of the SampleRTT values. It is an **Exponential Weighted Moving Average (EWMA)** that gives more weight to recent samples.
    - **Formula:** `EstimatedRTT = (1 - α) * EstimatedRTT + α * SampleRTT`
    - **Recommended α:** **0.125**

**2. Estimating RTT Variation**
- **DevRTT:** An estimate of how much the SampleRTT typically deviates from the EstimatedRTT. It is also an EWMA.
    - **Formula:** `DevRTT = (1 - β) * DevRTT + β * | SampleRTT - EstimatedRTT |`
    - **Recommended β:** **0.25**

**3. Setting the Retransmission Timeout Interval (RTO)**
- The timeout interval must be based on both the average RTT and its variability.
- **Formula:** `TimeoutInterval = EstimatedRTT + 4 * DevRTT`
- **Initial Value:** Recommended to be 1 second.
- **On Timeout:** When a timeout occurs, the `TimeoutInterval` is **doubled**. This is a form of backoff to prevent overloading a congested network. It is recalculated using the formula above when new ACKs arrive.
### **Principles in Practice: TCP Reliable Data Transfer**
- TCP provides reliable data transfer using acknowledgments, timers, and sequence numbers, similar to the rdt3.0 principles.
- It uses **pipelining** to have multiple unacknowledged segments in flight, improving throughput.
- It features an **implicit NAK** mechanism: the receipt of **three duplicate ACKs** (indicating a segment is missing) triggers a **fast retransmit** before the timer expires.
- The number of outstanding segments is controlled by **flow control** and **congestion control** mechanisms.
![[3.32.png]]
DETTE ER NOTER INDTIL 268, MANGLER FRA 268 TIL 289
### **3.5.4 Reliable Data Transfer**
TCP provides a reliable data transfer service on top of IP's unreliable service, ensuring the byte stream read by the receiving process is uncorrupted, without gaps, without duplication, and in sequence.

**A Simplified TCP Sender**
This simplified model uses a **single retransmission timer** and handles three major events:
1. **Data Received from Application:**
    - Create a TCP segment with sequence number `NextSeqNum`.
    - If the timer is not running, **start the timer**.
    - Pass the segment to IP and increment `NextSeqNum`.
2. **Timeout:**
    - **Retransmit the segment** with the smallest sequence number that has not been acknowledged.
    - **Restart the timer**.
3. **ACK Received (with value `y`):**
    - This is a **cumulative acknowledgment**.
    - If `y > SendBase` (the sequence number of the oldest unacknowledged byte), it means new data has been ACKed.
        - Update `SendBase = y`.
        - If there are still any not-yet-acknowledged segments, **restart the timer**.

**Scenarios Illustrating the Protocol**
- **Scenario 1: Lost ACK**
![[3.34.png]]
    - Host A sends a segment (seq=92). The ACK from B is lost.
    - A's timer expires, causing it to retransmit the segment.
    - Host B receives the duplicate data and simply discards it.
- **Scenario 2: Cumulative ACK Prevents Unnecessary Retransmission**
![[3.35.png]]
    - Host A sends two segments (seq=92 and seq=100). Both arrive, but both ACKs are lost before the timeout.
    - The timeout occurs for the first segment (seq=92), so it is retransmitted.
    - The ACK for the second segment (seq=100) arrives before _its_ timeout, so it is **not** retransmitted. The cumulative nature of the ACK (ACK=120) confirms receipt of all data up to byte 119.
- **Scenario 3: Cumulative ACK Covers Lost ACK**
-
    - Host A sends two segments (seq=92 and seq=100). The ACK for the first segment is lost.
    - Before the timeout for the first segment, Host A receives the ACK for the second segment (ACK=120).
    - This cumulative ACK (120) informs A that B received all data up to byte 119, so **neither segment is retransmitted**.

**Doubling the Timeout Interval**
- When a timeout occurs and a retransmission is triggered, TCP **doubles the timeout interval** for the next retransmission (e.g., 0.75s -> 1.5s -> 3.0s).
- This provides a **limited form of congestion control**. It backs off the retransmission rate in the face of persistent loss, which is likely due to network congestion.
- The timer is reset based on `EstimatedRTT` and `DevRTT` when it is started due to new data or a new ACK.

**Fast Retransmit**
- Waiting for a timeout to detect loss can be slow.
- **Duplicate ACKs** are used as an early warning sign of loss. A duplicate ACK is sent when the receiver gets an out-of-order segment (see Table 3.2).
- **Rule:** If the TCP sender receives **three duplicate ACKs** for the same data (i.e., four ACKs total for the same segment), it infers that the following segment was lost.
- The sender then performs a **fast retransmit**, resending the missing segment **immediately**, without waiting for its timer to expire. (INSERT FIGURE 3.37 HERE)

**TCP ACK Generation Policy (Table 3.2)**
- **In-order segment arrival:** Often uses a **delayed ACK**, waiting up to 500ms for another in-order segment to piggyback the ACK onto.
- **Out-of-order segment arrival:** Immediately sends a **duplicate ACK** for the last in-order byte received.

**Is TCP Go-Back-N or Selective Repeat?**
- TCP is a **hybrid**.
- It resembles **GBN** because it uses cumulative ACKs and the sender only tracks `SendBase` and `NextSeqNum`.
- However, it is more efficient than GBN because:
    1. Most implementations **buffer out-of-order segments** at the receiver (an SR feature).
    2. With fast retransmit, it often only retransmits the single lost segment.
- With the **Selective Acknowledgment (SACK)** extension, TCP becomes even more like an SR protocol, as the receiver can explicitly inform the sender about out-of-order blocks of data it has received.

















![[Table 3.2.png]]
