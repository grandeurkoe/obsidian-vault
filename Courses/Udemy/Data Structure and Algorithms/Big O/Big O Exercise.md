### **Big O Notation Exercises**

Big O notation is used to describe the performance or complexity of an algorithm. Specifically, it focuses on how the runtime or space requirement grows as the size of the input increases.

---

### **Exercise 01**

```python
def fun_challenge(input):
    a = 10            # O(1) - Constant time
    a = 50 + 3        # O(1) - Constant time
    for i in range(len(input)):    # O(n) - Loop over the input (size n)
        another_function()         # O(n) - Call a function with O(n) complexity
        stranger = True             # O(n) - Constant operation inside loop
        a += 1                     # O(n) - Constant operation inside loop
    return a            # O(1) - Constant time
```

- **Big O Analysis**:
    
    - The constant time operations (`a = 10`, `a = 50 + 3`, `return a`) are **O(1)**, meaning they don't depend on the input size.
        
    - The **for loop** runs **n times** (where **n** is the length of the input), and inside the loop, we have operations that are **O(1)** each. However, the loop contains several **O(1)** operations, which results in **O(n)**.
        
    - Therefore, the overall time complexity is **O(n)**, since the **O(1)** operations are dominated by the **O(n)** loop.

**Conclusion**: The Big O of this function is **O(n)**.

---

### **Exercise 02**

```python
def another_fun_challenge(input):
    a = 5            # O(1) - Constant time
    b = 10           # O(1) - Constant time
    c = 50           # O(1) - Constant time
    for i in input:  # O(n) - Loop over the input (size n)
        x = i + 1    # O(n) - Constant operation inside loop
        y = i + 2    # O(n) - Constant operation inside loop
        z = i + 3    # O(n) - Constant operation inside loop
    for j in input:  # O(n) - Another loop over the input (size n)
        p = j * 2    # O(n) - Constant operation inside loop
        q = j * 2    # O(n) - Constant operation inside loop
    who_am_i = "I don't know"  # O(1) - Constant time
```

- **Big O Analysis**:
    
    - The first block of code (assignments of **a**, **b**, **c**) are **O(1)** operations.
        
    - The first loop runs **n** times, performing **O(1)** operations (i.e., additions) within the loop. This makes it **O(n)**.
        
    - The second loop runs **n** times and also performs **O(1)** operations (multiplications) inside. This is also **O(n)**.
        
    - Finally, the statement `who_am_i = "I don't know"` is a **O(1)** operation.
        
    - The total time complexity is **O(n) + O(n) = O(2n)**, but constants are ignored in Big O notation, so the complexity simplifies to **O(n)**.

**Conclusion**: The Big O of this function is **O(n)**.

---

### **Exercise 03**

```python
boxes = [1, 2, 3, 4, 5]
def log_all_pairs(boxes):
    for i in boxes:          # O(n) - Loop over the boxes list (size n)
        for j in boxes:      # O(n) - Nested loop over the boxes list (size n)
            print(f"({i},{j})")
log_all_pairs(boxes)
```

- **Big O Analysis**:
    
    - The outer loop runs **n** times (for each element in the `boxes` list).
        
    - The inner loop also runs **n** times for each iteration of the outer loop, making it a **nested loop**.
        
    - Therefore, the total number of operations is **n * n**, which simplifies to **O(n^2)**.

**Conclusion**: The Big O of this function is **O(n^2)**.

---

### **Summary of Big O Notations**:

- **Exercise 01**: **O(n)** — The loop dominates the time complexity.
    
- **Exercise 02**: **O(n)** — The loops dominate, but the constants are ignored.
    
- **Exercise 03**: **O(n^2)** — The nested loops lead to quadratic time complexity.