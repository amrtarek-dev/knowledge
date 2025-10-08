he Tcpdump tool and its `libpcap` library are written in C and C++ and were released for Unix-like systems in the late 1980s or early 1990s. Consequently, they are very stable and offer optimal speed. The `libpcap` library is the foundation for various other networking tools today. Moreover, it was ported to MS Windows as `winpcap`.

`tcpdump`
`-i <interface>`
`-i any` -> for all interfaces
`-w <FILE>` -> save to file with .pcap extension
`-r <FILE>` -> read a .pcap file
`-c <COUNT>` -> limit the capture packets to number
`-n` -> to avoid DNS lookups (resolve IP address)
`-nn` -> to avoid port Numbers and DNS lookups
`-v` -> to print more data like: the time to live, identification, total length and options in an IP packet.
`-vv`
`-vvv`

## Filtering:
`src host <IP>` -> for filter to src host by ip
`src host <HOSTNAME>` -> for filter to src host by HOSTNAME
`dst host <IP>` -> for filter to destination host by IP
`dst host <HOSTNAME>` -> for filter to destination host by HOSTNAME

`port <NUMBER>` -> for port number filtering
`src port <NUMBER>`
`dst port <NUMBER>`

`<PROTOCOL>` -> ip, ip6, tcp, udp, icmp.

- `greater LENGTH`: Filters packets that have a length greater than or equal to the specified length
- `less LENGTH`: Filters packets that have a length less than or equal to the specified length

## Logic Operators:
- `and`: Captures packets where both conditions are true. For example, `tcpdump host 1.1.1.1 and tcp` captures `tcp` traffic with `host 1.1.1.1`.
- `or`: Captures packets when either one of the conditions is true. For instance, `tcpdump udp or icmp` captures UDP or ICMP traffic.
- `not`: Captures packets when the condition is not true. For example, `tcpdump not tcp` captures all packets except TCP segments; we expect to find UDP, ICMP, and ARP packets among the results.

## Binary Operations:
- `&` (And) takes two bits and returns 0 unless both inputs are 1, as shown in the table below.
- `|` (Or) takes two bits and returns 1 unless both inputs are 0. This is shown in the table below.
- `!` (Not) takes one bit and inverts it; an input of 1 gives 0, and an input of 0 gives 1, as shown in the table below.


## Header Bytes
How can we tell Tcpdump to filter packets based on the contents of protocol header bytes,
Using pcap-filter, Tcpdump allows you to refer to the contents of any byte in the header using the following syntax `proto[expr:size]`, where:
- `proto` refers to the protocol. For example, `arp`, `ether`, `icmp`, `ip`, `ip6`, `tcp`, and `udp` refer to ARP, Ethernet, ICMP, IPv4, IPv6, TCP, and UDP respectively.
- `expr` indicates the byte offset, where `0` refers to the first byte.
- `size` indicates the number of bytes that interest us, which can be one, two, or four. It is optional and is one by default.

- `ether[0] & 1 != 0` takes the first byte in the Ethernet header and the decimal number 1 (i.e., `0000 0001` in binary) and applies the `&` (the And binary operation). It will return true if the result is not equal to the number 0 (i.e., `0000 0000`). The purpose of this filter is to show packets sent to a multicast address. A multicast Ethernet address is a particular address that identifies a group of devices intended to receive the same data.  
    
- `ip[0] & 0xf != 5` takes the first byte in the IP header and compares it with the hexadecimal number F (i.e., `0000 1111` in binary). It will return true if the result is not equal to the (decimal) number 5 (i.e., `0000 0101` in binary). The purpose of this filter is to catch all IP packets with options.

For TCP:
You can use `tcp[tcpflags]` to refer to the TCP flags field. The following TCP flags are available to compare with:
- `tcp-syn` TCP SYN (Synchronize)
- `tcp-ack` TCP ACK (Acknowledge)
- `tcp-fin` TCP FIN (Finish)
- `tcp-rst` TCP RST (Reset)
- `tcp-push` TCP Push

Based on the above, we can write:
- `tcpdump "tcp[tcpflags] == tcp-syn"` to capture TCP packets with **only** the SYN (Synchronize) flag set, while all the other flags are unset.
- `tcpdump "tcp[tcpflags] & tcp-syn != 0"` to capture TCP packets with **at least** the SYN (Synchronize) flag set.
- `tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"` to capture TCP packets with **at least** the SYN (Synchronize) **or** ACK (Acknowledge) flags set.

## Show Packets
Tcpdump is a rich program with many options to customize how the packets are printed and displayed. We have selected to cover the following five options:
- `-q`: Quick output; print brief packet information
- `-e`: Print the link-level header
- `-A`: Show packet data in ASCII (American Standard Code Information Interchange)
- `-xx`: Show packet data in hexadecimal format, referred to as hex
- `-X`: Show packet headers and data in hex and ASCII