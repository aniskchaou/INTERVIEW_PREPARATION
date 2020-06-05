# Rat in a Maze
A Maze is given as N*N binary matrix of blocks where source block is the upper left most block i.e., maze[0][0] and destination block is lower rightmost block i.e., maze[N-1][N-1]. A rat starts from source and has to reach the destination. The rat can move only in two directions: forward and down.
  
 Gray blocks are dead ends (value = 0). 

[![](https://www.geeksforgeeks.org/wp-content/uploads/ratinmaze_filled11.png "ratinmaze_filled1")](https://www.geeksforgeeks.org/wp-content/uploads/ratinmaze_filled11.png)

Following is binary matrix representation of the above maze.

{1, 0, 0, 0}
{1, 1, 0, 1}
{0, 1, 0, 0}
{1, 1, 1, 1}

Following is a maze with highlighted solution path.

[![](https://www.geeksforgeeks.org/wp-content/uploads/ratinmaze_filled_path1.png "ratinmaze_filled_path")](https://www.geeksforgeeks.org/wp-content/uploads/ratinmaze_filled_path1.png)

Following is the solution matrix (output of program) for the above input matrx.

{1, 0, 0, 0}
{1, 1, 0, 0}
{0, 1, 0, 0}
{0, 1, 1, 1}
All enteries in solution path are marked as 1.
