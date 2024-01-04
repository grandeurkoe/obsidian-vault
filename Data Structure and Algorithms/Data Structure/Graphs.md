# Graphs

Graphs are one of the most used and useful data structure in computer science when it comes to modeling real life.

Graph is a set of values that are related in a pairwise fashion.

Each item in a graph is called a Node or Vertex.

Nodes are connected with each other and these connectors are called Edges.

![[Pasted image 20231010152550.png|500]]

Graphs are great data structure to model real life relationship.

Amazon uses graphs for their recommendation engines.

Scaling is hard because it is very costly.

## Types of Graphs

### Directed and Undirected Graphs

Directed and Undirected graphs are useful to describe traffic flow.

![[Pasted image 20231010152731.png|500]]

Unlike undirected graphs, directed graphs have directional movements. It can only move in one direction i.e., a one-way relationship.

Directed graphs can be cyclic i.e., the starting and the ending vertex can be same.

Indegree in directed graphs is the number of incoming edges to the vertex.

Outdegree in directed graphs is the number of outgoing edges from the vertex.

In undirected graphs, movements are bidirectional.

### Weighted and Unweighted Graphs

Values can be assigned to various aspects of a graph. Just as how we can assign a value to each node, we can also assign values to the edges of a graph.

![[Pasted image 20231010152830.png|500]]

Unlike unweighted graphs, weighted graphs have values assigned to its edges.

Weighted graphs are used to determine the shortest path to a node.

### Cyclic and Acyclic Graphs

When you have vertices connected in a cyclic fashion then these graphs are called as Cyclic Graphs.

![[Pasted image 20231010152924.png|500]]

The vertices of an Acyclic graph does not form a cyclic relationship.

Cyclic graphs are very common in weighted graphs.

## How to build a graph?

![[Pasted image 20231010153028.png|500]]

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