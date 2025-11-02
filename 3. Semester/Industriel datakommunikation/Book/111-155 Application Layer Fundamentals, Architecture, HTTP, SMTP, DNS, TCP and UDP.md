### Client-Server Architecture
An always-on host called a server services requests from many clients. The server has a fixed, well-known IP address. Clients do not communicate directly with each other. Examples include the Web, FTP, Telnet, and email. To handle high demand, services often use data centers with many servers to create a powerful virtual server.

### Peer-to-Peer (P2P) Architecture
Minimal reliance on dedicated servers. Instead, the application uses direct communication between intermittently connected hosts (peers), which are user-controlled devices. This architecture is self-scalable (each peer adds capacity by distributing resources) and cost-effective (no major server infrastructure). However, it faces challenges in security, performance, and reliability due to its decentralized nature. An example is the BitTorrent file-sharing protocol. 

### Communcating processes
Communication occurs between processes (running programs) on different end systems by exchanging messages across the network. These processes reside in the application layer.

**Client and Server Processes**  
In any communication session, one process is labeled the client and the other the server:
- The **client** is typically the process that initiates communication.
- The **server** is the process that waits to be contacted and responds to requests.  
    In some applications, like P2P, a process can act as both a client and a server in different sessions. For example, in file sharing, peer A downloading a file is the client for that transfer, while peer B uploading a file is the server.
### The Interface Between the Process and the Computer Network

A process communicates by sending and receiving messages through the underlying network via a software interface called a **socket**. A socket is analogous to a door: a process sends a message out through its socket, relying on the network infrastructure to deliver it to the destination process's socket.

As illustrated in Figure 2.3, a socket is the interface between the application layer and the transport layer within a host. It is the **Application Programming Interface (API)** used to build network applications.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.3.png]]
The application developer has control over:
1. The **choice of transport protocol** (e.g., TCP or UDP).
2. The ability to set a few **transport-layer parameters** (e.g., maximum buffer size, maximum segment size).

However, the developer has no control over the transport-layer side beyond these choices. Once the transport protocol is selected, the application is built using the services provided by that protocol. The operating system controls the transport-layer implementation.

### Addressing Processes (IP address and port number)
For a process on one host to send packets to a process on another host, the receiving process must be uniquely identified. This requires two pieces of information:
1. The **IP address** of the destination host.
2. A **port number** that specifies the receiving process (or socket) within that host.

An IP address is a 32-bit quantity that uniquely identifies a host on the Internet. The port number identifies the specific application process on the host, as a single host can run many network applications simultaneously. Well-known applications use standardized port numbers:
- **Web server:** port 80
- **SMTP mail server:** port 25
### Transport Services Available to Applications
The transport-layer protocol, chosen by the application developer, is responsible for delivering messages from the sending socket to the receiving socket. The choice depends on the specific services an application requires. Transport protocols can be evaluated along four key dimensions: reliable data transfer, throughput, timing, and security.
#### Reliable Data Transfer
Networks can lose packets due to buffer overflows or corruption. For many applications (e-mail, file transfer, web documents, financial apps), data loss is devastating. A transport protocol that **guarantees** correct and complete delivery provides **reliable data transfer**. The sending process can pass data into its socket with confidence it will arrive error-free at the receiver. Applications that cannot tolerate loss require this service. Conversely, **loss-tolerant applications** (like conversational audio/video) can tolerate some data loss, which may only cause minor glitches rather than a crucial failure.
#### Throughput
Throughput is the rate at which a sending process can deliver bits to the receiving process. As network conditions change, available throughput can fluctuate. A transport protocol can potentially provide a **guaranteed throughput** service, ensuring the available throughput is always at least at a specified rate (`r` bits/sec).
- **Bandwidth-sensitive applications** require a specific throughput. For example, an Internet telephony application encoding voice at 32 kbps must have this throughput sustained. If it cannot be provided, the application must encode at a lower rate or fail.
- **Elastic applications** can use any available throughput, with more being better. Examples include e-mail, file transfer, and web transfers. They do not have a strict minimum requirement.
#### Timing
A transport-layer protocol can provide **timing guarantees**, such as ensuring every bit sent arrives at the receiver's socket within a specified maximum delay (e.g., 100 msec). This service is critical for **interactive real-time applications** like:
- Internet telephony
- Virtual environments
- Teleconferencing
- Multiplayer games

These applications require tight timing constraints to avoid unnatural pauses (in conversation) or lag (in games), which degrade the user experience. For non-real-time applications, lower delay is preferable but not strictly required.
#### Security

A transport protocol can provide **security services**, including:
- **Confidentiality:** Encrypting data on the sending host and decrypting it on the receiving host to prevent eavesdropping.
- **Data Integrity:** Ensuring data is not altered in transit.
- **End-Point Authentication:** Verifying the identity of the communicating processes.

These services protect data even if it is intercepted during transmission.

![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.4.png]]
### Transport Services Provided by the Internet

The Internet offers two main transport protocols:
1. **UDP (User Datagram Protocol)**
2. **TCP (Transmission Control Protocol)**

When developing a network application, one of the first decisions is choosing between UDP and TCP, as each provides a different set of services.
### TCP Services
TCP provides two key services to applications:
- **Connection-oriented service:** Requires a handshake between client and server to establish a connection before data flow begins. This connection is full-duplex, allowing simultaneous two-way communication. The connection must be torn down after communication is complete.
- **Reliable data transfer:** Guarantees that all data sent is delivered without error, without loss, and in the correct order. A byte stream written to a socket will be received identically on the other end.

TCP also includes a **congestion-control mechanism** that throttles the sending rate when network congestion is detected, aiming to share network bandwidth fairly among all users. This benefits the overall health of the Internet.
### UDP Services

UDP is a lightweight, minimalistic transport protocol offering:
- **Connectionless service:** No handshake is required before communication begins.
- **Unreliable data transfer:** Provides no guarantee that messages will arrive, and those that do may arrive out of order.

UDP does not include congestion control. A sending process can inject data into the network at any rate, though the actual end-to-end throughput may be lower due to link capacity or congestion.
### Securing TCP (TLS)

Neither TCP nor UDP provides inherent encryption. Data sent in cleartext can be intercepted. To address this, **Transport Layer Security (TLS)** was developed as an enhancement to TCP. TLS provides critical security services:
- Encryption (confidentiality)
- Data integrity
- End-point authentication

TLS is not a separate transport protocol but an enhancement to TCP. TLS is implemented in the application layer using specialized libraries. An application passes cleartext data to a TLS socket, which encrypts it and passes it to the TCP socket for transmission. On the receiving end, TLS decrypts the data before delivering it to the application. 
### Application-Layer Protocols
An application-layer protocol defines the rules for communication between application processes running on different end systems. It specifies:

- **Message Types:** The types of messages exchanged (e.g., request messages, response messages).
- **Syntax:** The structure of messages, including how fields are defined and delineated.
- **Semantics:** The meaning of the information within each field.
- **Rules:** The timing for sending messages and how processes should respond.

Some protocols, like HTTP (for the Web), are public standards defined in RFCs. Others, like those used by Skype, are proprietary. It is crucial to distinguish between a **network application** (e.g., the Web, which includes browsers, servers, and document formats) and an **application-layer protocol** (e.g., HTTP, which defines the message exchange rules between browsers and servers). The protocol is a key component of the larger application.
### Network Applications
1. **The Web:** Uses HTTP. A client-server application for on-demand document retrieval.
2. **Electronic Mail:** Uses several application-layer protocols (e.g., SMTP).
3. **Directory Service (DNS):** Translates domain names to IP addresses. Invoked indirectly by other applications.
4. **Peer-to-Peer (P2P) Applications:** For file sharing and other decentralized services.
5. **Video Streaming:** Uses protocols like DASH for on-demand video delivery.
### The Web and HTTP
The World Wide Web, emerging in the early 1990s, revolutionized public access to the Internet. Its key features include:
- **On-Demand Operation:** Users access content when they want it.
- **Ease of Publishing:** Low cost for individuals to make information available.
- **Navigation Aids:** Hyperlinks and search engines facilitate information discovery.
- **Rich Content:** Supports photos, videos, and interactive elements via forms and JavaScript.
- **Platform Function:** Serves as the foundation for many other applications (e.g., YouTube, Gmail, Instagram, Google Maps).

The Web's application-layer protocol, HTTP, defines how browsers and servers communicate.
### HTTP
The HyperText Transfer Protocol (HTTP) is the core application-layer protocol of the Web, defined in RFCs 1945, 7230, and 7540. It is implemented as client and server programs that communicate by exchanging HTTP messages.
#### Web Terminology
- A **Web page** (or document) consists of multiple **objects**.
- An **object** is any addressable file, such as an HTML file, JPEG image, JavaScript file, CSS file, or video clip, each referenced by a unique **URL**.
- A typical Web page includes a **base HTML file** that references other objects via their URLs.
- A **URL** has two components: the **hostname** of the server and the **path name** of the object.
- **Browsers** (e.g., Chrome, Internet Explorer) act as HTTP clients.
- **Web servers** (e.g., Apache, Microsoft IIS) house Web objects and implement the server side of HTTP.
#### HTTP Operation
When a user requests a Web page (e.g., by clicking a hyperlink), the browser sends HTTP request messages for all objects in the page to the server. The server responds with HTTP response messages containing the requested objects.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.6.png]]
#### HTTP and TCP
HTTP uses **TCP** as its underlying transport protocol (not UDP). The process is as follows:
1. The HTTP client initiates a **TCP connection** with the server.
2. Once established, the browser and server communicate via their **socket interfaces**.
3. The client sends HTTP requests into its socket and receives HTTP responses from it.
4. The server receives requests from its socket and sends responses into it.
5. TCP provides **reliable data transfer**, ensuring HTTP messages arrive intact and in order. HTTP itself does not handle data loss or recovery—this is managed by TCP and lower layers.
#### Stateless Protocol
HTTP is a **stateless protocol**: the server does not retain any state information about clients. If the same client requests the same object multiple times, the server responds each time as if it were the first request, without remembering prior interactions.
#### HTTP Versions
- **HTTP/1.0:** The original version from the early 1990s.
- **HTTP/1.1:** The most commonly used version as of 2020.
- **HTTP/2:** A newer version increasingly supported by browsers and servers, offering performance improvements.
### Non-Persistent and Persistent Connections
When a client and server communicate over an extended period with multiple requests, a key design decision is whether to use a separate TCP connection for each request/response pair or a single shared connection.
- **Non-Persistent Connections:** Each request/response pair is sent over a **separate TCP connection**. The connection is closed immediately after the server sends the response.
- **Persistent Connections:** All requests and their corresponding responses are sent over the **same TCP connection**. The connection remains open for multiple transactions.
#### HTTP with Non-Persistent Connections
In this mode, used by default in HTTP/1.0, each TCP connection transports exactly one request and one response. The process for fetching a web page with a base HTML file and 10 images is as follows:
1. The client initiates a TCP connection to the server (port 80).
2. The client sends an HTTP request for the base HTML file.
3. The server sends the file in an HTTP response and then instructs TCP to close the connection.
4. The client receives the response, the TCP connection terminates, and the client parses the HTML.
5. **Steps 1-4 are repeated for each of the 10 referenced images (JPEGs).** This results in **11 separate TCP connections** for a single page.

**Performance Calculation:**  
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.7.png]]
The time to receive the base HTML file involves:
- **One RTT** for the TCP three-way handshake (client sends SYN, server responds with SYN-ACK).
- **Another RTT** for the client to send the HTTP request (piggybacked on the final ACK of the handshake) and receive the response.
- Plus the server's file transmission time.  
    Thus, the total response time is roughly **2 RTTs + transmission time**.

Browsers can open **parallel TCP connections** (e.g., multiple connections at once for images) to reduce total response time.
#### HTTP with Persistent Connections
This mode, the default in HTTP/1.1 and later, addresses the shortcomings of non-persistent connections:
1. The server leaves the TCP connection open after sending a response.
2. Subsequent requests and responses between the same client and server are sent over this same connection.
3. An entire web page (base HTML and all embedded objects) can be fetched over a single TCP connection.
4. Requests can be **pipelined**: the client can send multiple requests back-to-back without waiting for each response, improving efficiency.
5. The server eventually closes the connection after a period of inactivity (a timeout).

**Advantages over Non-Persistent:**
- **Reduced Overhead:** Eliminates the CPU and memory burden of establishing and tearing down multiple TCP connections.
- **Reduced Latency:** Avoids the handshake delay (1 RTT) for each object. Subsequent requests only incur the time to send the request and receive the response, significantly reducing total page load time.
- **Improved Performance:** Pipelining allows for more efficient use of the connection.
### HTTP Message Format
HTTP messages are defined in ASCII text, making them human-readable. There are two types: request messages and response messages.
#### HTTP Request Message
A typical HTTP request message has the following structure:
GET /somedir/page.html HTTP/1.1
Host: www.someschool.edu
Connection: close
User-agent: Mozilla/5.0
Accept-language: fr

**General Format:**
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.8.png]]
The message consists of:
1. A **request line**
2. Zero or more **header lines**
3. A **blank line** (signaled by a carriage return and line feed, `cr lf`)
4. An optional **entity body**

**Request Line:**  
The first line contains three fields separated by spaces (`sp`):
- **Method Field:** Specifies the action to be performed. Common methods are:
    - `GET`: Requests an object identified in the URL field. (Most common)
    - `POST`: Used when a user submits form data. The submitted data is contained in the _entity body_.
    - `HEAD`: Similar to GET, but asks the server to return the response _without_ the requested object. Used for debugging.
    - `PUT`: Uploads an object to a specified path on the server.
    - `DELETE`: Deletes an object specified in the URL field.
- **URL Field:** The path name of the requested object.
- **HTTP Version Field:** e.g., HTTP/1.1.

**Header Lines:**  
Subsequent lines provide additional information to the server. Each header line has the format: `Header-Field-Name: value`
- `Host: www.someschool.edu`: Specifies the hostname of the object. **Required** in HTTP/1.1, especially for proxy caches.
- `Connection: close`: Tells the server to use a non-persistent connection (close after response).
- `User-agent: Mozilla/5.0`: Specifies the browser type (e.g., Firefox). Allows the server to send different object versions tailored to specific browsers.
- `Accept-language: fr`: Indicates the user's language preference (e.g., French) for content negotiation.

**Entity Body:**
- Used with the `POST` method to send data from forms (e.g., search queries).
- Empty for the `GET` method. For `GET`, form data is often appended to the URL itself (e.g., `www.somesite.com/animalsearch?monkeys&bananas`).
### HTTP Response Message

A typical HTTP response message has the following structure:
HTTP/1.1 200 OK
Connection: close
Date: Tue, 18 Aug 2015 15:44:04 GMT
Server: Apache/2.2.3 (CentOS)
Last-Modified: Tue, 18 Aug 2015 15:11:03 GMT
Content-Length: 6821
Content-Type: text/html

(data data data data data ...)

**General Format:**
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.9.png]]
The message consists of:
1. A **status line**
2. Zero or more **header lines**
3. A **blank line**
4. An optional **entity body** (containing the requested object itself)

**Status Line:**  
The first line contains three fields separated by spaces (`sp`):
- **Protocol Version:** e.g., HTTP/1.1
- **Status Code:** A numeric code indicating the result of the request.
- **Status Phrase:** A human-readable text corresponding to the status code.

**Common Status Codes:**
- **200 OK:** Request succeeded; the information is returned in the response.
- **301 Moved Permanently:** The requested object has been permanently moved. The new URL is specified in the `Location:` header. The client will automatically retrieve the new URL.
- **400 Bad Request:** A generic error indicating the server could not understand the request.
- **404 Not Found:** The requested document does not exist on this server.
- **505 HTTP Version Not Supported:** The requested HTTP protocol version is not supported by the server.

**Header Lines:**  
Provide metadata about the response.
- `Connection: close`: Tells the client the server will close the TCP connection after sending the message.
- `Date: Tue, 18 Aug 2015 15:44:04 GMT`: The time and date when the server sent the response message.
- `Server: Apache/2.2.3 (CentOS)`: Indicates the server software and version. Analogous to the `User-agent` header in a request.
- `Last-Modified: Tue, 18 Aug 2015 15:11:03 GMT`: The time and date the object was created or last modified. Critical for caching.
- `Content-Length: 6821`: The number of bytes in the object being sent.
- `Content-Type: text/html`: The type of the object in the entity body (e.g., HTML text, JPEG image). This header, not the file extension, officially defines the object type.

**Entity Body:**  
Contains the requested object itself (e.g., the HTML file, image data).

**Viewing a Real HTTP Response:**  
You can use Telnet to manually send an HTTP request and see the raw response.
1. Open a command prompt and type: `telnet gaia.cs.umass.edu 80`
2. Type the request:  
    `GET /kurose_ross/interactive/index.php HTTP/1.1`  
    `Host: gaia.cs.umass.edu`
3. Press Enter twice. This opens a TCP connection and sends the request. The server's response, including headers and the HTML entity body, will be displayed. Replacing `GET` with `HEAD` will retrieve only the header lines.

**Header Generation:**  
The specific header lines included in a request or response are determined by:
- **Browser/Server type and version**
- **User configuration**
- **Caching status** (e.g., a browser may send headers related to a cached copy)
- **Server configuration**
### User-Server Interaction: Cookies

HTTP is a stateless protocol, but many websites need to identify users to restrict access or personalize content. **Cookies** allow sites to track users. Most major commercial websites use cookies.

**How Cookies Work:**  
Cookie technology has four components: 
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.10.png]]
1. A `Set-cookie:` header line in the **HTTP response message** from the server.
2. A `Cookie:` header line in the **HTTP request message** from the client.
3. A **cookie file** kept on the user's end system, managed by the browser.
4. A **back-end database** at the website.

**Example Workflow:**
1. **First Visit:** When a user (e.g., Susan) visits a site (e.g., [Amazon.com](https://amazon.com/)) for the first time, the server creates a unique ID for her (e.g., 1678) and stores it in its database.
2. **Server Response:** The server's HTTP response includes a `Set-cookie:` header containing the ID (e.g., `Set-cookie: 1678`).
3. **Browser Action:** The user's browser receives the response, sees the `Set-cookie:` header, and adds a new entry to its local cookie file. This entry includes the server's hostname and the ID.
4. **Subsequent Requests:** For every subsequent HTTP request to that server, the browser checks its cookie file, finds the ID for that hostname, and includes a `Cookie:` header in the request (e.g., `Cookie: 1678`).
5. **Server Tracking:** The server uses this ID to look up the user in its database, allowing it to track the user's activity (pages visited, items in a shopping cart) across multiple sessions.
6. **Long-Term Identification:** If the user registers and provides personal information (name, address, etc.), the server can link this information to the ID, enabling features like "one-click shopping" on future visits.

**Purposes of Cookies:**
- **User Identification:** Allows a server to recognize a user across multiple sessions.
- **Creating a Session Layer:** Adds state on top of stateless HTTP, enabling user sessions (e.g., for web-based email).
- **Personalization:** Websites can recommend products or content based on past activity.
- **Shopping Carts:** Maintain a list of a user's intended purchases across multiple page requests.

**Privacy Concerns:**  
Cookies are controversial because they can be used to collect extensive information about a user's browsing habits. When combined with voluntarily provided account information, websites can build detailed user profiles, which may be sold to third parties, raising significant privacy issues.
### Web Caching
A **Web cache** (or **proxy server**) is a network entity that satisfies HTTP requests on behalf of an origin server. It stores copies of recently requested objects in its disk storage. A user's browser can be configured to send all HTTP requests first to the Web cache.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.11.png]]
**How a Web Cache Works:**
1. The browser establishes a TCP connection to the Web cache and sends an HTTP request.
2. The Web cache checks its local storage for the object.
    - **If present (cache hit):** The cache returns the object to the browser immediately.
    - **If not present (cache miss):** The cache opens a TCP connection to the origin server, forwards the HTTP request, receives the object, stores a copy locally, and then forwards the object to the browser.

A Web cache acts as both a **server** (to browsers) and a **client** (to origin servers). ISPs often install caches to improve performance and reduce costs.

**Benefits of Web Caching:**
1. **Reduced Response Time:** A cache can deliver objects faster than the origin server, especially if the connection between the client and cache is faster than the connection to the origin server.
2. **Reduced Traffic:** Caches reduce the amount of traffic on an institution's access link to the Internet, delaying the need for costly bandwidth upgrades and improving overall Internet performance.

**Example Analysis:**  
Consider an institutional network with:
- A **100 Mbps LAN**.
- A **15 Mbps access link** to the Internet.
- Average object size: **1 Mbit**.
- Average request rate: **15 requests/sec**.

![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.12.png]]
**Without a Cache:**
- Traffic intensity on the access link = (15 req/sec * 1 Mbit/req) / 15 Mbps = **1.0**.
- A traffic intensity of 1.0 causes enormous delays, making the system unusable.

**Solutions:**
1. **Upgrade Access Link:** Increasing the access link to 100 Mbps reduces traffic intensity to 0.15, solving the delay problem but at high cost.
2. **Install a Web Cache:** Suppose the cache has a **hit rate of 0.4** (40% of requests are satisfied by the cache).
    - 40% of requests are served almost instantly (~10 ms) from the cache.
    - 60% of requests go to the origin server, but the traffic intensity on the access link is now reduced to 0.6.
    - Average delay = `0.4 * (0.01 seconds) + 0.6 * (2.01 seconds) ≈ 1.2 seconds`.  
        This provides better performance than upgrading the link, at a much lower cost.

![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.13.png]]
**Content Distribution Networks (CDNs):**  
CDNs use geographically distributed caches to localize traffic and improve performance further. They can be shared (e.g., Akamai, Limelight) or dedicated (e.g., Google, Netflix).
### The Conditional GET
Caching introduces the problem of **stale objects**—a cached copy may be outdated if the original object on the server has been modified. HTTP's **conditional GET** mechanism allows a cache to verify whether its stored object is still up-to-date.

A conditional GET request must:
1. Use the `GET` method.
2. Include an `If-Modified-Since:` header line.

**Benefits:**
- **Saves Bandwidth:** Avoids transferring the entire object if it hasn't changed.
- **Reduces Response Time:** The `304` response is much smaller and faster to transmit than the full object.

**Example Workflow:**

1. **Initial Request:** A proxy cache requests an object from a server:
    GET /fruit/kiwi.gif HTTP/1.1
    Host: www.exotiquecuisine.com

2. **Server Response:** The server responds with the object and includes the `Last-Modified:` header:
    HTTP/1.1 200 OK
    Date: Sat, 3 Oct 2015 15:39:29
    Server: Apache/1.3.0 (Unix)
    Last-Modified: Wed, 9 Sep 2015 09:23:24
    Content-Type: image/gif
    (data data data data data ...)

    The cache stores the object **and** the last-modified date.

3. **Subsequent Request (One Week Later):** Another browser requests the same object via the cache. The cache sends a **conditional GET** to the server, including the `If-Modified-Since:` header with the stored last-modified date:
    GET /fruit/kiwi.gif HTTP/1.1
    Host: www.exotiquecuisine.com
    If-modified-since: Wed, 9 Sep 2015 09:23:24

4. **Server Check:**
    
    - **If the object has not been modified:** The server responds with a `304 Not Modified` status and an empty entity body:
        HTTP/1.1 304 Not Modified
        Date: Sat, 10 Oct 2015 15:39:29
        Server: Apache/1.3.0 (Unix)
        (empty entity body)

The cache then serves its stored copy to the browser.

- **If the object has been modified:** The server responds with a `200 OK` status and sends the new object (and its new `Last-Modified:` date), which the cache then stores and forwards.
## HTTP/2
HTTP/2, standardized in 2015, is the first major update to HTTP since HTTP/1.1 (1997). By 2020, over 40% of the top 10 million websites supported HTTP/2, and all major browsers (Chrome, IE, Safari, Opera, Firefox) adopted it.

**Primary Goals of HTTP/2:**
- Reduce perceived latency by enabling **request and response multiplexing** over a single TCP connection.
- Provide **request prioritization** and **server push**.
- Offer efficient **compression of HTTP header fields**.
- **No changes** to HTTP methods, status codes, URLs, or header fields. Instead, it changes how data is formatted and transported.

**Motivation: Overcoming HTTP/1.1 Limitations**  
HTTP/1.1 uses persistent connections, sending all objects of a web page over a single TCP connection. This introduces a **Head-of-Line (HOL) blocking** problem:
- **Example:** A web page contains a large video and many small objects. Over a single TCP connection, the large video blocks the small objects behind it on a slow bottleneck link, delaying the entire page rendering.
- **Workaround:** Browsers open **multiple parallel TCP connections** (often up to 6) to fetch objects simultaneously, circumventing HOL blocking and grabbing a larger share of bandwidth via TCP congestion control.

**HTTP/2 Solutions:**
1. **Multiplexing:** Multiple requests and responses can be interleaved and sent concurrently over a **single TCP connection**, eliminating the need for parallel connections and reducing HOL blocking.
2. **Request Prioritization:** Allows the client to specify the priority of requests (e.g., load critical CSS/JS first), ensuring important resources are delivered sooner.
3. **Header Compression:** Uses HPACK compression to reduce overhead from repetitive header fields.
4. **Server Push:** Allows the server to proactively send resources to the client before they are explicitly requested (e.g., sending associated CSS files when an HTML page is requested).

**Benefits:**
- Reduces the number of TCP connections needed per page, decreasing server load.
- Improves page load times by mitigating HOL blocking and optimizing resource delivery.
- Allows TCP congestion control to function as intended (since multiple connections are no longer used to "cheat" bandwidth allocation).

### HTTP/2 Framing
HTTP/2 solves the Head-of-Line (HOL) blocking problem by introducing a **framing layer** that breaks HTTP messages into small, independent **frames**. These frames can be interleaved and multiplexed over a single TCP connection.

**How Framing Works:**
1. **Breaking Messages into Frames:** Each HTTP request and response is decomposed into multiple frames by the framing sub-layer.
    - The **header fields** become one frame (HEADERS frame).
    - The **message body** is broken into one or more DATA frames.
2. **Interleaving Frames:** Frames from multiple concurrent requests and responses are interleaved and sent over the same TCP connection.
3. **Reassembly:** At the receiving end, the framing sub-layer reassembles the frames into the original HTTP messages.

**Example:**  
Consider a web page with:
- One large video (1000 frames)
- Eight small objects (each 2 frames)

**Without HTTP/2 (Serialized):**  
The video would be sent entirely first (1000 frames), blocking the eight small objects until completion.

**With HTTP/2 (Interleaved):**
- After sending 1 video frame, the first frame of each small object is sent (8 frames).
- After sending the next video frame, the last frame of each small object is sent (8 more frames).
- Thus, all small objects are delivered after only **18 frames** instead of waiting for 1000+ frames.

This interleaving drastically reduces user-perceived latency, as critical resources (like CSS/JS) can be delivered early without being blocked by large objects.

**Binary Encoding:**  
HTTP/2 uses **binary encoding** for frames (instead of HTTP/1.1’s text-based format). Benefits include:
- **Efficient Parsing:** Binary protocols are faster and simpler for machines to parse.
- **Compact Frames:** Slightly smaller frame sizes reduce overhead.
- **Reduced Errors:** Less prone to errors compared to text-based parsing.

**Key Framing Features:**
- **Multiplexing:** Concurrent messages are interleaved at the frame level.
- **Prioritization:** Frames can be prioritized to ensure critical resources are delivered first.
- **Flow Control:** Prevents a single stream from monopolizing the connection.

This framing mechanism is the core innovation of HTTP/2, enabling efficient use of a single TCP connection while avoiding HOL blocking.

### Response Message Prioritization and Server Pushing
#### Prioritization
HTTP/2 allows clients to assign **weights (1-256)** to requests, enabling the server to prioritize response delivery. Higher weights indicate higher priority. Additionally, clients can specify **dependencies** between requests (e.g., stating that a CSS file must be delivered before a JavaScript file). This ensures critical resources (like render-blocking assets) are sent first, optimizing page load performance.
#### Server Push

HTTP/2 enables **server push**, where the server proactively sends additional resources to the client without waiting for explicit requests. For example:
- When a client requests an HTML page, the server can analyze it and push associated resources (e.g., CSS, JavaScript, images) alongside the HTML response.
- This eliminates the latency of multiple round-trip delays for individual requests, accelerating page rendering.

**Benefits:**
- **Reduced Latency:** Critical resources are delivered early, avoiding delays from sequential requests.
- **Efficiency:** The server leverages knowledge of page dependencies to optimize resource delivery.

**Mechanism:**
- The server sends a `PUSH_PROMISE` frame to notify the client of upcoming pushed resources, ensuring no duplication of requests.
- The client can cancel pushes if resources are already cached.

This feature shifts the paradigm from reactive (client-led requests) to proactive (server-led optimization), enhancing performance for complex web pages.

## HTTP/3
HTTP/3 is a new HTTP protocol designed to operate over **QUIC** (Quick UDP Internet Connections), a transport protocol implemented in the application layer on top of UDP. As of 2020, HTTP/3 was still in the standardization process (Internet drafts) but was already being adopted by major browsers and servers.

**Key Features:**
- **Built on QUIC:** HTTP/3 leverages QUIC’s features instead of reinventing them, leading to a simpler design compared to HTTP/2.
- **Multiplexing and Flow Control:** QUIC provides native **message multiplexing** (interleaving) and **per-stream flow control**, eliminating Head-of-Line (HOL) blocking at the transport layer (a limitation of TCP-based HTTP/2).
- **Faster Connection Establishment:** QUIC reduces latency with **0-RTT (zero round-trip time)** handshakes for repeated connections, speeding up session resumption.
- **Improved Security:** QUIC integrates TLS 1.3 encryption by default, enhancing privacy and security.
- **UDP-Based:** Unlike HTTP/2 (over TCP), HTTP/3 uses UDP to avoid TCP’s HOL blocking and ossification issues in network middleboxes.

**Why HTTP/3?**
- HTTP/2 still suffers from HOL blocking at the TCP layer—if a single packet is lost, all streams in the connection are blocked until retransmission.
- QUIC handles packet loss at the stream level, so only the affected stream is delayed.
- HTTP/3 offloads multiplexing, security, and congestion control to QUIC, simplifying the HTTP layer.

**Adoption:**
- Major browsers (Chrome, Firefox, Edge) and servers (Google, Cloudflare) support HTTP/3.
- It is designed for modern web performance, especially in high-latency or lossy networks (e.g., mobile).
### Electronic Mail in the Internet
Email is an asynchronous communication medium that remains one of the Internet's most critical applications. It supports features like attachments, hyperlinks, HTML formatting, and embedded photos. The system comprises three core components: **user agents**, **mail servers**, and **SMTP**(Simple Mail Transfer Protocol).
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.14.png]]
**Key Components:**
1. **User Agents:** Software (e.g., Outlook, Apple Mail, Gmail) that allows users to read, compose, reply, forward, and save messages. Alice’s user agent sends her message to her mail server.
2. **Mail Servers:** Manage mailboxes for recipients. Bob’s mailbox resides on his mail server, which receives, stores, and manages messages sent to him. If delivery fails, the sender’s server retries periodically (e.g., every 30 minutes) and notifies the sender after several days if unsuccessful.
3. **SMTP:** The principal application-layer protocol for transferring mail between servers. It uses TCP for reliable data transfer. Each mail server runs both client and server SMTP components:
    - Acts as an **SMTP client** when sending mail to other servers.
    - Acts as an **SMTP server** when receiving mail from other servers.
#### SMTP
SMTP (RFC 5321) is a legacy protocol that transfers messages directly from the sender’s mail server to the recipient’s mail server. It has archaic traits, such as restricting all message bodies to **7-bit ASCII**, requiring binary data (e.g., images) to be encoded before transmission and decoded after delivery. (HTTP does not have this limitation.)

**SMTP Workflow (Alice to Bob):**
1. Alice uses her user agent to compose a message for Bob and sends it.
2. The message is placed in the outgoing queue on Alice’s mail server.
3. The SMTP client on Alice’s server opens a **TCP connection to port 25** on Bob’s mail server.
4. After a handshake, the SMTP client sends Alice’s message over the connection.
5. The SMTP server on Bob’s server receives the message and places it in Bob’s mailbox.
6. Bob uses his user agent to read the message at his convenience.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.15.png]]
**SMTP Direct Connection:**  
SMTP does not use intermediate servers. If Bob’s server is down, Alice’s server retries later—the message remains in her server’s queue.

**SMTP Command Dialogue Example:**  
The client (C) and server (S) exchange commands and replies over the TCP connection:
S: 220 hamburger.edu
C: HELO crepes.fr
S: 250 Hello crepes.fr, pleased to meet you
C: MAIL FROM: <alice@crepes.fr>
S: 250 alice@crepes.fr ... Sender ok
C: RCPT TO: <bob@hamburger.edu>
S: 250 bob@hamburger.edu ... Recipient ok
C: DATA
S: 354 Enter mail, end with "." on a line by itself
C: Do you like ketchup?
C: How about pickles?
C: .
S: 250 Message accepted for delivery
C: QUIT
S: 221 hamburger.edu closing connection

**Key SMTP Commands:**
- `HELO`: Introduces the client.
- `MAIL FROM`: Specifies the sender.
- `RCPT TO`: Specifies the recipient.
- `DATA`: Begins message transmission; ends with a line containing only a period.
- `QUIT`: Closes the connection.

**Persistent Connections:**  
SMTP uses persistent connections. If multiple messages are sent to the same server, they are transmitted over the same TCP connection.

**Testing SMTP with Telnet:**  
You can interact directly with an SMTP server using Telnet:
telnet serverName 25

After connecting, issue SMTP commands (`HELO`, `MAIL FROM`, `RCPT TO`, `DATA`, etc.) to send a message manually. This helps understand the protocol mechanics.
### Mail Message Formats
An email message consists of a **header** and a **body**, separated by a blank line (CRLF). The header contains peripheral information defined in RFC 5322, with each line using a `Keyword: value` format. Key header lines include:
- `From:` (required): Sender’s email address.
- `To:` (required): Recipient’s email address.
- `Subject:` (optional): Brief summary of the message content.
- Other optional headers (e.g., `Date:`, `CC:`, `BCC:`).

**Example Header:**
From: alice@crepes.fr
To: bob@hamburger.edu
Subject: Searching for the meaning of life.

After the header, a blank line precedes the ASCII message body. You can test this using Telnet to connect to an SMTP server (port 25) and manually sending headers along with the message.
### Mail Access Protocols
Once SMTP delivers a message to the recipient’s mail server (e.g., Bob’s server), Bob needs to **retrieve** it using his user agent (e.g., Outlook, Gmail). Since SMTP is a **push** protocol, it cannot be used for retrieval (a **pull** operation). Instead, two common methods are used:
1. **HTTP (Web-based Email):** Services like Gmail or Yahoo Mail use HTTP for both sending and retrieving emails. Bob’s user agent (a web browser or smartphone app) communicates with the mail server via HTTP, which provides an interface for managing folders, deleting messages, and marking importance.
2. **IMAP (Internet Mail Access Protocol):** Used by desktop clients like Microsoft Outlook. IMAP (RFC 3501) allows Bob to manage folders directly on the mail server, including moving, deleting, and organizing messages. It keeps the user agent synchronized with the server.

**Why Relaying Through Alice’s Server?**  
Alice’s user agent typically does not send directly to Bob’s mail server. Instead:
- Alice’s agent sends the message to **her own mail server** via SMTP (or HTTP for webmail).
- Her mail server then acts as an SMTP client to **relay** the message to Bob’s mail server.

This two-step process ensures reliability: if Bob’s server is unreachable, Alice’s server can retry periodically (e.g., every 30 minutes) until delivery succeeds. Without this, Alice’s user agent would have no way to handle temporary failures in Bob’s server.

**Summary Path (Alice to Bob):**
1. Alice’s user agent → (SMTP/HTTP) → Alice’s mail server.
2. Alice’s mail server → (SMTP) → Bob’s mail server.
3. Bob’s user agent → (HTTP/IMAP) → Bob’s mail server to retrieve the message.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/3/Book/2.16.png]]

FOR DNS look at the next lecture