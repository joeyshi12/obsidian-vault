---
course: CPSC304
title: Problems
topic:
tags:
module: 
date: [[2022-11-22]]
---

Table schemas:
- Product(pid, name, price, category, make-cid)
- Purchase(buyer-sin, seller-sin, store, pid)
- Company(cid, name, stock price, country)
- Person(sin, name, phone, number, city)

Find the countries of all the companies
```
Ans1(C) :- Company(I, N, P, C)
```

Find the purchases of products with pid = 42
- RA: $\sigma_{\text{pid} = 42}(\text{Purchase})$
- Datalog:  `ANS(B, S, St, 42) :- Purchase(B, S, St, 42)`

Find all English companies with stock price less than $100
```
Ans2(I, N, P, 'England') :- Company(I, N, P, 'England'), P < 100
```

Find the names of all products
```
Ans3(N) :- Product(_, N, _, _, _)
```

Find names of people who have bought products from themselves
```
Ans4(N) :- Purchase(S, S, _, _), Person(S, N, _, _)
```

Find SINs of people who bought products in the "computers" category.
```
Ans5(S) :- Purchase(S, _, _, P), Product(P, _, _, 'computers', _)
```

Find the SIN of people who bought Canadian products
```
Ans6(S) :- Purchase(S, _, _, P), Product(P, _, _, _, C), Company(C, _, _, 'Canada')
```

Find names of people who bought products sold by a Canadian company that cost under 50
```
Ans7(N) :- Person(S, N, _, _), Purchase(S, _, _, P), Product(P, _, Pr, _, C), Company(C, _, _, 'Canada'), Pr < 50
```

Find SINs of people who bought stuff from a person named Joe or bought products from a company whose stock price is more than $50
```
Ans8(S) :- Purchase(S, S2, _, _), Person(S2, 'Joe', _, _)
Ans8(S) :- Purchase(S, _, _, P), Product(P, _, _, _, C), Company(C, _, SP, _), SP > 50
```

Find the SINs of people who are not named 'Joe'
```
Ans(S) :- Person(S, N, P, C), NOT Person(S, 'Joe', P, C)
```

Find 