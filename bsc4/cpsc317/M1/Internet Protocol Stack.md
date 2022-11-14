---
course: CPSC317
title: Internet Protocol Stack
tags:
module: 1
date: [[2022-10-12]]
---

| Stack       | Description                                                 | Examples Protocols        |
| ----------- | ----------------------------------------------------------- | ------------------------- |
| Application | application-layer protocols reside here                     | HTTP, SMTP, FTP, DHCP     |
| Transport   | transport app-layer message betweeen application end-points | TCP, UDP                  |
| Network     | move network-layer packets between hosts                    | IP                        |
| Link        | delivers datagram to next node                              | Ethernet, WIFI, ARP       |
| Physical    | transport individual bits                                   | Copper wire, fiber optics |

Each layer below the application layer can be thought as an abstract data transfer channel
between sender and receiver.

![[Pasted image 20221114111120.png|800]]

![[Pasted image 20220916090831.png|600]]