---
course: CPSC317
title: Sliding Window
tags: GBN, SR
module: 6
date: [[2022-11-14]]
---

## Go-Back-N
- The `base` is the oldest unacknowledged packet and `nextseqnum` is the seqnum of the next packet to be sent
- $SWS = N$ and $RWS = 1$
- There is a timer for each sent packet. If an ACK is not received before timeout, then another packet is sent

![[Pasted image 20221216161449.png|600]]

## Selective Repeat
- Similar to GBN, but $SWS = RWS = N$

## Selective Repeat Dilemma
- In selective repeat, the receiver does not see a difference between the 2 scenarios
    - A duplicate of an old packet can be received without error
- This can be avoided if
    - $\text{numSeqNumbers} \geq SWS + RWS$

![[Pasted image 20221216164400.png|400]]

## Sequence number cases
- $numSeqNumbers \geq RWS + SWS$
- $SWS \geq RWS$
- Stop and wait: $SWS = RWS = 1$
- GBN: $SWS = N$, $RWS = 1$
- SR: $SWS = RWS = N$