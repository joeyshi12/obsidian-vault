---
course: CPSC317
title: TCP
topic: TCP
tags:
module: 4
date: [[2022-10-23]]
---

**Full-duplex service**
If there is a TCP connection between Process A on one host and Process B on another host,
then application-layer data can flow from Process A to Process B at the same time
as application-layer data flows from Process B to Process A

**Connection-oriented**: 2 processes must first handshake
- Sending some preliminary segments

**Point-to-point**: single sender and single receiver (no multicast).
- Sender and receiver has their own send and receive buffer to read and write from

![[Pasted image 20221023233505.png|700]]

![[TCP 2022-10-21 09.22.01.excalidraw|800]]