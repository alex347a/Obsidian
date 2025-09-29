### Introduction and Transport-Layer Services

The transport layer is a central piece of the network architecture, residing between the application and network layers. It provides communication services directly to application processes running on different hosts.

**Logical Communication:**  
The transport layer provides **logical communication** between application processes. From the application's perspective, it seems as if the hosts are directly connected, even if they are on opposite sides of the planet connected via numerous routers. This abstraction frees applications from worrying about the underlying physical infrastructure. (INSERT FIGURE 3.1 HERE)

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
![[3.1.png]]
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
The transport layer delivers data to **sockets**, not directly to processes. Each socket is a unique endpoint for communication. A host running multiple network applications (e.g., a web browser, an FTP client, and Telnet sessions) will have multiple sockets. (INSERT FIGURE 3.2 HERE)

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
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/5/3.5.png]]
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
![[3.5.png]]

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
- **Sender Side:** Invoked by `rdt_send(data)` from the upper layer. Sends packets into the channel using `udt_send(packet)`.
- **Receiver Side:** Invoked by `rdt_rcv(packet)` from the lower layer. Delivers data to the upper layer using `deliver_data(data)`.
    
- The protocol is developed for **unidirectional** data transfer, but requires **bidirectional** communication for control packets (ACKs/NAKs).
    

---

### **Building a Reliable Data Transfer Protocol**

The protocol is built incrementally, handling increasingly complex channel models.

**1. rdt1.0: Perfectly Reliable Channel**

- **Assumption:** The underlying channel is perfectly reliable.
    
- **Operation:** The sender creates a packet from the data and sends it. The receiver receives the packet and delivers the data. There is no need for feedback from the receiver.
    
- This is a trivial protocol with one state for both sender and receiver. (INSERT FIGURE 3.9 HERE)
    

**2. rdt2.0: Channel with Bit Errors**

- **Assumption:** Packets can have bit errors, but are not lost and are delivered in order.
    
- **Mechanisms introduced:**
    
    - **Error Detection:** Using checksums (like UDP).
        
    - **Receiver Feedback:** The receiver sends positive acknowledgments (**ACK**) for correct packets and negative acknowledgments (**NAK**) for corrupted packets.
        
    - **Retransmission:** The sender resends the packet when a NAK is received.
        
- This is a **stop-and-wait** protocol: the sender sends one packet and then waits for an ACK or NAK before proceeding. (INSERT FIGURE 3.10 HERE)
    
- **Flaw:** What if the ACK or NAK itself is corrupted? The sender wouldn't know if the data was received correctly.
    

**3. rdt2.1 & rdt2.2: Handling Corrupted ACKs/NAKs**

- The solution is to add a **sequence number** to data packets.
    
- For this stop-and-wait scenario, a **1-bit sequence number** (0 or 1) is sufficient.
    
- The receiver uses the sequence number to detect duplicate packets caused by the sender retransmitting on a lost or corrupted ACK.
    
- **rdt2.1 (Figures 3.11 & 3.12):** Explicitly uses ACKs and NAKs. The sender and receiver FSMs double in size to track the current sequence number.
    
- **rdt2.2 (Figures 3.13 & 3.14):** A NAK-free version. The receiver sends an ACK for the last _correctly received_ packet. If the sender receives a **duplicate ACK** (two ACKs for the same sequence number), it knows the next packet was not received correctly and retransmits. The ACK packets now also include the sequence number they are acknowledging.
    

**4. rdt3.0: Lossy Channel with Bit Errors**

- **Assumption:** The underlying channel can now both corrupt _and lose_ packets.
    
- **New Mechanism: Timer-based Retransmission.**
    
    - The sender starts a **countdown timer** each time it sends a packet (first time or retransmission).
        
    - If the sender's timer expires before an ACK is received, it assumes the packet (or its ACK) was lost and **retransmits**.
        
    - This approach handles lost data packets and lost ACK packets.
        
    - The sequence number handles the duplicate packets that result from premature timeouts (when a packet or ACK is merely delayed, not lost).
        
- rdt3.0 is known as the **Alternating-Bit Protocol**. (INSERT FIGURE 3.15 & 3.16 HERE)
    

**Summary of Key Mechanisms:**

- **Checksums:** For error detection.
    
- **Sequence Numbers:** To detect duplicate packets.
    
- **Timers:** To recover from lost packets.
    
- **Acknowledgments (ACKs):** For positive receiver feedback.
    
- **Retransmission:** The core action for recovery from errors and loss.
    

These four mechanisms are the core building blocks for reliable data transfer, and are used extensively by TCP.




























![[3.16.png]]
![[Table 3.1.png]]
![[Table 3.2.png]]
