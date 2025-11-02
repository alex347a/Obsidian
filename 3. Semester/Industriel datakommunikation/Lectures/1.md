#### Transmission modes
Duplex
half-duplex
simplex
![[Duplex, half-duplex, simplex.png]]

#### Bits and bytes
Bit is a unit of information a byte is 8 bits.
on or off is 1 bits. 
4 states are 2 bits
numbers are more bits.

#### Communicating one bit
Examples are
Wire (copper):

| 0    | 1     |
| ---- | ----- |
| 0 V  | 5 V   |
| 12 V | -12 V |
Radio (air)

| AM                |
| ----------------- |
| FM                |
| frequency-hopping |
AM stands for amplitude-modulation
FM stands for frequency-modulation

Light (fiber/air)

| 0         | 1       |
| --------- | ------- |
| Color     |         |
| No light  | Light   |
| Flag down | Flag up |

#### Parallel and serial communication
Parrallel has multiple wires and serial is communcation over one wire.
Serial - one wire and you can either pull up or down to start communication. 

#### Endianness
Big Endian (Motorola)
MSB (most significant bit) first

Little Endian (Intel)
LSB (least significant bit) first
#### Information and exformation
Information is what you send and exformation is what you don't send. So exformation is how the message is to be interpreted while information is the actual message. The start bit is part of the information.

#### Protocols
Electrically: 0 - 5 V
Mathematically: 0 - 1
Logically: On - Off
Functionally, Light - No light

#### Binary and ASCII
Old ASCII used 7 bits and 1 parity bit.

![[Binary and ASCII.png]]

#### Network topologies
![[Network topologies.png]]
BUS uses a shared medium.
RING can only go to the next device.
MESH is that everyone are connected to at least one other device. A full MESH is that everyone is connected to everyone.
STAR only the links from the receiver and transmitter is occupied while in BUS the link is shared.
TREE the devices are connected to more and more devices down the ladder.

MESH and STAR are most common.

#### Peer-to-peer / multidrop
![[Peer-to-peer vs. multidrop.png]]

You can transfer data using a direct link without occupying the server. Multidrop is when they are all connected to the same communication bus. 

#### Sharing communication media
Synchronize so no one interrupts.
Token passing, like giving someone a ball and then they can communicate and give the ball to someone else afterwards.
FDM - Frequency Division Multiplexing.
TDM - Time Division Multiplexing.
Collision detect and recover.

#### FDM and TDM
FDM is split up the frequencies so everyone speaks at different frequencies at the same time.
TDM where the time is divided for the frequencies, so you take turns talking.
![[FDM and TDM.png]]

#### Circuit switching
![[Circuit Switching.png]]
Find a line and reserve it, mostly used for old telephone lines.

#### Packet switching
Packets are packages of information that are sent into junctions that send the packets in the right direction. The packets also have the advantage of being able to be split up and sent to different receiveres.
![[Packet Switching.png]]

#### Layering and encapsulation
![[Layering and encapsulation.png]]
The data gets packaged in a way that it can be sent to the right place. The h stands for header and f for footer.

#### OSI Reference Model
![[OSI Reference Model.png]]
The model is theoretical. The information gets more and more encapsulated until it is sent as bits whereafter the receiver decodes the information.
APDU stands for Application Data Protocol Units.

#### Communication speed
![[Communication speed.png]]
Bitrate is how fast you can transfer data, while delay is how long it takes before it is received. 

#### Other communication options
![[Other communication options.png]]
#### SPI
![[SPI.png]]
#### I2C
![[I2C.png]]
