## Data Dependency
- Caused by updates in memory (registers + main memory) not finishing before another instruction reads from that memory
- Require 3 nops for update instruction to write back to register before next instruction reads from register
- This can be mostly solved with **data forwarding**
