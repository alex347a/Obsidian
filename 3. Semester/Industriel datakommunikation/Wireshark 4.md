1. Run nslookup to obtain the IP address of the web server for the Indian Institute of Technology in Bombay, India: www.iitb.ac.in. What is the IP address of www.iitb.ac.in
![[Pasted image 20250922094655.png]]
2. What is the IP address of the DNS server that provided the answer to your nslookup command in question 1 above?
   10.220.2.24
   
3. Did the answer to your nslookup command in question 1 above come from an authoritative or non-authoritative server?
   Non-authoritative
   
4. Use the nslookup command to determine the name of the authoritative name server for the iit.ac.in domain. What is that name? (If there are more than one authoritative servers, what is the name of the first authoritative server returned by nslookup)? If you had to find the IP address of that authoritative name server, how would you do so?
unknown. I can just access a database and search the IP address.

![[Pasted image 20250922095300.png]]

5. Locate the first DNS query message resolving the name gaia.cs.umass.edu. What is the packet number in the trace for the DNS query message? Is this query message sent over UDP or TCP?
![[Pasted image 20250922100621.png]]
UDP. Packet number 30.
6. Now locate the corresponding DNS response to the initial DNS query. What is the packet number in the trace for the DNS response message? Is this response message received via UDP or TCP?