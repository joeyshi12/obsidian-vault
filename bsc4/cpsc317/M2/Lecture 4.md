---
course: "cpsc317"
topic: "IP"
module: "m2"
lecture: 4
---

**Network Layer: IP**

![[Pasted image 20220916090831.png|600]]


## Naming
- Purpose is to route messages from source to destination
- Name has
    - Format
    - Semantics
    - Properties
- Addressing -> Naming


## IPv4 Addresses
- IP = Internet Protocol
- Version 4
- 4 bytes total in decimal notation. 4 bytes = octet
    - e.g., 192.168.0.1
    - Possibly tested on binary
- IPv4 addresses an interface
    - Assigned to an interface card
- **Interface Card**: Hardware in device for communication
    - wifi, bluetooth
- Our computers may have multiple IPs for different communication mediums


## NATS
- Non-routable IP address
- Format: 192.().().()
- Routers will drop this


## Classless Inter Domain Routing (CIDR)
- IP Address
- **Format**: a.b.c.d/x
    - **Example**: 200.23.18.4/22

![[Pasted image 20220916094022.png|500]]