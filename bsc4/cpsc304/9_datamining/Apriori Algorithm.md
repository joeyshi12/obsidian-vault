## Apriori Algorithm
1. C_{k+1} is the candidate itemsets of the previous frequent item sets F_{k}
2. Let F_{k+1} be the frequent item sets of C_{k+1}
Note: Minimum support: threshold of support level

## Apriori Exercise

![[Pasted image 20221206160314.png|500]]

Let minimum support = 50%
Q: Find all frequent item sets
- **Note**: an item set is a possible frequent item set if every subset is a frequent item set

**Item sets of size 1**
- {apple} = 2/4
- {corn} = 4/4
- {dates} = 3/4
- ~~{rice} = 1/4~~ not frequent
- {tuna} = 3/4

**Item sets of size 2**
- Note support must be above 50%
- {apple, corn}
- {apple, dates}
- {corn, dates}
- {corn, tuna}
- {dates, tuna}

**Item sets of size 3**
- {apple, corn, dates} = 2/4
- {corn, dates, tuna} = 2/4

**Item set of size 4**
- Nothing

Let minimum support be 3/7; find frequent itemsets

Size 1:
- {cake} = 3/7
- {jam} = 6/7
- {rolls} = 4/7
- {tea} = 5/7
- $|C_1| = 4$
- $|F_1| = 4$

Size 2:
- {cake, jam} = 3/7
- ~~{cake, rolls} = 1/7~~
- ~~{cake, tea} = 2/7~~
- {jam, rolls} = 3/7
- {jam, tea} = 4/7
- {rolls, tea}  = 3/7
- $|C_2| = 6$
- $|F_2| = 4$

Size 3:
- ~~{jam rolls, tea} = 2/7~~
- $|C_3| = 1$
- $|F_3| = 0$