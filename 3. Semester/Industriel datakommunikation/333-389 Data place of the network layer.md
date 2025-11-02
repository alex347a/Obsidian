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

