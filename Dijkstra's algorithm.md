# Dijkstra's Algorithm
#computer-science #algorithm 

Dijkstra's alogirthm is a graph algorithm for finding the shortest path between [[Graph Node|nodes]] on a [[graphs|graph]].

## Algorithm Description
---
Let the node at which we are starting be called the initial node. Let the distance of node Y be the distance from the initial node to Y. Dijkstra's algorithm will initially start with infinite distances and will try to improve them step by step.

1. Mark all nodes unvisited. Create a [[set]] of all the unvisited nodes called the unvisited set.
2. Assign to every node a tentative distance value: set it to zero for our initial node and to infinity for all other nodes. The tentative distance of a node v is the length of the shortest path discovered so far between the node v and the starting node. Since initially no path is known to any other [[vertices|vertex]] than the source itself (which is a path of length zero), all other tentative distances are initially set to infinity. Set the initial node as current.
3. For the current node, consider all of its unvisited neighbors and calculate their tentative distances through the current node. Compare the newly calculated tentative distance to the current assigned value and assign the smaller one. For example, if the current node A is marked with a distance of 6, and the edge connecting it with a neighbor B has length 2, then the distance to B through A will be 6 + 2 = 8. If B was previously marked with a distance greater than 8 then change it to 8. Otherwise, the current value will be kept.
4. When we are done considering all of the unvisited neighbors of the current node, mark the current node as visited and remove it from the unvisited set. A visited node will never be checked again.
5. If the destination node has been marked visited (when planning a route between two specific nodes) or if the smallest tentative distance among the nodes in the unvisited set is infinity (when planning a complete traversal; occurs when there is no connection between the initial node and remaining unvisited nodes), then stop. The algorithm has finished.
6. Otherwise, select the unvisited node that is marked with the smallest tentative distance, set it as the new current node, and go back to step 3.

When planning a route, it is actually not necessary to wait until the destination node is "visited" as above: the algorithm can stop once the destination node has the smallest tentative distance among all "unvisited" nodes (and thus could be selected as the next "current").

## Algorithm Implementation
---

```python
class Graph:
	vertices: int
	graph: 
    def __init__(self, vertices: int):
        self.vertices   = vertices
        self.graph      = [[0 for column in range(vertices)] for row in range(vertices)]
        
    def print_solution(self,dist):
        print("Vertex \t Distance from Source")
        for node in range(self.vertices):
            print(node, "\t\t", dist[node])
            
    def min_distance(self, dist, sptSet) -> int:
        min = 1e7
        
        for vertice in range(self.vertices):
            if dist[vertice] < min and sptSet[vertice] == False:
                min = dist[vertice]
                min_index = vertice
                
        return min_index
        
    def dijkstra(self, src):
        dist        = [1e7] * self.vertices
        dist[src]   = 0
        sptSet      = [False] * self.vertices
 
        for cout in range(self.vertices):
            u           = self.min_distance(dist, sptSet)
            sptSet[u]   = True
 
            for vertice in range(self.vertices):
                if (self.graph[u][vertice] > 0 and sptSet[vertice] == False and dist[vertice] > dist[u] + self.graph[u][vertice]):
                    dist[vertice] = dist[u] + self.graph[u][vertice]
 
        self.print_solution(dist)

graph = Graph(9)
graph.graph = [[0, 4, 0, 0, 0, 0, 0, 8, 0],
           [4, 0, 8, 0, 0, 0, 0, 11, 0],
           [0, 8, 0, 7, 0, 4, 0, 0, 2],
           [0, 0, 7, 0, 9, 14, 0, 0, 0],
           [0, 0, 0, 9, 0, 10, 0, 0, 0],
           [0, 0, 4, 14, 10, 0, 2, 0, 0],
           [0, 0, 0, 0, 0, 2, 0, 1, 6],
           [8, 11, 0, 0, 0, 0, 1, 0, 7],
           [0, 0, 2, 0, 0, 0, 6, 7, 0]
           ]

# Use Dijkstra's algorithm to find the shortest path from the node (vertice) starting at 0
graph.dijkstra(0)
```
