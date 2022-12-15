---
course: CPSC317
title: Traceroute
tags: Network Discovery Tools
module: 2
date: 2022-10-12
---

## Traceroute
- Lists router hops from client host to remote host.
- IP address and domain name of each router is returned to the client.

## Algorithm
- Sets TTL = 1, sends UDP datagram
- Sets TTL = 2, sends UDP datagram
- ... continue until remote host is reached
- Note: traceroute samples 3 roundtrips since some trips to a node may take more time due to conjestion
    - $n$ hops implies $3n$ packets are sent from the client

## Traceroute to Swizerland
- 18 ms on row 6 implies congestion
- The jump in time on line 9 is due to travelling to a different continent

![[Pasted image 20221003093420.png|800]]
