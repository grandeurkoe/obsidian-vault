# What is Big O?

Another term for Big O is Asymptotic Analysis.

Good code is readable and scalable(speed or time complexity + memory or space complexity).

Big O helps us to ascertain the scalability of a executable code.

Big O notation is used to figure out how long it takes for an algorithm to execute.

Big O notation describes the worst-case scenario or the maximum amount of resources (time or space) an algorithm might use for a given input size. It provides an upper limit on the growth rate, which means the actual performance of the algorithm will not exceed the described complexity.

Checkout the Big O complexity graph [here](Big%20O%20-%20Know%20Thy%20Complexities.pdf).
## [O(1)](Big%20O%20-%20Cheat%20Sheet.pdf)

For a single input the Big O is O(1) and if the number of inputs is 10,000 the Big O is O(10000).  

This is also known as constant time. Here irrespective of the number of inputs the number of operation will remain constant.  

The algorithm's performance is constant, regardless of the input size.

This has no loops.

O(1) is of good complexity

## [O(log n)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is also known as logarithmic time.

The algorithm's performance grows logarithmically with the size of the input.

Usually searching algorithms have log n if they are sorted (Binary Search).

O(log n) is of good complexity.

## [O(n)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is also known as linear time. Here n is an arbitrary variable. So, as the number of inputs increase the number of operations also increase linearly.  

O(n) is the most common Big O notation you will find.

The performance is directly proportional to the size of the input.

Common in algorithms with a `for` or a `while` loop.

O(n) is of fair complexity.

## [O(n log n)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is also known as linearithmic time.

Common in efficient sorting algorithms like merge sort and heap sort.

O(n log n) is of bad time complexity.

## [O(n^2)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is also known as quadratic time. Here the number the operation will be square of the number of inputs.  

Common in algorithms with a nested loop.

The performance is proportional to the square of the size of the input.

O(n^2) is of horrible complexity.

## [O (2^n)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is also known as exponential time.

Common in recursive algorithm that solve a problem of size N.

The performance doubles with each additional element in the input.

O(2^n) is of horrible complexity.

## [O(n!)](Big%20O%20-%20Cheat%20Sheet.pdf)

This is known as factorial time. Here the number of nested loops increase for every input.  

The performance grows factorially with the size of the input.

O(n!) is of horrible complexity. If you're doing this you've fucked up.