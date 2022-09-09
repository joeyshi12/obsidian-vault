## Branch Prediction
- **No stalling occurs with control hazards when using branch prediction**
- Either assume always jump or never jump or a combination
	- Logic block for this is called the predictor
- In the jump instruction, we know whether the branch prediction was correct near the end of the execute stage (we can check CC here)
	- On mispredictions, we do no worse than no prediction
    - On mispredictions, we squash 2 instructions in the pipeline (NO STALLS)
- A good branch predictor improves **CPI** (cycles per instruction)

![[Pasted image 20220202144411.png]]

## Unconditional Jumps
- Feed `f_valC` into `nextPC`
- No stalls
- *Same with call instruction*

## Ret
- Always require stalling 3 cycles