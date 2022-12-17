SuperRentInfo(I, N, E, S, ED, C, CN, B, T, P)  
1) I → N, E  
2) CN → I  
3) B → C  
4) CN, B → T  
5) CN, B, T → S, ED  
6) P → I, CN

Update anomaly:
- Updating city in rows 1 requires us to update city in row 3
Insertion anomaly:
- Inserting a new row with customerName Jeff requires us to insert additional columns.
Deletion anomaly:
- If we remove row 2, we lose the fact that Richmond is in Vancouver.

SI1(I, N, E, S, C, CN, B)
SI2(C, P, T, ED, CN, B)

$SI1 \cap SI2 = \{C, CN, B\}$
$\{C, CN, B\}^{+} = \{C, CN, B, I, T, S, ED, N, E\}$
$SI1\cap SI2 \to SI1$
Hence, the decomposition is lossless

$I \to N, E$
$CN \to I$
$B \to C$
$CN, B \to T$
$CN, B, T \to S, ED$
$P \to I, CN$

Left:
- B, P
Middle:
- I, CN, T
Right:
- N, E, C, S, ED

$\{B, P\}^{+} = \{B, P, C, I, CN, N, E, T, S, ED\}$
Any key must include B, P and {B, P} is a superkey,
so {B, P} is the only key.

