![[Pasted image 20250929082057.png]]
### Segments
![[Pasted image 20250929082109.png]]
Part of a message are sent at a time.
![[Pasted image 20250929082254.png]]
![[Pasted image 20250929082303.png]]
The transport layer doesnt concern itself with how we get across the internet, but mostly if we sucessfully got across (which doesn't even happen for UDP)
### Transport service requirements
![[Pasted image 20250929082349.png]]
![[Pasted image 20250929082433.png]]
### Transport vs. network layer
![[Pasted image 20250929082722.png]]
### Multiplex/demultiplex
![[Pasted image 20250929083130.png]]
Multiplexing is NOT packaging packets into one big package, but instead that all of the different packets are sent. Demultiplexing is making sure the packets are received at the right host.
### Summary of the transport layer's role
![[Pasted image 20250929083334.png]]
## UDP - User Datagram Protocol
![[Pasted image 20250929083422.png]]
### Connectionless demultiplexing 
![[Pasted image 20250929083706.png]]
For UDP the same destination port will have the same socket open no matter who the source IP addresses are sent from.
#### Example
![[Pasted image 20250929084028.png]]
### UDP: Segment header / Segment structure
![[Pasted image 20250929084147.png]]
Sometimes you can send jumbo packages for example for sending an HD image and making sure the entire frame is received at once. Datagram contains all of the data, while the segments are parts of the data, so the segments are a part of a datagram.
### UDP: Checksum
![[Pasted image 20250929084817.png]]
#### Example
![[Pasted image 20250929085207.png]]
Then you just do the ones compliment of the number. The checksum is computed at the sender, the sum is computed at both the sender and receiver, so the receiver calculates a sum from its received data and checks if it fits the checksum that was sent from the sender. It is not perfect, but it works pretty well for how easy it is to compute and is therefore a good match for UDP.
## TCP - Transmission Control Protocol
![[Pasted image 20250929101906.png]]
Throughput: no means that there is no guarantee of what the throughput rate is.
![[Pasted image 20250929102053.png]]
### TCP segment structure
![[Pasted image 20250929102738.png]]
RST: RESET
SYN: SYNCHRONIZE
FIN: FINISH
![[Pasted image 20250929103117.png]]
#### Example
![[Pasted image 20250929103336.png]]
There are two different sequences for the hosts and when they send the number it means they have received data up to that sequence, so the number is the next to be sent. 
![[Pasted image 20250929103737.png]]
### Example threaded vs. non-threaded
![[Pasted image 20250929103921.png]]
![[Pasted image 20250929104238.png]]
Threaded is if one process needs to talk to different users at once.
![[Pasted image 20250929104752.png]]
### Retransmission scenarios
![[Pasted image 20250929104947.png]]
Cumulative acknowledgements: the connection knows that all data up to that point have been received.
### TCP Fast retransmit
![[Pasted image 20250929105107.png]]
### TCP Connection management
![[Pasted image 20250929105214.png]]
