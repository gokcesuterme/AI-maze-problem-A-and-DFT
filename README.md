********* WRITTEN AND CODED BY GOKCESU TERME *******************
********************************************************************

******************************************************************************
***************** MAZE GRAPH CONSTRUCTION AND TOUR FINDING *******************
******************************************************************************



 ************************** OVERVIEW *****************************************

	This Python script provides functionality to construct a graph from a maze layout
	and perform various pathfinding algorithms to find optimal paths within the maze.


 ***************** REQURIMENETS ***********************************************


Ensure Python 3 is installed on your system.
Run the script with python filename.py.
Modify file_path in main() function to point to the maze layout file.

 *************** MAZE TXT FILE **************************************************

 The file for the content of the layout of maze is already included.
 The description of the maze :
 # # B . . . .
. . . . . # #
. # # # . . C
. . . . . # .
. . # # . # .
# . # . . # .
# . # . # # .
. A . . . . D

' #'  denotes obstacles
' . ' denotes the walkable paths

' A ' our main robots location. If the content is going to be change make sure that
you locate and write A for the starting node.

the other words for the location of mr robots friends.



 *********FUNCTIONS *****************

 1 ) load_and_parse_maze(file_path)


	Description: Reads a maze layout from a file and extracts walkable nodes and their coordinates.
	Input: file_path - Path to the file containing the maze layout.
	Output: Tuple (nodes, walkable), where nodes is a dictionary mapping node names to their coordinates,
	and walkable is a set of coordinates representing walkable nodes.


 2) construct_graph(file_path)
	Description: Constructs a graph representation of the maze by finding shortest paths between nodes using
	the A* search algorithm.
	Input: file_path - Path to the file containing the maze layout.
	Output: Tuple (nodes, graph), where nodes is a dictionary mapping node names to their coordinates,
	and graph is a dictionary representing the graph with nodes as keys and their neighboring nodes with associated costs as values.
3)dfs(current, path, visited, graph, start_node, total_nodes)
	Description: Performs a depth-first search to find a minimal distance tour within the maze.
	Inputs:
	current - Current node being explored.
	path - Path traversed so far.
	visited - Set of visited nodes.
	graph - Graph representation of the maze.
	start_node - Starting node for the tour.
	total_nodes - Total number of nodes in the maze.
	Output: Path representing a minimal distance tour if found, otherwise None.

4) ucs(start_node, graph, total_nodes)
	Description: Performs uniform cost search to find a minimal distance tour within the maze.
	Inputs:
	start_node - Starting node for the tour.
	graph - Graph representation of the maze.
	total_nodes - Total number of nodes in the maze.
	Output: Path representing a minimal distance tour if found, otherwise None.
5) print_edges(graph)
	Description: Prints all edges of the graph in alphabetical order.
	Input: graph - Graph representation of the maze.
	Output: Prints each edge of the graph in the format node1,node2,cost.
6) main()
	Description: Entry point of the script. Constructs the graph, prints its edges,
	and performs minimal distance tours using DFS and UCS algorithms.
