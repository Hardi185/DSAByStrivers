A graph is a data structure used to model pairwise relationships between objects. It consists of two main components:

**Vertices (Nodes):** These are the individual entities or points in the graph. They can represent anything from people in a social network, cities in a map, or tasks in a project.

**Edges (Links):** These are the connections between pairs of vertices. They represent the relationships or interactions between the entities.

![image](https://github.com/user-attachments/assets/4e6670a1-f830-4ff3-a8bc-e54fc06ca40a)

---

## Types of Graphs

### Directed Graph (Digraph)
- **Definition**: In a directed graph, edges have a direction. That is, an edge from vertex A to vertex B is distinct from an edge from vertex B to vertex A.
- **Representation**: Ordered pair of vertices, such as `(A → B)`.
- **Example**: A one-way street between two cities.

### Undirected Graph
- **Definition**: In an undirected graph, edges do not have a direction. The edge simply connects two vertices.
- **Representation**: Unordered pair of vertices, such as `{A, B}`.
- **Example**: A road between two cities where traffic can go in both directions.

### Cyclic Graph
- **Definition**: Contains at least one cycle, i.e., a path that starts and ends at the same vertex, traversing at least one edge more than once.
- **Example**: A network where `A → B → C → A` forms a cycle.

### Acyclic Graph
- **Definition**: Does not contain any cycles. There are no closed loops in the graph.
- **Example**: A tree is a special case of an acyclic graph.

### Directed Acyclic Graph (DAG)
- **Definition**: A directed graph with no cycles. It is often used to represent processes with dependencies, such as tasks in a project (task ordering).
- **Example**: Task scheduling where each task depends on previous ones.

## Graph Representation

### Adjacency Matrix
- **Definition**: A 2D array used to represent a graph. The element at row `i` and column `j` is non-zero if there is an edge from vertex `i` to vertex `j`.
- **Advantages**: Good for dense graphs.
- **Space Complexity**: `O(n²)` where `n` is the number of vertices.

### Adjacency List
- **Definition**: A more space-efficient representation where each vertex has a list of all the vertices it is connected to.
- **Advantages**: Suitable for sparse graphs.
- **Space Complexity**: `O(n + e)` where `e` is the number of edges.

### Edge List
- **Definition**: The graph is represented by a list of edges. Each edge is an unordered or ordered pair (depending on whether the graph is undirected or directed).

## Key Terminology in Graphs

### Path
- **Definition**: A sequence of vertices such that there is an edge between consecutive vertices.
- **Cycle**: A path that starts and ends at the same vertex.
- **Simple Path**: Does not contain any repeated vertices.

### Degree of a Vertex
- **Undirected Graph**: The number of edges connected to the vertex.
- **Directed Graph**:
  - **Indegree**: Number of incoming edges to the vertex.
  - **Outdegree**: Number of outgoing edges from the vertex.

### Connected Graph
- **Undirected Graph**: There is a path between every pair of vertices.
- **Directed Graph**: Strongly connected if there is a path between every pair of vertices in both directions.

### Disconnected Graph
- **Definition**: There are two or more vertices that do not have a path between them.

### Weighted Graph
- **Definition**: Each edge has a weight (or cost) associated with it, often used to represent distances or costs.

### Unweighted Graph
- **Definition**: All edges are treated equally, with no associated weight.

### Subgraph
- **Definition**: A graph formed from a subset of the vertices and edges of another graph.

### Tree
- **Definition**: A special type of acyclic graph where there is exactly one path between any two vertices.
- **Binary Tree**: A specific type of tree where each vertex has at most two children.

## Graph Traversal

### Depth-First Search (DFS)
- **Definition**: Explores as far down a branch as possible before backtracking.
- **Usage**: Pathfinding, cycle detection, topological sorting.
- **Implementation**: Uses a stack or recursion.

### Breadth-First Search (BFS)
- **Definition**: Explores the graph level by level, visiting all neighbors of a node before moving to the next level.
- **Usage**: Shortest path problems, finding connected components in an unweighted graph.
- **Implementation**: Uses a queue.

## Special Graphs

### Tree
- **Definition**: An acyclic connected graph with exactly `n - 1` edges for `n` vertices.

### Forest
- **Definition**: A disjoint set of trees.

### Complete Graph
- **Definition**: Every pair of vertices is connected by an edge.
- **Edge Count**:
  - **Undirected Graph**: `n(n-1)/2`
  - **Directed Graph**: `n(n-1)`

### Bipartite Graph
- **Definition**: Vertices can be divided into two disjoint sets such that every edge connects a vertex in one set to a vertex in the other set.
- **Usage**: Modeling relationships between two distinct groups, such as jobs and workers.
