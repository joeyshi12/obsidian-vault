![[Pasted image 20220207140344.png|500]]

 ![[Pasted image 20220207140437.png|500]]
 
 ![[Pasted image 20220207140617.png|500]] 


## Throughput
- Affected by:
    - Clock speed
        - Increase by deepening/extending the pipeline
            - Increases CPI
    - CPI
        - Optimized with
            - Instruction level parallelism
                - Compiler
                - Workload
            -  Forwarding (for data hazards), branch prediction (for control hazards)
            

## Super Scalar
- How to get $CPI < 1$
![[Drawing 2022-02-07 14.20.04.excalidraw]]


## Multicore
![[Drawing 2022-02-07 14.23.12.excalidraw|200]]


## Hyper Threading
- Still $CPI = 1/(\text{number of cores})$
![[Drawing 2022-02-07 14.29.02.excalidraw]]


## SIMD
- SISD: 1 thread
- MIMD: 7 thread

|                    |        | Data Stream |       |
| ------------------ | ------ | ----------- | ----- |
|                    |        | Single      | Multi |
| Instruction Stream | Single | SISD        | SIMD  |
|                    | Multi  | MISD        | MIMD  |

