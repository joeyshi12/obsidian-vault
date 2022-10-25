---
course: CPSC317
title: Traceroute
tags: Network Discovery Tools
module: 2
date: 2022-10-12
---

Used to discover the route packets take to reach the destination network host.
It first sends packet with TTL 1 to find the first node in the route.
It proceeds by sending packets with incremented TTL to find other nodes in the route.

Traceroute samples the entire roundtrip 3 times because 1 trip to a node may take more time due to conjection.
- If the destination is $n$ hops away, the host sends $n$ packets with TTL $1,\dots, n$ for 1 round trip.
- 3 round trips => $3n$ packets sent from host.