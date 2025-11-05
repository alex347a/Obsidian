### The network layer at the host
![[Pasted image 20251103082848.png]]
### The network layer at the router
![[Pasted image 20251103082906.png]]
### Network layer
![[Pasted image 20251103082923.png]]
### Two key network layer functions 
![[Pasted image 20251103082936.png]]
### Network layer: Data plane vs. control plane
![[Pasted image 20251103082952.png]]
### Per-router control plane
![[Pasted image 20251103083007.png]]
The routers know how to reach the others by communicating through the other routers, so not every router has a direct connection to another router, but it will find a way to a router that is connected to the router it wants to communicate with.
### Logically centralized control plane
![[Pasted image 20251103083026.png]]
### Network service model
![[Pasted image 20251103083042.png]]
### Router architecture overview
![[Pasted image 20251103083100.png]]
It's a fabric because the connections are interwoven together, it's just an electrical circuit.
### Input port functions
![[Pasted image 20251103083117.png]]
![[Pasted image 20251103083154.png]]
### Destination-based forwarding
![[Pasted image 20251103083200.png]]
You just modify the forwarding table.
### Longest prefix matching
![[Pasted image 20251103083216.png]]
The first example goes to 0, the second goes to 1.
### Switching fabrics
![[Pasted image 20251103083228.png]]
The first one is slow, but it's cheap and can transfer multiple at a time, the second one can only do one at a time, but it's cheap, the third one is fast, but expensive.
### Input port queuing
![[Pasted image 20251103083234.png]]
### Output ports
![[Pasted image 20251103083249.png]]
### Scheduling mechanisms
![[Pasted image 20251103083258.png]]
### The internet network layer
![[Pasted image 20251103083310.png]]
### IP datagram format
![[Pasted image 20251103083324.png]]
Type of service er vigtigheden af dataet, så man kan prioritere.
### IP fragmentation, reassembly
![[Pasted image 20251103083334.png]]
### IP fragmentation and reassembly
![[Pasted image 20251103083345.png]]
Since they have different IP's it shouldn't be an issue but since people on the same network use NAT, it will look like they share the same public IP. In practise it isn't an issue because the ID is a random 16 bit number.
### IP addressing: introduction
![[Pasted image 20251103083408.png]]
![[Pasted image 20251103101131.png]]
### Subnets
![[Pasted image 20251103101202.png]]
![[Pasted image 20251103101213.png]]
### IP addressing: CIDR
![[Pasted image 20251103101924.png]]
![[Pasted image 20251103101934.png]]
1 subnet because its out of 16, so 223.1 is all the same, but if it was 24, then the next number would also count making it a higher number of subnets.
### IP addresses: How to get one?
![[Pasted image 20251103102050.png]]
### DHCP: Dynamic Host Configuration Protocol
![[Pasted image 20251103102157.png]]
### DHCP client-server scenario
![[Pasted image 20251103102258.png]]
### DHCP: more than IP addresses
![[Pasted image 20251103102315.png]]
### IP addresses: how to get one?
![[Pasted image 20251103102705.png]]
![[Pasted image 20251103102723.png]]
### NAT: Network Address Translation
![[Pasted image 20251103103226.png]]
![[Pasted image 20251103103235.png]]
![[Pasted image 20251103103239.png]]
![[Pasted image 20251103103245.png]]
![[Pasted image 20251103103249.png]]
### Port forwarding
![[Pasted image 20251103103254.png]]
### IPv6: Motivation
![[Pasted image 20251103103300.png]]
### IPv6 datagram format
![[Pasted image 20251103103306.png]]
Priority er f.eks. best effort, voice, excellent effort osv. flow er at man f.eks. kan skrive at dataet er videostreaming, og så kan der hurtigere findes ud af hvor dataet skal hen. Next hdr er hvilken type af data det er, f.eks. TCP, UDP, ICMPv6 osv.
### Transitioning from IPv4 to IPv6
![[Pasted image 20251103103314.png]]
### Tunnelling
![[Pasted image 20251103103402.png]]
### IPv6: adoption
![[Pasted image 20251103103413.png]]
### Generalized forwarding and SDN (Software-Defined Networking)
![[Pasted image 20251103105108.png]]
### OpenFlow data plane abstraction
![[Pasted image 20251103105200.png]]
![[Pasted image 20251103105217.png]]
### Openflow: Flow table entries
![[Pasted image 20251103105226.png]]
