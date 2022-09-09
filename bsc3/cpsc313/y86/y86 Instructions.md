#  Instructions
- [[y86 Move Instructions]]
- [[y86 Diagrams]]
- [[y86 Jump Instructions]]
- [[Y86_instruction_set_cheat_sheet.pdf]]

```
rrmovq: R[rB] <- R[rA]

irmovq: R[rB] <- valC

mrmovq: R[rA] <- M8[R[rB] + valC]

rmmovq: M8[R[rB] + valC] <- R[rA]

<op>q: R[rB] <- R[rB] <fun> R[rA]

pushq: R[rsp] <- R[rsp] - 8
       M8[R[rsp]] <- R[rA]

popq: R[rA] <- M8[R[rsp]]
      R[rsp] <- R[rsp] + 8

call: R[rsp] <- R[rsp] - 8
      M8[R[rsp]] <- PC
      PC <- Dest

ret: PC <- M8[R[rsp]]
     R[rsp] <- R[rsp] + 8   
````
