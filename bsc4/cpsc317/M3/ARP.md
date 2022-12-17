---
course: CPSC317
title: ARP
tags: ARP
module: 3
date: [[2022-10-5]]
---

# Address Resolution Protocol
ARP is a communication protocol used for discovering the link layer address ([[MAC Address]]) associated with a given internet layer address ([[IPv4 Address]])
1. Host A sends Frame with [[ARP Packet Format|ARP Packet]]
2. Hosts B, C has a different IP address from 192.168.1.1 => ignore
3. R creates a ARP reply packet
    - Fills in MAC address in ARP packet and sends back
4. A caches IP-to-MAC address pair in **ARP table**
    - ARP table contains IP to MAC and a TTL column for the pair

![[Address Resolution Protocol 2022-10-11 12.24.51.excalidraw|700]]