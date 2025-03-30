### **Searching and Traversal**

Searching and traversal are fundamental operations performed on data structures. These operations help us locate specific values or visit every node in a tree or graph.

#### **Types of Searches:**

1. **Linear Search**
    
2. **Binary Search**
    
3. **Breadth-First Search (BFS)**
    
4. **Depth-First Search (DFS)**
    

**Traversal** is the process of visiting every node in a tree or graph. The time complexity for tree and graph traversal is **O(n)**, where **n** is the number of nodes.

---

### **Linear Search**

**Linear Search** (also known as Sequential Search) is a method of finding a target value within a list by sequentially checking each element until it is found or the end of the list is reached.

- **Best-case time complexity**: **O(1)** (when the target is the first element).
    
- **Worst-case time complexity**: **O(n)** (when the target is at the end or not in the list).

---

### **Binary Search**

**Binary Search** works on a sorted list or array and follows the **divide and conquer** approach. It reduces the search space by half with each comparison.

**Steps:**

1. Start with the middle element of the sorted list.
    
2. If the target value is smaller than the middle value, discard the right half of the list.
    
3. If the target value is larger, discard the left half.
    
4. Repeat steps 2 and 3 until the target value is found or the list is exhausted.
    

- **Time complexity**: **O(log n)** (because the list is halved with each comparison).

---

### **Breadth-First Search (BFS)**

**Breadth-First Search (BFS)** is used to traverse a tree or graph level by level, visiting all nodes at the present depth level before moving to nodes at the next level.

**Steps:**

1. Start with the **root node** or the **starting node**.
    
2. Visit the node and then visit its immediate neighbors (left to right).
    
3. Continue to visit the neighbors at each level.
    

**Use cases of BFS**:

- **Shortest Path**: BFS can find the shortest path in an unweighted graph.
    
- **Closer Nodes First**: BFS explores the closest nodes first.

**Downside of BFS**:

- **Memory-intensive**: BFS stores pointers to each child node at every level, making it more memory-heavy.
    

#### **Implementation**:

1. [Breadth-First Search (BFS) - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/breadth-first-search)
    
2. [Breadth-First Search Recursive - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/breadth-first-search-recursive)

---

### **Depth-First Search (DFS)**

**Depth-First Search (DFS)** explores as far as possible along one branch before backtracking to explore other branches.

**Steps:**

1. Start from the **root node** or starting node.
    
2. Traverse down a branch, exploring nodes until reaching the deepest level or a dead-end.
    
3. Backtrack to the parent node and explore the next unexplored branch.
    
4. Repeat steps 2 and 3 until all nodes are visited.
    

**DFS vs BFS**:

- **Memory efficiency**: DFS requires less memory than BFS because it doesn’t need to store pointers for every child at each level.
    
- **Slow for deep solutions**: DFS can be slower when the target node is located deep in the rightmost part of the tree.


![[Pasted image 20231010174525.png|500]]

![[Pasted image 20231010174543.png|500]]

#### **DFS Implementation**:

- [Depth-First Search (DFS) - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/depth-first-search)
    

---

### **BFS vs DFS Comparison**

- **Time Complexity** for both BFS and DFS: **O(n)** where **n** is the number of nodes.

#### **When to Use BFS**:

1. **Shortest Path**: BFS is ideal for finding the shortest path in an unweighted graph.
    
2. **Closer Nodes**: BFS explores closer nodes first, which is useful when you need nodes closest to the source.

**Downside of BFS**:

- **Memory-intensive**: It stores pointers for each child node at every level.

#### **When to Use DFS**:

1. **Memory-efficient**: DFS is more memory-efficient as it does not store pointers for every child.
    
2. **Path Existence**: DFS is useful when determining if a path exists between nodes.

**Downside of DFS**:

- **Slower**: If the target node is in the deep rightmost part of the tree, DFS can take longer to find it.
    

---

### **Quiz**

1. **If you know a solution is not far from the root of the tree**: **BFS**
    
2. **If the tree is very deep and solutions are rare**: **DFS** (DFS will take less time, as BFS would require more memory).
    
3. **If the tree is very wide**: **DFS** (BFS would require too much memory).
    
4. **If solutions are frequent but located deep in the tree**: **DFS**
    
5. **Determining whether a path exists between two nodes**: **DFS**
    
6. **Finding the shortest path**: **BFS**

---

### **Bellman-Ford vs Dijkstra Algorithm**

**Bellman-Ford Algorithm** and **Dijkstra's Algorithm** are both used to find the shortest path in weighted graphs.

- **Bellman-Ford**:
    
    - Can handle **negative edge weights**.
        
    - Time complexity: **O(V * E)** where **V** is the number of vertices and **E** is the number of edges.
        
    - Slower than Dijkstra’s algorithm.
        
- **Dijkstra's Algorithm**:
    
    - Cannot handle **negative edge weights**.
        
    - Time complexity: **O(V^2)** in the simplest form, but can be improved to **O(E + V log V)** with a priority queue.
        
    - More efficient than Bellman-Ford when edge weights are positive.
