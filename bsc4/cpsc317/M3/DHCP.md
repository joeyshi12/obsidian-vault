---
course: CPSC317
title: DHCP
tags: DHCP, IP
module: 3
date: [[2022-10-12]]
---

## Dynamic Host Configuration Protocol

A protocol for dynamically obtain IP address from network server when it joins network.
DHCP provides, at minimum:
- IP address
- Network mask
- IP address of router (default gateway)

DHCP is a client and server protocol:
- Each subnet needs a DHCP server or a DHCP relay agent (e.g., a router) that knows the address of a DHCP server for that network.
- Each step of DHCP is a broadcast.
- Since TCP requires both ends to have unique IP addresses, DHCP must use UDP.

| Step        | Description                                                                                                                                               |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Discover    | Find a DHCP server to interact with. Client sends UDP packet to port 67 which is encapsulated inside IP datagram. SRC = 0 and DST = all 1s' for broadcast |
| Offer       | Server broadcasts transaction ID of the received discover message, the proposed IP address for the client, the network mask, and an IP address lease time |
| Request     | Client broadcasts 1 choice from the offer with a DHCP request message (echos back the received config params)                                                   |
| Acknowledge | Server broadcasts message confirming the requested params                                                                                                 |

![[Pasted image 20221023121220.png|500]]

![[Dynamic Host Configuration Protocol 2022-10-12 09.14.59.excalidraw|800]]