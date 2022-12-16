---
course: CPSC317
title: TCP Versus UDP
topic: Transport Level Protocols
tags: TCP, UDP
module: 4
date: [[2022-10-17]]
---

Ordered delivery -> delivers segments in-order (in M6)  
Bidirectional -> data flows both ways  
Unidirectional -> data can flow only one way  
Connection oriented -> first makes a connection between ends  
Connection-less -> no hand-shake
Segmentation -> cut the data stream into segments for IP  
Data bundling -> optimization to send full packets (Nagle –not  covered)  
Stream-oriented -> sends a stream of bytes  
Message-oriented -> send messages  
Multicast -> can multicast on LAN  
Non-duplication -> handle duplicate packets

| Service               | TCP | UDP |
| --------------------- | --- | --- |
| Partial delivery      |     |     |
| Reliable delivery     | 1   |     |
| Flow control          | 1   |     |
| Conjestion control    | 1   |     |
| Signaling             | 1   |     |
| Ordered delivery      | 1   |     |
| Bidirectional         | 1   |     |
| Unidirectional        |     | 1   |
| Connection oriented   | 1   |     |
| Connectionless        |     | 1   |
| Segmentation          | 1   |     |
| Data Bundling         | 1   |     |
| Stream-oriented       | 1   |     |
| Stream-oriented       |     | 1   |
| Message-oriented      |     | 1   |
| Multicast             |     |     |
| Non-duplication       | 1   |     |
| One-to-one connection | 1   |     |

![[Untitled 2022-10-19 09.13.05.excalidraw|800]]