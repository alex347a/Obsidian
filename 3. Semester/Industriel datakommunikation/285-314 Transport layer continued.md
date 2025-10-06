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

This is up to page 298, need fast recover and so forth.