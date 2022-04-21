# Hazards
- [[Data Hazards]]
- [[Control Hazards]]

## Control Dependency
- Caused by jump instructions depending on condition codes

## Cycle Counting
- Register operations that depend on other register operations = 3 instruction gap
	- With forwarding, there is no gap
- Memory operations need 3 instruction gap
	- With mrmovq or rmmovq, we need 1 instruction gap with ALU / register dependency
- Conditional jumps need 2 instruction gap even with forwarding
	- With prediction, 2 when wrong; otherwise none 