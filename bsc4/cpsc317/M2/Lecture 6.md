---
course: "cpsc317"
topic: "IP Header"
module: "m2"
lecture: 6
---

## IP Format
- IP consists of a network section and host section
- 128.0.0.1/x, where x is the host bits
- $0 \leq x \leq 32$
    - $x = 0$ implies all host bits
        - All zero network mask
        - Do not do this
    - $x = 32$ implies all network bits
        - All one network mask
        - Broadcast

How many host address are there?
- Given $k$ network bits, $2^k - 2$

## Packet Network
- No call setup at network layer
- Routers: no state about end-to-end connections
    - No network-level concept of "connection"
    - packets forwarded using destination host address
        - Packets between same source-destination pair may take different paths
        
## Protocol Design
- Packet header + opaque payload (why opaque??)
    - Opaque: can't look into it
    - Layer violation
    - Keeps good division between different layers
 
![[Pasted image 20220921091208.png|500]]

**What do we have to do?**
- Read packets correctly
- Get packet to the destination
- Get responses to the packet back to source
- Carry data
- Tell host what to do with packet once arrived
- Specify any speical network handling of the packet
- Deal with problems tha arise along the path

## Exercise
- 6 networks
- Remove links involving routers (cylinders), count fragments

![[Pasted image 20220921094625.png|700]]