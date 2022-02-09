# Hazards
## Data Dependency
- Caused by updates in memory (registers + main memory) not finishing before another instruction reads from that memory
- Require 3 nops for update instruction to write back to register before next instruction reads from register
- This can be mostly solved with **data forwarding**

## Control Dependency
- Caused by jump instructions depending on condition codes

## Branch Prediction
- **No stalling occurs with control hazards when using branch prediction**
- Either assume always jump or never jump or a combination
	- Logic block for this is called the predictor
- In the jump instruction, we know whether the branch prediction was correct near the end of the execute stage (we can check CC here)
	- On mispredictions, we do no worse than no prediction
- A good branch predictor improves **CPI** (cycles per instruction)

![[Pasted image 20220202144411.png]]

## Cycle Counting
- Register operations that depend on other register operations = 3 instruction gap
	- With forwarding, there is no gap
- Memory operations need 3 instruction gap
	- With mrmovq, we need 1 instruction gap with ALU / register dependency
- Conditional jumps need 2 instruction gap even with forwarding
	- With prediction, 2 when wrong; otherwise none 