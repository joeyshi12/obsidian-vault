---
course: CPSC317
title: Network Routing - One Hop
topic: Routing
tags:
module: 2
date: [[2022-11-23]]
---


![[Pasted image 20220923091550.png|800]]

Source `192.168.0.45` is trying to send a message to destination `23.96.1.0`
1. Compare `23.96.1.0` to my own *IP address*
    - `192.168.0.0` <- 24 bits,
    - `23.96.1.0`
    - Does not match
2. No match -> go to default address -> router
    - `206.87.0.0` is a *network address*
    - Compare with `23.96.1.0`
    - Does not match
3. Hops to rightmost router `23.96.0.1/13` <- first 13 bits
    - First 13 bits matches with destination