---
course: CPSC317
title: Sliding Window
topic:
tags:
module: 6
date: [[2022-11-14]]
---

Sender has k-bit sequence number in header and a window size of N
- \# Seq Numbers >= RWS; otherwise we have duplicate sequence numbers in the window
- Allows us to put more packets in flight or fill the pipe.

## Go-Back-N
- Packets after the most recent uncorrected packet is dropped
- RWS = 1

## Selective Repeat
- Similar to Go-Back-N, but SWS = RWS = N

## Selective Repeat Dilemma
- Can be avoided if \# Sequence numbers >= SWS + RWS