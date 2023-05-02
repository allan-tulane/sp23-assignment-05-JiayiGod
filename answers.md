# CMPS 2200 Assignment 5
## Answers

**Name:**______Jiayi Xu___________________


Place all written answers from `assignment-05.md` here for easier grading.





- **1a.**

To find the optimal solution, we set greedy criterion as: each time we try to make change with largest denomination not exceeding the amount to be exchanged as possible. Since, denominations are 2's power, we can easily find the solution for greedy criterion by taking logarithm operation to our amount of money and round down.And we repeat our criterion until entire amount is exchanged. For example, if we have 70 dollars, we will choose denomination of 2^6=64 first. Then, with 6 dollars left, we choose denomination of 2^2=4. Finally, with 2 dollars left, we choose denomination of 2^1=2. Totally, we use 3 coins.

This algorithm is optimal because the available coin denominations are in powers of 2, which ensures that choosing the largest possible denomination first is always the minimum possible number of coins needed to represent the amount to be exchanged. Since if we choose several smaller coins, we can always use less larger coins instead, as all coins are 2's power.

- **1b.**

The work of the algorithm is $O(\log n)$, where n is total amount of money, since it involves at most $\log n$ iterations of the loop that selects the largest possible denomination of coin. The span of the algorithm is also $O(\log n)$ since each iteration of the loop can't be performed independently.


- **2a.**

Here is a counterexample: if the denominations is {1,6,7} and we have 12 dollars, with greedy algorithm introduced in last question, we will choose 7 first and then 5 coins of 1. So, we totally use 6 coins. However, we can just choose 2 coins of 6, which is a better solution.

The reason why the greedy algorithm does not work optimally in Fortuito is that the optimal solution may require choosing a smaller denomination over a larger one in some cases. This violates the greedy choice property, which states that the locally optimal choice at each step should lead to a globally optimal solution.


- **2b.**

Let $C(i)$ be minimum number of coins needed and $i$ be the total amount of money. Let $D_k$ be the k-th denomination. Then, the optimal substructure would be:

$C(i)=min(C(i-D_k)+1)$ , where $0<=k<=n$, $i>=D_k$, $C(0)=0$, and $C(i)=-1$ when it can't be exchanged

The optimal substructure means that we consider all possible denominations $D_k$ that are less than or equal to $i$, and recursively compute the minimum number of coins needed to make change for $i-D_k$ dollars, plus one coin of denomination $D_k$.

We can use bottom-up memoization for the solution. Then, the work is $O(nk)$, where $n$ is the total amount of money and $k$ is total types of denominations, since we need to compute $O(n)$ different nodes in DAG and each node requires $O(k)$ work due to iteration of k denominations. The Span is $O(n)$, which is the longest path in DAG.

- **3a.**

see in main.py





- **3b.**

see in main.py




- **3c.**

see in main.py

