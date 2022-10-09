---
course: "cpsc317"
topic: "IP Header"
module: "m2"
lecture: 7
---

## Network Layer
- The network table contains a list of network addresses

![[Pasted image 20220923090145.png|700]]

e.g.,
|             |        |
| ----------- | ------ |
| CA, NS      | Link 1 |
| CA, BC, Van | Link 2 |
| CA, ONT, TO | Link 3 |


## Router
- Needs a "routing table"
- Needs to look-up and forward packets
- A routing protocol to maintain the routing table; creating and updating the table based on network conditions

*We give interface cards IP addresses*


## Look-up and Forwarding
[[Network Routing - One Hop]]

**Hopping across the Network**
Routers make routing decisions by comparing the Network Prefix part
of networks in its routing table to the destination IP address in the IP header


## Two key network-layer functions
| Function   | Description                                                 |
| ---------- | ----------------------------------------------------------- |
| Forwarding | Move packets from router's input to appropriate router      |
| Routing    | Determine route taken by packets from source to destination |

**Data plane**
- Local, per-router function
- determines how datagram arriving on router input port is forwarded to router output port
- Forwarding function

**Control plane**
- Network-wide logic
- Determines how datagram is routed among routers along end-end path from source host to destination host
- Two control-plane approaches:
    - **Traditional routing algo**: implemented in routers
    - **Software-defined networking (SDN)**: implemented in (remote) servers
![[Pasted image 20220923093942.png|800]]


## Longest Prefix Match
- Table of CIDR network addresses of different length? Which do you match?  
    - 23/8
    - 23.15/16  
- Table matching
    - Convert the advertised address to binary. 
    - Strip off any bits past the X bits (A.B.C.D/x)  
    - Always a default that matches everything (default value 0.0.0.0 (or /0), see next bullet)
    - See how many bits of the prefix match the destination IP. (use a MASK with prefix 1’s and AND)


## Interior Gateway Routing Protocols (IGP - OSPF, IGRP, RIP)
- Link State
    - Broadcast link information to all routers
    - Create a "map" of the network
- Distance vector
    - Send local information to neighbouring routers
    - Create "signposts" for routing

Obtain state information by sending *route advertisements*


## Private networks
- AS \# = Autonomous System Number

![[Pasted image 20220923094825.png|700]]
