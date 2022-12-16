## M1
| Term              | Description                                                                                                                                                                            |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Protocol          | The format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event |
| Packet-switching  | Data is broken into packets and travels through communication links and *packet switches* (routers or link-layer switches)                                                           |
| Circuit-switching | Communication path between end systems are *reserved*                                                                                                                                |
| StatMux           |                                                                                                                                                                                        |
|                   |                                                                                                                                                                                        |

A host can connect to routers/NAT routers.
This is contained in the ISP, which is contained inside an AS.

## M2
| Term               | Description                                                                                                                                         |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Forwarding]]     | Local router action for transferring a packet from an input link interface to an output link interface                                              |
| AS                 | Group of routers under the same administrative control. Routers in an AS run the same intra-autonomous system routing protocol                      |
| [[OSPF]]           | Intra-AS routing protocol, where each router in the AS determines shortest-path to all subnets                                                      |
| [[BGP]]            | Inter-AS routing protocol that provides each router as means to obtain reachability info on neighbouring AS and find best routes to addres prefixes |
| Hot Potato Routing | OSPF sends packets to the closest border router                                                                                                     |

- A port is a number attached to a socket
- TCP matches port to socket based on the 4-tuple
- On socket accept, the new port for the client fd is the same port as the original socket fd

How do we get from the interface card to the router?
- Ethernet / layer-2 / data link layer
- Only TTL and checksum gets updated in this process

| Protocol | Depends on |
| -------- | ---------- |
| BGP      | TCP        |
| DNS      | UDP        |
| DHCP     | UDP        |
| ICMP     | IP         |
| ARP      | Ethernet   | 

RDT 2.2 will be given for the exam
Formula for average intesity will be given

RDT 2.0: corrupted messages
- Added checksum
- ACK/NAK
- Retransmissions

Lost messages => add timeout

Sequence space of size 2 helps us against duplicate packets

Utilization = percent of time the client is busy

Average queuing delay = $S/(1-u)$

Larger delay => bigger window size
- Maximize utilization for the sender

Lost packet
- Send entire window
Selective repeat can receive out of order packets

TCP
- ACKs thing it wants to receive
- Dynamic window size (receive window size in TCP segment) => flow control

Passive firewall