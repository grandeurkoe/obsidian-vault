# Searching and Traversal

Searching and Traversal are one of the most important operation you can perform on a data structure.

The following are the different kinds of search -

1. Linear Search.
2. Binary Search.
3. Depth First Search.
4. Breadth First Search.

Traversal is the process of visiting every node in the tree or a graph.

Time complexity for graph and tree traversal is O(n) because we are visiting every node.

## Linear Search

Linear Search or Sequential Search is the method of finding a target value within a list.

In Linear Search, it sequentially searches the list for the target value until it is found or you reach the end of the list.

Time complexity of linear search is O(n) if the target value is at the end of the list.

In the best case scenario, the time complexity is O(1).


## Binary Search

Binary Search involves searching in an already sorted list.

Sorted list can be turned into a binary search tree.

Binary search tree is more efficient than a sorted or unsorted list.

Time complexity of an already sorted binary search tree is O(log n) because it uses the divide and conquer approach.

1. We start by getting the central value in the list.
2. If the target value is less than or greater than the target value, then we discard elements to the right of the central value or we discard elements to the left of the central value respectively.
3. The we perform step(2) and step(3) iteratively until we find the target value.

## Breadth First Search(BFS)

1. In Breadth First Search, you start with the root node
2. Then you move left to right down the level.
3. You keep doing step(2) until you find the node you're looking for or you've traversed every node.

### Implementation

1. Breadth First Search - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/breadth-first-search)
2. Breadth First Search Recursive - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/breadth-first-search-recursive)

## Depth First Search (DFS)

1. In Depth First Search, you start from the root node.
2. The you traverse by following one branch of the tree down as many level as possible until you've found the target value or you've reached the end of tree branch.
3. It then goes back to the parent node with an unexplored branch.
4. Then you iteratively perform step(2) and step(3).

Depth First Search has a lower memory requirement than Breadth First Search because it is not necessary to store pointers for each child at every level.

DFS can be implemented in three different ways -

![[Pasted image 20231010174525.png|500]]

![[Pasted image 20231010174543.png|500]]

### Implementation

Depth First Search - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/algorithms/searching/depth-first-search)

## Breadth First Search(BFS) vs Depth First Search (DFS)

Time complexity of both BFS and DFS is O(n).

What is BFS for?

1. Shortest Path.
2. Closer Nodes - Since in BFS we traverse the closer nodes first.

Downside of BFS?

1. More Memory - Since it has to store pointer for every child at every level.

What is DFS for?

1. Less Memory - Doesn't store pointer for every child at every level.
2. Does the path exist from the source node to the target node.

Downside of DFS?

1. Can get slow, if the target node is in the rightmost subtree.

Graphs also use BFS and DFS for traversal.

DFS in Graphs can be used in a get out of the maze program.

### Quiz

Q1. If you know a solution is not far from the root of the tree:

BFS

Q2. If the tree is very deep and solutions are rare,

BFS (DFS will take long time. )

Q3. If the tree is very wide:

DFS (BFS will need too much memory)

Q4. If solutions are frequent but located deep in the tree

DFS

Q5. determining whether a path exists between two nodes

DFS

Q6. Finding the shortest path

BFS

## Bellman Ford and Dijkstra Algorithm

These algorithms are used to find the shortest path.

Since BFS, doesn't consider edge weight. So the shortest path that BFS finds, might not be the most weight efficient path.

Bellman Ford and Dijkstra's Algorithm allows us to find the shortest path that is also weight efficient.

Bellman Ford Algorithm can accommodate negative weight edges.

Dijkstra's Algorithm can't accommodate negative weight edges.

The drawback of Bellman Ford is that it is not the most efficient i.e. time complexity of Bellman Ford is O(V * E) which is greater than the time complexity of Dijkstra's algorithm i.e. O(V^2).