# IP Header

## PDU

PDU stands for Protocol Data Unit. It refers to a unit of data transmitted between network entities at a specific layer of a communication protocol stack, like the OSI model or TCP/IP model.

![ip_header_ipv4](../img/ip_header_ipv4.png)

![ip_header_ipv6](../img/ip_header_ipv6.png)

## Summary Table

| feature | IPv4 Header | IPv6 Header |
|:-------:|:-----------:|:-----------:|
| Header Size | 20-60 bytes (variable) | 40 bytes (fixed) |
| Address Size | 32 bits | 128 bits |
| Header Complexity | More complex, variable length | Simpler, fixed length |
| Fragmentation | Done by both sender and routers | Only done by sender |
| Checksum | Present (in header) | Removed (handled by upper layers) |
| Options | Supported via optional fields | Moved to extension headers |
| QoS Support | Type od Service (ToS) field | Traffic Class and Flow Label |
| Security | Optional (IPsec) | Mandatory support for IPsec |

## IPv4 Header Fields

* Version (4 bits): IP version (always 4).
* IHL (Internet Header Length): Header length in 32-bit words.
* Type of Service (ToS): Used for QoS.
* Total Length: Length of the entire packet (header + data).
* Identification, Flags, Fragment Offset: Used for fragmentation and reassembly.
* TTL (Time to Live): Limits packet lifetime.
* Protocol: Next layer (e.g., TCP, UDP).
* Header Checksum: Error-checking for the header.
* Source IP Address (32-bit).
* Destination IP Address (32-bit).
* Options (optional): Extra features, not commonly used.
* Variable length due to optional fields makes parsing more complex and slower.

## IPv6 Header Fields

* Version (4 bits): IP version (always 6).
* Traffic Class: Similar to ToS in IPv4, for QoS.
* Flow Label: Identifies packet flows for special handling.
* Payload Length: Size of the payload (excludes the header).
* Next Header: Identifies the type of header following this one (e.g., TCP, UDP, or an extension header).
* Hop Limit: Same as TTL in IPv4.
* Source Address (128-bit).
* Destination Address (128-bit).
* No options or checksum in the base header. Extension headers are used if needed, improving performance and flexibility.

## Key Improvements in IPv6

* Fixed header size = faster processing by routers.
* No checksum = offloads responsibility to upper layers like TCP/UDP.
* Larger address space = supports more devices (128-bit vs 32-bit).
* Extension headers = optional and modular, allowing cleaner design.

IPv4 and IPv6 are both Internet Protocol versions used to identify devices on a network. Their headers contain important metadata that routers and other network devices use to deliver packets. Here’s a comparison between the two:

| criterion | IPv4 | IPv6 |
|:---------:|:----:|:----:|
| Designed for | Simpler networks, fewer hosts | Modern internet with billions of devices |
| Routing | More overhead | Optimized and streamlined |
| Performance | Less efficient | More efficient header processing |