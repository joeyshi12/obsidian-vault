---
course: CPSC317
title: IPsec and VPNs
tags: IPsec, VPN
module: 7
date: [[2022-12-15]]
---

# IP Security Protocol
- Protocol that provides **confidentiality** at the network layer by encrypting the IP datagram
- Institutions use IPsec to create VPNs
- IPsec can provide:
    - Confidentiality
    - Source authentication
    - Data integrity

## Authentication Protocol & Encapsulation Security Payload
- IPsec consists of 2 principal protocols: **AH** and **ESP**
- AH provides source authentication and data integrity only
- ESP provides source authentication, data integrity, and confidentiality

## Security Association
- A unidirectional logical connection from source to destination for sending IPsec datagrams
- 2 SA connections are required for sending from both directions
- Example: suppose there are $n$ workers at a branch office and there is bi-directional IPsec traffic between the headquarter's gateway router R1 and the workers. In this VPN, how many SAs are there?
    - There are 2 SAs between R1 and R2 and each worker has 2 SAs between themself and R1
    - Number of SA connections = $2n + 2$

![[Pasted image 20221216151715.png|600]]

## IPsec Datagram Format
- Encrypts IP datagram and ESP trailer according to algorithm and key specified by SA
- Appends ESP header
- Creates and appends authentication MAC at the end
- Appends new IP header at the front. Everything after the header is referred to as the payload

![[Pasted image 20221216151007.png|600]]