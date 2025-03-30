# Graphs

Graphs are one of the most used and useful data structure in computer science when it comes to modeling real life.

Graph is a set of values that are related in a pairwise fashion.

Each item in a graph is called a Node or Vertex.

Nodes are connected with each other and these connectors are called Edges.



Graphs are great data structure to model real life relationship.

Amazon uses graphs for their recommendation engines.

Scaling is hard because it is very costly.

## Types of Graphs

### Directed and Undirected Graphs

Directed and Undirected graphs are useful to describe traffic flow.



Unlike undirected graphs, directed graphs have directional movements. It can only move in one direction i.e., a one-way relationship.

Directed graphs can be cyclic i.e., the starting and the ending vertex can be same.

Indegree in directed graphs is the number of incoming edges to the vertex.

Outdegree in directed graphs is the number of outgoing edges from the vertex.

In undirected graphs, movements are bidirectional.

### Weighted and Unweighted Graphs

Values can be assigned to various aspects of a graph. Just as how we can assign a value to each node, we can also assign values to the edges of a graph.



Unlike unweighted graphs, weighted graphs have values assigned to its edges.

Weighted graphs are used to determine the shortest path to a node.

### Cyclic and Acyclic Graphs

When you have vertices connected in a cyclic fashion then these graphs are called as Cyclic Graphs.



The vertices of an Acyclic graph does not form a cyclic relationship.

Cyclic graphs are very common in weighted graphs.

## How to build a graph?



There's three ways you can build a graph -

### Edge List

This list simply show the connection between two nodes.

`graph = [[2, 0], [1, 2], [1, 3], [2, 3]]`

### Adjacency List

In this list, the index is the node and the value at that index would be a list of nodes connected to that index node.
```python
graph = [2, [2, 3], [0, 1, 3], [1, 2]]
# OR
graph = {0: 2, 1:[2, 3], 2: [0, 1, 3], 3: [1,2]}
```

### Adjacency Matrix

Here, we assign a value of 0 if the nodes are not connected and 1 if they are connected.
```python
graph = [
[0, 0, 1, 0],
[0, 0, 1, 1],
[1, 1, 0, 1 ],
[0, 1, 1, 0],
]
```

## Implementation

Implementing a Graph using Adjacency List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/450ac5d11eb4c3a9ba922317cf39357b608c4f56/data-structures/graphs/implementing-a-graph-using-adjacent-list)


# **Graphs**

Graphs are a fundamental data structure used to model relationships between entities in many real-life scenarios, such as social networks, web pages, and transportation systems.

A **graph** consists of a set of **nodes** (also called **vertices**) and **edges** (connections between nodes). Graphs are useful for modeling complex systems where relationships between elements are important.

![[Pasted image 20231010152550.png|500]]

## **Types of Graphs**

### **1. Directed vs. Undirected Graphs**

![[Pasted image 20231010152731.png|500]]

- **Directed Graph (Digraph)**: In a directed graph, the edges have a direction. Each edge points from one node to another, representing a one-way relationship. Example: Twitter followers or road directions.
    
    - **Indegree**: Number of incoming edges to a node.
        
    - **Outdegree**: Number of outgoing edges from a node.
        
- **Undirected Graph**: In an undirected graph, the edges do not have a direction. The relationship between nodes is bidirectional. Example: A friendship on social media.
    

### **2. Weighted vs. Unweighted Graphs**

![[Pasted image 20231010152830.png|500]]

- **Weighted Graph**: Each edge in the graph has a weight or value assigned to it. These values can represent distances, costs, or other metrics. Example: Roads between cities with distances or costs.
    
- **Unweighted Graph**: All edges are considered equal, meaning they don't have any specific weights.
    

### **3. Cyclic vs. Acyclic Graphs**

![[Pasted image 20231010152924.png|500]]

- **Cyclic Graph**: A graph that contains at least one cycle, where a path leads from a node back to itself.
    
- **Acyclic Graph**: A graph that has no cycles. This type of graph is commonly used for modeling hierarchical structures or dependencies. A special case of acyclic graphs is a **tree**.
    

---

## **How to Build a Graph?**

![[Pasted image 20231010153028.png|500]]

There are several ways to represent a graph in memory. The most common representations are:

### **1. Edge List**

An edge list is a simple list of pairs of nodes that are connected by an edge.

Example:

```python
graph = [[2, 0], [1, 2], [1, 3], [2, 3]]
```

This means:

- Node 0 is connected to Node 2
    
- Node 1 is connected to Node 2
    
- Node 1 is connected to Node 3
    
- Node 2 is connected to Node 3
    

### **2. Adjacency List**

An adjacency list represents a graph where each node is associated with a list of all the nodes to which it is directly connected.

Example using a list:

```python
graph = [[], [2, 3], [0, 1, 3], [1, 2]]
```

Or using a dictionary:

```python
graph = {0: [2], 1: [2, 3], 2: [0, 1, 3], 3: [1, 2]}
```

This means:

- Node 0 is connected to Node 2
    
- Node 1 is connected to Nodes 2 and 3
    
- Node 2 is connected to Nodes 0, 1, and 3
    
- Node 3 is connected to Nodes 1 and 2
    

### **3. Adjacency Matrix**

An adjacency matrix is a 2D matrix (array), where the rows and columns represent nodes, and the value at position `(i, j)` is `1` if there is an edge from node `i` to node `j`, otherwise `0`.

Example:

```python
graph = [
    [0, 0, 1, 0],  # Node 0 is connected to Node 2
    [0, 0, 1, 1],  # Node 1 is connected to Nodes 2 and 3
    [1, 1, 0, 1],  # Node 2 is connected to Nodes 0, 1, and 3
    [0, 1, 1, 0],  # Node 3 is connected to Nodes 1 and 2
]
```

---

## **Graph Visualization**

Graphs are excellent for modeling real-life relationships. For instance:

- **Amazon** uses graphs in their **recommendation engine** to suggest products based on user preferences.
    
- **Social networks** use graphs to model the relationship between users (e.g., Facebook).
    
- **Routing and networking algorithms** (like in the internet or transportation systems) are based on graph traversal.
    

---

## **Graph Implementation Example**

You can implement a graph using an **Adjacency List** to efficiently store nodes and their connections. Here's a GitHub link for implementing a graph using an adjacency list:

- [Implementing a Graph Using Adjacency List - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/450ac5d11eb4c3a9ba922317cf39357b608c4f56/data-structures/graphs/implementing-a-graph-using-adjacent-list)
    

---

Graphs are versatile and essential for a wide range of algorithms and real-world applications!