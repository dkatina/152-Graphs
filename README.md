## Learning Objectives

- The students should be able to differentiate between directed and undirected graphs and understand their respective applications in modeling relationships.
- The students should be able to analyze and interpret adjacency matrices and adjacency lists as representations of graphs
- The students should be able to calculate the degree of a vertex in a graph and apply this concept to understand the connectivity of different nodes within the graph.
- The students should be able to describe the practical applications of graph algorithms, such as Dijkstra's Algorithm, in various domains including route planning, network routing, social network analysis, and resource allocation.

#### Graphs
Graphs are another linked data structure, whose nodes connect in a more abstract way.

They're made up of two components: `Verticle` (the node) and `Edges` (also called links)

A good way to think about graphs, is to compare them to destinations (Verticles) on a map with routes between these desitinations (Edges), Graphs are a useful datatype when trying to find the shortest possible route between to points, and that's why they're used in mapping and gps systems.

##### Directed graphes:
Would be similar to a singly-linked list in that the connections move in only one direction, so you can move from one verticle to the next, but can't necessarily go back

##### Undirected graphes:
Are similar to a doubly-linked list, and the connections between verticals move in both directions.

### How we track the connections.

##### Adjacency Matrices:
Are like tables where each row and column header represent a verticle, and the values within the table represent represent the edges (connections) between the verticles.

![Adjacency](https://www.cs.mtsu.edu/~xyang/3080/images/adjDirectedGraph.png)

```python
adj_matrix = [
    [0,1,1,0,0],
    [0,0,1,0,1],
    [0,0,0,1,0],
    [0,0,0,0,1],
    [0,0,0,0,0]
]
```

##### Adjacency Lists:
Similar to an Adjacency Matrix, adj_lists represent the connections of a graph in a more compact way, listing each of the verticies as keys in a dictionary, whose value is a list of the vertices it's connected to.

```python
adj_list = {
    0: [1,2],
    1: [2,4],
    2: [3],
    3: [4],
    4: []
}
```

### Properties of Graphs

#### Degree of a Vertex:
The degree of a vertex, represents the number of edges connecting to and from that vertex, for the example above the degree of 1 would be 3, since 0 connects to 1 and 2, and 4 connect from 1.

#### Paths:
Paths are essentially how you can traverse from one vertex to another. 0 to 4 has two paths:
- 0 -> 2 -> 3 -> 4
- 0 -> 1 -> 4

#### Cycles:
Are paths that start and end in at the same vertex.

### The Dijkstras Algorithm:

The Dijkstars Algorithm allows us the determine the quickest route between vertices, based on the distance/ weight of the edges that connect them.

By assigning a weight to the connections we can traverse from node to neighbor and measure the path of least resistance.

