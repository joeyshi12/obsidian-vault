---
title: "MAC Address"
topics: ["MAC Address"]
module: 3
---

A link-layer address is referred as a **MAC Address**.
- e.g., `00:2A:C6:4B:00:44`
- 48 bits

MAC address space is managed by IEEE
When a company purchases a chunk of address space,
IEEE fixes the first 24 bits of a MAC address and lets the company
create up to $2^{24}$ unique combinations of the last 24 bits for each adapter.

## MAC Address vs IP Address
- 32-bit IP Address
    - Network-layer address
    - Used to get [[IPv4 Datagram Format|datagram]] from source to destination IP subnet
    - Laptop IP addresses change when moved
- 48-bit MAC Address
    - Used to get [[Ethernet Frame Format|frame]] from one interface to another physically-connected interface (same network)
    - Laptop MAC addresses do not change