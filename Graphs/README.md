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


![image](https://github.com/user-attachments/assets/b41d4d6f-08f8-4606-8182-adf1dff9f081)

### Undirected Graph
- **Definition**: In an undirected graph, edges do not have a direction. The edge simply connects two vertices.
- **Representation**: Unordered pair of vertices, such as `{A, B}`.
- **Example**: A road between two cities where traffic can go in both directions.


![image](https://github.com/user-attachments/assets/452b6ec2-1a24-4d31-8b11-ac7b7685fc49)


### Cyclic Graph
- **Definition**: Contains at least one cycle, i.e., a path that starts and ends at the same vertex, traversing at least one edge more than once.
- **Example**: A network where `A → B → C → A` forms a cycle.

![image](https://github.com/user-attachments/assets/348ef729-6c92-4a77-981d-fde0298b204c)


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

![image](https://github.com/user-attachments/assets/5dabadd4-3f2e-4587-86c7-f66fcabd1fb2)

![image](https://github.com/user-attachments/assets/c7abcf71-41cc-4e5c-ad10-c916266606a7)
  

### Adjacency List
- **Definition**: A more space-efficient representation where each vertex has a list of all the vertices it is connected to.
- **Advantages**: Suitable for sparse graphs.
- **Space Complexity**: `O(n + e)` where `e` is the number of edges.

![image](https://github.com/user-attachments/assets/c9d20554-faeb-4443-bcb7-69838103c50e)


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
 
![image](https://github.com/user-attachments/assets/0373e795-da53-479c-befa-9432cf9bee32)


### Connected Graph
- **Undirected Graph**: There is a path between every pair of vertices.
- **Directed Graph**: Strongly connected if there is a path between every pair of vertices in both directions.

![image](https://github.com/user-attachments/assets/c34828b4-19e9-4c6a-94d5-d086a582ef08)

### Disconnected Graph
- **Definition**: There are two or more vertices that do not have a path between them.

### Weighted Graph
- **Definition**: Each edge has a weight (or cost) associated with it, often used to represent distances or costs.

![image](https://github.com/user-attachments/assets/a38511d1-0e7e-4437-bf58-947a52836e40)

### Unweighted Graph
- **Definition**: All edges are treated equally, with no associated weight.
  
![image](https://github.com/user-attachments/assets/a30353ad-cb32-4d13-a5bd-8d651a828552)

### Subgraph
- **Definition**: A graph formed from a subset of the vertices and edges of another graph.

![image](https://github.com/user-attachments/assets/502bb77c-4cc5-4716-8784-3734f9db5bce)

### Tree
- **Definition**: A special type of acyclic graph where there is exactly one path between any two vertices.
- **Binary Tree**: A specific type of tree where each vertex has at most two children.

## Graph Traversal

### Depth-First Search (DFS)
- **Definition**: Explores as far down a branch as possible before backtracking.
- **Usage**: Pathfinding, cycle detection, topological sorting.
- **Implementation**: Uses a stack or recursion.

![image](https://github.com/user-attachments/assets/44354f1a-c3df-4b2f-aa37-1e2fcccdde59)

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

![image](https://github.com/user-attachments/assets/1e9b2555-653b-4d84-b481-c3d8dd2cc226)

### Bipartite Graph
- **Definition**: Vertices can be divided into two disjoint sets such that every edge connects a vertex in one set to a vertex in the other set.
- **Usage**: Modeling relationships between two distinct groups, such as jobs and workers.
