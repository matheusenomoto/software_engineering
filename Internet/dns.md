# Domain Name System - DNS 

DNS is a hierarchical and distributed system that translates human-friendly domain names (like example.com) into IP addresses (like 93.184.216.34), which computers use to locate each other on a network.

## DNS Root

The Root is the top of the DNS hierarchy. If you query www.example.com, the root server doesn't know the IP but says: "Ask the .com TLD servers."

## TLD (Top-Level Domain)

One level below the root. The TLD server responds with: "Ask the authoritative server for example.com."

## Authoritative Name Server

Stores the actual DNS records (A, AAAA, MX, TXT, etc.) for a domain. Authoritative server response: "www.example.com resolves to 93.184.216.34.

<img width="1079" height="721" alt="dns_tree" src="https://github.com/user-attachments/assets/c9a9a67f-7449-46f7-82d9-0bb12f00e247" />

<img width="943" height="645" alt="dns_workflow" src="https://github.com/user-attachments/assets/62c415e9-45b8-48ca-9313-db2d6f4ebcf6" />


## DNS Record Types

| type | stands for | purpose |
|:----:|:----------:|:--------|
| A | Address | Maps a domain to an IPv4 address |
| AAAA | IPv6 Address | Maps a domain to an IPv6 address |
| CNAME | Canonical Name | Maps a domain to another domain name (alias) |
| NS | Name Server | Specifies the authoritative name servers for a zone |
| MX | Mail Exchange | Defines mail servers for a domain |
| TXT | Text | Stores arbitrary text (e.g., SPF, DKIM, verification) |
| SOA | Start of Authority | Contains administrative info about the zone |
| PTR | Pointer | Used for reverse DNS lookups |
| SRV | Service | Defines services like SIP or XMPP |
| CAA | Certification Auth. | Restricts which CAs can issue certs for a domain |

## DNS message format

<img width="517" height="412" alt="dns_message_format" src="https://github.com/user-attachments/assets/b58b5cf3-9cfd-49e5-a1d9-f0c00457b7c5" />
