---
course: "cpsc317"
module: "m1"
lecture: 3
---

## Protocol vs Interface
- Interface
- Protocol: series of actions


## Finite State Machines
![[Drawing 2022-09-14 09.07.00.excalidraw]]


## Communicating State Machines
![[Pasted image 20220914091305.png|700]]


## Where to put shared information and functionality?
- Across networks
    - Use of different types of networks (WiFi vs Ethernet vs Bluetooth)
    - Distributed management of these networks
- Across applications
    - Information on different applications
- Performance


## Layering
![[Pasted image 20220914091650.png|1000]]
- Layers: each layer implements a service
    - via its own internal-layer actions
    - relying on services provided by layer below

Decoupled -- changes in gate procedure doesn't affect the rest of the system

![[Drawing 2022-09-14 09.19.16.excalidraw]]


## Five-Layer Internet Reference Model
![[Pasted image 20220914092604.png|700]]


## Internet Protocol Stack
- application: supporting network  applications  
    - FTP, SMTP, DNS  
- transport: host-host data transfer
    - TCP, UDP  
- network: routing of datagrams from  source to destination  
    - IP, routing protocols  
- link: data transfer between  neighboring network elements  
    - PPP, Ethernet  
- physical: bits “on the wire”

![[Pasted image 20220914092820.png|200]]


## Protocol Layering and Data
- Each layer takes data from above and adds header info to create new data unit
- Passes new data unit to layer below

![[Pasted image 20220914093146.png|600]]


## Telcos versus Internet
- Telcos: Smart system, dumb end-stations
- Internet: Dumb system, smart end-stations


## End to end argument
- Can't implement security reliably => implement it at the end stations
- Advantages to E2E:
    - Keep it simple
        - Argues against low-level function implementation
        - Layers provide a simple service, not a lot of state
        - Avoid complex operations that can be handled with simpler logic at application layer
        - Allows for innovation at the ends


## Fate Sharing
- Engineering design philosophy where related parts of a system **fails together or not at all**
- For the internet, 2 endpoints should be *yoked* together (DOES NOT MEAN ENTIRE INTERNET NEED TO GO DOWN)