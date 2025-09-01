![[09 Data communication Slide.pdf]]

| Slide: | Concept:                                                              |
| ------ | --------------------------------------------------------------------- |
| 5-17   | Communication interfaces, Data, synchronous clock, asynchronous clock |
| 18-21  | SSDuplex, Half Duplex, simplex                                        |
| 22-24  | Protocol                                                              |
| 25-30  | Digital sensors                                                       |
| 31-47  | I2C (Inter- integrated circuit)                                       |
| 48-53  | I2C in pico                                                           |
| 54-73  | SPI (Serial Peripheral Interface)                                     |
| 74-78  | SPI in pico                                                           |
| 79-95  | UART (Universal Asyncronous Receiver Transmitter)                     |
| 96-111 | UART in pico                                                          |
**Communication interfaces, Data, synchronous clock, asynchronous clock**

- Communication interfaces are methods for exchanging data between devices.
- Data refers to the information being transferred.
- Synchronous clock: Data transfer is synchronized with a clock signal.
- Asynchronous clock: Data transfer is not dependent on a clock signal; timing is determined by start and stop bits.

**Duplex, Half Duplex, Simplex**

- Duplex: Two-way communication.
- Half Duplex: Two-way communication, but not simultaneously.
- Simplex: One-way communication only.

**Protocol**

- A set of rules that govern communication between devices, ensuring proper data exchange.
- Examples: (not so important)
  - **HTTP (Hypertext Transfer Protocol)**
    
    - Used for transferring web pages over the internet. It’s the foundation of data exchange on the World Wide Web.
- **FTP (File Transfer Protocol)**
    
    - Enables the transfer of files between a client and a server on a network. Commonly used for uploading files to a website.
- **TCP/IP (Transmission Control Protocol/Internet Protocol)**
    
    - The foundational protocols for network communication over the internet, handling data transmission and ensuring reliable connections.
- **Bluetooth**
    
    - A wireless protocol for short-range communication between devices, such as phones, computers, and speakers.
- **USB (Universal Serial Bus)**
    
    - Protocol for data transfer and power supply between computers and peripheral devices like keyboards, mice, and storage.
- **CAN (Controller Area Network)**
    
    - Used in automotive and industrial applications for communication among microcontrollers and devices without a host computer.
- **NFC (Near Field Communication)**
    
    - A protocol for short-range wireless communication, commonly used for contactless payments and secure data exchange between smartphones.

**Digital sensors**

- Sensors that convert physical signals into digital data, enabling interaction with microcontrollers.

**I2C (Inter-integrated circuit)**

- A communication protocol using two wires for data transfer: SDA (data) and SCL (clock). It's used for communication between multiple devices.
  ![[I2C.jpg]]

**I2C in pico**

- I2C implementation on the Raspberry Pi Pico for connecting peripherals using the I2C protocol, supporting multiple devices on the same bus.

**SPI (Serial Peripheral Interface)**

- A communication protocol that uses four signals: MOSI, MISO, SCK, and SS, allowing high-speed communication between a master and multiple peripherals.
  ![[SPI.jpg]]

**SPI in pico**

- SPI on the Raspberry Pi Pico allows easy connection to various peripherals, with multiple devices controlled by a single master.

**UART (Universal Asynchronous Receiver Transmitter)**

- A communication protocol for transmitting and receiving data asynchronously using two lines: TX (transmit) and RX (receive), typically with start and stop bits.
  ![[UART.png]]

**UART in pico**

- UART on the Raspberry Pi Pico allows communication with external devices, like sensors or other microcontrollers, via TX and RX pins.