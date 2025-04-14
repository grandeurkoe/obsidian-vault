### **Recursion**

Recursion is not an algorithm itself but rather a **concept** or technique that is frequently used to solve problems in computer science.

In simple terms, recursion is when **something is defined in terms of itself**.

A **recursive function** is a function that calls itself within its definition, enabling it to solve a problem by breaking it down into smaller instances of the same problem.

#### **Example of a Recursive Function:**

```python
def my_function():
    print("Hi!")
    my_function()  # Recursive call

my_function()
```

In this example, the `my_function()` keeps calling itself indefinitely, printing "Hi!" until the program runs out of memory, leading to a **stack overflow**.

---

### **Drawbacks of Recursion:**

The main drawback of recursion is **stack overflow**.

- When a recursive function keeps calling itself, each call gets added to the **call stack**.
    
- If the function keeps calling itself without stopping (or without a **base case**), the stack grows too large and eventually leads to a crash (stack overflow).
    

#### **Base Case in Recursion:**

A **base case** is the condition that stops the recursive calls. Without it, the recursion would continue indefinitely, leading to a stack overflow.

### **Three Key Steps in Recursion:**

1. **Identify the base case**: This defines the stopping point for recursion.
    
2. **Identify the recursive case**: This is the part where the function calls itself (e.g., `my_function()`).
    
3. **Get closer to the base case**: Each recursive call should reduce the problem size, bringing it closer to the base case.
    

---

### **Recursive vs Iterative**

- **Recursion** is elegant, often leading to **cleaner, more readable code**. It can also help in keeping code **DRY** (Don’t Repeat Yourself).
    
    - **Pros**:
        
        - Simplifies complex problems (e.g., tree traversal, divide and conquer).
            
        - Makes the code more readable and concise.
            
    - **Cons**:
        
        - **Memory Intensive**: Recursion uses a lot of memory due to the call stack.
            
        - **Potential Stack Overflow**: If the recursion depth is too high, it can result in a stack overflow.
            
- **Iteration**:
    
    - Iterative solutions don't build a large stack of function calls, making them **more memory-efficient**.
        
    - **Pros**:
        
        - More **memory efficient** because it doesn't rely on the function call stack.
            
        - Generally **faster** in terms of execution time for simple tasks.
            
    - **Cons**:
        
        - **Less readable** for problems naturally suited for recursion, such as tree traversal or divide and conquer.
            
        - Can lead to **repetition of code** (breaking the DRY principle).
            

---

### **When to Use Recursion?**

Consider using recursion in the following cases:

- **Tree Traversal**: Recursion is ideal for traversing tree-like data structures (e.g., binary trees, file systems).
    
- **Divide and Conquer**: When a problem can be divided into smaller subproblems of the same type (e.g., quicksort, mergesort).
    
- **Problem Subdividing**: When you can break the problem into multiple smaller, identical problems that can be solved independently and then combined to form a solution.
    

#### **Key Features of Recursive Problems**:

1. The problem can be divided into smaller instances of the same problem.
    
2. Each subproblem is **identical** in nature to the original problem.
    
3. The solutions to the subproblems can be **combined** to solve the main problem.
    

---

### **Tail Call Optimization**

**Tail Call Optimization (TCO)** is a technique used by some compilers to optimize recursive calls that are in the "tail" position, which can help prevent the stack from growing excessively. In languages that support TCO, the compiler can reuse the current function’s stack frame for the next function call, avoiding stack overflow.

---

### **Recursion Implementation Examples:**

1. **Fibonacci Sequence (Iterative & Recursive)**
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/fibonacci-sequence-iterative-and-recursive)
        
2. **Factorial (Iterative & Recursive)**
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/find-factorial-iterative-and-recursive)
        
3. **Recursion Basics**
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/recursion)
        
4. **Reverse a String (Iterative & Recursive)**
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/recursion/reverse-a-string-iterative-and-recursive)

---

### **Conclusion:**

- **Recursion** provides an elegant solution to problems that involve breaking them down into smaller subproblems, especially when working with tree structures or divide and conquer approaches.
    
- **Stack overflow** is a risk in recursion, but this can be mitigated by ensuring proper **base cases** and by using **tail call optimization** where applicable.
    
- **Iteration** is an alternative that might be more efficient in terms of memory, but it can be less intuitive and harder to read for complex recursive problems.