## lec 1 What is Discrete Math?
- Discrete math is "sophisticated version of kindergartner math", just counting, arithmetic, connecting the dots,and coloring maps etc
- combinatorics, number theory, and graph theory

## lec2 Basic Concepts of Combinatorics
- combinatorics is the math of **counting**
- How many ways can we pick 5 numbers from 1 to 10? This question depends on 2 factors: **Does order matter?** and **Can you repeat numbers**
- **Order matters + Allow repeat: Sequence (like password and zipcodes)**
- **Order matters + No repeat: Arrangement/Permutation (like horse race top 3 winner)** N! is the number of ways to arrange N different objects (order matters)
- **Order does not matter + No repeat: Subset/Combination (n choose k, Binomial Coefficient)** (n k) is the number of ways to choose k objects from n *distinct* objects, order not important and no repetition
- A deck of 52 cards: 1-13 with 4 suits (spades, hearts, diamonds, clubs)
- there are (52 choose 5) ways to create a 5-card poker hand
- **(n choose k) is officially defined as the number of subsets of set {1,2,...,n} with size k** = n!/(k!(n-k)!)
-(n choose 0) == 1, because there is 1 way to pick 0 objects out of n (or 1 size-0 subset of {1,...,n})
-  How many are full houses (3 of one value and 2 of another)? There are 13 choices for which card value is tripled, then 12 choices for which card value is doubled, then (4 choose 3) ways to assign suits to the tripled value, then (4 choose 2) ways to assign suits to the doubled value. Multiplying these, we get 13 × 12 × 4 × 6 = 3744.
- **NOTE: (52 choose x) includes same number different suites, but (13 choose x) does not**
- How many hands have exactly 1 pair? There are 13 choices for the paired value, then (4 choose 2) = 6 ways to decide which 2 of the 4 possible cards will make up the pair, then (12 choose 3) = 220 ways to pick the 3 other values. Then we assign suits for those cards, in  `4*4*4` = 64 ways. Multiplying gives us 1,098,240 ways to be dealt 1 pair
- How many hands have the same suit (flush)? There are 4 choices for suits, and (13 choose 5) ways to get the value. So 4 x (13 choose 5) = 5148
- **Sequences: order matters and repetition is allowed: n^k ways**
- **Arrangements: order matters and repetition is NOT allowed: n!/(n-k)! ways**
- **Subsets/Combinations: order doest NOT matter and repetition is NOT allowed: (n choose k) = n!/(k!(n-k)!)**
- When **you can repeat items** and **order does NOT matter** these are **multisubsets**

## lec3 12-fold way of combinatorics
- 12 different versions of the question “How many ways can we place x pieces of candy  into b bags?”
- The answer depends on whether the objects are distinguishable or identical, whether the bags are distinguishable or identical, and whether the bags can hold any number of objects, can hold at most 1 object, or must have at least 1 object.
