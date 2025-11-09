### **Chapter 5 Summary**
- Two broad approaches to control: **per-router control** (e.g., OSPF, BGP) and **logically centralized, SDN control**.
- We covered the fundamental **routing algorithms**: **Link-State (LS/Dijkstra)** and **Distance-Vector (DV/Bellman-Ford)**.
- Key Internet routing protocols: **OSPF** (Intra-AS) and **BGP** (Inter-AS), the "glue" of the Internet.
- **SDN**, examining the architecture of the **SDN controller**, the **OpenFlow protocol**, and how they enable programmable networks.
- Network management protocols: **ICMP** (for error reporting and `traceroute`), **SNMP/MIB** (for monitoring), and the modern **NETCONF/YANG** framework (for configuration).
### **The Network Layer: Control Plane - Introduction**
This chapter covers the **control-plane** component of the network layer—the network-wide logic that controls how a datagram is routed and how network services are configured.

**Key Topics:**
- **Routing Algorithms:** The foundation for computing paths (OSPF, BGP).
- **OSPF:** A routing protocol used _within_ a single ISP's network.
- **BGP:** The inter-domain routing protocol that interconnects all networks in the Internet; the "glue" that holds it together.
- **SDN Controllers:** The logically centralized control in Software-Defined Networking.
- **Management Protocols:** ICMP and SNMP.
### **Two Control Plane Approaches**
The control plane's job is to compute, maintain, and install the forwarding/flow tables used by the data plane.
1. **Per-Router Control (Traditional):**
    - A **routing algorithm** runs in _each and every_ router.
    - Each router has a routing component that communicates with the routing components in _other routers_ to compute its forwarding table.
    - Used for decades in the Internet (OSPF, BGP are based on this). (INSERT FIGURE 5.1, PER-ROUTER CONTROL, HERE)
2. **Logically Centralized Control (SDN):**
    - A **logically centralized controller** computes and distributes the forwarding tables to all routers.
    - Each router has a simple **Control Agent (CA)** that communicates with the controller and follows its commands.
    - The CAs do not communicate with each other or compute paths themselves.
    - This is the approach of **SDN** and is used in major production networks (Google's B4, Microsoft's SWAN, AT&T, 4G/5G). (INSERT FIGURE 5.2, LOGICALLY CENTRALIZED CONTROL, HERE)
### **Routing Algorithms**
The goal of a routing algorithm is to determine **good paths** (routes) from senders to receivers through a network of routers. A "good" path is typically the **least cost path**.

**Graph Abstraction:**
- We model the network as a graph `G = (N, E)`.
- **Nodes (N):** Represent **routers** (or, in BGP, entire networks).
- **Edges (E):** Represent the **physical links** between routers.
- **Edge Cost:** A value assigned to a link, which could represent physical length, link speed, monetary cost, etc. We denote the cost between node `x` and `y` as `c(x, y)`. (INSERT FIGURE 5.3, ABSTRACT GRAPH MODEL, HERE)

**The Least-Cost Path Problem:**
- A **path** is a sequence of nodes connected by edges.
- The **path cost** is the sum of the costs of all edges in the path.
- The goal is to find the path between a source and destination that has the **minimum possible cost**.
### **Classification of Routing Algorithms**
Routing algorithms can be classified in several ways:
**1. Based on Information Scope:**
- **Centralized Routing Algorithm:**
    - Computes least-cost paths using **complete, global knowledge** of the network (all nodes, all links, all costs).
    - Also known as **Link-State (LS) algorithms**.
    - The algorithm can be run on a central controller or replicated in every router.
- **Decentralized Routing Algorithm:**
    - The calculation is **iterative and distributed**.
    - No node has global information. Each node starts with knowledge only of its own directly connected links.
    - Through iterative message exchange with neighbors, it gradually calculates least-cost paths.
    - Also known as **Distance-Vector (DV) algorithms**.

**2. Based on Change Frequency:**
- **Static Routing Algorithms:** Routes change very slowly, often via manual human intervention.
- **Dynamic Routing Algorithms:** Routes change as network traffic loads or topology change. They are more responsive but also more susceptible to issues like routing loops.

**3. Based on Load Sensitivity:**
- **Load-Sensitive Algorithms:** Link costs change dynamically to reflect current congestion levels. (Early ARPAnet; not used in today's Internet main protocols).
- **Load-Insensitive Algorithms:** Link costs do not reflect current congestion. (Used in today's Internet routing protocols like RIP, OSPF, and BGP).
### **The Link-State (LS) Routing Algorithm**
In a **Link-State (LS) algorithm**, every node has **complete, global knowledge** of the network topology and all link costs. This is achieved by having each node broadcast **link-state packets** to all other nodes in the network.

**Dijkstra's Algorithm**  
This is the canonical Link-State algorithm. It computes the least-cost path from a **source node** to **all other nodes** in the network. It is iterative; after the *k*th iteration, the least-cost paths to *k* destinations are known.

**Notation:**
- **D(v):** Current cost of the least-cost path from the source to node `v`.
- **p(v):** The previous node (neighbour) along the current least-cost path from the source to `v`.
- **N':** The set of nodes to which the least-cost path is **definitively known**.

**Algorithm Steps:**
1. **Initialization:** Start with the source node. Set costs to neighbours to the direct link cost, and costs to all other nodes to infinity.
2. **Loop:** Find the node `w` not in `N'` with the minimum cost.
3. Add `w` to `N'`.
4. **Update** the cost to each of `w`'s neighbours not in `N'`. The new cost is the minimum of the old cost or the cost to `w` plus the cost from `w` to the neighbour.
5. Repeat until all nodes are in `N'`.

**Example:** The table shows the algorithm's progress for the network graph, computing paths from source node `u`. (INSERT TABLE 5.1, RUNNING THE LINK-STATE ALGORITHM, HERE)

**Result:** When the algorithm terminates, we can construct the **entire least-cost path** from the source to every destination and build the node's **forwarding table**. (INSERT FIGURE 5.4, LEAST COST PATH AND FORWARDING TABLE, HERE)

**Computational Complexity:**
- The straightforward implementation has a worst-case complexity of **O(n²)**, where `n` is the number of nodes.
- A more efficient implementation using a heap data structure can reduce this.

**Oscillations:**
- A potential problem arises when **link costs depend on the traffic load** (e.g., delay).
- This can cause **oscillations**, where routers simultaneously run LS, shift traffic to a better path, which then becomes congested, leading them to shift back in a cycle. (INSERT FIGURE 5.5, OSCILLATIONS, HERE)
- **Solution:** Prevent all routers from running the LS algorithm at the same time by adding randomization.
### **The Distance-Vector (DV) Routing Algorithm**
The **Distance-Vector (DV) algorithm** is a **decentralized, iterative, and asynchronous** algorithm where each node only communicates with its directly connected neighbors.

**The Bellman-Ford Equation**  
This is the heart of the DV algorithm. It states that the least cost from node `x` to node `y` is the minimum, over all of `x`'s neighbors `v`, of the cost from `x` to `v` plus the least cost from `v` to `y`.
- **Formula:** `dₓ(y) = minᵥ { c(x, v) + dᵥ(y) }`
- **Intuition:** To get to `y`, `x` must first go to a neighbor `v`. The total cost is the cost to get to `v` plus the cost from `v` to `y`. The best path is found by choosing the neighbor `v` that minimizes this sum.

**Distance Vectors**
- Each node `x` maintains a **distance vector**: `Dₓ = [Dₓ(y): y in N]`, which is its current estimate of the cost to all other nodes `y` in the network.
- Each node also maintains the distance vectors it has received from each of its neighbors.

**The DV Algorithm Process**
1. **Initialization:** Each node starts by knowing only the cost to its direct neighbors. Costs to all other nodes are set to infinity.
2. **Update:** From time to time, each node sends a copy of its distance vector to its neighbors.
3. **Recomputation:** When a node `x` receives a new distance vector from a neighbor, it saves it and uses the Bellman-Ford equation to update its own distance vector: `Dₓ(y) = minᵥ { c(x, v) + Dᵥ(y) }`.
4. **Propagation:** If its own distance vector changes as a result of this update, node `x` then sends its updated vector to its neighbors. This process continues iteratively until no more updates are sent.

**Example:** The figure illustrates the algorithm's operation in a simple 3-node network, showing how distance vectors are exchanged and updated until they converge to the actual least costs. (INSERT FIGURE 5.6, DV ALGORITHM IN OPERATION, HERE)
### **DV: Link-Cost Changes and Link Failure**
**Good News Travels Fast**
- When a link cost **decreases**, the network converges to the new least-cost paths very quickly (often in just a few iterations).

**Bad News Travels Slow & The Count-to-Infinity Problem**
- When a link cost **increases**, a major problem can occur.
- **Scenario:** Two neighboring nodes, `y` and `z`, both route through each other to get to `x`. When the direct link from `y` to `x` fails (cost becomes very high), `y` thinks it can still get to `x` via `z`, and `z` simultaneously thinks it can get to `x` via `y`. This creates a **routing loop**.
- They will slowly increment their cost estimates to `x` in a series of steps until the cost finally exceeds the value of a direct (but more expensive) link, a phenomenon known as **count-to-infinity**. (INSERT FIGURE 5.7, CHANGES IN LINK COST, HERE)

**Poisoned Reverse**
- A technique used to avoid two-node routing loops.
- **Rule:** If node `A` routes through neighbor `B` to get to destination `X`, then `A` will **advertise to `B` that its cost to `X` is infinity**.
- This prevents `B` from thinking it can use `A` to get to `X`, thus breaking the immediate loop.
- **Limitation:** Poisoned reverse does **not** solve count-to-infinity problems involving loops of **three or more nodes**.
### **A Comparison of LS and DV Routing Algorithms**

|Attribute|Link-State (LS) Algorithm|Distance-Vector (DV) Algorithm|
|---|---|---|
|**Information Scope**|**Global**. Each node has a complete map of the network.|**Decentralized**. Each node knows only its neighbors and communicates only with them.|
|**Message Complexity**|**O(**\|**N**\|**\|**E**\|**)**. LS floods link costs to all nodes.|Can vary. Exchanges messages only between neighbors. Can be lower.|
|**Speed of Convergence**|**O(**\|**N**\|**²)** algorithm. Fast convergence.|Can be **slow**. Prone to routing loops and count-to-infinity problems during convergence.|
|**Robustness**|**More robust**. Routers compute their own paths. An incorrect node calculation has a more limited impact.|**Less robust**. An incorrect or malicious node can advertise incorrect paths, and this error can **diffuse through the entire network**.|

**Conclusion:** Neither algorithm is a clear "winner." Both are used in the Internet (OSPF is LS-based, RIP and BGP are DV-based).
### **Intra-AS Routing in the Internet: OSPF**
Organizing all Internet routers under a single routing algorithm is impractical due to:
1. **Scale:** The sheer number of routers (hundreds of millions) makes storing routing information and broadcasting updates infeasible.
2. **Administrative Autonomy:** ISPs want to operate and control their own networks independently.

**Solution: Autonomous Systems (ASs)**
- An **Autonomous System (AS)** is a group of routers under the same administrative control (e.g., a single ISP).
- Each AS is assigned a globally unique **Autonomous System Number (ASN)**.
- The routing algorithm running _within_ an AS is called an **intra-autonomous system routing protocol**.
#### **Open Shortest Path First (OSPF)**
OSPF is a widely used **intra-AS routing protocol**. It is a **link-state protocol**.
- **Operation:** Each router:
    1. Broadcasts **link-state information** to **all other routers in the AS** (using flooding).
    2. Constructs a complete topological map of the AS.
    3. Locally runs **Dijkstra's algorithm** to compute the shortest-path tree to all subnets, with itself as the root.
- **Link Weights:** The network administrator configures the cost (weight) of each link. This allows for traffic engineering (e.g., setting weights inversely proportional to link capacity).

**Key OSPF Features:**
- **Security:** OSPF messages can be authenticated to prevent malicious routers from participating.
- **Multiple Same-Cost Paths:** OSPF can use multiple paths if they have the same cost (load balancing).
- **Support for Hierarchy (Areas):** A large OSPF AS can be partitioned into **areas** to reduce overhead.
    - Each area runs its own OSPF link-state algorithm.
    - **Area Border Routers** route traffic between areas.
    - A **backbone area** interconnects all other areas.
- **Integrated Multicast Support:** Multicast OSPF (MOSPF) extends OSPF for multicast routing.

**PRINCIPLES IN PRACTICE: Setting OSPF Weights**
- The cause-and-effect relationship can be reversed. Instead of weights determining paths, network operators often **set OSPF link weights to achieve specific traffic engineering goals**, such as minimizing the maximum link utilization, based on known traffic demands.
### **Routing Among the ISPs: BGP**
To route packets _between_ autonomous systems, an **inter-autonomous system routing protocol** is needed. The Internet uses a single, standardized protocol: the **Border Gateway Protocol (BGP)**. BGP is the "glue" that holds the Internet together.
#### **The Role of BGP**
BGP provides each router with the means to:
1. **Obtain prefix reachability information:** Allows subnets to advertise their existence to the entire Internet. ("I exist and I am here!").
2. **Determine the "best" routes to prefixes:** When multiple routes to a prefix exist, BGP runs a route-selection procedure to choose the best one based on reachability information and, crucially, **policy**.

In BGP, routers exchange information about **CIDRized prefixes** (e.g., `138.16.68/22`), not individual IP addresses.
#### **Advertising BGP Route Information**
**BGP Connections:**
- BGP routers exchange routing information over semi-permanent **TCP connections** (port 179).
- **eBGP (external BGP):** A BGP connection between routers in **different** ASs. Used to exchange routing information across AS boundaries.
- **iBGP (internal BGP):** A BGP connection between routers in the **same** AS. Used to ensure all routers in the AS have consistent routing information. (INSERT FIGURE 5.9, BGP CONNECTIONS, HERE)

**Propagating Reachability:**
- The process of advertising a prefix involves a chain of eBGP and iBGP messages.
- **Example:** For prefix `x` in AS3 to be known in AS1:
    1. Router 3a (AS3) sends an **eBGP** message to 2c (AS2): "`AS3 x`".
    2. Router 2c uses **iBGP** to tell all routers in AS2, including 2a.
    3. Router 2a sends an **eBGP** message to 1c (AS1): "`AS2 AS3 x`".
    4. Router 1c uses **iBGP** to tell all routers in AS1.
- This process informs routers not only that `x` exists, but also the **AS path** (`AS2, AS3`) to reach it. (INSERT FIGURE 5.8, NETWORK WITH THREE ASs, HERE)

**Multiple Paths:**
- There can be multiple paths to a prefix. In the example, if a direct link is added from AS1 to AS3, routers in AS1 would learn two paths: "`AS2 AS3 x`" and "`AS3 x`". BGP will select the best one. (INSERT FIGURE 5.10, NETWORK WITH MULTIPLE PATHS, HERE)
### **Determining the Best Routes in BGP**
A router often learns multiple possible paths (routes) to a destination prefix. BGP selects the best one using a sequential, multi-step decision process that considers both technical metrics and policy.

**BGP Terminology: Routes and Attributes**
- In BGP, a **route** is a prefix along with its attributes.
- Key Attributes:
    - **AS-PATH:** The list of ASs that the advertisement for the prefix has passed through. Used to **prevent loops** (a router rejects a route if it sees its own AS in the path).
    - **NEXT-HOP:** The **IP address** of the router interface that begins the AS-PATH. This is the critical link between inter-AS (BGP) and intra-AS (e.g., OSPF) routing
#### **Hot Potato Routing**
This is a simple, "selfish" routing strategy where a router chooses the route that gets the packet **out of its own AS as quickly as possible**.
- **Process:** The router uses its **intra-AS routing information** to calculate the cost to each possible NEXT-HOP router for the destination prefix. It then selects the route with the **closest NEXT-HOP.**
- **Analogy:** The packet is a "hot potato" that you want to pass to someone else (another AS) as fast as possible.
- **Result:** Different routers within the same AS might choose different exit points for the same destination. (INSERT FIGURE 5.11, STEPS FOR HOT POTATO ROUTING, HERE)
#### **The BGP Route-Selection Algorithm**
In practice, BGP uses a more sophisticated algorithm that incorporates but supersedes hot potato routing. The router applies the following elimination rules **in sequence** until only one route remains:
1. **Local Preference (Highest):** This is a **policy attribute** set by the network administrator. Routes with the **highest local preference** are chosen first. This is the primary policy control knob.
2. **Shortest AS-PATH:** From the remaining routes, the one with the **shortest AS-PATH** (fewest AS hops) is selected.
3. **Hot Potato Routing (Closest NEXT-HOP):** From the remaining routes, the one with the **closest NEXT-HOP** router (using the intra-AS routing metric) is selected.
4. **BGP Identifier:** If multiple routes still remain, the router uses the BGP identifier to break the tie.

**Key Takeaway:** Policy (Local Pref) is considered first, then the inter-AS path length, and finally the intra-AS path cost (hot potato).
### **IP-Anycast**
BGP is also used to implement **IP-Anycast**, a service that allows multiple, geographically distributed servers to share the **same IP address**.
- **How it works:**
    1. **Configuration:** Multiple servers in different locations are configured with the **same IP address**.
    2. **BGP Advertisement:** Each server's local router uses BGP to advertise this shared IP address into the Internet.
    3. **Route Selection:** BGP routers throughout the Internet receive these multiple advertisements. They run the standard BGP route-selection algorithm and install the "best" route (typically the one with the shortest AS-PATH, i.e., the geographically closest server) in their forwarding tables.
    4. **Traffic Direction:** When a client sends a packet to this IP address, BGP automatically routes it to the **"nearest"** server.

**Primary Use Case: DNS**
- IP-Anycast is extensively used for **DNS root servers** and top-level domain (TLD) servers.
- There are 13 IP addresses for root servers, but each address corresponds to **many physical servers** around the world. BGP and IP-Anycast direct a user's query to the closest root server instance.

**Limitation for Stateful Protocols:**
- CDNs generally **avoid** IP-Anycast for serving web content because BGP route changes could cause different packets of the **same TCP connection** to be delivered to different servers, breaking the connection. It is ideal for stateless protocols like DNS queries.
### **BGP Routing Policy**
In BGP, **policy considerations often trump technical metrics** like shortest path. Policy is primarily implemented through the **Local Preference** attribute, which is set by the network administrator.

**Example Policy Scenario:** (INSERT FIGURE 5.13, A SIMPLE BGP POLICY SCENARIO, HERE)
- **ASs W, X, Y** are **access ISPs** (stub networks). Their traffic must only be to/from themselves.
- **ASs A, B, C** are **backbone provider** networks.

**Implementing Policy with Route Advertisement:**
- An access ISP like **X** can prevent itself from being used as a transit network by **only advertising routes to itself**. Even if X knows a path to Y (via C), it will not advertise this path to B. This way, B will never send traffic for Y through X.
- A backbone ISP like **B** may choose not to advertise routes from A to C (and vice versa) to avoid carrying **transit traffic** between them without compensation. The rule of thumb is that traffic on an ISP's backbone should be to/from one of its own customers.

**Peering Agreements:** The commercial contracts between ISPs that govern these routing policies are often confidential.
### **PRINCIPLES IN PRACTICE: Why Different Inter-AS and Intra-AS Routing Protocols?**
The Internet uses different protocols for routing within an AS (Intra-AS, e.g., OSPF) and between ASs (Inter-AS, e.g., BGP) for three fundamental reasons:
1. **Policy:**
    - **Inter-AS:** **Policy dominates.** An AS needs strict control over what traffic it carries and which paths are allowed. BGP is built for this, with attributes like AS-PATH and LOCAL-PREF.
    - **Intra-AS:** **Policy is less important.** A single organization controls the entire network, so the primary goal is efficient routing.
2. **Scale:**
    - **Inter-AS:** Routing algorithms and data structures must **scale to the entire Internet**. BGP is designed for this massive scale.
    - **Intra-AS:** Scalability is less critical. If an AS becomes too large, it can be split into two separate ASs.
3. **Performance:**
    - **Inter-AS:** Performance is often **secondary to policy**. A longer path that satisfies a policy may be chosen over a shorter one.
    - **Intra-AS:** With policy concerns minimized, the focus can be on **performance metrics** like delay and throughput.
### **Putting the Pieces Together: Obtaining Internet Presence**
To make a company's server (e.g., `www.xanadu.com`) accessible on the Internet requires several steps and protocols working together:
1. **Contract with a Local ISP:** Obtain **Internet connectivity** and a block of IP addresses (e.g., a `/24` prefix).
2. **Contract with a Registrar:** Obtain a **domain name** (e.g., `xanadu.com`).
3. **Configure DNS:**
    - Provide your registrar with the IP address of your **authoritative DNS server**.
    - In your DNS server, create records (e.g., A records) that map your server names (`www.xanadu.com`) to their specific IP addresses.
4. **Advertise Your Prefix via BGP:** Your local ISP uses **BGP** to advertise your company's IP prefix to the rest of the Internet. This is the final, crucial step that allows routers worldwide to know how to forward packets destined for your servers.
### **The SDN Control Plane**
SDN makes a clear **separation between the data and control planes**. The control plane is logically centralized and implemented in software.

**Four Key Characteristics of SDN:**
1. **Flow-Based Forwarding:** Packet forwarding is based on **any number of header fields** (not just destination IP), as defined by the flow tables we saw in Section 4.4.
2. **Separation of Data and Control Planes:**
    - **Data Plane:** Simple, fast packet switches that perform "match-plus-action."
    - **Control Plane:** A separate, remote entity that computes and manages the flow tables.
3. **Network Control Functions: External to Data-Plane Switches:** The control logic runs on servers, not inside the switches. The control plane consists of:
    - An **SDN Controller** (or Network OS): Maintains network state and provides an API to applications.
    - **Network-Control Applications:** The "brains" that implement functions like routing, access control, and load balancing.
4. **A Programmable Network:** The network's behavior is defined by software applications, leading to innovation and flexibility. (INSERT FIGURE 5.14, SDN CONTROL PLANE ARCHITECTURE, HERE)

**The "Unbundling" of Networking:**  
SDN unbundles network functionality, similar to the shift from monolithic mainframes to PCs with separate hardware, operating systems, and applications. This allows for independent innovation in switches, controllers, and control applications.
### **The SDN Control Plane: SDN Controller and Applications**
The SDN control plane is divided into two main parts: the **SDN Controller** (the "network operating system") and the **SDN Network-Control Applications** (the programs that define network behavior).
#### **SDN Controller Architecture**
A generic SDN controller's functionality is organized into three layers: (INSERT FIGURE 5.15, COMPONENTS OF AN SDN CONTROLLER, HERE)
1. **Communication Layer (Southbound Interface):**
    - This is the lowest layer, responsible for **communicating between the controller and the network devices** (switches, hosts).
    - It uses a protocol (like **OpenFlow**) to send commands to devices and to receive event notifications from them (e.g., link up/down, new device).
    - This defines the **southbound API**.
2. **Network-Wide State-Management Layer:**
    - The controller maintains a **centralized, global view** of the entire network's state.
    - This includes information about hosts, links, switches, statistics, and the flow tables themselves.
    - This database provides a consistent source of truth for all control applications.
3. **Interface to Network-Control Applications (Northbound Interface):**
    - This is the **API** that network-control applications use to interact with the controller.
    - Applications can read/write network state, register for event notifications, and control the network through this interface.
    - Many controllers use a **RESTful API** for this northbound interface.

**Logical vs. Physical Centralization:** The controller is **logically centralized** (it appears as a single point of control) but is often **physically distributed** across multiple servers for fault tolerance, high availability, and scalability.
#### **OpenFlow Protocol**
The **OpenFlow protocol** is a specific, widely used protocol that operates in the controller's **communication layer**. It runs over **TCP** (port 6653).
**Key Messages from Controller to Switch:**
- **Configuration:** Query/set a switch's parameters.
- **Modify-State:** Add, delete, or modify entries in the switch's **flow table**.
- **Read-State:** Collect statistics and counter values from the switch.
- **Send-Packet:** Direct the switch to send a specific packet out of a specified port.

**Key Messages from Switch to Controller:**
- **Flow-Removed:** Informs the controller that a flow table entry has been removed (e.g., due to a timeout).
- **Port-status:** Informs the controller of a change in a port's state (e.g., link goes down).
- **Packet-in:** Sends a packet to the controller because it didn't match any flow table entry, or because a matching rule specified this action.
### **PRINCIPLES IN PRACTICE: Google's Software-Defined Global Network (B4)**
Google operates a global WAN called **B4** that interconnects its data centers using a custom SDN control plane built on OpenFlow.
- **Why it's a good fit for SDN:** Google controls all devices, the main traffic is large, deferrable data transfers, and the number of sites is manageable for centralized control.
- **Result:** B4 achieves dramatically higher link utilization (~70% vs. the typical ~30%) by using SDN to perform **traffic engineering**, splitting application flows over multiple paths based on priority and demand.
- **Architecture:** Uses custom switches with an OpenFlow Agent (OFA) that communicates with an OpenFlow Controller (OFC) in a central Network Control Server (NCS).
### **Data and Control Plane Interaction: An Example**
Let's trace the steps of how the SDN control plane responds to a network event, like a **link failure**, to recompute routes using Dijkstra's algorithm. (INSERT FIGURE 5.16, SDN CONTROLLER SCENARIO, HERE)

**Scenario:** The link between switch s1 and s2 fails.
1. **Detection & Notification:** Switch s1 detects the link failure and sends a **Port-status** message to the SDN controller via OpenFlow.
2. **State Update:** The controller's communication layer receives the message. The **link-state manager** in the state-management layer updates the network-wide link-state database.
3. **Application Notification:** The **Dijkstra's routing application** had previously registered for link-state change events. It is now notified of the change.
4. **Recomputation:** The routing application gets the updated link state from the database and **recomputes the least-cost paths** for the entire network.
5. **Flow Table Determination:** The application works with the **flow table manager** to determine the exact changes needed in the flow tables of affected switches (s1, s3, s4).
6. **Configuration:** The flow table manager uses **OpenFlow Modify-State messages** to update the flow tables on the affected switches, implementing the new paths.

**Key Advantage:** This demonstrates the flexibility of SDN. Changing the entire network's routing behavior only requires updating the software in the centralized controller, not in every individual router.
### **SDN: Past and Future**
**Historical Roots:**
- The technical roots of SDN and data/control plane separation go back to the early 2000s and even to ATM networks in the late 1990s.
- The **Ethane project (2007)** was a direct precursor to OpenFlow, featuring a network of simple flow-based switches and a centralized controller.

**Future Directions:**
- **Network Functions Virtualization (NFV):** A generalization of SDN that aims to replace dedicated, proprietary middleboxes (e.g., firewalls, load balancers) with software running on commodity servers.
- **Inter-AS SDN:** Extending SDN concepts from within a single AS to routing _between_ autonomous systems.
### **PRINCIPLES IN PRACTICE: SDN Controller Case Studies**
Two major open-source SDN controllers are **OpenDaylight (ODL)** and **ONOS**.

**The OpenDaylight (ODL) Controller:** (INSERT FIGURE 5.17, OPENDAYLIGHT CONTROLLER, HERE)
- **Service Abstraction Layer (SAL):** The core that allows different components and applications to communicate and abstracts the underlying southbound protocols (OpenFlow, NETCONF, SNMP).
- **Northbound API:** Provides a **RESTful API** for applications.
- **Model-Driven Approach:** Uses the **YANG** data modeling language to define network models, which are then configured using the **NETCONF** protocol.

**The ONOS Controller:** (INSERT FIGURE 5.18, ONOS CONTROLLER, HERE)
- **Intent Framework:** A key feature that allows applications to specify _what_ they want the network to do (e.g., "connect host A to host B") without specifying _how_ to do it.
- **Distributed Core:** Designed from the ground up to run as a distributed service on multiple servers for scalability and high availability.
- **Southbound Abstractions:** Provides a high-level abstraction layer that hides the heterogeneity of the underlying network devices and protocols.
### **ICMP: The Internet Control Message Protocol**
ICMP is used by hosts and routers to communicate network-layer information, most commonly for **error reporting**.
- **Architecture:** ICMP messages are carried **inside IP datagrams** as payload (IP protocol number 1).
- **Message Structure:** ICMP messages have a **type** and **code** field, and include the header and first 8 bytes of the IP datagram that triggered the message.

**Common ICMP Message Types:** (INSERT FIGURE 5.19, ICMP MESSAGE TYPES, HERE)
- **Type 0/8: Echo Reply / Echo Request:** Used by the **`ping`** program to test reachability.
- **Type 3: Destination Unreachable:** Indicates a packet could not be delivered (e.g., network, host, port unreachable).
- **Type 11: Time Exceeded:** Used when a packet's TTL reaches 0. This is the fundamental mechanism behind **`traceroute`**.

**How Traceroute Works:**
1. The source sends a series of IP datagrams to the destination. The first has a **TTL=1**, the second **TTL=2**, and so on.
2. The *n*th router discards the *n*th datagram (because the TTL expires) and sends an **ICMP Time Exceeded** message back to the source. This message reveals the router's identity.
3. The source stops when it receives an **ICMP Port Unreachable** message from the destination host, which indicates a packet finally reached it.

**ICMPv6:** A new version of ICMP exists for IPv6, adding new types and codes required by the new protocol's functionality.
### **Network Management and SNMP, NETCONF/YANG**
**Network Management** includes the set of architecture, protocols, and tools that allow network administrators to monitor, configure, and maintain network devices.

**Key Protocols:**
- **SNMP (Simple Network Management Protocol):** A widely used protocol for network management. Its core components are:
    - **Managed Device:** A network node (router, switch, server) that is managed.
    - **Agent:** Software running on the managed device that maintains management data and communicates with the manager.
    - **Network Management Station (NMS):** The central management system that runs applications to monitor and control managed devices.
    - **Management Information Base (MIB):** A structured, hierarchical database of managed objects on a device that can be queried or set.
    - **SNMP Protocol:** The protocol used for communication between the NMS and agents, allowing the manager to **get** (retrieve), **set** (configure), and **trap** (receive notifications from) managed devices.
- **NETCONF/YANG:**
    - **NETCONF:** A more modern network management protocol that uses XML-based data encoding and remote procedure calls (RPCs) over SSH. It provides operations to retrieve, configure, copy, and delete configuration data.
    - **YANG:** A **data modeling language** used to model the configuration and state data manipulated by NETCONF. It defines the structure, constraints, and semantics of the managed data.
### **Network Management and SNMP, NETCONF/YANG**
**Network Management** is the deployment and coordination of hardware, software, and human elements to monitor, configure, analyze, and control a network to meet performance and QoS requirements.
#### **The Network Management Framework**
The framework consists of several key components: (INSERT FIGURE 5.20, ELEMENTS OF NETWORK MANAGEMENT, HERE)
- **Managing Server:** An application (with human managers) in a central Network Operations Center (NOC) that collects, processes, and dispatches management information and commands.
- **Managed Device:** Network equipment (routers, switches, hosts, etc.) that is managed.
- **Data (State):** Information associated with a managed device.
    - **Configuration Data:** Set by the manager (e.g., IP address).
    - **Operational Data:** Acquired by the device (e.g., OSPF neighbors).
    - **Device Statistics:** Status indicators and counts (e.g., packets dropped).
- **Network Management Agent:** A software process running on the managed device that communicates with the managing server and executes commands locally.
- **Network Management Protocol:** The protocol that runs between the managing server and managed devices, enabling querying and control. It provides capabilities but does not _do_ the management itself.

**Three Common Management Approaches:**
1. **CLI (Command Line Interface):** Direct, device-specific commands (via console, Telnet, SSH). Powerful but error-prone and difficult to scale.
2. **SNMP/MIB:** Uses the **Simple Network Management Protocol** to query and set data in a device's **Management Information Base**. Good for monitoring; less so for large-scale configuration.
3. **NETCONF/YANG:** A modern approach with a **network-wide, holistic view**, emphasizing configuration management with correctness constraints and atomic operations across multiple devices.
#### **The Simple Network Management Protocol (SNMP) and MIB**
**SNMPv3** is an application-layer protocol used for network management, typically running over **UDP**.

**Management Information Base (MIB):**
- A structured, hierarchical database of **managed objects** on a device.
- Objects are defined using a formal data description language called **SMI (Structure of Management Information)**.
- Related objects are grouped into **MIB modules**.

**SNMP Protocol Data Units (PDUs):** (INSERT TABLE 5.2, SNMPV3 PDU TYPES, HERE)
- **GetRequest, GetNextRequest, GetBulkRequest:** Sent from manager to agent to **retrieve** MIB object values. The agent replies with a **Response** PDU.
- **SetRequest:** Sent from manager to agent to **set** (modify) MIB object values.
- **Response:** Sent by an agent (or manager) in response to a request.
- **InformRequest:** Sent by one manager to notify another manager of MIB information.
- **SNMPv2-Trap:** An **asynchronous notification** sent from an agent to a manager to report an exceptional event (e.g., link failure, system reboot). (INSERT FIGURE 5.21, SNMP PDU FORMAT, HERE)

**Key Points:**
- SNMP is primarily used for **monitoring** rather than control, partly due to historical security concerns.
- **SNMPv3** added critical security and administration features that were lacking in earlier versions.
#### **NETCONF/YANG**
This is a more modern and powerful approach to network management, especially for configuration.
- **YANG (Yet Another Next Generation):** A **data modeling language** used to model the configuration and operational data for a network. It defines the structure, constraints, and semantics of the data.
- **NETCONF:** A network management protocol used to **install, manipulate, and delete** the configuration of network devices. It uses XML-based data encoding and RPCs over SSH.
- **Together:** YANG defines the "what" (the data model), and NETCONF defines the "how" (the protocol) to manage that data. This approach provides a structured, programmatic, and network-wide way to manage device configuration.
### **The Management Information Base (MIB) in Detail**
An MIB is a structured collection of **managed objects** that represent a device's operational state, configuration, and statistics.
- **MIB Objects:** Can be counters (e.g., number of IP datagrams discarded), descriptive info (e.g., software version), status information, or protocol-specific data.
- **MIB Modules:** Related MIB objects are grouped into modules. There are hundreds of standard IETF MIB modules (e.g., for IP, TCP, UDP) and many more vendor-specific ones.
- **SMI (Structure of Management Information):** The formal data description language used to define the syntax and semantics of MIB objects, ensuring they are unambiguous.

**Example MIB Object: `ipSystemStatsInDelivers`**
- **Type:** A 32-bit, read-only counter.
- **Purpose:** Tracks the total number of IP datagrams successfully delivered to an upper-layer protocol (like TCP, UDP, or ICMP) on the managed device.
- This object is defined within the IP MIB module ([RFC 4293]).
### **The Network Configuration Protocol (NETCONF) and YANG**
This is a modern framework for network management, with a strong emphasis on **configuration**.
#### **NETCONF Protocol**
NETCONF is a protocol that provides mechanisms to install, manipulate, and delete the configuration of network devices.
- **Operation:** Uses a **Remote Procedure Call (RPC)** model. Messages are encoded in **XML** and exchanged over a **secure, connection-oriented session** (like TLS over TCP).
- **Session Flow:** (INSERT FIGURE 5.22, NETCONF SESSION, HERE)
    1. Establish a secure connection.
    2. Exchange `<hello>` messages to declare capabilities.
    3. Exchange `<rpc>` (request) and `<rpc-reply>` (response) messages.
    4. Managed devices can send asynchronous `<notification>` messages.
    5. Close the session.

**Key NETCONF Operations:** (INSERT TABLE 5.3, SELECTED NETCONF OPERATIONS, HERE)
- **`<get-config>`, `<get>`:** Retrieve configuration and operational data from the device.
- **`<edit-config>`:** Modify the device's configuration. Supports atomic transactions and rollback on error.
- **`<lock>`, `<unlock>`:** Lock the device's configuration to prevent conflicting changes from other sources.
- **`<create-subscription>`:** Subscribe to event notifications from the device.

**Example NETCONF Message:**  
An `<edit-config>` message to set the MTU of an interface to 1500 bytes is a human-readable XML document that clearly specifies the target and the new value. The device replies with an `<ok/>` message upon success.
#### **YANG (Yet Another Next Generation)**
YANG is the **data modeling language** used with NETCONF.
- **Purpose:** To **model** the configuration and operational data used by NETCONF. It precisely defines the structure, constraints, and semantics of the data.
- **Function:** Similar to **SMI** for SNMP, but more powerful and modern.
- **Capabilities:**
    - Defines a hierarchy of data.
    - Allows modelers to express **constraints** that a valid configuration must satisfy, helping to prevent errors.
    - Used to specify NETCONF notifications.
- **Modules:** YANG definitions are contained in modules, from which XML documents for device configuration can be generated.