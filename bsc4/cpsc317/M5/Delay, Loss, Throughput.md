---
course: CPSC317
title: Delay, Loss, Throughput
topic: Packet-Switched Networks
tags:
module: 5
date: [[2022-10-31]]
---

# Delay from Node
$d_{\text{nodal}} = d_{\text{proc}} + d_{\text{queue}} + d_{\text{trans}} + d_{\text{prop}}$

## Delay Types

| Type         | Description                                                        |
| ------------ | ------------------------------------------------------------------ |
| Processing   |                                                                    |
| Queuing      | Depends on traffic from other packets/varies from packet to packet |
| Transmission | Frame Size/BW = L/R                                                |
| Propagation  |                                                                    |

## Traffic Intensity

Suppose packets arrive at a queue at a rate of $a$ packets/second.
Then, the average rate at which bits arrive is $La$ and the traffic intensity is $La/R$.
Traffic intensity estimates queuing delay.
If $La/R > 1$, the rate at which bits arrive in the queue exceeds the rate at which bits can be transmitted,
so the queue will increase without bound.

**Packet Loss**: If a packet arrives to a full queue, the router will **drop** the packet.