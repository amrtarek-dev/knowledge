Network is a group of connected devices

The devices on a network can communicate with each other over network cables, or wireless connections.

These devices will use unique addresses, or identifiers, to locate each other

two types of networks: 
a local area network, also known as a LAN, and a wide area network, also known as a WAN.

A hub is a network device that broadcasts information to every device on the network.

A switch makes connections between specific devices on a network by sending and receiving data between them. 
A switch is more intelligent than a hub. 
It only passes data to the intended destination.

A router is a network device that connects multiple networks together.

A modem is a device that connects your router to the internet, and brings internet access to the LAN. with an internet service provider (ISP). ISPs provide internet connectivity via telephone lines or coaxial cables.

A **wireless access point** sends and receives digital signals over radio waves creating a wireless network.

Virtualization tools are pieces of software that perform network operations.

Virtualization tools carry out operations that would normally be completed by a hub, switch, router, or modem, and they are offered by Cloud service providers.

A **firewall** is a network security device that monitors traffic to or from your network.

**Servers** provide information and services for devices like computers, smart home devices, and smartphones on the network.

**Network diagrams** are maps that show the devices on the network and how they connect.

## Network Topology
- Star Topology: devices are individually connected via a central networking device such as a switch or hub.
- Bus Topology: relies upon a single connection which is known as a backbone cable
- Ring Topology: (token topology) works by sending data across the loop until it reaches the destined device, using other devices along the loop to forward the data.


## Data
- **Frame**: is used at Layer 2 (Data Link) of the OSI model, which, encapsulates the packet and adds additional information such as MAC addresses.
- **packet**:  is a piece of data from Layer 3 (Network Layer) of the OSI model, containing information such as an IP header and payload
a basic unit of information that travels from from one device to another within a network.
it consists of:
- Header: IP address/ Mac/ Protocol Number
- Body: the message
- Footer: send that the package is finished

## Bandwidth
The amount of data a device receives every second.

## Speed
The rate at which data packets are received or download

## Packet sniffing
The practice of capturing and inspecting data packets across a network.

## TCP:
An internet communication protocol that allows two devices to form a connection and stream data.

## Internet Protocol (IP):
A set of standards used for routing and addressing data packets as they travel between devices on a network.
A unique string of characters that identifies the location of a device.
- IPv4 (123,123,123,123)
- IPv6 (32 character)

## MAC Address
A unique alphanumeric identifier that is assigned to each physical device on network.

## Port
A software-based location that organizes the sending and receiving of data between devices on a network.

### Port number
allow computers to split the network traffic and prioritize the operations they will perform with the data.
- 25 for email
- 443 https
- 20 ftp

## TCP/IP
Transmission Control Protocol and internet Protocol. is the standard model used for network communication.

TCP/IP Model is a framework used to visualize how data is organized and transmitted across the network.

it has 4 layers:
1. Network access layer
2. Internet layer
3. Transport layer
4. Application layer.

### Network access layer
(Data link layer) deals with creation of data packets and their transmission across a network. (Hardware devices) (Ethernet, wireless).
- ARP: Address resolution protocol: mapping the IP address to MAC address.

## Internet Layer
(Network Layer) is where IP addresses are attached to data packets to indicate the location of the sender and receiver. (LAN or WAN) (IPv4,6)
- **Internet Protocol (IP)**: sends data packets to the correct destination.
- **Internet Control Message Protocol (ICMP)**: Shares the error information and status updates of data packets.


## Transport layer
It includes protocols to control the flow of traffic across a network.
These protocols permit or deny communication with other devices and include information about the status of the connection. (Error control) (TCP, UDP)
- **Transmission Control Protocol (TCP)**: It ensures that data is reliably transmitted to the destination service.
- **User Datagram Protocol (UDP)**: is a connectionless protocol that does not establish a connection between devices before transmissions.

## Application layer
Determine how the data packets will interact with receiving devices. (File transfer and email services) (HTTP, TLS, DNS)
This layer defines which internet services and applications any user can access
- Hypertext transfer protocol (HTTP)
- Simple mail transfer protocol (SMTP)
- Secure shell (SSH)
- File transfer protocol (FTP)
- Domain name system (DNS)


## OSI Model 
Open system Interconnection is a standardized concept that describes the seven layers computers use to communicate and send data over the network.

- Application Layer
	- Application
	- Presentation
	- Session
- Transport layer
	- Transport
- Internet layer
	- Network
- Network Access Layer
	- Data Link
	- Physical

The application layer includes all of the networking protocols that software applications use to connect a user to the internet.

The presentation layer involve data translation and encryption for the network.

A session describes when a connection is established between two devices. An open session allows the devices to communicate with each other. it is responsible for activities such as authentication, reconnection, and setting checkpoints during a data transfer.

The transport layer is responsible for delivering data between devices. This layer also handles the speed of data transfer, flow of the transfer, and breaking data down into smaller segments to make them easier to transport.

The network layer oversees receiving the frames from the data link layer (layer 2) and delivers them to the intended destination. The intended destination can be found based on the address that resides in the frame of the data packets.
 protocols include:
 - **OSPF** (**O**pen **S**hortest **P**ath **F**irst) 
 - **RIP** (**R**outing **I**nformation **P**rotocol).

The data link layer organizes sending and receiving data packets within a single network. The data link layer is home to switches on the local network and network interface cards on local devices
Protocols like:
- network control protocol (NCP)
- high-level data link control (HDLC)
- synchronous data link control protocol (SDLC)
are used at the data link layer

The physical layer corresponds to the physical hardware involved in network transmission.

| Layer Number | Layer Name         | Main Function                                         | Example Protocols and Standards           |
| ------------ | ------------------ | ----------------------------------------------------- | ----------------------------------------- |
| Layer 7      | Application layer  | Providing services and interfaces to applications     | HTTP, FTP, DNS, POP3, SMTP, IMAP          |
| Layer 6      | Presentation layer | Data encoding, encryption, and compression            | Unicode, MIME, JPEG, PNG, MPEG            |
| Layer 5      | Session layer      | Establishing, maintaining, and synchronising sessions | NFS, RPC                                  |
| Layer 4      | Transport layer    | End-to-end communication and data segmentation        | UDP, TCP                                  |
| Layer 3      | Network layer      | Logical addressing and routing between networks       | IP, ICMP, IPSec                           |
| Layer 2      | Data link layer    | Reliable data transfer between adjacent nodes         | Ethernet (802.3), WiFi (802.11)           |
| Layer 1      | Physical layer     | Physical data transmission media                      | Electrical, optical, and wireless signals |

## Operations at the network layer
A data packet is also referred to as an IP packet for TCP connections or datagram for UDP connections.

IPv4 format: 4 decimal numbers separated by periods (0-255). 4.3 billion.
- Header: 20-60 bytes (first 20 bytes for information of source and destination)
	- Version (VER) 4 bits for the protocol packet is using
	- IP Header length (HLEN or IHL): where it header ends and data begins.
	- Type of service (ToS): provide the router with the packet priority.
	- Total Length: tells the total length of the IP packet including the header and data.
	- Identification: a unique identifier for all the fragments of the original IP packet so it can reassembled once they reach their destination.
	- Flags: if the original packet has been fragmented and if there are more fragments.
	- Time to Live (TTL): It contains a counter that is set by the source, which decrement by every pass through each router along its path.  which prevents data packets from being forwarded by routers indefinitely.
	- Protocol: a field tells the receiving device which protocol will be used for the data portion of the packet.
	- Header Checksum: checksum for the header. (Corrupted packet)
	- Source IP address: the sender device IP
	- Destination IP address: the receiver device IP
	- Options: for security options (HLEN value is greater than 5)
- Data: Header + Data = 20-65535 bytes

IPv6: 8 hexadecimal number separated by colons, each up to 4 hexadecimal digits. (16 bytes total.)


### Routing
routing protocols
- **OSPF (Open Shortest Path First)**: OSPF is a routing protocol that allows routers to share information about the network topology and calculate the most efficient paths for data transmission. It does this by having routers exchange updates about the state of their connected links and networks. This way, each router has a complete map of the network and can determine the best routes to reach any destination.
- **EIGRP (Enhanced Interior Gateway Routing Protocol)**: EIGRP is a Cisco proprietary routing protocol that combines aspects of different routing algorithms. It allows routers to share information about the networks they can reach and the cost (like bandwidth or delay) associated with those routes. Routers then use this information to choose the most efficient paths for data transmission.
- **BGP (Border Gateway Protocol)**: BGP is the primary routing protocol used on the Internet. It allows different networks (like those of Internet Service Providers) to exchange routing information and establish paths for data to travel between these networks. BGP helps ensure data can be routed efficiently across the Internet, even when traversing multiple networks.
- **RIP (Routing Information Protocol)**: RIP is a simple routing protocol often used in small networks. Routers running RIP share information about the networks they can reach and the number of hops (routers) required to get there. As a result, each router builds a routing table based on this information, choosing the routes with the fewest hops to reach each destination.


### NAT
With the increase in the number of devices connected to the Internet, from computers and smartphones to security cameras and washing machines, it was clear that the IPv4 address space would be depleted quickly. One solution to address depletion is Network Address Translation (NAT).

The idea behind NAT lies in using **one public IP address** to provide Internet access to **many private IP addresses**

NAT-supporting routers maintain a table translating network addresses between internal and external networks. Generally, the internal network would use a private IP address range, while the external network would use a public IP address.

## Network Protocols
A set of rules used by two or more devices on a network to describe the order of delivery and the structure of the data.

When you request a website, your device establish a communication with the web server, this communication protocol called TCP.

### TCP 21
- TCP: Transfer control protoctol: also verifies both devices (Handshake) before any further communications.
Three-way handshake: the term given for the process used to establish a connection between two devices.
  
| **Step** | **Message** | **Description**                                                                                                                                                                                                                                    |
| -------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1        | SYN         | A SYN message is the initial packet sent by a client during the handshake. This packet is used to initiate a connection and synchronise the two devices together (we'll explain this further later on).                                            |
| 2        | SYN/ACK     | This packet is sent by the receiving device (server) to acknowledge the synchronisation attempt from the client.                                                                                                                                   |
| 3        | ACK         | The acknowledgement packet can be used by either the client or server to acknowledge that a series of messages/packets have been successfully received.                                                                                            |
| 4        | DATA        | Once a connection has been established, data (such as bytes of a file) is sent via the "DATA" message.                                                                                                                                             |
| 5        | FIN         | This packet is used to _cleanly (properly)_ close the connection after it has been complete.                                                                                                                                                       |
| 6        | FIN/ACK     | To acknowledge the finish command to close                                                                                                                                                                                                         |
| 7        | ACK         | Acknowledge                                                                                                                                                                                                                                        |
| 7        | RST         | This packet abruptly ends all communication. This is the last resort and indicates there was some problem during the process. For example, if the service or application is not working correctly, or the system has faults such as low resources. |
  
TCP packets contain various sections of information known as headers that are added from encapsulation. Let's explain some of the crucial headers in the table below: 

| Header                 | Description                                                                                                                                                                                                                                         |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Source Port            | This value is the port opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).                                                                      |
| Destination Port       | This value is the port number that an application or service is running on the remote host (the one receiving data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.                       |
| Source IP              | This is the IP address of the device that is sending the packet.                                                                                                                                                                                    |
| Destination IP         | This is the IP address of the device that the packet is destined for.                                                                                                                                                                               |
| Sequence Number        | When a connection occurs, the first piece of data transmitted is given a random number. We'll explain this more in-depth further on.                                                                                                                |
| Acknowledgement Number | After a piece of data has been given a sequence number, the number for the next piece of data will have the sequence number + 1. We'll also explain this more in-depth further on.                                                                  |
| Checksum               | This value is what gives TCP integrity. A mathematical calculation is made where the output is remembered. When the receiving device performs the mathematical calculation, the data must be corrupt if the output is different from what was sent. |
| Data                   | This header is where the data, i.e. bytes of a file that is being transmitted, is stored.                                                                                                                                                           |
| Flag                   | This header determines how the packet should be handled by either device during the handshake process. Specific flags will determine specific behaviours, which is what we'll come on to explain below.                                             |

### UDP
The **U**ser **D**atagram **P**rotocol (**UDP**) is another protocol that is used to communicate data between devices.
UDP is a **stateless** protocol that doesn't require a constant connection between the two devices for data to be sent.

UDP packets are much simpler than TCP packets and have fewer headers. However, both protocols share some standard headers, which are what is annotated in the table below:
 
| **Header**          | **Description**                                                                                                                                                                                                                   |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Time to Live (TTL)  | This field sets an expiry timer for the packet, so it doesn't clog up your network if it never manages to reach a host or escape!                                                                                                 |
| Source Address      | The IP address of the device that the packet is being sent from, so that data knows where to return to.                                                                                                                           |
| Destination Address | The device's IP address the packet is being sent to so that data knows where to travel next.                                                                                                                                      |
| Source Port         | This value is the port that is opened by the sender to send the UDP packet from. This value is randomly chosen (out of the ports from 0-65535 that aren't already in use at the time).                                            |
| Destination Port    | This value is the port number that an application or service is running on the remote host (the one receiving the data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random. |
| Data                | This header is where data, i.e. bytes of a file that is being transmitted, is stored.                                                                                                                                             |

### DNS
DNS: Domain Name System: Translate internet domain into IP address.
There are 3 levels of domain:
- TLD(Top level Domain):
	- gTLD: generic top level :.com, .net
	- ccTLD: Country Code Top level: .com.eg, .net.uk
- Second level domain: amrtarek, tryhackme (limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens)
- Subdomain: academy.varapps (The same length limit of the second level)
	- Can be multiple subdomain with multiple dots. (But the length must be kept to 253 characters or less. There is no limit to the number of subdomains you can create for your domain name.)
There are 5 types of DNS records
- A: resolve to IPv4 addresses, for example 104.26.10.229
- AAAA:  resolve to IPv6 addresses, for example 2606:4700:20::681a:be5
- CNAME: resolve to another domain name
- MX: resolve to the address of the servers that handle the email for the domain you are querying.
- TXT: free text fields where any text-based data can be stored.

DNS Servers:
- Recursive DNS server: is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked up domain names.
- Root server: act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request.
- Authoritative DNS server: the server that is responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made.

### HTTP
HyperText Transfer Protocol: developed by Tim Berners-Lee and his team between 1989-1991.
- HTTPS: HyperText Transfer Protocol Secure: a network protocol that provides a secure method of communication between clients and website servers.
	- HTTPS encrypts data using the Secure Sockets Layer (SSL) and Transport Layer Security (TLS) (SSL/TLS) to keep the information secure.
- URL: Uniform Resource Locator:
A URL is predominantly an instruction on how to access a resource on the internet.
http://user:password@amrtarek.dev:80/view-page?id=1#test

- **Scheme:** (http/https) This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP (File Transfer Protocol).
- **User:** (user:password)Some services require authentication to log in, you can put a username and password into the URL to log in.
- **Host:** (amrtarek.dev) The domain name or IP address of the server you wish to access.
- **Port:** (80) The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.
- **Path:** (view-page)The file name or location of the resource you are trying to access.
- **Query String:** (id=1) Extra bits of information that can be sent to the requested path. For example, /blog?**id=1** would tell the blog path that you wish to receive the blog article with the id of 1.
- **Fragment:** (#test) This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.

HTTP Request:
- HTTP Methods: They are a way for the client to show their intended action when making an HTTP request.
	- **GET**: getting information from a web server
	- **POST**: submitting data to the web server and adding information
	- **PUT**: submitting data and update information
	- **DELETE**: deleting information/records form the web server.
- Request Headers: headers that are sent from the client (usually your browser) to the server
	- **Host:** Some web servers host multiple websites so by providing the host headers you can tell it which one you require, otherwise you'll just receive the default website for the server.
	- **User-Agent:** This is your browser software and version number.
	- **Content-Length:** When sending data to a web server such as in a form, the content length tells the web server how much data to expect in the web request.
	- **Accept-Encoding:** Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.
	- **Cookie:** Data sent to the server to help remember your information

HTTP Response:
- Status code:
These status codes can be broken down into 5 different ranges:

**Information Responses (100–199)**  
These codes tell the client that the initial part of the request has been received and they should continue. They are rarely used in modern applications, but historically helped manage large or multi-step requests.

**Success Responses (200–299)**  
This range confirms that the client’s request was understood and successfully processed.
- **200 (OK)** means everything worked as expected.
- **201 (Created)** indicates something new was made, like a user account or a blog post.
In practice: clients can safely proceed since the server has completed what was asked.

**Redirection (300–399)**  
These codes redirect the client to another location.
- **301 (Moved Permanently)** tells browsers and search engines that the resource has a new permanent address.
- **302 (Found)** is a temporary redirect, meaning the original URL may be valid again later.
In practice: applications and search engines should update references for permanent moves, while temporary redirects are handled on the fly.

**Client Errors (400–499)**  
These codes indicate that something went wrong with the client’s request.
- **400 (Bad Request):** the request was malformed or missing details.
- **401 (Not Authorised):** authentication is required (like logging in).
- **403 (Forbidden):** access is blocked even if you are logged in.
- **404 (Not Found):** the resource simply doesn’t exist.
- **405 (Method Not Allowed):** the request method is wrong (e.g., GET instead of POST).
In practice: clients should adjust their request—check parameters, log in properly, or verify the URL.

**Server Errors (500–599)**  
These errors mean the server itself couldn’t handle the request.
- **500 (Internal Server Error):** a generic problem occurred that the server couldn’t resolve.
- **503 (Service Unavailable):** the server is overloaded or undergoing maintenance.
In practice: the issue is not with the client but with the server; retrying later or reporting the error is usually the best option.

---

 **How to handle them in real-world applications:**
- **200/201:** Proceed normally, maybe update the UI to reflect the successful action.
- **301/302:** Follow the redirect automatically (browsers do this for you). For APIs, update stored URLs if it’s a 301.
- **400-series errors:** Fix the request. Double-check parameters, authentication, or permissions.
- **500-series errors:** Retry after some time or show the user a “something went wrong” message while logging the issue for developers.


- Response Headers: the headers that are returned to the client from the server after a request.
	- **Set-Cookie:** Information to store which gets sent back to the web server on each request
	- **Cache-Control:** How long to store the content of the response in the browser's cache before it requests it again.
	- **Content-Type:** This tells the client what type of data is being returned, i.e., HTML, CSS, JavaScript, Images, PDF, Video, etc.
	- **Content-Encoding:** What method has been used to compress the data

### Cookies
Because HTTP is stateless (doesn't keep track of your previous requests), cookies can be used to remind the web server who you are, some personal settings for the website or whether you've been to the website before

Cookies are saved when you receive a "Set-Cookie" header from a web server.

Cookies can be used for many purposes but are most commonly used for website authentication. The cookie value won't usually be a clear-text string where you can see the password, but a token (unique secret code that isn't easily humanly guessable).


### DHCP
 DHCP: Dynamic Host Configuration Protocol: to assign a unique IP address to each device and provide (DNS server, and default gateway), The server operate on UDP (Port 67), while the client on (UDP port 68)

DHCP follows four steps: Discover, Offer, Request, and Acknowledge (DORA):
1. **DHCP Discover**: The client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists.
2. **DHCP Offer**: The server responds with a DHCPOFFER message with an IP address available for the client to accept.
3. **DHCP Request**: The client responds with a DHCPREQUEST message to indicate that it has accepted the offered IP.
4. **DHCP Acknowledge**: The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client.

``` shell
tshark -r DHCP-G5000.pcap -n 
1 0.000000 0.0.0.0 → 255.255.255.255 DHCP 342 DHCP Discover - Transaction ID 0xfb92d53f 
2 0.013904 192.168.66.1 → 192.168.66.133 DHCP 376 DHCP Offer - Transaction ID 0xfb92d53f 
3 4.115318 0.0.0.0 → 255.255.255.255 DHCP 342 DHCP Request - Transaction ID 0xfb92d53f 
4 4.228117 192.168.66.1 → 192.168.66.133 DHCP 376 DHCP ACK - Transaction ID 0xfb92d53f
```
IP address that a client uses when it sends a DHCP Discover packet 255.255.255.255
IP address a client uses when trying to get IP network configuration over DHCP 0.0.0.0

### ARP
ARP: Address Resolution Protocol: (Network access layer protocol in the TCP/IP) which map the IP to MAC address.
Bridging Layer 3 Addressing to Layer 2 Addressing

ARP is considered layer 2 because it deals with MAC addresses. Others would argue that it is part of layer 3 because it supports IP operations. What is essential to know is that ARP allows the translation from layer 3 addressing to layer 2 addressing.

MAC address used in an ARP Request ff:ff:ff:ff:ff:ff

### ICMP
Internet Control Message Protocol (ICMP) is mainly used for network diagnostics and error reporting. Two popular commands rely on ICMP, and they are instrumental in network troubleshooting and network security. The commands are:

- `ping`: This command uses ICMP to test connectivity to a target system and measures the round-trip time (RTT). In other words, it can be used to learn that the target is alive and that its reply can reach our system.
- `traceroute`: This command is called `traceroute` on Linux and UNIX-like systems and `tracert` on MS Windows systems. It uses ICMP to discover the route from your host to the target.


### FTP
Unlike HTTP, which is designed to retrieve web pages, File Transfer Protocol (FTP) is designed to transfer files. As a result
commands defined by the FTP protocol are:
- `USER` is used to input the username
- `PASS` is used to enter the password
- `RETR` (retrieve) is used to download a file from the FTP server to the client.
- `STOR` (store) is used to upload a file from the client to the FTP server.
- `LIST` to list the current directory

``` bash
ftp 10.10.149.120
```
ls -> to list the file
get -> to download the file.


### SMTP
SMTP: (Simple Mail Transfer Protocol): 
is used to transmit and route email from the sender to the recipient’s address. 
it defines how a mail client talks with a mail server and how a mail server talks with another.

Some of the commands used by your mail client when it transfers an email to an SMTP server:
- `HELO` or `EHLO` initiates an SMTP session
- `MAIL FROM` specifies the sender’s email address
- `RCPT TO` specifies the recipient’s email address
- `DATA` indicates that the client will begin sending the content of the email message
- `.` is sent on a line by itself to indicate the end of the email message

(plaintext (TCP/UDP port 25)), encrypted (SSL/TLS over TCP/UDP port 587)
	- MTA (Message Transfer Agent): which searches DNS servers to resolve email addresses to IP addresses.

Receiving Email
#### Pop3 (port 110)
Post Office Protocol version 3 (POP3) is designed to allow the client to communicate with a mail server and retrieve email messages.
POP3 commands are:
- `USER <username>` identifies the user
- `PASS <password>` provides the user’s password
- `STAT` requests the number of messages and total size
- `LIST` lists all messages and their sizes
- `RETR <message_number>` retrieves the specified message
- `DELE <message_number>` marks a message for deletion
- `QUIT` ends the POP3 session applying changes, such as deletions

``` shell
telnet 10.10.149.120 110
AUTH
+OK
PLAIN
.
USER linda
+OK
PASS Pa$$123
+OK Logged in.
STAT
+OK 4 2216
LIST
+OK 4 messages:
1 690
2 589
3 483
4 454
.
RETR 4
+OK 454 octets
Return-path: <user@client.thm>
Envelope-to: linda@server.thm
Delivery-date: Thu, 12 Sep 2024 20:12:42 +0000
...
```
#### IMAP
IMAP: Internet Message Access Protocol: 
downloads the header of email and the message content, the emails remains on the server, but it allows the access from multiple devices (Sync across devices).  
(plaintext (TCP/UDP port 143)), encrypted (SSL/TLS over TCP/UDP port 993)

POP3 is enough when working from one device, e.g., your favourite email client on your desktop computer. However, what if you want to check your email from your office desktop computer and from your laptop or smartphone? In this scenario, you need a protocol that allows synchronization of messages instead of deleting a message after retrieving it. One solution to maintaining a synchronized mailbox across multiple devices is Internet Message Access Protocol (IMAP).

IMAP allows synchronizing read, moved, and deleted messages. IMAP is quite convenient when you check your email via multiple clients. Unlike POP3, which tends to minimize server storage as email is downloaded and deleted from the remote server, IMAP tends to use more storage as email is kept on the server and synchronized across the email clients.

The IMAP protocol commands are more complicated than the POP3 protocol commands. We list a few examples below:

- `LOGIN <username> <password>` authenticates the user
- `SELECT <mailbox>` selects the mailbox folder to work with
- `FETCH <mail_number> <data_item_name>` Example `fetch 3 body[]` to fetch message number 3, header and body.
- `MOVE <sequence_set> <mailbox>` moves the specified messages to another mailbox
- `COPY <sequence_set> <data_item_name>` copies the specified messages to another mailbox
- `LOGOUT` logs out



| **Protocol** | **Transport Protocol** | **Default Port Number** |
| ------------ | ---------------------- | ----------------------- |
| TELNET       | TCP                    | 23                      |
| DNS          | UDP or TCP             | 53                      |
| HTTP         | TCP                    | 80                      |
| HTTPS        | TCP                    | 443                     |
| FTP          | TCP                    | 21                      |
| SMTP         | TCP                    | 25                      |
| POP3         | TCP                    | 110                     |
| IMAP         | TCP                    | 143                     |


- SNMP: Simple Network Management protocol: to monitor and managing devices on a network (Application layer)
- SFTP: Secure File Transfer Protocol: Secure file transfer protocol over SSH (Port 22)
- NAT (Network Address Translation): The router replace a private source IP address with its public IP address and perform the reverse operation for responses.(Layer 2 (Internet layer), Layer 3 transport layer (TCP/IP model))
- Telnet: Application layer protocol clear text communication over TCP (PORT 23).
- SSH: Secure Shell protocol: encrypted application layer protocol over TCP (PORT 22)
- POP: Post office protocol: application layer (layer 4 (TCP/IP)) to manage and retrieve email from a mail server. (POP3) is the commonly used version. (plaintext (TCP/UDP port 110)), encrypted (SSL/TLS over TCP/UDP port 995)

- SMB: Server Message BlockL 445: This protocol is similar to the File Transfer Protocol (FTP); however, as well as files, SMB allows you to share devices like printers.
- RDP: Remote Desktop Protocol: 3389: This protocol is a secure means of logging in to a system using a visual desktop interface (as opposed to the text-based limitations of the SSH protocol).