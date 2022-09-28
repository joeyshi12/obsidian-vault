## Packet-switching
- Divide the data into packets to send
- **Independently** route packets from source to destination
- On demand
    - Message is divided and forwarded to dest
    - Routers independently decide how to forward packets
    - Connection-less communication

## Circuit-switching
- Reservations
    - Set up a circuit, where a circuit is a dedicated path from source to dest
    - Reserve a path along which to send the data, no need for packets
    - Connection-oriented communication, like a telephone call

## Comparison
- Packet-switching is good for sharing, robust, but no guarantees on service
- Circuit-switching guantees on service, but no sharing, channels can be idle