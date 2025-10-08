# Layer 2 and 3

In the OSI model, Layer 2 (Data Link) and Layer 3 (Network) are responsible for data transmission and routing respectively. Each layer has specific protocols that are essential for communication:

## Layer 2 – Data Link Layer

This layer handles node-to-node data transfer and physical addressing (MAC addresses).

| protocol| description |
|:--------|:------------|
| Ethernet (IEEE 802.3) | The most common LAN protocol; defines framing and MAC addressing. |
| Wi-Fi (IEEE 802.11) | Wireless LAN protocol with MAC layer functions. |
| PPP (Point-to-Point Protocol) | Used over direct connections (e.g., serial links); encapsulates network layer packets. |
| HDLC (High-Level Data Link Control) | Synchronous data link protocol used in WANs. |
| Frame Relay | Packet-switched WAN protocol, mainly legacy now. |
| ATM (Asynchronous Transfer Mode) | High-speed networking using fixed-size cells. |
| MAC (Media Access Control) | Sub-layer responsible for addressing and channel access. |
| LLC (Logical Link Control, IEEE 802.2) | Provides multiplexing of protocols and error control above MAC. |
| STP/RSTP (Spanning Tree Protocol / Rapid STP) | Prevents loops in Ethernet networks. |

## Layer 3 – Network Layer

This layer is responsible for routing, addressing (IP), and packet forwarding between networks.

| protocol| description |
|:--------|:------------|
| IP (Internet Protocol – IPv4 / IPv6) | Core protocol for routing packets across networks. |
| ICMP (Internet Control Message Protocol) | Used for diagnostics (e.g., `ping`, `traceroute`). |
| IGMP (Internet Group Management Protocol) | Manages multicast group memberships (IPv4). |
| IPsec (Internet Protocol Security) | Provides authentication and encryption at the IP level. |
| ARP (Address Resolution Protocol) | Resolves IP addresses to MAC addresses (IPv4). |
| RARP (Reverse ARP) | Legacy protocol to get IP from MAC (mostly obsolete). |
| NDP (Neighbor Discovery Protocol) | IPv6 equivalent of ARP, with additional functions. |
| **Routing Protocols** |
| OSPF (Open Shortest Path First) | Interior gateway protocol (IGP), link-state based. |
| BGP (Border Gateway Protocol) | Exterior gateway protocol (EGP), used for internet routing. |
| EIGRP (Enhanced Interior Gateway Routing Protocol) | Cisco proprietary IGP, hybrid of distance-vector and link-state. |
| RIP (Routing Information Protocol) | Simple distance-vector IGP, now mostly legacy. |