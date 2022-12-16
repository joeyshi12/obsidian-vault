## M1

| Term              | Description |
| ----------------- | ----------- |
| Protocol          |             |
| Packet-switching  |             |
| Circuit-switching |             |
| StatMux           |             |

A host can connect to routers/NAT routers.
This is contained in the ISP, which is contained inside an AS.
An AS can connect to other AS.

| Term              | Description                                                                                            |
| ----------------- | ------------------------------------------------------------------------------------------------------ |
| Router forwarding | Local router action for transferring a packet from an input link interface to an output link interface |
| ISP               |                                                                                                        |
| AS                |                                                                                                        |
| iBGP              | Needed for scalability, has policies for different administrative domains                              |
| BGP               | Policy-based                                                                                           |
| OSPF              | Does not scale                                                                                         |

- Hot potato routing: OSPF sends to closest border
- A port is a number attached to a socket
- TCP matches port to socket based on the 4-tuple
- On socket accept, the new port for the client fd is the same port as the original socket fd

How do we get from the interface card to the router?
- Ethernet / layer-2 / data link layer
- Only TTL and checksum gets updated in this process

BGP uses TCP
DNS uses UDP
DHCP uses UDP
ICMP uses IP
ARP uses Ethernet

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