## Hardware
- Determining which memory location to write an evicted cache line to - transfer back to SW when returned back to application
- Determining how long the processor stalls on data hazards - y86
- Determining the address to jump to using branch prediction - predictor component in y86
- Transfer control from user to OS
- On x86, load entry from page table to TLB/handling TLB fault


## Software
- Cause [[Traps]]
- Use ALU
- Invalidate something in cache
- Read value from CPU register
- **Kernel-specific**
    - Setting address in trap handler table - OS
    - Determining which disk block to allocate when a file needs to be extended (FREE SPACE MANAGEMENT)
    - Interact with hardware directly
    - Disable interrupts
    - Power-off computer
    - Update page table entry
    - Allocate and initialize page that faulted