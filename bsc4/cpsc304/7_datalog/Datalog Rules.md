---
course: CPSC304
title: Datalog Rules
topic: Datalog
tags: Datalog
module: 7
date: [[2022-11-22]]
---

Table schemas:
- Product(pid, name, price, category, make-cid)
- Purchase(buyer-sin, seller-sin, store, pid)
- Company(cid, name, stock price, country)
- Person(sin, name, phone, number, city)

## Projection
Find the names of all products
```
Ans(N):- Product(P, N, PR, C, M)
```

## Selection
Find all purchases with the same buyer and seller
- RA: $\sigma_{\text{buyer-sin} = \text{seller-sin}}(\text{Purchase})$
- Datalog: `Ans(B, B, S, P) :- Purchase(B, B, S, P)`

## Anonymous Variables
Each _ means a fresh, new variable
```
Ans4(N) :- Person(S, N, _, _), Puchase(S, _, 'Gizmo Store', _)
```

## Union
Find the names of people that are either buyers or sellers
```
A(N) :- Person(S, N, _, _), Purchase(S, _, _, _)
A(N) :- Person(S, N, _, _), Purchase(_, S, _, _)
```

## Negation
Find people who live in Vancouver but have not bought anything at “The Bay”
```
VancouverAntiBay(buyer,seller,product,store) :-
Person(B, name, phone,“Vancouver”),
Purchase(buyer, seller, store, product),
not Purchase(buyer, seller, “The Bay”, product)
```
The NOT in Datalog means “there exists no”

## Rule Safety
Sin, Ph, City are unsafe
```
Ans(Sin) :- NOT Person(Sin, 'Joe', Ph, City)
```

## Division
- Cust(cid, cname, rating, salary)
- Order(iid, cid, day, qty)

Find items that are ordered by every customer
- $\pi_{iid, cid}(Order)/\pi_{cid}(Cust)$

Datalog:
```
Witness(I,C) :- Order(I,C,_,_)  
Bad(I) :- Cust(_,C,_,_), Order(I,_,_,_), NOT Witness(I,C)
Good(I) :- Order(I,C, _, _), NOT Bad(I)
```
- Witness is all items that have been ordered
- Bad finds all items that have not been ordered
- Good: finds all items that have not been not ordered by some customer