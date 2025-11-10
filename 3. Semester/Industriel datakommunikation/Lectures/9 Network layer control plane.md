### summary
![[Pasted image 20251110082144.png]]
### Network-layer functions
![[Pasted image 20251110082154.png]]
### Routing protocols
![[Pasted image 20251110082411.png]]
### Graph abstraction of the network
![[Pasted image 20251110082542.png]]
E = edges (vertices), which is the links.
### Graph abstraction: cost
![[Pasted image 20251110082825.png]]
### Routing algorithm classification
![[Pasted image 20251110082950.png]]
### A link-state routing algorithm
![[Pasted image 20251110083113.png]]
### Dijkstra's algorithm: example
![[Pasted image 20251110083550.png]]
You simply check the paths which ones have the lowest combined weight, if you can find another path that has a lower weight you update the table, if not you keep the lowest value in the table. So this algorithm checks all paths and finds the shortest path to all routers and maps them in the forwarding table.
![[Pasted image 20251110084231.png]]
![[Pasted image 20251110084755.png]]
### Distance vector routing algorithm
![[Pasted image 20251110085005.png]]
### Bellman-Ford example
![[Pasted image 20251110085234.png]]
You add the cost of all of the neighbours of the starting point to the end point and thereby find the shortest path. This has the infinity counting up problem when two links think they are both the shorter path to the destination and keep going through each other until one of them realise another link is shorter. This is solved by Poison reverse, where it sets its number to infinity if it is going through the same one as before.
### Distance vector algorithm strategy
![[Pasted image 20251110090347.png]]
### Comparison of LS and DV algorithms
![[Pasted image 20251110093454.png]]
### Intra Autonomous System Routing
![[Pasted image 20251110093845.png]]
### Internet approach to scalable routing
![[Pasted image 20251110094121.png]]
### Interconnected AS's
![[Pasted image 20251110094305.png]]
### Inter-AS tasks
![[Pasted image 20251110094348.png]]
### Intra-AS routing
![[Pasted image 20251110094501.png]]
### OSPF: Open Shortest Path First
![[Pasted image 20251110094643.png]]
### Hierarchical OSPF
![[Pasted image 20251110094753.png]]
### Internet inter-AS routing: BGP
![[Pasted image 20251110094920.png]]
1 inter-AS routing BGP to rule them all, since all intranet can have different protocols.
![[Pasted image 20251110095137.png]]
**eBGP (external BGP)** is a BGP session between routers in **different** ASs. Used to exchange routes across AS boundaries. **iBGP (internal BGP)** a BGP session between routers in the **same** AS. Used to ensure all routers in the AS have consistent routing information.
![[Pasted image 20251110095301.png]]
### Path attributes and BGP routes
![[Pasted image 20251110095444.png]]
### BGP path advertisement
![[Pasted image 20251110095631.png]]
### BGP: achieving policy via advertisements
![[Pasted image 20251110095821.png]]
![[Pasted image 20251110095839.png]]
### Hot potato routing
![[Pasted image 20251110095851.png]]
### Intra-AS vs. inter-AS routing
![[Pasted image 20251110100247.png]]
### SDN: Software-Defined Network
![[Pasted image 20251110100352.png]]
![[Pasted image 20251110100649.png]]
![[Pasted image 20251110100702.png]]
![[Pasted image 20251110100754.png]]
### ICMP: Internet Control Message Protocol
![[Pasted image 20251110101127.png]]
### Traceroute and ICMP
![[Pasted image 20251110101409.png]]
