---
course: "cpsc317"
module: "m1"
lecture: 2
---

**Internet**: network of networks
**Packet-switching**: "hop, hop, hop"
**Circuit-switching**: "reservation"

## Communication Channel
1. Share different frequency (frequency division multiplexing; FDM)
2. Time division multiplexing (TDM)
    - Split transmission line in time intervals
    - ![[Drawing 2022-09-12 09.16.09.excalidraw]]
    - 3 Users / Slots (A, B, C)
    - 3 Channels => communicates a stream of data

## Statistical Multiplexing
- Allows data from a number of channels to be combined for transmission over a single transmission line (statmux)
- **Idea**: a sharing strategy that depends on statistical information about the arrival rate of data. Bandwidth is allocated according to the probability of need.
- Works well when
    - Aggregate average load is much less than the aggregate peak of individual loads
    - Demand is *bursty*
    - Therefore, it is better to share resources than to strictly partition them...
$$\sum_i s_i\quad (Ave) << \sum_i s_i\quad (peak)$$
$$
\begin{align*}
P_1: && 2 \text{ day/wk} && 5 \text{ days} \\
P_2: && 2 \text{ day/wk} && 5 \text{ days} \\
P_3: &&\vdots && \vdots \\
&& 2 \text{ Ave} && 5 \text{ Peak}
\end{align*}
$$
## Circuits or Packets
- Advantages of circuits:
    - Better application performance (reserved bandwidth)
    - More predictable and understandable (without failures)
    - If you need a constant flow. (constant bit rate)
- Advantages of packets:
    - Easier recovery from failure (don't have to follow same path)
    - Simpler state in routers (not per-flow)  
    - Faster startup to first packet delivered (no reservation)  
    - More efficient use of the network when combined with statmux

![[Lecture 2 2022-10-07 08.48.33.excalidraw]]
![[Lecture 2 2022-10-07 08.49.20.excalidraw]]
## Protocol
