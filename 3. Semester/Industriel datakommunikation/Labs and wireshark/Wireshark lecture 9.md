1. What is the IP address of your host? What is the IP address of the destination host?
10.126.65.89 is the source, 143.89.209.9 is the destination
![[Pasted image 20251110103652.png]]
2. Why is it that an ICMP packet does not have source and destination port numbers?
	Because you are not asking for the port on a router, you are asking the router not a server
3. Examine one of the ping request packets sent by your host. What are the ICMP type and code numbers? What other fields does this ICMP packet have? How many bytes are the checksum, sequence number and identifier fields?
	Type 8 code 0 (echo (ping) request), the checksum is 2 bytes, sequence number (BE): 6048 (LE): 40983, identifier fields (BE) 1 and (LE) 256
![[Pasted image 20251110104347.png]]
4. Examine the corresponding ping reply packet. What are the ICMP type and code numbers? What other fields does this ICMP packet have? How many bytes are the checksum, sequence number and identifier fields?
Type 0 code 0, identifier (BE) 1 and (LE) 256, sequence number (BE): 6048 (LE): 40983
5. What is the IP address of your host? What is the IP address of the target destination host?
The same as last:
![[Pasted image 20251110105645.png]]
6. If ICMP sent UDP packets instead (as in Unix/Linux), would the IP protocol number still be 01 for the probe packets? If not, what would it be?
	UDP has the protocol 