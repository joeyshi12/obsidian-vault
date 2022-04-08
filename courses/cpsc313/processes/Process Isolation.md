    ---
course: "cpsc313"
title: "Process Isolation"
---

- Programs run in different **processes**
- Each process has its own **address space**
- Address spaces provide **process isolation**
- Process isolation means:
    - Anything one process does should not affect what another process does, unless the processes agree (e.g., set up a communication channel)
    - Each process behaves as if it controls the entire machine's resources

The operating system is a layer between processes and hardware; processes should not access hardware directly
```
Processes: P0, P1, P2

--- Protection Boundary ---

Operating system

--- Hardware/software interface

Hardware
```

Processes runs in *user mode*
The operating system runs in *kernel mode*

The core sends a virtual address, mode, and access type to the memory management unit (MMU) and
either returns a physical address or faults (if not permitted)