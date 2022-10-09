---
topics: ["Network Discovery Tools"]
module: 3
lecture: 9
---

## Traceroute
1. Starts from source and sets TTL = 1
    - Expires and ICMP message to source
2. Repeat with TTL = 2
3. Continue until TTL is large enough to reach host


## Traceroute to Swizerland
![[Pasted image 20221003093420.png|800]]
- 18 ms on row 6 implies congestion
- Jump in time on line 9 is due to travelling to a different continent

## Link Layer
- Hosts and routers are **nodes**
- Communication channels that connect adjacent nodes along communication path are **links**
    - Wired links
    - Wireless links
    - LANS
- Layer-2 packet is a **frame**, encapsulates datagram


## Adaptors Communicating
![[Pasted image 20221003094342.png|800]]
- Digital to analog and analog to digital
    - Bits on a wire is just modulation on a wire


## Multiple Access Links and Protocols
- Two types of links
    - Point-to-point (between 2 routers)
    - Broadcast (shared by a wire or medium)

> "A router is a layer 3 device"


