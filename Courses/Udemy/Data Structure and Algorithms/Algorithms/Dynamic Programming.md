### **Dynamic Programming**

**Dynamic Programming (DP)** is an optimization technique that leverages **caching** to improve performance by solving problems by breaking them down into smaller subproblems. The idea is to solve each subproblem once, store the result in a cache (such as a hash table), and then reuse that result when the same subproblem appears again. This avoids redundant calculations and significantly reduces the time complexity.

Dynamic Programming combines the principles of **divide and conquer** with **memoization**.

#### **How DP Works:**

1. **Problem Breakdown**: Divide the problem into smaller, manageable subproblems.
    
2. **Solve Subproblems**: Solve each subproblem individually.
    
3. **Store Results**: Save the results in a cache (hash table or dictionary) so that when a similar subproblem arises, we can directly retrieve the result instead of recomputing it.

**Visual Explanation:** ![Dynamic Programming](Pasted%20image%2020231010175816.png)

### **How to Identify if a Problem Requires Dynamic Programming**

Dynamic Programming is useful when a problem has the following characteristics:

- **Overlapping Subproblems**: The problem can be broken down into smaller subproblems that repeat multiple times.
    
- **Optimal Substructure**: The optimal solution of the problem can be constructed efficiently from the optimal solutions of its subproblems.
    

**Diagram to Help Identify DP Problems**: ![Identifying DP](Pasted%20image%2020231010175845.png)

### **Example: Fibonacci Sequence**

Dynamic programming can drastically reduce time complexity. For instance, in the naive recursive approach to calculating Fibonacci numbers, the time complexity is **O(2^n)**, because the same subproblems are solved repeatedly.

However, using dynamic programming, we can reduce the time complexity to **O(n)** by storing previously calculated Fibonacci values in a cache and avoiding redundant computations.

---

### **Memoization or Caching**

**Memoization** is a technique where you store the results of expensive function calls and reuse them when the same inputs occur again. By caching intermediate results, you can speed up the program significantly.

### **Benefits of Memoization**:

- **Faster Execution**: Avoid redundant calculations.
    
- **Improved Time Complexity**: Reduces time complexity from **O(2^n)** to **O(n)** in many cases.
    

However, the **trade-off** is increased **space complexity** due to the cache (hash table) used for storing the results.

---

### **Implementation Examples**

1. **Fibonacci Dynamic Bottom-Up**:
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/fibonacci-dynamic-bottom-up)
        
2. **Fibonacci Dynamic Programming**:
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/fibonacci-dynamic-programming)
        
3. **Memoization Closure**:
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/memoization-closure)
        
4. **Memoization**:
    
    - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/dynamic-programming/memoization)
        

---

By applying **Dynamic Programming** and **Memoization**, you can solve complex problems efficiently by reducing redundant computations, although the space complexity increases due to storing the intermediate results.
