---
course: "cpsc313"
tutorial: 10
---

## Processes and Process Isolation
1. Transferring control from a user process to the OS
    1. Hardware
2. Creating an address space for a new process
    1. Software
3. On x86: loading an entry from a page table into the TLB
    1. Hardware (done by MMU) (modifying TLB done by hardware)
4. On the x86: handling a TLB fault
    1. Same as 3, hardware
5. Handling a page fault
    1. 