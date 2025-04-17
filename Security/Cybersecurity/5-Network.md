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

## 

## Data Packet
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

The data link layer organizes sending and receiving data packets within a single network. The data link layer is home to switches on the local network and network interface cards on local devices
Protocols like:
- network control protocol (NCP)
- high-level data link control (HDLC)
- synchronous data link control protocol (SDLC)
are used at the data link layer

The physical layer corresponds to the physical hardware involved in network transmission.


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


## Network Protocols
A set of rules used by two or more devices on a network to describe the order of delivery and the structure of the data.

When you request a website, your device establish a communication with the web server, this communication protocol called TCP.

- TCP: Transfer control protoctol: also verifies both devices (Handshake) before any further communications.

- HTTPS: HyperText Transfer Protocol Secure: a network protocol that provides a secure method of communication between clients and website servers.
	- HTTPS encrypts data using the Secure Sockets Layer (SSL) and Transport Layer Security (TLS) (SSL/TLS) to keep the information secure.
- DNS: Domain Name System: Translate internet domain into IP address.
- SNMP: Simple Network Management protocol: to monitor and managing devices on a network (Application layer)
- SFTP: Secure File Transfer Protocol: Secure file transfer protocol over SSH (Port 22)
- NAT (Network Address Translation): The router replace a private source IP address with its public IP address and perform the reverse operation for responses.(Layer 2 (Internet layer), Layer 3 transport layer (TCP/IP model))
- DHCP: Dynamic Host Configuration Protocol: to assign a unique IP address to each device and provide (DNS server, and default gateway), The server operate on UDP (Port 67), while the client on (UDP port 68)
- ARP: Address Resolution Protocol: (Network access layer protocol in the TCP/IP) which map the IP to MAC address.
- Telnet: Application layer protocol clear text communication over TCP (PORT 23).
- SSH: Secure Shell protocol: encrypted application layer protocol over TCP (PORT 22)
- POP: Post office protocol: application layer (layer 4 (TCP/IP)) to manage and retrieve email from a mail server. (POP3) is the commonly used version. (plaintext (TCP/UDP port 110)), encrypted (SSL/TLS over TCP/UDP port 995)
- IMAP: Internet Message Access Protocol: downloads the header of email and the message content, the emails remains on the server, but it allows the access from multiple devices (Sync across devices).  (plaintext (TCP/UDP port 143)), encrypted (SSL/TLS over TCP/UDP port 993)
- SMTP: (Simple Mail Transfer Protocol): is used to transmit and route email from the sender to the recipient’s address. (plaintext (TCP/UDP port 25)), encrypted (SSL/TLS over TCP/UDP port 587)
	- MTA (Message Transfer Agent): which searches DNS servers to resolve email addresses to IP addresses.
