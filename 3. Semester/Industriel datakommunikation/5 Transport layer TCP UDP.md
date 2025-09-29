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
### UDP: Segment header
![[Pasted image 20250929084147.png]]
Sometimes you can send jumbo packages for example for sending an HD image and making sure the entire frame is received at once. Datagram contains all of the data, while the segments are parts of the data, so the segments are a part of a datagram.
### UDP: Checksum
![[Pasted image 20250929084817.png]]
#### Example
![[Pasted image 20250929085207.png]]
Then you just do the ones compliment of the number.