---
course: CPSC317
title: Dynamic Host Configuration Protocol
tags: DHCP, IP
module: 3
date: [[2022-10-12]]
---

Protocol for dynamically obtain IP address from network server when it joins network
DHCP provides (minimum)
- IP address
- Network mask
- IP address of router (default gateway)

DHCP is a client and server protocol. Each subnet needs a DHCP server
or no server is present on the subnet,
a DHCP relay agent (typically a router) that knows the address of a DHCP server for that network is needed.

The client broadcsts a request for one of the offers and
the server acknowledges the client's use of IP address
- D: Find a DHCP server to interact with. Client sends UDP packet to port 67 which is encapsulated inside IP datagram. SRC = 0 and DST = all 1s' for broadcast
- O: Server broadcasts transaction ID of the received discover message, the proposed IP address for the client, the network mask, and an IP address lease time
- R: Client broadcasts + chooses 1 offer with a DHCP request message (echos back the received config params)
- A: Server broadcasts message confirming the requested params

![[Pasted image 20221023121220.png|500]]

![[Dynamic Host Configuration Protocol 2022-10-12 09.14.59.excalidraw|800]]