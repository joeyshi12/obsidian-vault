---
course: CPSC317
title: Address Resolution Protocol
topic: ARP
tags: ARP
module: 3
date: [[2022-10-5]]
---

The Address Resolution Protocol (ARP) is a is a communication protocol used for discovering the link layer address, such as a MAC address, associated with a given internet layer address, typically an IPv4 address. (Wikipedia)
1. Host A sends Frame with [[ARP Packet Format|ARP Packet]]
2. Hosts B, C has a different IP address from 192.168.1.1 => ignore
3. R creates a ARP reply packet
    - Fills in MAC address in ARP packet and sends back
4. A caches IP-to-MAC address pair in **ARP table**
    - ARP table contains IP to MAC and a TTL column for the pair

![[Address Resolution Protocol 2022-10-11 12.24.51.excalidraw|700]]
