### DNS—The Internet’s Directory Service
The Internet uses two primary identifiers for hosts:
- **Hostnames** (e.g., `www.facebook.com`): Mnemonic (meaning easy to remember) and human-friendly, but provide no location information and are difficult for routers to process.
- **IP Addresses** (e.g., `121.7.106.83`): Fixed-length, hierarchical numerical addresses preferred by routers for efficient processing. They provide specific location information within the network.

The **Domain Name System (DNS)** translates hostnames to IP addresses, reconciling human preference for names with the network's need for numerical addresses.
#### Services Provided by DNS
DNS is:
1. A **distributed database** implemented in a hierarchy of DNS servers.
2. An **application-layer protocol** (running over UDP on port 53) that allows hosts to query this database.

**How DNS Works with an Application (e.g., HTTP):**
1. A user's browser extracts the hostname (e.g., `www.someschool.edu`) from a URL.
2. The host OS runs the DNS client, which sends a query containing the hostname to a DNS server.
3. The DNS client eventually receives a reply with the corresponding IP address.
4. The browser uses this IP address to initiate a TCP connection to the web server.

This process adds delay, but caching in nearby DNS servers helps reduce both traffic and average delay.

**Additional DNS Services:**
- **Host Aliasing:** A host with a complex **canonical hostname** (e.g., `relay1.west-coast.enterprise.com`) can have simpler **alias** names (e.g., `enterprise.com`, `www.enterprise.com`). DNS can resolve aliases to both the canonical name and the IP address.
- **Mail Server Aliasing:** DNS allows mnemonic email addresses (e.g., `bob@yahoo.com`) to resolve to the canonical hostname of a mail server (e.g., `relay1.west-coast.yahoo.com`) via **MX records**. This enables a company's mail and web servers to share the same alias (e.g., `enterprise.com`).
- **Load Distribution:** For replicated servers (e.g., multiple web servers for `cnn.com`), DNS associates one alias with a set of IP addresses. The DNS server rotates the order of these addresses in its responses, distributing client requests across the servers. This technique is used for both web traffic and email.

DNS is a critical infrastructure that translates hostnames to IP addresses. It is an application-layer protocol that uses the client-server paradigm and runs over UDP (port 53). Unlike user-facing applications, DNS operates in the background to provide a core Internet function.

**Why a Distributed, Hierarchical Design?**  
A centralized DNS server would be impractical due to:
- **Single point of failure:** A crash would disable the entire Internet.
- **Traffic volume:** One server couldn't handle all global queries.
- **Distant database:** Clients far from the server would experience high latency.
- **Maintenance:** Managing all Internet host records would be overwhelming.

Instead, DNS uses a **distributed, hierarchical database** with three main server classes, organized in a hierarchy as shown:
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/4/Book/2.17.png]]
#### 1. Root DNS Servers
- There are over 1,000 root server instances worldwide, replicating 13 logical root servers.
- They provide the IP addresses of **Top-Level Domain (TLD) servers**.
![[Noter/Pasted Images/3. Semester/Industriel datakommunikation/4/Book/2.18.png]]

#### 2. Top-Level Domain (TLD) Servers
- Each TLD (e.g., `.com`, `.org`, `.edu`, country codes like `.uk`) has its own server cluster.
- They provide the IP addresses for **authoritative DNS servers**.
#### 3. Authoritative DNS Servers
- Every organization with public hosts must have an authoritative server that stores DNS records mapping its hostnames to IP addresses.
- Organizations can run their own or use a provider's service.
#### Local DNS Server (Default Name Server)
- Not part of the hierarchy but critical to the architecture.
- Provided by the user's ISP (via DHCP). It is "close" to the user's host.
- Acts as a **proxy**, forwarding queries into the DNS hierarchy on behalf of the host.

#### DNS Query Process Example
To resolve `gaia.cs.umass.edu` for a host at `cse.nyu.edu`:
1. The host sends a **recursive query** to its local DNS server (`dns.nyu.edu`).
2. The local server sends an **iterative query** to a root server.
3. The root server responds with the address of a `.edu` TLD server.
4. The local server queries the `.edu` TLD server.
5. The TLD server responds with the address of the authoritative server for `umass.edu` (`dns.umass.edu`).
6. The local server queries `dns.umass.edu`.
7. The authoritative server responds with the IP address for `gaia.cs.umass.edu`.
8. The local server returns the IP address to the original host.

This process involved **8 messages** (4 queries + 4 replies). In more complex hierarchies, additional intermediate servers may be involved, increasing the number of messages.
#### Recursive vs. Iterative Queries
- **Recursive Query:** The queried server assumes the task of resolving the query and returns the final answer.
- **Iterative Query:** The queried server returns the best answer it has (e.g., the address of another server to ask), and the querier continues the process.

In practice, the query from the host to its local DNS server is recursive, while the local server's subsequent queries to the hierarchy are typically iterative.
![[2.19.png]]
### DNS Caching

DNS caching is a critical performance feature that reduces DNS query delay and the number of messages across the Internet. When a DNS server receives a reply, it can **cache** the mappings (hostname-to-IP) and other information (like TLD server addresses) in its local memory. Subsequent queries for the same hostname can be answered immediately from the cache, bypassing the entire query chain.
![[2.20.png]]
- **Example:** If `dns.nyu.edu` caches the IP for `cnn.com` after a query from `apricot.nyu.edu`, it can instantly return that IP to another NYU host (`kiwi.nyu.edu`) hours later without contacting other servers.
- **Cache Expiry:** Cached records have a **Time to Live (TTL)** value (often ~2 days) after which they are discarded to ensure data freshness.
- **Bypassing Root Servers:** Caching TLD server addresses allows local DNS servers to bypass root servers for most queries, improving efficiency.
### DNS Records and Messages
DNS servers store information in **Resource Records (RRs)**, which are four-tuples:  
`(Name, Value, Type, TTL)`
- **TTL:** Time to Live; determines when the record expires and should be removed from caches.
- **Name & Value:** Their meaning depends on the **Type**:
#### Common DNS Record Types:
1. **Type A (Address):**
    - **Name:** Hostname.
    - **Value:** IP address.
    - _Example:_ `(relay1.bar.foo.com, 145.37.93.126, A)`
2. **Type NS (Name Server):**
    - **Name:** Domain (e.g., `foo.com`).
    - **Value:** Hostname of an **authoritative DNS server** for that domain.
    - _Example:_ `(foo.com, dns.foo.com, NS)`
3. **Type CNAME (Canonical Name):**
    - **Name:** Alias hostname.
    - **Value:** Canonical hostname.
    - _Example:_ `(foo.com, relay1.bar.foo.com, CNAME)`
4. **Type MX (Mail Exchange):**
    - **Name:** Domain alias.
    - **Value:** Canonical name of the domain's **mail server**.
    - _Example:_ `(foo.com, mail.bar.foo.com, MX)`
    - Allows mail servers to have simple aliases. Note: A domain can use the same alias for its web server (via CNAME) and mail server (via MX).
#### How Records Are Used:
- An **authoritative DNS server** for a hostname will have a **Type A** record for it.
- A **non-authoritative server** (e.g., a TLD server) will have:
    - A **Type NS** record for the domain (e.g., `(umass.edu, dns.umass.edu, NS)`).
    - A **Type A** record for the authoritative server’s hostname (e.g., `(dns.umass.edu, 128.119.40.111, A)`).

DNS reply messages carry one or more resource records to provide the requested information or direct the query to the next server in the hierarchy.

### DNS Messages
There are only two types of DNS messages: **query** and **reply**. Both share the same format as seen in the figure below:
![[2.21.png]]
The message is divided into five main sections:
#### 1. Header Section (12 bytes)
Contains key control fields:
- **Identification:** A 16-bit number to match replies with their corresponding queries.
- **Flags:** Important 1-bit indicators include:
    - **Query/Reply Flag:** `0` for query, `1` for reply.
    - **Authoritative Flag:** Set to `1` in a reply if the server is authoritative for the queried name.
    - **Recursion-Desired (RD):** Set by the client to request recursive resolution.
    - **Recursion-Available (RA):** Set by the server to indicate it supports recursion.
- **Number-of Fields:** Four fields that specify the number of entries in the subsequent data sections (Questions, Answer RRs, Authority RRs, Additional RRs).
#### 2. Question Section
Contains the query being made:
- **Name Field:** The domain name being queried (e.g., `www.example.com`).
- **Type Field:** The type of record requested (e.g., `A`, `MX`, `NS`).
#### 3. Answer Section
(In reply messages) Contains the **Resource Records (RRs)** that answer the original query. For example, it may contain multiple `A` records if a hostname has several IP addresses.
#### 4. Authority Section
(In reply messages) Contains RRs that point to other **authoritative name servers** that might be able to resolve the query, helping to direct the client further along the resolution path.
#### 5. Additional Section
(In reply messages) Contains "helpful" RRs that are related to the query but not the direct answer. A common example:
- In a reply to an `MX` (mail server) query, the **Answer** section contains the canonical name of the mail server.
- The **Additional** section would then contain the `A` record (IP address) for that mail server's hostname, saving the client an extra lookup.
#### Using `nslookup`
You can send DNS queries manually using the `nslookup` tool available in Windows Command Prompt and UNIX terminals. By typing `nslookup`, you can query any DNS server and see the human-readable reply. Alternatively, many websites offer remote `nslookup` functionality.

### Inserting Records into the DNS Database

To make a domain name (e.g., `networkutopia.com`) accessible, its records must be inserted into the DNS database. This process involves:
1. **Registering the Domain:** You must register your domain name (e.g., `networkutopia.com`) with an **ICANN-accredited registrar**. The registrar verifies the name's uniqueness and collects a fee.
2. **Providing DNS Server Information:** During registration, you provide the names and IP addresses of your **primary and secondary authoritative DNS servers** (e.g., `dns1.networkutopia.com`, `212.212.212.1` and `dns2.networkutopia.com`, `212.212.212.2`).
3. **Registrar Updates TLD Servers:** The registrar inserts **Type NS** and **Type A** records for your authoritative servers into the **TLD `.com` servers**:
    - `(networkutopia.com, dns1.networkutopia.com, NS)`
    - `(dns1.networkutopia.com, 212.212.212.1, A)`
    - (And similar records for the secondary server)
4. **Configuring Your Authoritative Server:** You must then configure your own authoritative DNS server with the necessary resource records for your services, such as:
    - A **Type A** record for your web server: `(www.networkutopia.com, 212.212.71.4, A)`
    - A **Type MX** record for your mail server: `(networkutopia.com, mail.networkutopia.com, MX)`
    - (And a corresponding **Type A** record for `mail.networkutopia.com`)

**Dynamic Updates:** While DNS records were traditionally configured statically, the DNS protocol now supports **dynamic updates** (RFC 2136, RFC 3007), allowing records to be added or deleted via DNS messages.
### DNS Vulnerabilities
As a critical Internet component, DNS is a target for attacks:
- **DDoS Attacks:** Attackers can flood DNS servers with traffic.
    - **Root Server DDoS:** An attack on October 21, 2002, flooded root servers with ICMP packets. Impact was minimal due to packet filtering and caching in local DNS servers, which often bypass root servers.
    - **TLD Server DDoS:** More effective. An attack on October 21, 2016, targeted Dyn, a TLD service provider, using a botnet of ~100,000 infected IoT devices. It disrupted major sites like Amazon and Twitter for nearly a day.
- **Man-in-the-Middle Attacks:** Attackers intercept DNS queries and return false replies to redirect users to malicious sites.
- **DNS Poisoning (Cache Poisoning):** Attackers send forged replies to a DNS server, tricking it into storing incorrect records in its cache. This can also redirect users to malicious sites.
- **DNSSEC (DNS Security Extensions):** Designed to protect against these attacks by providing origin authentication and data integrity. It is a secured version of DNS that is increasingly being deployed.
### Verification Example: Accessing [www.networkutopia.com](https://www.networkutopia.com/)
1. Alice's host sends a DNS query for `www.networkutopia.com` to her **local DNS server**.
2. The local server queries a **TLD `.com` server** (contacting a root server first if necessary).
3. The TLD server responds with the **NS and A records** for `networkutopia.com`'s authoritative server (inserted by the registrar).
4. The local server then queries the **authoritative server** (`212.212.212.1`) for the **A record** of `www.networkutopia.com`.
5. The authoritative server responds with the IP address (`212.212.71.4`).
6. The local server passes this IP to Alice's host, which can now initiate a TCP connection to the web server.

### Peer-to-Peer File Distribution
P2P architecture minimizes reliance on always-on infrastructure servers. Instead, peers (user-controlled devices like PCs and smartphones) communicate directly to distribute files. This is highly efficient for distributing large files (e.g., software updates, videos) to a large number of peers.
![[2.22.png]]
#### Scalability of P2P vs. Client-Server Architectures
A quantitative model compares the **distribution time** (time to deliver a file of size $F$ to $N$ peers) for both architectures. The analysis assumes:
- Internet core bandwidth is abundant; bottlenecks are in **access networks**.
- Server and peers dedicate all upload/download bandwidth to file distribution.
**Client-Server Distribution Time ($D_{cs}$):**
- The server must send $N$ copies of the file: $\text{time} ≥ \frac{NF}{u_{s}}$ (where $u_s$ is server upload rate).
- The slowest peer (download rate $d_{\min}$) requires: $\text{time} ≥ \frac{F}{d_{\min}}$.
- Thus, the minimum distribution time is:  
    $$D_{\text{cs}} \geq \text{max} \left(\frac{NF}{u_{s}}, \frac{F}{d_{\min}}\right) $$
- For large $N$, $D_{cs} ≈ \frac{NF}{u_s}$, meaning distribution time **increases linearly** with the number of peers.

**P2P Distribution Time ($D_{P2P}$):**
- The server must send each bit at least once: $\text{time} ≥ \frac{F}{u_{s}}$.
- The slowest peer requires: $\text{time} ≥ \frac{F}{d_{\min}}$.
- The total system upload capacity is $u_{\text{total}} = u_s + \sum_{i=1}^{N} u_i$. The system must deliver $NF$ bits: $$\text{time} ≥ \frac{NF}{u_s + \sum_{i=1}^{N} u_i}$$
- Thus, the minimum distribution time is:
$$D_{\text{P2P}} \geq \text{max} \left(\frac{F}{u_{s}}, \frac{F}{d_{\min}}, \frac{NF}{u_{s} + \sum_{i=1}^{N} u_{i}}\right) $$
- P2P achieves this lower bound in practice (with efficient chunk redistribution).

**Key Insight:**
- Client-server distribution time **grows linearly** with `$N$`, becoming impractical for very large numbers of peers.
- P2P distribution time is **bounded** and remains low even for large $N$, as the total upload capacity increases with each new peer. This makes P2P **self-scaling**.

![[2.23.png]]
The figure illustrates this comparison, showing that for P2P, the distribution time remains below a fixed threshold (e.g., 1 hour) for any number of peers, while it grows without bound for client-server.
### BitTorrent Protocol Details
BitTorrent is a sophisticated P2P protocol designed for efficient file distribution. It operates by breaking a file into **chunks** and having peers in a **swarm** (a set of peers participating in distributing a particular file) exchange these chunks directly.
![[2.24.png]]

**Key Mechanisms:**
1. **Neighbor Lists and Chunk Requests:**
    - Each peer maintains TCP connections to a subset of peers in the swarm (its **neighbors**).
    - Periodically, a peer (e.g., Alice) asks each neighbor for their list of chunks.
    - Alice then requests chunks she needs from these neighbors.
2. **Chunk Selection: Rarest First**
    - To decide _which_ chunks to request first, Alice uses the **rarest first** algorithm.
    - She requests the chunks that are the least common (rarest) among her neighbors first.
    - This strategy aims to equalize the availability of all chunks across the swarm quickly, preventing any single chunk from becoming a bottleneck.
3. **Upload Policy: Tit-for-Tat (Reciprocity)**
    - To decide _which neighbors_ to upload to, BitTorrent uses a clever trading algorithm to incentivize sharing and discourage free-riding ("leeching").
    - **Unchoking:** Every 10 seconds, Alice measures the download rate from all her neighbors. She identifies the **top four** peers supplying data at the highest rate and **unchokes** them (prioritizes uploading chunks to them). This is direct reciprocity.
    - **Optimistic Unchoking:** Every 30 seconds, Alice randomly selects **one additional neighbor** (e.g., Bob) and unchokes them. This is called **optimistic unchoking**. It serves two purposes:
        - It allows new peers (who have no data to trade yet) to receive chunks and get started.
        - It allows Alice to discover new, potentially faster trading partners. If Bob provides a good upload rate in return, he may become one of her top four.
    - **Choking:** All other neighbors are **choked** (no uploads are sent to them).

This system of incentives, often called **tit-for-tat**, encourages peers to upload to others to maintain a high download rate for themselves. While this incentive scheme can be circumvented, it is crucial for the health of the ecosystem. Without it, freeriding would be common, and the system would likely collapse.

**Other Features:**  
BitTorrent includes other optimizations not detailed here, such as:
- **Pieces:** Breaking chunks into smaller "mini-chunks" for finer-grained exchange.
- **Pipelining:** Requesting multiple chunks simultaneously to keep the TCP connection saturated.
- **Endgame Mode:** Aggressively requesting all remaining chunks from all peers when a download is nearly complete to avoid delays from slow peers.
- **Anti-Snubbing:** Handling situations where a previously reliable peer stops sending data.
#### Distributed Hash Tables (DHTs)
Beyond file sharing, P2P architecture is also used to build **Distributed Hash Tables (DHTs)**. A DHT is a distributed database where data records are spread across many peers in a P2P system. DHTs provide a lookup service similar to a hash table: given a key, they can route a request to the peer that stores the corresponding value. DHTs are a fundamental component of many P2P systems, including later versions of BitTorrent (which use a DHT to find peers without relying on a central tracker). They have been the subject of extensive research.

### Video Streaming and Content Distribution Networks
Streaming video (e.g., Netflix, YouTube, Amazon Prime) dominates Internet traffic. These services use application-level protocols and distributed servers, often resembling caches, to deliver content efficiently.
#### Internet Video
Streaming involves delivering pre-recorded video from servers to users on demand. Key characteristics of video:
- **Composition:** A video is a sequence of images (frames) displayed at a constant rate (e.g., 24 or 30 fps).
- **Compression:** Video is compressed to reduce bit rate, trading off quality for size. Compression allows creation of multiple versions of the same video at different bit rates (e.g., 300 kbps, 1 Mbps, 3 Mbps) to accommodate varying user bandwidth.
- **High Bit Rates:** Compressed video ranges from ~100 kbps (low quality) to over 10 Mbps (4K). A 2 Mbps video for 67 minutes consumes 1 GB of traffic and storage.
- **Throughput Requirement:** For continuous playout, the network must provide an average throughput **at least equal to the video's bit rate**.
#### HTTP Streaming and DASH
**HTTP Streaming (Traditional):**
- The video is stored as a file on an HTTP server.
- A client establishes a TCP connection and sends an HTTP GET request for the file.
- The server sends the file as fast as possible. The client buffers bytes and begins playback once the buffer exceeds a threshold.
- **Shortcoming:** All clients receive the same encoding, regardless of their available bandwidth.

**DASH (Dynamic Adaptive Streaming over HTTP):**
- **Core Idea:** The video is encoded into multiple versions at different bit rates. The client dynamically requests small video chunks (a few seconds each) from different versions based on its current available bandwidth.
- **Manifest File:** The HTTP server provides a manifest file that lists the URLs and bit rates for all available versions.
- **Client Operation:**
    1. The client first downloads the manifest file.
    2. It measures its received bandwidth and checks its buffer level.
    3. It uses a **rate determination algorithm** to select the next chunk from an appropriate version (high bit rate if bandwidth is high and buffer is full; low bit rate if bandwidth is low or buffer is empty).
    4. It requests each chunk via an HTTP GET request (specifying a URL and byte range).
    
- **Benefits:**
    - Supports clients with different access rates (e.g., 3G vs. fiber).
    - Adapts to bandwidth fluctuations during a session (crucial for mobile users).
    - Allows the client to freely switch between quality levels.
### Content Distribution Networks
Distributing high-bitrate video to a global audience presents significant challenges: ensuring high throughput to avoid freezing, avoiding redundant transmission of popular content over the same links, and eliminating single points of failure. **Content Distribution Networks (CDNs)** solve these problems.

A CDN is a network of geographically distributed servers that store copies of content (videos, images, web pages) and attempt to direct each user request to a server that can provide the best performance.

**CDN Server Placement Philosophies:**
1. **Enter Deep:**
    - **Strategy:** Deploy many smaller server clusters **deep within access networks** (e.g., within thousands of local ISPs worldwide).
    - **Goal:** Get as close as possible to end users to minimize the number of links and routers between the server and the user, thereby reducing delay and improving throughput.
    - **Example:** Akamai.
    - **Trade-off:** Excellent performance but high maintenance and management complexity due to the vast number of locations.

2. **Bring Home:**
    - **Strategy:** Build fewer but larger server clusters at key locations, such as **Internet Exchange Points (IXPs)**.
    - **Goal:** Reduce maintenance and management overhead by consolidating infrastructure into fewer, larger sites.
    - **Example:** Limelight.
    - **Trade-off:** Easier to manage but may result in slightly higher delay and lower throughput for some users compared to the "enter deep" approach.

**CDN Operation:**
- **Content Replication:** CDNs do not store every video in every cluster. They use a **pull strategy**: when a client requests a video not stored in the local cluster, the cluster retrieves it from a central repository or another cluster, stores a copy locally, and streams it to the client simultaneously.
- **Cache Management:** Similar to web caching, when a cluster's storage is full, it evicts the least frequently requested content.

**Types of CDNs:**
- **Private CDN:** Owned and operated by the content provider itself (e.g., Google's CDN for YouTube).
- **Third-Party CDN:** A service provider that distributes content on behalf of multiple content providers (e.g., Akamai, Limelight, Level-3).
### CDN Operation
A CDN's primary function is to intercept a user's request for content and redirect it to an optimal server within its distributed network. This process heavily relies on **DNS redirection**.
![[2.25.png]]
**Mechanics of Request Redirection via DNS:**
The process is illustrated in Figure 2.25 and involves the following steps, using the example of a content provider (NetCinema) using a third-party CDN (KingCDN):
1. **User Visits Web Page:** A user visits NetCinema's website and clicks on a link for a video, e.g., `http://video.netcinema.com/6Y7B23V`.
2. **DNS Query for Video Hostname:** The user's host sends a DNS query to resolve `video.netcinema.com`.
3. **Authoritative DNS Hands Off to CDN:** NetCinema's authoritative DNS server, configured to recognize the `video` subdomain, does not return an IP address. Instead, it returns a hostname within the CDN's domain (e.g., `a1105.kingcdn.com`). This effectively hands the query over to KingCDN.
4. **CDN's DNS Selects Server:** The user's Local DNS Server (LDNS) now sends a new query for `a1105.kingcdn.com`. This query enters KingCDN's DNS infrastructure. **This is the critical step** where KingCDN's DNS system selects the optimal server cluster for the user based on factors like:
    - Client proximity to clusters.
    - Current load on clusters.
    - Network conditions.  
        It returns the IP address of the chosen CDN server to the LDNS.
5. **IP Address Forwarded to Client:** The LDNS forwards this CDN server IP address back to the user's host.
6. **Direct Content Retrieval:** The user's host establishes a **direct TCP connection** to the CDN server at the provided IP address and issues an HTTP GET request for the video. If DASH is used, the server first sends a manifest file, and the client then requests chunks.
#### Case Study: Google's Network Infrastructure
Google uses a massive **three-tiered CDN and private network** to support its services:
1. **Mega Data Centers (~19):** Large facilities (~100,000 servers each) handling dynamic, personalized content (search, Gmail).
2. **"Bring Home" Clusters (~90):** Located at **Internet Exchange Points (IXPs)**. These clusters, with hundreds of servers each, serve static content like YouTube videos.
3. **"Enter Deep" Clusters (100s):** Small clusters (tens of servers) deployed **deep within access ISPs**. They perform TCP splitting and serve static web page elements.

This infrastructure is connected by **Google's private network**, making its core services largely independent of the public Internet. A single user request (e.g., a search) may be serviced by multiple tiers: static content from a nearby "enter-deep" cache, while the query is forwarded over the private network to a mega data center for personalized results. A YouTube video page might combine the video from an IXP cluster, the surrounding page from a local cache, and ads from a data center.

### Case Studies: Netflix and YouTube
Netflix and YouTube are two massive-scale video streaming services that employ different architectures, yet both leverage CDNs and adaptive streaming principles.
#### Netflix
Netflix's architecture has two major components: the **Amazon cloud** and its own **private CDN** (Open Connect).

**Amazon Cloud Handles:**
- **Website & Backend:** User registration, billing, catalogue, recommendations.
- **Content Ingestion & Processing:** Receives master copies from studios, processes them into multiple formats and bit rates for different devices using **DASH**.
- **Upload to CDN:** Pushes processed video versions to its CDN servers.
![[2.26.png]]

**Netflix's Private CDN:**
- **Server Placement:** Installs server racks in **IXPs** (over 200 locations) and within **residential ISPs**.
- **Content Distribution:** Uses **push caching**. Videos are distributed to CDN servers during off-peak hours. Popular videos are stored in all locations; the entire library is stored in larger IXP installations.
- **Server Selection:** The Netflix application (in the Amazon cloud) directly tells the client which CDN server to use, bypassing the need for DNS redirection. It selects the best server, prioritizing one within the client's own ISP if available.
- **Streaming:** Clients use a **proprietary DASH** implementation. They receive a manifest file and directly request ~4-second video chunks from the assigned CDN server, adapting quality based on measured throughput.
#### YouTube
YouTube, owned by Google, also uses a massive **private CDN** but with a different operational philosophy.

**Google's CDN for YouTube:**
- **Server Placement:** Server clusters in hundreds of **IXPs** and **ISPs**, as well as Google's massive data centers.
- **Content Distribution:** Uses **pull caching**. A cluster retrieves and stores a video only when a client requests it.
- **Server Selection:** Uses **DNS redirection**. Google's DNS system typically directs a client to the cluster with the lowest RTT, but may redirect to a more distant cluster to balance load.
- **Streaming:** Uses **HTTP streaming** but **not adaptive streaming (DASH)**. Users must manually select the video quality version. YouTube uses HTTP byte-range requests to prefetch a target amount of video and then throttles transmission to save bandwidth if the user stops watching.
- **Upload & Processing:** Users upload videos over HTTP. All processing (format conversion, creating multiple versions) occurs within Google's data centers.

**Summary of Key Differences:**

| Feature                | Netflix                                             | YouTube                                          |
| ---------------------- | --------------------------------------------------- | ------------------------------------------------ |
| **CDN Type**           | Private CDN (Open Connect)                          | Private CDN (Google)                             |
| **Caching**            | **Push Caching** (pre-placed during off-peak hours) | **Pull Caching** (cached on-demand upon request) |
| **Server Selection**   | App-directed (no DNS redirection)                   | **DNS redirection**                              |
| **Adaptive Streaming** | **Yes** (Proprietary DASH)                          | **No** (Manual quality selection)                |
| **Upload/Processing**  | Done in **Amazon cloud**                            | Done in **Google data centers**                  |
### Socket Programming: Creating Network Applications
Network applications are created by writing code for **client** and **server** programs that communicate by reading from and writing to **sockets**. The developer's main task is to write this code.
#### Types of Network Applications
1. **Open (Standard Protocol) Applications:**
    - The operation is specified in a standard document (e.g., an RFC).
    - Client and server programs must strictly follow the protocol rules to ensure interoperability.
    - _Example:_ A Chrome browser (HTTP client) communicating with an Apache server (HTTP server).
2. **Proprietary Network Applications:**
    - Use a custom, unpublished application-layer protocol.
    - A single developer/team creates both client and server, maintaining full control.
    - Other developers cannot create interoperable applications since the protocol is not open.
#### Key Development Decisions
1. **Transport Protocol:** Choose between **TCP** (connection-oriented, reliable byte-stream) or **UDP** (connectionless, unreliable datagrams).
2. **Port Numbers:**
    - For open protocols, use the **well-known port number** assigned by the RFC (e.g., port 80 for HTTP).
    - For proprietary applications, avoid well-known ports to prevent conflicts.

### Socket Programming with UDP
UDP is a connectionless protocol. Communication occurs by sending discrete packets (datagrams) to a destination address, without first establishing a connection.
#### The UDP Communication Process
1. **Sending a Packet:** The sending process must attach a **destination address** to the packet before pushing it out of its socket. This address consists of:
    - **Destination IP Address:** To route the packet through the Internet to the correct host.
    - **Destination Port Number:** To identify the specific socket (application process) on the destination host.
2. **Source Address:** The **source IP address** and **source port number** are also attached to the packet. This is typically done automatically by the operating system, not the application code.
3. **Receiving a Packet:** The receiving process retrieves the packet from its socket and inspects its contents.
#### Example Application
We will implement a simple client-server application to demonstrate UDP sockets:
1. **Client:** Reads a line of text from the keyboard and sends it to the server.
2. **Server:** Receives the text, converts it to uppercase.
3. **Server:** Sends the modified text back to the client.
4. **Client:** Receives the modified text and displays it on the screen.
Figure 2.27 illustrates this socket interaction.
![[2.27.png]]
**Server Port Number:** For this example, we arbitrarily choose port number `12000` for the server.

#### UDPClient.py
The following code provides a minimal, functional example focusing on the core concepts.
```python
from socket import *
serverName = ’hostname’
serverPort = 12000
clientSocket = socket(AF_INET, SOCK_DGRAM)
message = input(’Input lowercase sentence:’)
clientSocket.sendto(message.encode(),(serverName, serverPort))
modifiedMessage, serverAddress = clientSocket.recvfrom(2048)
print(modifiedMessage.decode())
clientSocket.close()
```
Let's examine the code for the UDP client, line by line.

```python
from socket import *
```

- **Purpose:** Imports Python's `socket` module, which provides the necessary functions and classes for network communication.

```python
serverName = 'hostname'
serverPort = 12000
```

- **`serverName`:** A string variable that should be set to either the server's **IP address** (e.g., `'128.138.32.126'`) or its **hostname** (e.g., `'cis.poly.edu'`). If a hostname is used, a DNS lookup is automatically performed to resolve it to an IP address.
- **`serverPort`:** An integer variable set to the port number on which the server process is listening. We've arbitrarily chosen `12000`.

```python
clientSocket = socket(AF_INET, SOCK_DGRAM)
```
- **Purpose:** Creates the client's socket, named `clientSocket`.
- **`AF_INET`:** Specifies the address family for IPv4.
- **`SOCK_DGRAM`:** Specifies that this will be a **UDP socket** (as opposed to `SOCK_STREAM` for TCP).
- **Note:** The client's port number is not specified here; it is assigned automatically by the operating system.

```python
message = input('Input lowercase sentence:')
```
- **Purpose:** Prompts the user to type a line of input. This input string is stored in the variable `message`.

```python
clientSocket.sendto(message.encode(), (serverName, serverPort))
```
- **Purpose:** Sends the message through the socket to the server.
- **`message.encode()`:** Converts the string `message` into a sequence of **bytes**, which is the required format for socket transmission.
- **`(serverName, serverPort)`:** A tuple specifying the **destination address** (IP and port).
- **Note:** The OS automatically attaches the client's own source address (IP and port) to the packet.

```python
modifiedMessage, serverAddress = clientSocket.recvfrom(2048)
```
- **Purpose:** Receives a response packet from the server.
- **`recvfrom(2048)`:** This method waits to receive data from the socket. The parameter `2048` specifies the buffer size (maximum number of bytes to receive).
- **Return Values:**
    - `modifiedMessage`: The data payload from the received packet (as bytes).
    - `serverAddress`: The source address of the packet (a tuple containing the server's IP and port). While the client already knows this address, the method provides it.

```python
print(modifiedMessage.decode())
```
- **Purpose:** Displays the server's response to the user.
- **`modifiedMessage.decode()`:** Converts the received bytes back into a string for display.

```python
clientSocket.close()
```
- **Purpose:** Closes the client's socket. The process then terminates.

#### UDPServer.py
Let’s now take a look at the server side of the application:
```python
from socket import *
serverPort = 12000
serverSocket = socket(AF_INET, SOCK_DGRAM)
serverSocket.bind((’’, serverPort))
print(”The server is ready to receive”)
while True:
message, clientAddress = serverSocket.recvfrom(2048)
modifiedMessage = message.decode().upper()
serverSocket.sendto(modifiedMessage.encode(),
clientAddress)
```
The server code begins similarly to the client but has key differences in its purpose and operation.

```python
from socket import *
serverPort = 12000
serverSocket = socket(AF_INET, SOCK_DGRAM)
```
- **Purpose:** These lines import the socket module, define the port number (`12000`), and create a UDP socket, just like the client.

```python
serverSocket.bind(('', serverPort))
```
- **Purpose:** This is a critical difference. The `bind()` method assigns the socket to a specific port number on the server's machine.
- **`('', serverPort)`:** The empty string `''` signifies that the socket should be bound to **all available interfaces** (IP addresses) on the server. The `serverPort` is the specific port it will listen on.
- **Result:** Any packet sent to this server's IP address on port `12000` will be delivered to this socket.

```python
while True:
    message, clientAddress = serverSocket.recvfrom(2048)
```
- **Purpose:** The server enters an infinite loop to continuously listen for incoming packets from any client.
- **`recvfrom(2048)`:** This method blocks and waits until a UDP datagram arrives. It returns:
    - `message`: The data from the packet (as bytes).
    - `clientAddress`: A tuple containing the **source IP address and source port number** of the client that sent the packet. This is the "return address" needed to send a reply.

```python
	modifiedMessage = message.decode().upper()
```
- **Purpose:** This is the application's logic. It processes the received data.
- **Steps:**
    1. `.decode()`: Converts the received bytes into a string.
    2. `.upper()`: A string method that converts the string to uppercase.

```python
	serverSocket.sendto(modifiedMessage.encode(), clientAddress)
```
- **Purpose:** Sends the modified data back to the client.
- **`modifiedMessage.encode()`:** Converts the uppercase string back into bytes for transmission.
- **`clientAddress`:** Uses the source address from the received packet as the destination address for the reply. This ensures the response is sent to the correct client and port.

**Key Difference from Client:** The server uses the `clientAddress` obtained from `recvfrom()` to know where to send the reply, whereas the client explicitly knew the server's address beforehand.
### Testing the Applications
1. **Run the Server:** Execute `UDPServer.py` on the server host. The process will start and wait idle for incoming packets.
2. **Run the Client:** Execute `UDPClient.py` on a client host. Ensure the `serverName` variable in the client code contains the correct hostname or IP address of the server host.
3. **Interact:** In the client, type a lowercase sentence and press enter. The client will send it to the server, which will return the uppercase version to be displayed.
### Modifying the Application
You can easily modify this basic framework to create different UDP applications:
- **Change Server Logic:** Instead of `.upper()`, the server could perform other operations on the received data (e.g., count characters, perform a calculation).
- **Change Client Behavior:** Modify the client to send multiple messages or interact continuously with the server.

### Socket Programming with TCP
TCP is a **connection-oriented** protocol. Before data can be exchanged, a **TCP connection** must be established between the client and server through a **three-way handshake**. This connection is a reliable byte stream.
#### Key TCP Socket Concepts
1. **Welcoming Socket (Server):** The server must first create a **welcoming socket**. This socket is bound to a specific port and listens for incoming connection requests from _any_ client. It is the initial point of contact.
2. **Connection Socket (Server):** When a client attempts to connect, the welcoming socket accepts the connection. This action creates a new, dedicated **connection socket** specifically for communicating with that individual client. The original welcoming socket remains open to listen for other new connections.
3. **Client Socket:** The client creates a single socket to initiate the connection to the server's welcoming socket. Once the connection is established, this socket is used for all communication with the server.

**Analogy:** The welcoming socket is like a receptionist who accepts all incoming calls. When a call comes in, the receptionist patches it through to a specific department (the connection socket) that handles the conversation from that point on, while the receptionist remains free to accept other calls.
![[2.28.png]]
#### The TCP Communication Process
The process for our simple application (client sends a line, server capitalizes it and sends it back) is illustrated in Figure 2.29. 
![[2.29.png]]

The main steps are:
**Server Setup:**
1. The server process must be running first.
2. It creates a welcoming socket (`serverSocket`) and binds it to a known port.
3. It sets the welcoming socket to listen for incoming connection requests.

**Client Connection:**  
4. The client creates its socket and initiates the three-way handshake by specifying the server's IP and port.  
5. The server's welcoming socket "accepts" the connection, creating a new connection socket (`connectionSocket`) for this client.

**Data Exchange:**  
6. The client sends data by writing bytes into its socket. TCP guarantees the data arrives reliably and in order at the server's connection socket.  
7. The server reads the data from its connection socket, processes it (converts to uppercase), and writes the response back into the same connection socket.  
8. TCP delivers the response reliably to the client's socket.  
9. The client reads the response from its socket.

The code for the TCP client (`TCPClient.py`) and server (`TCPServer.py`) will implement this logic, building on the UDP example but with the added steps required to manage a connection.

#### TCPClient.py
Here is the code for the client side of the application:
```Python
from socket import *
serverName = ’servername’
serverPort = 12000
clientSocket = socket(AF_INET, SOCK_STREAM)
clientSocket.connect((serverName,serverPort))
sentence = input(’Input lowercase sentence:’)
clientSocket.send(sentence.encode())
modifiedSentence = clientSocket.recv(1024)
print(’From Server: ’, modifiedSentence.decode())
clientSocket.close()
```
Let’s now take a look at the various lines in the code that differ significantly from the
UDP implementation. The first such line is the creation of the client socket.

```Python
clientSocket = socket(AF_INET, SOCK_STREAM)
```
This line creates the client’s socket, called clientSocket. The first parameter
again indicates that the underlying network is using IPv4.
- **`SOCK_STREAM`:** This parameter is the key difference. It specifies that the socket will be a **TCP socket**, not a UDP (`SOCK_DGRAM`) socket.

```python
clientSocket.connect((serverName, serverPort))
```
- **Purpose:** This line is fundamental to TCP. It initiates the **three-way handshake** to establish a reliable TCP connection with the server.
- **Process:** The client sends a connection request to the server's address (`serverName`, `serverPort`). This method blocks until the handshake is complete and the connection is established.
- **Result:** A virtual connection now exists between `clientSocket` and the server's socket.

```python
sentence = input('Input lowercase sentence:')
```
- **Purpose:** Identical to the UDP client. Gets user input.

```python
clientSocket.send(sentence.encode())
```
- **Purpose:** Sends data through the established TCP connection.
- **Key Difference from UDP:** There is no `sendto()` method and **no need to specify a destination address**. The connection itself defines the path. The OS handles packaging the data into TCP segments.
```python
modifiedSentence = clientSocket.recv(2048)
```
- **Purpose:** Receives data from the server over the TCP connection.
- **Key Difference from UDP:** There is no `recvfrom()` method and **no return of the server's address**. The connection already implies who the data is coming from.

```python
print(modifiedSentence.decode())
clientSocket.close()
```
- **Purpose:** Prints the server's response and then closes the socket.
- **`close()`:** This action terminates the TCP connection. It initiates the TCP connection teardown process (another exchange of messages at the transport layer), ensuring a graceful closure.
### Summary of TCP vs. UDP Client Code

|Operation|UDP Client|TCP Client|
|---|---|---|
|**Socket Creation**|`socket(AF_INET, SOCK_DGRAM)`|`socket(AF_INET, SOCK_STREAM)`|
|**Define Destination**|Set `serverName` and `serverPort`|Set `serverName` and `serverPort`|
|**Establish Connection**|_Not required_ (connectionless)|`connect((serverName, serverPort))`|
|**Send Data**|`sendto(data, address)`|`send(data)`|
|**Receive Data**|`recvfrom(bufsize)` returns `(data, address)`|`recv(bufsize)` returns `data`|
|**Close**|`close()`|`close()` (also tears down the connection)|
#### TCPServer.py
The TCP server's operation is more complex than the UDP server because it must manage a welcoming socket and individual connection sockets for each client.

```python
from socket import *
serverPort = 12000
serverSocket = socket(AF_INET, SOCK_STREAM)
serverSocket.bind(('', serverPort))
```
- **Purpose:** These initial lines are similar to the UDP server: create a TCP socket (`SOCK_STREAM`) and bind it to the server's port. This socket is the **welcoming socket**.

```python
serverSocket.listen(1)
```
- **Purpose:** This crucial line activates the welcoming socket, putting it in a **listening** state. It is now ready to accept incoming connection requests from clients.
- **Parameter (`1`):** This defines the **backlog**. It specifies the maximum number of queued, unaccepted connection requests the system will allow before refusing new ones. A value of 1 is sufficient for this simple server.

```python
print('The server is ready to receive')
while True:
    connectionSocket, addr = serverSocket.accept()
```
- **`accept()`:** This is the most important line in the TCP server. This method **blocks** and waits for a client to attempt a connection. When a connection request arrives, it does three things:
    1. **Creates a new socket:** It returns a brand new socket object (`connectionSocket`) dedicated solely to communicating with this specific client.
    2. **Returns the client's address:** It also returns the client's IP address and port number (`addr`).
    3. **Completes the handshake:** The TCP three-way handshake is completed, establishing the connection between the client's socket and this new `connectionSocket`.
- The original `serverSocket` remains open and unchanged, continuing to listen for new connection requests.

```python
    sentence = connectionSocket.recv(1024).decode()
    capitalizedSentence = sentence.upper()
    connectionSocket.send(capitalizedSentence.encode())
```
- **Purpose:** The server now uses the _connection socket_ (`connectionSocket`) to communicate with the connected client, not the welcoming socket.
- **`recv(1024)`:** Reads data sent by the client over the established TCP connection.
- **`send()`:** Sends the modified data back to the client over the same connection. No destination address is needed.

```python
    connectionSocket.close()
```
- **Purpose:** After serving the client, the server closes the **connection socket**. This terminates the TCP connection with that specific client.
- **Crucially,** the **welcoming socket** (`serverSocket`) remains open. The server loop continues, and the `serverSocket.accept()` call will handle the next connection request, creating a new `connectionSocket` for the next client.
### Summary of TCP vs. UDP Server Code

|Operation|UDP Server|TCP Server|
|---|---|---|
|**Socket Creation**|`socket(AF_INET, SOCK_DGRAM)`|`socket(AF_INET, SOCK_STREAM)`|
|**Setup**|`bind()`|`bind()` then `listen()`|
|**Wait for Client**|`recvfrom()` blocks waiting for a **datagram**|`accept()` blocks waiting for a **connection**|
|**Client Communication**|Uses the **original socket** for all clients. Must manage client addresses manually.|Creates a **new socket** (`connectionSocket`) for each client. The connection manages the address.|
|**Send/Receive**|`recvfrom()` / `sendto(address)`|`recv()` / `send()` on the connection socket|
|**Close**|`close()` the original socket|
