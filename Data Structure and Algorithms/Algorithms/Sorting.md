# Sorting

Python has an in-build `sort()` function.

The drawback of using the in-built `sort()` function is that it would not be efficient when we are dealing with large data sets.

The time complexity of the built-in `sort(`) function in various languages can be different because of the way they are implemented.

Time complexity of built-in `sort()` function in python is O(N log N).

Built-in Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/builtin-sort)

## Stable vs Unstable Algorithms

A sorting algorithm is said to be stable if two objects with equal keys appear in the same order in sorted output as they appear in the input array to be sorted. Some sorting algorithms are stable by nature like Insertion sort, Merge Sort, Bubble Sort, etc. And some sorting algorithms are not, like Heap Sort, Quick Sort, etc.

Background: A "stable" sorting algorithm keeps the items with the same sorting key in order. 

Suppose we have a list of 5-letter words:


```
peach  
straw  
apple  
spork
```

If we sort the list by just the first letter of each word then a stable-sort would produce:

```
apple  
peach  
straw  
spork
```

In an unstable sort algorithm, straw or spork may be interchanged, but in a stable one, they stay in the same relative positions (that is, since straw appears before spork in the input, it also appears before spork in the output).

## Bubble Sort

Bubble sort is an elementary sort algorithm.

Bubble sort is the simplest and least efficient sorting algorithm.

In bubble sort, we create a bubble of consecutive pairs. compare them and then arrange the two in ascending order. This will eventually bubble up the largest number to the end of the list.

We keep doing this until the list is completely sorted.

Time complexity for bubble sort is O(n^2).

[Bubble-sort with Hungarian ("Csángó") folk dance](https://www.youtube.com/watch?v=lyZQPjUT5B4)

### Implementation

Bubble Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/bubble-sort)

## Selection Sort

Selection sort is an elementary sort algorithm.

In selection sort, we scan for the smallest element and then swap that element with the first position element. We repeat this till be reach the end of the list.

Time complexity for selection sort is O(n^2).

[Select-sort with Gypsy folk dance](https://www.youtube.com/watch?v=Ns4TPTC8whw)

### Implementation

Selection Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/selection-sort)

## Insertion Sort

Insertion sort is an elementary sort algorithm.

Insertion sort is useful when you know that the list is almost or fully sorted.

In the best-case scenario you can get a time complexity of O(n).

[Insert-sort with Romanian folk dance](https://www.youtube.com/watch?v=ROalU379l3U)

### Implementation

Insertion Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/insertion-sort)

## Merge Sort

Time complexity of Merge Sort is O(n log n).

However, the space complexity of merge sort is O(n) because of function call stack.

Merge sort utilizes a divide and conquer approach i.e., recursion.

[Merge-sort with Transylvanian-saxon (German) folk dance](https://www.youtube.com/watch?v=XaqR3G_NVoo)

### Implementation

Merge Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/merge-sort)

## Quick Sort

Quick sort utilizes a divide and conquer approach i.e., recursion.

In quick sort, we pick a randomly pick a pivot, then we push all elements less than the pivot to the left and all the elements greater than the pivot to the right.

Then we divide the list w.r.t the pivot into two sub lists and then we perform the above step on them recursively.

Quick and merge sort are the most commonly used sorting algorithms.

Time complexity of quick sort is O(n log n).

Space complexity of quick sort is O(n log n).

If the pivot is the largest element in the list then the time complexity will be increase to O(n^2).

[Quick-sort with Hungarian (Küküllőmenti legényes) folk dance](https://www.youtube.com/watch?v=ywWBy6J5gz8)

### Implementation

Quick Sort - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/sorting/quick-sort)

## Counting and Radix Sort

Bubble sort, Selection sort, Insertion sort, Merge sort and Quick sort are examples of comparison sort.

Counting and Radix sort do not use comparisons. Hence, they are called non-comparison sort.

In these sorting, we leverage the way numbers and data is stored on computers as 0's and 1's. We use this to sort our data.

Counting and Radix sort only works with numbers specifically integers or string with fixed-size keys in a restricted range. For example, in the range from 0 - 100.

## Which Sort is the Best?

Insertion sort should be used when inputs are small or items are mostly sorted.

Insertion sort uses very little space i.e., O(1) and is very easy to implement.

Bubble sort and Selection sort are never really used. Its uses are limited to educational purposes.

Merge sort uses the divide and conquer approach. Its time complexity is O(n log n) for all cases(best, average and worst).

But if memory is important for you then perhaps merge sort might not be a good choice as it has a space complexity of O(n).

Quick sort is overall better than merge sort because it has a time complexity of O( n log n) and space complexity of O(n log n).

The only downside of quick sort is that in the worst case it has a time complexity of O(n^2).