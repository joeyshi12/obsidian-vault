---
course: "cpsc317"
module: "m1"
lecture: 1
---

1. Design
2. Protocols, layering, encapsulation
3. Design of the Internet
4. End-end, fate sharing, isolation

## Internet: the nuts and bolts

- End-stations / end-systems
    - Endpoints of an ip-address
    - eg, PCs, servers, smart phones, **running netowkr apps**
- Communication links
    - Varying **bandwidth/latency**
    - eg, fiber, copper, radio, satellite
- Routers
    - Forward packets (chunks of data)


![[Pasted image 20220909091355.png|400]]


## Communication

Necessary conditions:
- A communication **medium**: modulation of some medium (air)
- Source and destination
- Protocol: shared information (language)
- Message: information from *source to dest* on a *medium* using a *protocol*


## Desired properties of large-scale systems

- Heterogeneous
    - Different rules and techniques
    - Different physical characteristics
    - Openness
- Over large and varied geographical regions
- Between different administrative entities
- Dependable and safe

**Examples**:
- Telephone
- Mail
- Railway (not global; local)
- Airline (global scale)
- Shipping
- Roadways

**Challenges**
- Communication
- Support many apps + networks
- Scalability
- Etc...


## Designing the Internet

**Goal**: Effective technique for multiplexed utilization of existing interconnected networks
- Multiplexed = Shared
- Security was not apart of the goals initially

**Packet-switching**
- Divide data into packets to send
- **Independently** route packets from source to destination
- Go out on any available link

Packet = units of data
Channel = physical resource for transferring a stream of data
InterNetwork: a collection of channels

**Circuits provide guaranteed performance**
- Packet switching: good for sharing, robust but no guarantees on service
- Circuit switching: guarantees on service, but no sharing, channels can be idle