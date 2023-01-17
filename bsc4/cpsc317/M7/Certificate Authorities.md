# Certificate Authorities
- When Alice wants to communicate with Bob using public key cryptography, she needs to verify that the public key is indeed from Bob
- Certificate authorities are hosts whose job is to bind public keys to entities/validate identity and issue certificates
    - Certificates contain public key and globally unique ID info
- Every host keeps track of trusted authorities public keys.
- Alice may trust a root authority and Bob might trust Alice. This creates a **chain of trust**.
- To create a certificate, the certifier includes a digital signature (hash of Alice's info + public key) and sign with the certifier's private key