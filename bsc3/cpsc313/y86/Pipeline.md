## Pipeline
- Pros
	- Uses hardware more efficiently by working in parallel
	- A **collection** of instructions completes faster
- Cons
	- Individual instruction takes longer because pipeline registers add latency
	- If some phases take longer than others, short phases will wait on longer phases
	- Sometimes you didn't have the right information at the right time

![[Pasted image 20220125163645.png|700]]


## Terminology
- **Latency**: end to end time to complete execution of a single instruction
- **Retirement latency**: time between the completion of one instruction and the completion of the next instruction
- **Throughput**: rate at which instructions complete (GIPS: 10^9 instructions per second)
    - `output GIPS = 1000 / (retirement latency in ps)`


## Latency Example
- 5 registers + 5 stages for pipeline implementation
- Each stage takes 200ps, each registers adds 20ps
- Unpipelined implementation: 1020ps for 1 instruction
- Pipelined implementation: 1100ps for 1 instruction
- Throughput = 1000 / (retirement rate for one instruction in ps)

![[Pasted image 20220126141840.png]]