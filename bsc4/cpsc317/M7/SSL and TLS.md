---
course: CPSC317
title: SSL/TLS
topic:
tags: SSL, TLS
module: 7
date: [[2022-12-05]]
---

## SSL
- Bob = Client, Alice = Server
- Bob sends Alice an SSL hello
- Alice sends Bob a certificate to verify her identity & public key
- Bob uses the certificate to create a master secret and sends the MS to Alice
- Alice decrypts the MS
- The MS contains 4 keys
    - $K_c$ symmetric encryption key for data from client to server
    - $M_c$ MAC for data from client to server
    - $K_s$ symmetric encryption key for data from server to client
    - $M_s$ MAC for data from server to client
    - Note: using the same key for more than one cryptographic operation is considered bad practice, so that's why we have keys for both directions

![[Pasted image 20221205133339.png|500]]

## Key exchange
- IKE: Internet key exchange
    - Allows us to run a key exchange algorithm (i.e., Diffie-Hellman Key Exchange)

## Block ciphers
- One popular example is DES (Digital Encryption Standard)
    - Permute each 8-bit sub-block of a 64-bit block
    - Jumble the entire block (using XORs or rotations)

![[Secure Sockets Layer 2022-12-05 09.44.57.excalidraw]]