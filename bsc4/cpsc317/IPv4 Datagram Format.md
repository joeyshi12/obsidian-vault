---
module: "M2"
topic: "IPv4 Datagram Format"
chapter: "4.3.1"
---

![[Pasted image 20220912075624.png]]

- **Datagram**: Network-layer packet
- **Version Number**: IP protocol version of datagram. Determines datagram format
- **Header length**: IPv4 datagram has variable number of options => header length locates payload
- **Type of service**: Distinguish types of IP datagrams (eg, real-time telephone vs non-real-time FTP)
- **Datagram length**: Size of header+data
- **Identifier, flags, fragmentation offset**: Related to IP fragmentation, discuss later
- **Time-to-live**: Router must drop datagram if TTL reaches 0
- **Protocol**: Specify TCP, UDP, or other
- **Header checksum**: Detect bit errors in IP datagram
- **Source and destination IP addresses**: Source inserts these fields on datagram creation. Source determines the destination address via DNS lookup
- **Options**: Additional fields, meant to be rarely used
- **Data (payload)**: data to be delivered