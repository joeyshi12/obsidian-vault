- [ ] ---
module: "M2"
topic: "IPv4 Datagram Format"
chapter: "4.3.1"
---

![[Pasted image 20220912075624.png]]

| Term                                        | Definition                                                                                                 |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Datagram**                                | Network-layer packet                                                                                       |
| **Version Number**                          | IP protocol version of datagram. Determines datagram format                                                |
| **Header length**                           | IPv4 datagram has variable number of options => header length locates payload                              |
| **Type of service**                         | Distinguish types of IP datagrams (eg, real-time telephone vs non-real-time FTP)                           |
| **Datagram length**                         | Size of header+data                                                                                        |
| **Identifier, flags, fragmentation offset** | Related to IP fragmentation, discuss later                                                                 |
| **Time-to-live**                            | Router must drop datagram if TTL reaches 0                                                                 |
| **Protocol**                                | Specify TCP, UDP, or other                                                                                 |
| **Header checksum**                         | Detect bit errors in IP datagram                                                                           |
| **Source and destination IP addresses**     | Source inserts these fields on datagram creation. Source determines the destination address via DNS lookup |
| **Options**                                 | Additional fields, meant to be rarely used                                                                 |
| **Data (payload)**                          | data to be delivered                                                                                       |

| Type   | Size    |
| ------ | ------- |
| Word   | 32 bits |
| Byte   | 8 bits  |
| Nibble | 4 bits  |

## Reading the Datagram
- Numbers for network ar- e represented in BIG ENDIAN BINARY
- Where does the header end?
    - Header length in 1 word
    - Typically 20 bytes
- Where does the packet end?
    - Length field is the entire size of the datagram in bytes = 16 bits
- https://www.rfc-editor.org/rfc/rfc3514