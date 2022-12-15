---
course: CPSC317
title: Link Layer
tags: Link Layer
module: 3
date: [[2022-12-14]]
---

## Link Layer
- Hosts and routers are **nodes**
- Communication channels that connect adjacent nodes along communication path are **links**
    - e.g., wired links, wireless links, LANs
- Layer-2 packets are called **frames** (encapsulates [[IPv4 Datagram Format|datagram]])
    - Passing datagram up to network layer is handled by software
- Implemented inside a chip called the network adapter/NIC (Network Interface Controller)

## Link Layer Services
The network adapter implements many **link layer services** in hardware.

| Duty          | Description                                                     | Links                                          |
| ------------- | --------------------------------------------------------------- | ---------------------------------------------- |
| Framing       | Encapsulate datagram into frame, adding header                  | [[Ethernet Frame Format]]                      |
| Link Access   | MAC protocol for coordinating frame transmissions between nodes |                                                |
| Addressing    | MAC addresses distinguish src and dest                          | [[MAC Address]]                                |
| Error Control | Detection and correction                                        | [[Hamming Codes]], [[Cyclic Redundancy Check]] |
| Flow Control  | Pacing between adjacent sending and receiving nodes             |                                                |
