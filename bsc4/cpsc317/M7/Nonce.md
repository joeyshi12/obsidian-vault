## Playback Attack
- Trudy records a packet from Alice and later plays it back to Bob
    - Encryption does not help here
- Solution: **nonce** (number used once)
    - Let $K_{A-B}$ be a shared key
    - Bob sends Alice an encrypted nonce $K_{A-B}(R)$ and Alice authenticates herself by decrypting $R$ with $K_{A-B}$.
