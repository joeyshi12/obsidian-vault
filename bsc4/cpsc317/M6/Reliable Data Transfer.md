---
course: CPSC317
title: Reliable Data Transfer
topic: RDT
tags: RDT
module: 6
date: [[2022-11-02]]
---

Recall that reliability in networking means either
1. We get the correct msg or
2. We get notified of failure

## Reliable Data Transfer Protocol

RDT provides a service abstraction for the application layer.
In particular, the packets that are passed between transport and network layer
can be corrupted and it is the job of the transport layer provide a reliable channel.

RDT ensures data from the sending process is received correctly and in-order by using
1. Flow control
2. Sequence numbers
3. Acknowledgments
4. Timers


![[Pasted image 20221114111120.png|800]]