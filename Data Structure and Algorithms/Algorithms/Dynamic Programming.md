# Dynamic Programming

Dynamic Programming is an optimization technique that makes use of caches.

Dynamic Programming is a way to solve problems by breaking it down into a collection of subproblems. Then you solve each of these subproblems and save the results in a cache i.e. hash table, so that you can access these results when a similar subproblems appears.

![[Pasted image 20231010175816.png|500]]

Dynamic programming is combining divide & conquer and memoization.

How to figure out if a problem requires dynamic programming -

![[Pasted image 20231010175845.png|500]]

With Dynamic programming, we can reduce the time complexity from O(2^n) to O(n) in fibonacci.

The drawback of dynamic programming is that space complexity increases(hash table).

## Memoization or Caching

Caching is the process of storing values so that you can access them later on.

Caching important values can speed up the program.

### Implementation

1. Fibonacci Dynamic Bottom Up - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/fibonacci-dynamic-bottom-up)
2. Fibonacci Dynamic Programming - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/fibonacci-dynamic-programming)
3. Memoization Closure - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/memoization-closure)
4. Memoization - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/memoization)