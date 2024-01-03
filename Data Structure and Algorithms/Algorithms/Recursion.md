# Recursion

Recursion is not an algorithm but like more of a concept that we'll use throughout this section.

Recursion is defining something in terms of itself.

Recursive function is a function that refers to itself within the function.

The biggest drawback of recursion is stack overflow.

A recursive function looks something like this -

```python
def my_function():
	print("Hi!")
my_function()
```

The `my_function()` call within the function definition of `my_function()` will keep calling my_function. This is what it means for a function to be recursive.

When we make a call to `my_function()`,  the compiler will keep printing "Hi!" on the console repeatedly until it crashes.

Each function call gets added to the call stack until the computer runs out of memory. This causes a stack overflow.

Stack overflow can be prevented by providing a base case.

A base case is the stopping point for a recursive function.

The three most important step of recursion is -

1. Identify the base case.
2. Identify the recursive case i.e., return my_function().
3. Get closer and closer and return when needed. Usually has two returns

## Recursive vs Iterative

Anything that can be implemented recursively can also be implemented iteratively.

Recursion makes your code much more readable.

Recursion also keeps your code DRY i.e., Don't Repeat Yourself.

However, it creates a large stack of function call that eats up a lot of memory.

Iterative functions are more efficient because they don't make a large stack of function calls.

Downside of iterative function is that they are not as readable.

Recursion is useful when we don't know how deep data structures are.

Recursion is useful in traversing the tree data structure.

Tail Call Optimization solves the issue of function call stack in recursive functions.

## When to use recursion?

Everytime you are using a tree or converting something into a tree, consider recursion.

In interviews, complex question can be solved by divide and conquer method that utilizes recursion.

1. Divided into a number of subproblems that are smaller instances of the same problem.
2. Each instance of the subproblem is identical in nature.
3. The solution of each subproblem can be combined to solve the problem at hand.

## Implementation

1. Fibonacci Sequence Iterative and Recursive - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/fibonacci-sequence-iterative-and-recursive)
2. Factorial Iterative and Recursive - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/find-factorial-iterative-and-recursive)
3. Recursion - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/recursion)
4. Reverse a String Iterative and Recursive - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/reverse-a-string-iterative-and-recursive)