# **Trees**

A **Tree** is a hierarchical data structure made up of **nodes**, where each node points to other nodes, forming a parent-child relationship. Unlike linear data structures like **Arrays** and **Linked Lists**, trees have multiple branches or child nodes originating from each parent node. This structure allows for efficient organization and searching of data.

---

## **Key Concepts in Trees**

1. **Node**: A basic unit of a tree containing data and possibly references to other nodes.
    
2. **Root**: The topmost node in a tree. Every tree has exactly one root.
    
3. **Parent**: A node that has one or more child nodes.
    
4. **Child**: A node that has a parent node.
    
5. **Leaf**: A node with no children.
    
6. **Siblings**: Nodes that share the same parent.
    
7. **Subtree**: A tree formed by a node and all its descendants.
    
8. **Depth**: The number of edges from a node to the root node.
    
9. **Height**: The length of the longest path from a node to a leaf. The height of a tree is the height of the root node.
    
10. **Binary Tree**: A tree in which each node has at most two children (left and right).
    
11. **Binary Search Tree (BST)**: A binary tree where the left child contains smaller values, and the right child contains larger values.
    
12. **Traversal**: The process of visiting all nodes in a tree, with methods like **in-order**, **pre-order**, and **post-order**.
    
13. **Balanced Tree**: A tree in which the height difference between the two child subtrees of any node is at most one.
    
14. **Forest**: A collection of disjoint trees.
    
15. **Parental Relationship**: The connection between a node and its parent.
    

---

## **Types of Trees**

### **Binary Tree**

A **Binary Tree** is a tree in which each node has at most two children: a **left** and a **right** child. The topmost node is the **root**, and the nodes without children are the **leaves**.

**Example of Binary Tree**:

```
    1
   / \
  2   3
 / \
4   5
```

### **Binary Search Tree (BST)**

A **Binary Search Tree** (BST) is a binary tree with an ordered structure:

- The **left** child contains values **less than** the node.
    
- The **right** child contains values **greater than** the node.
    

**Example of a Binary Search Tree**:

```
       8
      / \
     3   10
    / \    \
   1   6    14
      / \   /
     4   7  13
```

In a BST, the left subtree of a node contains only nodes with values less than the node’s value, and the right subtree contains only nodes with values greater than the node's value.

### **Perfect Binary Tree**

A **Perfect Binary Tree** is a binary tree in which:

- Every level is completely filled.
    
- All nodes are as left as possible.
    
- All nodes have either 0 or 2 children.
    

**Example of a Perfect Binary Tree** with height 2:

```
        1
       / \
      2   3
     / \
    4   5
```

For a perfect binary tree of height **h**, the number of nodes is 2h+1−12^{h+1} - 1.

---

## **Properties of Binary Trees**

1. **Binary trees** have at most two children per node.
    
2. The **height** of a binary tree is the length of the longest path from the root to a leaf node.
    
3. The **number of nodes** in a perfect binary tree is given by 2h+1−12^{h+1} - 1 where **h** is the height.
    

---

## **Binary Heap**

A **Binary Heap** is a complete binary tree that satisfies the **heap property**:

- In a **Max Heap**, the value of each parent node is **greater** than or equal to its children.
    
- In a **Min Heap**, the value of each parent node is **less** than or equal to its children.
    

**Time Complexity**:

1. **LOOKUP**: O(N)
    
2. **INSERT**: O(log N)
    
3. **DELETE**: O(log N)
    

---

## **Trie (Prefix Tree)**

A **Trie** is a tree-like data structure used for efficient retrieval of keys in a set of strings, often used in applications like **auto-completion** and **spell checking**. It allows for fast lookup of words or parts of words by sharing common prefixes among nodes.

**Example Trie**:

```
START
  |
  A - T
  |   |
  S   O
 / \   \
T   S   O
```

**Time Complexity**: O(length of word being searched.

---

## **Balanced vs. Unbalanced Trees**

- **Balanced Trees**: In a balanced tree, the difference in heights between the left and right subtrees of any node is at most 1. Examples of balanced trees include **AVL trees** and **Red-Black trees**.
    
- **Unbalanced Trees**: When a binary search tree (BST) becomes unbalanced, one subtree becomes much deeper than the other, leading to performance degradation. In this case, the operations may take O(n) time instead of O(log n).
    

---

## **Key Operations in Trees**

1. **Traversal**: Traversing a tree means visiting each node in a specific order. Common methods are:
    
    - **In-order traversal** (left, root, right)
        
    - **Pre-order traversal** (root, left, right)
        
    - **Post-order traversal** (left, right, root)
        
2. **Insertion**: Adding a new node to the tree while maintaining the tree's properties.
    
3. **Deletion**: Removing a node from the tree and adjusting the structure to maintain the properties of the tree.
    

---

## **Time Complexity of Tree Operations**

1. **Balanced Binary Search Tree (BST)**:
    
    - **LOOKUP**: O(log N)
        
    - **INSERT**: O(log N)
        
    - **DELETE**: O(log N)
        
2. **Unbalanced Binary Search Tree (BST)**:
    
    - **LOOKUP**: O(N)
        
    - **INSERT**: O(N)
        
    - **DELETE**: O(N)
        

---

## **Conclusion**

Understanding trees and their properties is essential for building efficient data structures and algorithms. Trees are widely used in **hierarchical** data representation, **searching** algorithms (like in Binary Search Trees), **sorting** (via heaps), and even in **text processing** (using Tries). Tree operations like insertion, deletion, and traversal have different time complexities based on whether the tree is balanced or unbalanced, and knowing when to use different tree types can significantly optimize performance in various applications.