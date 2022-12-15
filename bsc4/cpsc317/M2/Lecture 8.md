---
course: cpsc317
topic: AS Organization
tags: Path Vectors, Aggregation, BGP Internals
module: 2
lecture: 8
---

## Topics
- Path Vectors
- Aggregation
- BGP Internals

## Autonomous System (AS)
- An autonomous system (AS) is a collection of  connected Internet Protocol (IP) routing prefixes under  the control of one or more network operators on behalf  of a single administrative entity or domain that  presents a common, clearly defined routing policy to  the Internet.
 - A unique ASN is allocated to each AS for use routing.   The ASN uniquely identifies each network on the   Internet.  
-  Until 2007, AS numbers were defined as 16-bit   integers, but are now 32-bit numbers (still supporting   the old style)

## Peering and Transit
- Peering
    - Two ISPs pass traffic between each other for their customers
- Transit
    - Passing traffic across an AS to get to a different AS
- Stub network, single provider as Internet Gateway

## BGP - Path Vector Routing
![[Pasted image 20220926091430.png|800]]

$W, A, B, C, X, Y$ are AS numbers

**How to find out about your network $x$**?
- $W$ advertises to $A$ => $A$ advertises to $B$ and $C$ => ...

**Loop Detection**
- Requires/trusts BGP tables are accurate

## Scalable Design
- Interior gateway protocols cannot scale to the Internet
- Routing table sizes is a problem in the core

## Supernetting Example

![[Pasted image 20220926092939.png|800]]
```
200.23.20.0/22    (20 = 00010100)
200.23.16.0/22    (16 = 00010000)

These addresses can be combined into 200.23.16.0/21.
i.e., advertising 200.23.16.0/21 is the same as advertising the other 2 addresses.
```

## BGP Terminology
| Term        | Definition                                                                               |
| ----------- | ---------------------------------------------------------------------------------------- |
| BGP speaker | creates a   TCP connection between   two routers both speaking   BGP   Border router     |
| iBGP        | propagate   reachability information to   all AS-internal routers and   advertise prefix |
| eBGP        | obtain subnet   reachability information   from neighboring ASs                          |

**All border routers run eBGP**