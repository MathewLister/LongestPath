# LongestPath
Prints the length on longest paths on DAG from a source node in O(n+m)

# Describe the problem:
The longest path problem can be represented using a graph. The idea is to find the longest simple path with no cycles on a given graph. The length can be calculated by counting edges between nodes our summing the weights of edges between nodes (1). This problem is NP-hard for general graphs (2). This problem also doesn’t have an optimal substructure property so dynamic programming and greedy is not an option (3)&(2). In Figure 1, the longest path from 1 to 5 is 1-2-3-4-5. However, the longest path from 2 to 5 is not 2-3-4-5, it is 2-1-3-4-5. Because of this characteristic you cannot break the problem into sub problems. A brute force approach of enumerating all possible paths then selecting the largest one is exponential and would reach 2^n possible paths. 
  
  ![Figure 1](Images/Longes Path Graphs.svg)

  
Figure 1: No Substructure for Longest Path Problem

1.	http://www.mathcs.emory.edu/~cheung/Courses/171/Syllabus/11-Graph/Docs/longest-path-in-dag.pdf
2.	https://www.geeksforgeeks.org/find-longest-path-directed-acyclic-graph/
3.	https://www.geeksforgeeks.org/optimal-substructure-property-in-dynamic-programming-dp-2/

# Describe the solution:
The best solution to finding the longest path is to first turn the graph into a directed acyclic graph DAG if it is not one already. Searching for the longest path on a DAG allows for a liner time solution using topological sorting. First initialize all distances to all nodes as infinity and the distance from the source node as zero, next run topological sorting to get the linear ordering. Once the linear ordering is established the DAG has an optimal substructure so we can use dynamic programming. In topological order or DFS, visit each node and update the distances of the adjacent nodes using the distance of the current vertex. 
	
# Applications of the solution/Importance:
Finding the longest path in a graph is helpful in many situations. The longest path can help find a critical path; these paths are used in many disciplines. The critical path can be used in digital circuit design to determine the limits of the design (1). The critical path can also be used in project planning and scheduling (2). Finding the longest path can also help find Hamiltonian paths and can be seen in GPS or directions apps (3). Finding the longest path can also help you attack a computer network. It provides an efficient way to dismantle a network by continuously finding the longest path and removing the edges between nodes until there are no longer any paths within the network rendering it useless (4). 
1.	https://www.allaboutcircuits.com/technical-articles/design-considerations-for-digital-vlsi/
2.	https://web.stanford.edu/class/cee320/CEE320B/CPM.pdf
3.	https://mathworld.wolfram.com/HamiltonianPath.html
4.	https://arxiv.org/pdf/1405.7231.pdf

# Running Solution:
Sample Graph:
	![Sample Graph](Images/Longes Path Graphs(1).svg)
	
Sample Run:
	![Demo](Images/sampleRun.gif)

	 
