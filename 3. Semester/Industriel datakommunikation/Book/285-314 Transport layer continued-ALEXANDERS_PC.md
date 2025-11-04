### **Principles of Congestion Control**

Congestion occurs when too many sources send too much data too fast for the network to handle, leading to router buffer overflow and packet loss. While retransmissions treat the _symptom_ (loss), congestion control aims to treat the _cause_ by throttling senders.
### **The Causes and the Costs of Congestion**
**Scenario 1: Two Senders, a Router with Infinite Buffers**
- **Setup:** Two hosts send at rate `λ_in` over a shared link of capacity `R`. The router has **infinite buffers**.
- **Observation:**
    - **Throughput:** When `λ_in` is between 0 and R/2, throughput equals the sending rate. When `λ_in` exceeds R/2, the maximum throughput for each connection is capped at **R/2**.
    - **Delay:** As the sending rate approaches R/2, the **queuing delay becomes infinite** because the buffer backlog grows without bound.
- **Cost of Congestion:** **Extremely large queuing delays** occur as the packet arrival rate nears the link capacity, even without packet loss.
![[Pasted image 20251006084040.png]]
**Scenario 2: Two Senders and a Router with Finite Buffers**
- **Setup:** Same as Scenario 1, but the router has **finite buffers** (so packets are dropped), and the senders use **reliable data transfer** with retransmissions.
- **Offered Load (`λ'_in`):** The total rate of data sent into the network, including original data and retransmissions.
- **Observations:**
![[Pasted image 20251006084222.png]]
    - **"Perfect" Sending:** If the sender could magically send only when buffer space is available, throughput would equal `λ_in` (up to R/2) with no loss. (Figure 3.46a)
    - **Realistic Retransmission:** Senders retransmit lost packets. This means `λ'_in > λ_in`. The useful throughput (`λ_out`) is less than the offered load because some of the capacity is wasted on sending retransmissions. (Figure 3.46b)
    - **Premature Timeout:** If a sender retransmits a delayed-but-not-lost packet, the router does **wasted work** forwarding duplicate packets. This further reduces the maximum useful throughput. (Figure 3.46c)
- **Costs of Congestion:**
    1. Senders must perform **retransmissions** to compensate for lost packets.
    2. **Wasted transmission capacity** is used to send unneeded retransmissions.

**Scenario 3: Four Senders, Routers with Finite Buffers, and Multihop Paths**
- **Setup:** Multiple senders use overlapping multi-hop paths.
![[Pasted image 20251006084242.png]]
- **Observation:** As the offered load becomes very large, the throughput for a connection can **drop to zero**. This is because a packet dropped later on its path wastes all the transmission capacity used to get it to the point of drop.
- **Cost of Congestion:** **Upstream transmission capacity is wasted** on packets that are eventually dropped downstream.

**Summary of Congestion Costs:**
1. Large queuing delays.
2. Sender must perform retransmissions for dropped packets.
3. Wasted capacity due to unneeded retransmissions of delayed packets.
4. Wasted upstream capacity when a packet is dropped after traversing multiple links.
### **Approaches to Congestion Control**
There are two broad approaches to congestion control.
**1. End-to-End Congestion Control**
- The **network layer (IP) provides no explicit help**.
- The end systems must **infer congestion** based on observed network behavior (e.g., packet loss, increased delay).
- **TCP uses this approach.** It interprets segment loss (via timeout or duplicate ACKs) as a sign of congestion and reduces its sending rate.

**2. Network-Assisted Congestion Control**
- **Routers provide explicit feedback** to the sender/receiver about the congestion state of the network.
- This feedback can be:
    - A direct **choke packet** sent from a router to the sender.
![[Pasted image 20251006084327.png]]
    - A **mark in a packet header** (e.g., setting a bit) as it travels from sender to receiver. The receiver then informs the sender. This method takes a full round-trip time.
- Examples: Early SNA, DECnet, ATM, and modern Explicit Congestion Notification (ECN) in IP/TCP.

### **TCP Congestion Control**
TCP uses **end-to-end congestion control**, as the IP layer provides no explicit network feedback. The sender infers congestion and adjusts its rate accordingly.

**Classic TCP Congestion Control**
**How TCP Limits its Sending Rate:**
- TCP uses a **congestion window (`cwnd`)** to limit the amount of unacknowledged data in flight.
- The constraint is: `LastByteSent – LastByteAcked <= min{cwnd, rwnd}`
- Ignoring flow control (`rwnd`), the sender's rate is roughly **`cwnd / RTT`**.
- By adjusting `cwnd`, the sender controls its transmission rate.

**How TCP Perceives Congestion:**
- A **"loss event"** is the primary signal of congestion. This is either:
    1. A **timeout**.
    2. The receipt of **three duplicate ACKs** (which triggers fast retransmit).
- Loss is interpreted as an implicit indication that congestion has occurred somewhere in the network.

**How TCP Adjusts its Rate: The Guiding Principles**
1. **Decrease on Loss:** When a loss event occurs, decrease `cwnd` (and thus the sending rate).
2. **Increase on ACK:** When an ACK for new data arrives, increase `cwnd`. This makes TCP **self-clocking**—ACKs clock the arrival of new data.
3. **Bandwidth Probing:** TCP increases its rate until a loss event occurs, then backs off. This cycle of increasing and decreasing continuously probes the available bandwidth.
### **The TCP Congestion Control Algorithm**
The algorithm has three main parts: **Slow Start**, **Congestion Avoidance**, and **Fast Recovery**.
**1. Slow Start**
- **Goal:** Quickly find the available bandwidth.
- **Initial State:** `cwnd` starts at **1 MSS**.
- **Growth:** `cwnd` increases by **1 MSS for every ACK received**.
    - This leads to **exponential growth** of the sending rate, doubling `cwnd` every RTT. 
![[Pasted image 20251006084552.png]]
- **How Slow Start Ends:**
    - **Timeout:** A timeout indicates severe congestion. React by:
        - `ssthresh` (slow start threshold) = `cwnd / 2`
        - `cwnd` = **1 MSS**
        - Restart Slow Start.
    - **`cwnd` reaches `ssthresh`:** Transition to **Congestion Avoidance**.
    - **Three Duplicate ACKs:** Transition to **Fast Recovery**.

**2. Congestion Avoidance**
- **Goal:** Increase the rate cautiously, probing for additional bandwidth without causing congestion.
- **Growth:** `cwnd` increases by **roughly 1 MSS per RTT**.
    - A common implementation: For each new ACK received, increase `cwnd` by `MSS * (MSS / cwnd)`. This results in a linear increase over time.
- **How Congestion Avoidance Ends:**
    - **Timeout:** Treat as severe congestion. Same reaction as in Slow Start:
        - `ssthresh = cwnd / 2`
        - `cwnd = 1 MSS`
        - Enter **Slow Start**.
    - **Three Duplicate ACKs:** Treat as a milder form of congestion. React by:
        - `ssthresh = cwnd / 2`
        - `cwnd = ssthresh + 3 MSS` (This is part of Fast Recovery)
        - Enter **Fast Recovery**.

**Summary FSM (Figure 3.51):**  
![[Pasted image 20251006084448.png]]
The TCP congestion control algorithm can be represented as a finite state machine that transitions between these states (Slow Start, Congestion Avoidance, Fast Recovery) based on the events of ACK arrival, duplicate ACKs, and timeouts.
### **Fast Recovery**
- **Purpose:** A recommended (but not mandatory) component for handling loss indicated by **three duplicate ACKs**, which suggests that some data is still getting through.
- **Action:**
    - On entering Fast Recovery, `cwnd` is set to `ssthresh + 3 MSS` (accounting for the three duplicate ACKs received).
    - For each **additional duplicate ACK** received, `cwnd` is increased by **1 MSS**. This artificially inflates the window to keep data flowing.
    - When the **ACK for the retransmitted segment** (the one that caused the duplicate ACKs) finally arrives, `cwnd` is set to `ssthresh` and TCP enters **Congestion Avoidance**.
- **Timeout in Fast Recovery:** If a timeout occurs, TCP behaves as it would in Slow Start or Congestion Avoidance: `cwnd` is set to **1 MSS** and it enters **Slow Start**.

### **TCP Tahoe vs. TCP Reno**
- **TCP Tahoe:** On _any_ loss event (timeout or 3 dup ACKs), it always sets `cwnd = 1 MSS` and enters Slow Start.
- **TCP Reno:** Incorporates **Fast Recovery**. It only resets `cwnd` to 1 on a _timeout_. For triple duplicate ACKs, it uses Fast Recovery, which is less severe. (INSERT FIGURE 3.52 HERE)

### **The AIMD Principle**
- TCP's core congestion control mechanism is **Additive-Increase, Multiplicative-Decrease (AIMD)**.
- **Additive Increase:** In Congestion Avoidance, `cwnd` increases by ~1 MSS per RTT.
- **Multiplicative Decrease:** On a loss event, `cwnd` is halved.
- This creates the classic **"sawtooth" pattern** of TCP's sending rate. (INSERT FIGURE 3.53 HERE)
### **TCP CUBIC**
- A more modern TCP flavor that changes the **Congestion Avoidance** phase to be more efficient, especially on high-speed, long-distance networks.
- **Goal:** After a loss event, **ramp up the sending rate more quickly** to the pre-loss value (`W_max`), and then probe more carefully for new bandwidth.
- **Method:** Instead of a linear increase, CUBIC increases `cwnd` based on a **cubic function** of the time since the last loss event.
    - It grows quickly when far from `W_max`.
    - It grows slowly when close to `W_max` to avoid causing another loss immediately.
- **Result:** TCP CUBIC can achieve higher throughput and better utilize available bandwidth than TCP Reno.
![[Pasted image 20251006085916.png]]
### **Network-Assisted and Delay-Based Congestion Control**
**1. Explicit Congestion Notification (ECN)**
- A form of **network-assisted congestion control**.
- **How it works:**
    1. A congested router can **mark a bit** in the IP header of a packet instead of dropping it.
    2. The receiver sees this mark and **echoes it back** to the sender in a TCP ACK.
    3. The sender reacts to this explicit signal **by halving `cwnd`**, just as if a loss had occurred, but _before_ a loss actually happens.
- This avoids the cost of packet loss and retransmission, leading to better performance.
![[Pasted image 20251006085943.png]]
**2. Delay-Based Congestion Control (e.g., TCP Vegas, BBR)**
- These protocols use **increases in RTT** (queuing delay) as a signal of impending congestion, rather than waiting for packet loss.
- **Intuition:** "Keep the pipe just full, but no fuller." Increase the sending rate until queuing delays start to build up, then back off.
- **Examples:** TCP Vegas, BBR (used by Google). BBR is designed to compete fairly with loss-based TCP flows like CUBIC.
### Fairness
**Goal of Fairness:** When multiple flows share a bottleneck link, a fair congestion-control protocol should give each flow an **equal share** of the bottleneck bandwidth.

**Is TCP Fair?**
- TCP's AIMD algorithm, under **idealized conditions** (same RTT, same packet size, long-lived flows), converges to provide fairness among competing TCP connections.
![[Pasted image 20251006090019.png]]
- However, in practice, fairness can be broken:
    - **UDP:** Applications using UDP (e.g., VoIP, video streaming) do not have built-in congestion control and can grab an unfair share of bandwidth, "crowding out" TCP traffic.
    - **Parallel TCP Connections:** A single application (like a web browser) opening multiple parallel TCP connections to the same server will get a larger share of the bandwidth than an application using only a single connection.
    - **Different RTTs:** Connections with **shorter RTTs** can grab available bandwidth more quickly and thus achieve higher throughput than connections with longer RTTs.
### **Evolution of Transport-Layer Functionality**
**The Proliferation of TCP Flavours**
- While UDP and TCP are the foundational protocols, experience has shown they are not ideal for all scenarios.
- This has led to the development of many specialized versions of TCP:
    - **TCP CUBIC, BBR:** For high-speed, long-distance paths.
    - **DCTCP, DCQCN:** Optimized for data center networks.
    - Versions for wireless links, paths with packet reordering, and for different priorities.
- The common thread is the use of the **TCP segment format** and a goal of **fairness**.
### **QUIC: Quick UDP Internet Connections**
QUIC is an **application-layer protocol** that uses **UDP** as its underlying transport. It is designed to improve performance for secure HTTP and is the basis for **HTTP/3**.
**Key Features of QUIC:**
1. **Connection-Oriented and Secure:**
    - Requires a handshake to set up state.
    - **All packets are encrypted.**
    - **Major Innovation:** Combines the **transport connection handshake** with the **security (TLS) handshake** into a single step, reducing connection setup time from multiple RTTs to **1 RTT** (or 0 RTT for repeated connections).
![[Pasted image 20251006090233.png]]
2. **Streams:**
    - Allows **multiple application-level "streams"** to be multiplexed over a single QUIC connection.
    - Each stream provides reliable, in-order, bi-directional data delivery.
    - This solves the **Head-of-Line (HOL) Blocking** problem of TCP. If a packet for one stream is lost, only that stream is blocked; other streams can continue to deliver data.
![[Pasted image 20251006090249.png]]
3. **Reliable, TCP-Friendly Congestion Control:**
    - Provides **reliable data transfer on a per-stream basis**, using acknowledgment mechanisms similar to TCP.
    - Its congestion control algorithm is based on **TCP NewReno**, making it friendly to competing TCP traffic.
    - By implementing reliability and congestion control at the application layer, updates can be deployed much faster than changes to the core TCP protocol in operating systems.
### **Summary**
**Transport Layer Services:**
- The transport layer provides logical communication between application processes.
- It can range from a simple, **no-frills service** (like **UDP**) to a complex service with **reliability, flow control, and congestion control** (like **TCP**).

**Reliable Data Transfer (RDT):**
- Can be implemented at the link, network, transport, or application layer.
- The core principles involve **sequence numbers, acknowledgments, timers, and retransmissions**.

**TCP:**
- A complex, connection-oriented protocol that provides **reliable data transfer, flow control, and congestion control**.
- Its complexity is hidden from the application, which simply uses a socket interface.

**Congestion Control:**
- Essential to prevent network "gridlock."
- **Classic TCP** uses an **end-to-end, Additive-Increase, Multiplicative-Decrease (AIMD)** approach.
- Newer approaches include:
    - **TCP CUBIC:** Faster probing for bandwidth.
    - **Delay-based (e.g., BBR):** Uses increased delay as a congestion signal.
    - **ECN (Explicit Congestion Notification):** Network-assisted congestion control.

**Evolution:**
- The transport layer continues to evolve, with **QUIC** being a prime example of moving traditional transport-layer functions (reliability, congestion control) into the **application layer** for greater flexibility and faster deployment.