---
course: CPSC317
title: TCP RDT Service
tags:
module: 
date: [[2022-12-13]]
---

TCP creates a RDT service on top of IP's unreliable best-effort service.
TCP RDT service ensures the data stream in TCP recv buffer is
- Uncorrupted
- Without gaps
- Without duplication
- And in sequence

## Doubling the Timeout Interval

When TCP retransmit a segment, the timeout is doubled.
For example, in the diagram below, segment 100 will not be retransmitted.

![[Pasted image 20221213180326.png|500]]

## Fast Retransmit
- If `sendBase >= lastACK`, retransmit `lastACK`
- Resend seq=100 packet if 3-duplicate ACKs are detected

![[Pasted image 20221213180415.png|400]]