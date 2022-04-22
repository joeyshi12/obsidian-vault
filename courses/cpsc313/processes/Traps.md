---
course: "cpsc313"
title: "Traps"
---

## Traps
- On boot, the OS initializes a table indexed by trap number that contains a pointer to the **trap handler** to be executed
    - 1 = syscall
    - 2 = timer interrupt
    - 3 = disk interrupt
    - 4 = interprocessor interrupt

![[Pasted image 20220421213508.png|700]]

## Types of Traps
- System Call
- Exception
- Interrupt

## X86 Trap Handling
- **Interrupt Descriptor registers (IDT)** contains **gates**
- **Gates** provide access from lower priveleged segments to higher priveledged segments