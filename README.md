## lec 1 What is Discrete Math?
- Discrete math is "sophisticated version of kindergartner math", just counting, arithmetic, connecting the dots,and coloring maps etc
- combinatorics, number theory, and graph theory

## lec 2 Basic Concepts of Combinatorics
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

## lec 3 12-fold way of combinatorics
- 12 different versions of the question “How many ways can we place x pieces of candy  into b bags?”
- The answer depends on whether the objects are distinguishable or identical, whether the bags are distinguishable or identical, and whether the bags can hold any number of objects, can hold at most 1 object, or must have at least 1 object.

## lec 4 Pascal's Triangle and Binomial Theorem
- French mathematician Blaise Pascal discovered Pascal's triangle in 1654 for *Problem of Points*
- Players A and B in a fair game of chance. Each game worth 1 point and whoever reaches n points wins.
- for n>=0, the nth row of Pascal's triangle is (n choose 0) (n choose 1), ..., (n choose n)
- For 0 < k < n, we have (n choose k) = (n-1 choose k) + (n-1 choose k-1): **prove it combinatorially, (n choose k) is the number of size-k committees from a class of n students, the number of committees that do not use student n is (n-1 choose k), the number of committes that must include student n is (n-1 choose k-1), think of student n as a new student on top of existing n-1 partitions**
- **Combinatorial proof for Sum(n choose k) = 2^n: From a class of n students, how many ways can I create a committee of any size?** On the one hand, since a committee can have any size from 0 to n, we get the sum. On the other hand, to create a committee, we can decide, student by student, if they are in or out of the committee, which can be done 2n ways.
- **Binomial Theorem: (x+y)^n = Sum((n choose k)x^k y^n-k)**
- Sierpinski's Triangle for where the odd numbers are located
- notice that from the score 9-8, the match can last at most 2 more games. Let us insist that they play 2 games (even if A wins the first game) (allowing for the possibility  that some player may end up with more than 10 points). A wins the game in 3 out of the 4 scenarios

## lec 5 Advanced Combinatorics: Multi-choosing
- For any subset/combination, you can create k! different ways of permutations, so there are k! times as many permutations without repetition as combinations
- If you allow repetition of elements, 2 Vanilla ice cream and 1 Strawberry ice cream, there can be 3 sequences: VVA, VAV, AVV, not k!(6)
- **Q: From 31 flavors, how many triple combinations are possible (order not important) with repetition allowed? We can break the question into three scenarios, How many uses 3 flavors (31 choose 3)? How many uses 2 flavors? How many uses 1 flavors (31 choose 1)?**
- **How many use 2 flavors? After you choose two flavors (31 choose 2), for each way, you need to choose if it two chocolate one vanilla, or two vanilla one chocolate. So (31 choose 2) x 2**
- **Multichoosing: ((n choose k)) => (n multi-choose k) has two sets of parenthesis: it is the number of ways to choose k objects from a set of n objects where order is not important, but repetition is allowed**
- (3 multi-choose 2) => (3 flavors {1,2,3}, 2 scoops) => 11, 12, 13, 22, 23
- (2 multi-choose 3) => (2 flavors {1,2}, 3 scoops) => all of them flavor 1, two of them flavor 1, one of them flavor 1, or none of them flavor 1 => 111, 112, 122, 222
- (3 multi-choose 10) => (3 flavors {1,2,3}, 10 scoops) => **the number of ways to arrange 10 stars and 2 bars**
- `****|**|****` = 4 scoops of flavor 1, 2 scoops of of flavor 2, 4 scoops of flavor 3, this corresponds to the multisubset {1,1,1,1,2,2,3,3,3,3}
- `**|********|`, 2 scoops of flavor 1, 8 scoops of flavor 2, and 0 scoops of flavor 3, multisubset {1,1,2,2,2,2,2,2,2,2}
- (3 multi-choose 10) = 12 positions choose two locations for bars = (12 choose 2)
- (n multi-choose k), n flavors, k scoops, you need **k stars** and **n-1 bars**
- If each ninja must get at least 1 candy, you start by giving each ninja 1 candy in the beginning (1 way), the problem reduces to *distribute the k-n candies to n ninjas*
- Another way to combinatorially prove each ninja must get at least one candy is: `*_*_*_*_*_*_*` and you put the bars in the slots, so (k-1 choose n-1)
- the "stars" and "bars" approach is much harder when the candies are *distinct*... need to use inclusion exclusion
