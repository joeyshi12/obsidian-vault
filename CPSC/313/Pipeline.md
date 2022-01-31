# Pipeline
- Pros
	- Uses hardware more efficiently by working in parallel
	- A **collection** of instructions completes faster
- Cons
	- Individual instruction takes longer because pipeline registers add latency
	- If some phases take longer than others, short phases will wait on longer phases
	- Sometimes you didn't have the right information at the right time

[[Pasted image 20220125163645.png]]

## Pipeline Registers
- Holds onto state at each stage

[[Pasted image 20220125170729.png]]

[[Pasted image 20220125171026.png]]

## Terminology
- Stage / Phase
- Throughput: rate at which instructions complete (GIPS: 10^9 instructions per second)

## Latency
- 5 registers + 5 stages for pipeline implementation
- Each stage takes 200ps, each registers adds 20ps
- Unpipelined implementation: 1020ps for 1 instruction
- Pipelined implementation: 1100ps for 1 instruction
- Throughput for pipeline: 1000

[[Pasted image 20220126141840.png]]