### End systems
End systems are systems like a computer that are connected to the internet through communication links and packet switches. End systems access the internet through ISPs (Internet Service Providers). Another word for end systems is hosts, which can be divided into to two categories: clients and servers. Clients are phones and computers while servers reside in data centers.

### Packet switches
Routers and link-layer switches.
The sequence of communication links and packet switches traversed by a packet are called a route or path. 
Most packet switches use store-and-forward transmission at the inputs to the links. Store-and-forward transmission means that the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link. 
Packet switches (like routers) use output buffers (or output queues) for each of their connected links. These buffers store packets waiting to be sent. If a packet arrives for transmission but the link is busy, the packet must wait in the output buffer. This waiting time creates an additional queuing delay for packets, on top of other processing delays. However, these buffers have a finite size. If a network is highly congested, a buffer can become completely full. When a new packet arrives at a full buffer, packet loss occurs, meaning a packet (either the new arrival or an existing one) is dropped.

### Circuit switches
The resources (buffers, link transmission rate) are reserved for the duration of the communication duration.

### Protocols
A protocol defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event. End systems packet switches and other pieces of the internet run protocols that control the sending and receiving of information like TCP (Transmission Control Protocol) and IP (Internet Protocol) 

### RFCs Requests For Comments
Are general guidelines to ensure there is a certain standard used for networking. Examples include TCP, IP, HTTP (web), SMTP (e-mail).

### Socket interface
The socket interface is a set of rules that the sending program must follow so that the Internet can deliver the data to the destination program.

### Types of broadband digital access
1. DSL (Digital Subscriber Line)
2. Cable.

Since DSL is usually obtained from the same company that provides wired phone access. This means the line carries both data and traditional telephone signals simultaneously and therefore is encoded at different frequencies:
1. 50 kHz to 1MHz band high-speed downstream channel
2. 4 kHz to 50 kHz medium-speed upstream channel
3. 0 to 4 kHz ordinary two-way telephone channel
This enables the single DSL link to appear as three separate links and can therefore simultaneously be used, which is called frequency-division multiplexing.

Cable instead uses the cable television infrastructure. Since both fiber and coaxial cable are used in this system it is referred to as HFC (hybrid fiber coax). Cable is shared so speed can vary depending on the people using the same cable. A collission problem can occur where if two modems try to send data to the same neighbourhood at the exact same time, the packets can be corrupted. Therefore a protocol ensures this doesn't happen. FTTH (Fiber To The Home) is a new concept where fiber goes directly to each home allowing for multiple gigabit speeds.

### Guided media vs. unguided media
With guided media, the waves are guided along a solid medium, such as a fiber-optic cable, a twisted-pair copper wire, or a coaxial cable. With unguided media, the waves propagate in the atmosphere and in outer space, such as in a wireless LAN or a digital satellite channel. 

### Guided media types
A twisted-pair copper wire is one communication link. UTP (Unshielded Twisted Pair) is usually used for computer networks in a building where the speed depends on the thickness of the wire and the distance between the receiver and transmitter.

Coaxial cable are two copper conductors that are concentric instead of parallel, with special insulation and shielding they can achieve higher speeds. Coaxial cable can be used as a shared medium.

An optical fiber is a thin, flexible medium that conducts pulses of light, with each pulse representing a bit. It is immune to eletromagnetic interference, are hard to tap and have very low signal attenuation.
### Unguided media types
Radio channels carry signals in the electromagnetic spectrum. They are an attractive medium because they require no physical wire to be installed, can penetrate walls, provide connectivity to a mobile user, and can potentially carry a signal for long distances. There are three categories:
1. Very low distance (1-2 m)
2. Local area (10-300 m)
3. Wide area (tens of kilometers)

A communication satellite links two or more Earth-based microwave transmitter/receivers, known as ground stations. The satellite receives transmissions on one frequency band, regenerates the signal using a repeater (discussed below), and transmits the signal on another frequency. Two types of satellites are used in communications: 
1. Geostationary satellites. They stay above the same spot on the Earth by being in orbit 36000 km above the ground, introduces 280 millisecond delay.
2. Low-earth orbiting (LEO). They rotate around the earth and satellites.
### End-to-end delay
$$
d_{\text{end-to-end}} = N \frac{L}{R} 
$$
2. Low-earth orbiting (LEO). They rotate around the earth and communicate with each other and ground stations.

### IP-address
On the Internet, every device has a unique, hierarchical **IP address**. To send a packet, the source includes the destination's IP address in the packet header.
Routers use this address to decide where to forward the packet. Each router has a **forwarding table** that acts like a roadmap, matching portions of destination IP addresses to specific **outbound links**.

The process is:
1. A packet arrives at a router.
2. The router examines the destination IP address in the packet's header.
3. It looks up that address in its forwarding table to find the correct outbound link.
4. The router then forwards the packet to that adjacent router or network.

### Multiplexing, FDM (frequency-division multiplexing) vs. TDM (time-division multiplexing)
With FDM, the frequency spectrum of a link is divided up among the connections established across the link. Specifically, the link dedicates a frequency band to each connection for the duration
of the connection. In telephone networks, this frequency band typically has a width of
4 kHz (that is, 4,000 hertz or 4,000 cycles per second). The width of the band is
called the bandwidth.
For a TDM link, time is divided into frames of fixed duration, and each frame is divided into a fixed number of time slots. When the network establishes a connection across a link, the network dedicates one time slot in every frame to this connection. These slots are dedicated for the sole use of that connection, with one time slot available for use (in every frame) to transmit the connection’s data.
![[FDM and TDM.png]]
### ISPs, peering, multi-homing and IXPs
The internet is a network of networks, it is a a multi-tiered system with global Tier-1 providers at the top, followed by regional ISPs, and access ISPs at the bottom. This structure is further refined by **peering, multi-homing, and IXPs**, which are driven by economics and the need for efficient traffic exchange.

**Points of Presence (PoPs):** Provider-owned router facilities in various locations where customers can connect to join the provider's network, reducing connection costs.

**Multi-homing:** When an ISP (e.g., an access ISP) connects to **more than one** provider for redundancy and reliability.

**Peering:** When ISPs at the **same level** (e.g., two regional ISPs) connect to exchange traffic **directly without paying each other**, to save money and improve performance.

**Internet Exchange Points (IXPs):** Physical locations where multiple ISPs can meet to establish peering connections.

### Four types of nodal delay (processing, queuing, transmission and propagation)
1. **Processing Delay**
    - **What it is:** The time the router takes to examine the packet's header, perform error checking, and decide which outgoing link to send it to.
    - **Typical Scale:** Microseconds or less.
2. **Queuing Delay**
    - **What it is:** The time the packet spends waiting in an output buffer (queue) for its turn to be transmitted onto the link. This depends on the number and size of other packets already in the queue.
    - **Key Factor:** Highly variable. It can be **zero** if the queue is empty or very **long** during periods of network congestion.
    - **Typical Scale:** Microseconds to milliseconds.
3. **Transmission Delay**
    - **What it is:** The time it takes to "push" the entire packet's bits onto the physical link. It is a function of the packet's **length (L)** and the link's **transmission rate (R)**.
    - **Formula:** `Transmission Delay = L / R`
    - **Analogy:** The time it takes for a long caravan of cars to pass through a toll booth. The toll booth (router) can process cars (bits) at a fixed rate (R).
    - **Typical Scale:** Microseconds to milliseconds.
4. **Propagation Delay**
    - **What it is:** The time it takes for a single bit to travel from the beginning of the link to the end (from Router A to Router B). It is a function of the **distance (d)** and the **propagation speed (s)** of the physical medium (e.g., fiber, copper).
    - **Formula:** `Propagation Delay = d / s`
    - **Analogy:** The time it takes for the first car of the caravan to drive from the toll booth (Router A) to the next city (Router B).
    - **Typical Scale:** Milliseconds (especially in wide-area networks).
#### Key Distinction: Transmission vs. Propagation
- **Transmission Delay** is about the **volume of data** (the entire packet). It is the time to put the data _onto_ the link. It depends on the packet's length and the link's **data rate**.
- **Propagation Delay** is about the **distance** the signal must travel. It is the time for a bit to travel _across_ the link. It depends on the physical distance and the **speed of light** in the medium.
### TCP/UDP
The internets transport layer transports application-layer messages between application endpoints. TCP provides a connection-oriented service to its applications. This service includes guaranteed delivery of application-layer messages to the destination and flow control (that is, sender/receiver speed matching). TCP also breaks long messages into shorter segments and provides a congestion-control mechanism, so that a source throttles its transmission rate when the network is congested. 
UDP provides a connectionless service to its applications. This is a no-frills service that provides no reliability, no flow control, and no congestion control.  The transport-layer packet is also called a segment.

The Internet’s network layer routes a datagram through a series of routers between the source and destination. To move a packet from one node (host or router) to the next node in the route, the network layer relies on the services of the link layer. In particular, at each node, the network layer passes the datagram down to the link layer, which delivers the datagram to the next node along the route. At this next node, the link layer passes the datagram up to the network layer. The services provided by the link layer depend on the specific link-layer protocol that is employed over the link. The link-layer packets are also called frames.

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

###

