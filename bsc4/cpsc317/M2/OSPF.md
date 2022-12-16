---
course: CPSC317
title: OSPF
tags: AS
module: 2 
date: [[2022-12-16]]
---

## Open Shortest Path First
- An intra-AS routing protocol
- Each router:
    - determines a shortest-path tree to all subnets
    - broadcasts routing information to all other routers in the autonomous system. A router broadcasts link-state information whenever there is a change in a link’s state (up/down status) and periodically (at least once every 30 minutes)
- OSPF messages/advertisements are held inside of the [[IPv4 Datagram Format|IP Datagram]] (upper-layer protocol = 89)

## Advantages
- Security
- Multiple same-cost paths
- Integrated support for unicast and multicast routing
- Support for hierarchy within a single AS

## Disadvantages
- OSPF does not scale well, but works fine as long as it's implemented locally inside an AS