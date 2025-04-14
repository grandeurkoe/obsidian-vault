# **Sorting Algorithms**

Sorting is the process of arranging data in a particular order (e.g., ascending or descending). Python has a built-in `sort()` function, but for large data sets, more efficient sorting algorithms might be necessary.

## **Built-in Sort Function**

- Python's built-in `sort()` function has a time complexity of **O(N log N)**, which is efficient for most cases.
    
- However, the built-in sort might not be the most efficient for extremely large datasets.
    
- **GitHub Link**: [Built-in Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/builtin-sort)

---

## **Stable vs Unstable Sorting Algorithms**

- **Stable sorting algorithm**: Keeps elements with equal keys in the same relative order they appeared in the input list.
    
    - Examples of stable sorting algorithms: **Insertion Sort**, **Merge Sort**, **Bubble Sort**.
        
- **Unstable sorting algorithm**: Does not guarantee to preserve the order of equal elements.
    
    - Examples of unstable sorting algorithms: **Quick Sort**, **Heap Sort**.

**Example**:

Given the list of 5-letter words:

```
peach  
straw  
apple  
spork
```

- **Stable sort** by the first letter would produce:
    
    ```
    apple  
    peach  
    straw  
    spork
    ```
    
- **Unstable sort** could produce any order, like:
    
    ```
    apple  
    straw  
    peach  
    spork
    ```

---

## **Sorting Algorithms**

### **Bubble Sort**

- **Description**: The simplest sorting algorithm, Bubble Sort compares each pair of adjacent elements and swaps them if they are in the wrong order. The largest element "bubbles" to the end of the list in each iteration.
    
- **Time Complexity**:
    
    - Worst and Average Case: **O(n²)**
        
    - Best Case (already sorted): **O(n)** (if optimized to detect no swaps).
        
- **Drawback**: **Inefficient** for large datasets.
    
- **GitHub Link**: [Bubble Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/bubble-sort)

---

### **Selection Sort**

- **Description**: In Selection Sort, we repeatedly find the smallest element in the unsorted portion of the list and swap it with the first unsorted element.
    
- **Time Complexity**:
    
    - Worst and Average Case: **O(n²)**
        
    - Best Case: **O(n²)** (no optimization possible).
        
- **GitHub Link**: [Selection Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/selection-sort)

---

### **Insertion Sort**

- **Description**: In Insertion Sort, we build the sorted list one element at a time by inserting the current element into the correct position in the already sorted portion of the list.
    
- **Time Complexity**:
    
    - Worst and Average Case: **O(n²)**
        
    - Best Case (already sorted): **O(n)**.
        
- **Best Use Case**: When the list is nearly sorted or the list size is small.
    
- **GitHub Link**: [Insertion Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/insertion-sort)

---

### **Merge Sort**

- **Description**: Merge Sort is a divide-and-conquer algorithm. It divides the list into two halves, recursively sorts each half, and then merges the two sorted halves.
    
- **Time Complexity**: **O(n log n)** (consistent in all cases).
    
- **Space Complexity**: **O(n)** due to the additional space needed for the merged lists.
    
- **GitHub Link**: [Merge Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/merge-sort)

---

### **Quick Sort**

- **Description**: Quick Sort is a divide-and-conquer algorithm that selects a pivot element, partitions the list around the pivot, and recursively sorts the left and right sublists.
    
- **Time Complexity**:
    
    - Best and Average Case: **O(n log n)**
        
    - Worst Case (if pivot is poorly chosen): **O(n²)**.
        
- **Space Complexity**: **O(log n)** (for the recursive call stack).
    
- **GitHub Link**: [Quick Sort](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/quick-sort)

---

### **Counting and Radix Sort**

- **Counting Sort**: Counts the frequency of each element and uses that information to place elements in their correct position in the output array. Works only for non-negative integers.
    
- **Radix Sort**: Sorts numbers by processing individual digits. It works by sorting the elements based on each digit, starting from the least significant digit (LSD) or most significant digit (MSD).
    
- **Time Complexity**:
    
    - Counting Sort: **O(n + k)** (where k is the range of the input).
        
    - Radix Sort: **O(nk)** (where k is the number of digits in the maximum number).
        
- **Key Advantage**: These are **non-comparison sorts** and can be faster than comparison-based algorithms when the range of numbers is small.
    

---

## **Which Sort Should You Use?**

- **Insertion Sort**:
    
    - Best for small datasets or nearly sorted lists.
        
    - **Time Complexity**: **O(n²)**, but with space complexity **O(1)**.
        
- **Bubble Sort and Selection Sort**:
    
    - These are **not recommended** for large datasets due to their poor **O(n²)** time complexity. They are mainly used for educational purposes.
        
- **Merge Sort**:
    
    - Great for large datasets with consistent **O(n log n)** time complexity.
        
    - **Drawback**: High **space complexity (O(n))** due to recursion and merging.
        
- **Quick Sort**:
    
    - The most widely used sorting algorithm due to its **O(n log n)** time complexity and **O(log n)** space complexity.
        
    - **Drawback**: Worst-case time complexity of **O(n²)** if the pivot selection is poor.
        
- **Counting Sort and Radix Sort**:
    
    - These non-comparison sorts are very efficient when sorting numbers or strings with a fixed range, with time complexities often better than comparison sorts in specific situations.
        

---

## **Sorting Algorithm Summary**

|Algorithm|Best Time Complexity|Worst Time Complexity|Space Complexity|Stable|
|---|---|---|---|---|
|**Bubble Sort**|**O(n)**|**O(n²)**|**O(1)**|Yes|
|**Selection Sort**|**O(n²)**|**O(n²)**|**O(1)**|No|
|**Insertion Sort**|**O(n)**|**O(n²)**|**O(1)**|Yes|
|**Merge Sort**|**O(n log n)**|**O(n log n)**|**O(n)**|Yes|
|**Quick Sort**|**O(n log n)**|**O(n²)**|**O(log n)**|No|
|**Counting Sort**|**O(n + k)**|**O(n + k)**|**O(k)**|Yes|
|**Radix Sort**|**O(nk)**|**O(nk)**|**O(n + k)**|No|

---

These algorithms offer a range of options depending on the size and nature of the data being sorted. The choice of algorithm often depends on:

- Whether stability is important.
    
- The expected size of the dataset.
    
- Memory constraints.
    
- The distribution and range of input data.