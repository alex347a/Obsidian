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