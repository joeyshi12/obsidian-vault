## Data Hazard
- An instruction reads data that an earlier, not-yet-retired instruction wrote
- Require 3 nops for update instruction to write back to register before next instruction reads from register
- This can be mostly solved with **data forwarding**

![[y86 Implementation Diagram.png]]