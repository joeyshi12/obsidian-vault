# Hazards
- [[Data Hazards]]
- [[Control Hazards]]

## Control Dependency
- Caused by jump instructions depending on condition codes

## Stalling
- ALU operations: 3 stalls
- MOV operations: 3 stalls
- RET: 3 stalls
- POP: 3 stalls
- JMP: 0 stalls
- CALL: 0 stalls
- JXX: 2 stalls

## Forwarding
- **Implementation**
    - Forwards e_valE into the register file
    - Forward M_valE to the new logic
    - Forward e_valE to the beginning of Execute
- y86 uses **backward taken, forward not taken**
- Worst case, we squash 2 cycles, which is the same amount wasted as forwarding (**Squash != Stall**)

![[y86 Implementation Diagram.png]]