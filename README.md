# 8-puzzle

INTRODUCTION

The 8-puzzle problem is a popular problem since the game was invented. This problem is a problem that attracts the attention of artificial intelligence and computer science. It consists of a 3x3 grid with eight numbered tiles and one empty space. The objective is to move the tiles around the grid to achieve a specific goal state, typically where the tiles are ordered numerically. This problem is a simplified version of the more general n-puzzle problem and serves as a useful model for studying search algorithms.

The A* algorithm is a widely used search algorithm known for its efficiency and optimality in finding the shortest path to a goal state. It employs a heuristic function to estimate the cost from the current state to the goal state, guiding the search process towards the most efficient paths.

This project aims to apply the A* algorithm to solve 8 puzzle problems and analyze its performance. The implementation is done in Java using the Board, Tile, and Eight Puzzle classes provided in the base code.

PROBLEM STATEMENT

The 8-puzzle problem consists of a 3x3 grid containing eight numbered tiles and one empty space. The tiles can be moved horizontally or vertically into the empty space, to reach a specific goal state. The goal state is defined as having the tiles arranged in numerical order from left to right, top to bottom, with the empty space in the bottom-right corner.

The challenge of the 8 puzzle problem lies in finding the most efficient sequence of moves to transition from the initial random state to the target state. This requires exploring various possible situations and choosing the most appropriate path to achieve the goal. In this case, the A* algorithm comes into play.

METHODOLOGY

A* algorithm is used to solve 8 puzzle problems. The purpose of this algorithm is to solve 8 puzzle problems by finding the most efficient and optimal path from the initial starting state of the puzzle to the desired target state. The priorities of the nodes are determined according to the cost function f(n) = g(n) + h(n); where:

•	g(n) is the cost from the start node to the current node n.

•	h(n) is the heuristic estimate of the cost from node n to the goal state.

The Manhattan distance heuristic is used in this implementation, which calculates the sum of the absolute differences between the current positions of the tiles and their goal positions. Briefly, the Manhattan method is calculated by counting the number of moves along the grid in which each tile is shifted from its target position and summing these values over all tiles.

The Java implementation involves three main classes:

•	Board: Represents the state of the puzzle, including the positions of the tiles and the empty space. It provides methods to move the tiles and check if the goal state has been reached.

•	Tile: Represents an individual tile in the puzzle, storing its number and position.

•	Eight Puzzle: Moves the tiles in the puzzle. It creates the mechanics of the puzzle.

IMPLEMENTATION

 The implementation in Java involves several key methods and classes:

•	Board class:

•	getTilesAsArray(): Converts the board state into a 2D array for easy comparison with the goal state.

•	clone(): Creates a deep copy of the board, useful for exploring different move sequences without altering the original board.

•	equals() and hashCode(): Overridden these methods to allow comparison of Board objects based on their tile arrangements. This is important for tracking visited states in the A* algorithm.

•	Tile class:

•	getNumber(): Added a method to return the number on the tile. This is used to convert the board's tiles into a 2D array of integers in the Board class.

•	EightPuzzle class:

•	User choice mechanism: Added a simple menu that lets the user choose between having the A* algorithm solve it automatically or solving the puzzle manually.

•	solveAutomatically(): Added a method that solves the puzzle automatically using the A* algorithm. It prints the solution steps and updates the board to reflect each move.

•	solveManually(): Added a method that allows the user to solve the puzzle manually using the arrow keys. The method updates the board and redraws it after each move until the puzzle is solved.

•	solve(): A* algorithm is implemented in this method. This method uses a priority queue to explore board states in order of their estimated cost to reach the goal. The Manhattan distance is used as the heuristic.

There is also helper methods and classes for the A* algorithm:

•	makeMove(): Applies a move to a given board and returns the resulting board.

•	isGoal(): Checks if a given board is in the goal state.

•	heuristic(): Calculates the Manhattan distance heuristic for a given board.

•	reconstructPath(): Reconstructs the path to the solution from the information stored during the search.

•	oppositeMove(): Returns the opposite of a given move, used in the path reconstruction process.

•	Node(): Represents a node in the A* algorithm, containing a board state and its associated costs (g and h).


RESULT

The A* algorithm successfully solves the 8-puzzle problem, providing a sequence of moves to reach the goal state from an initial random state. The Manhattan distance heuristic effectively guides the search process, allowing the algorithm to find the shortest path to the solution.

For example, let the initial state of the board be as shown below. In this case, the solution would be Up, Left, Down, Right, Down.

    1	3	5
    4	2	0
    7	8	6

The solution is efficient and optimal. This means it uses the lowest possible moves to reach the desired goal state.

DISCUSSION

It is obvious that the A* algorithm is an accurate method for solving the 8 puzzle problem. The Manhattan distance heuristic is particularly well-suited for combinatorial puzzles such as the 8-puzzle problem because it provides a good and accurate estimate of the distance to the target state without any overestimation. Although it provides us with accurate results, there are some limitations. Its limitation is that it does not explicitly address the case where the initial state is unsolvable. In the 8-puzzle problem, not all random initial states are solvable. A future development could include a method to check the solvability of the initial state before attempting to solve the puzzle.

CONCLUSION

This project asked us to solve the n-puzzle with the A* algorithm. N-puzzle is a classic sliding block game that takes place on a k*k grid of tiles, each numbered from 1 to n ((k * k) - 1) (HackerRank, 2015). The goal is to reposition the tiles in their proper order. To solve the n-puzzle problem using the A* algorithm, we need to modify the given code to include the logic for the A* search. The A* algorithm requires a heuristic function to estimate the cost from the current state to the goal state. In this case, we can use the Manhattan distance as the heuristic, which is the sum of the absolute differences between the current positions of the tiles and their goal positions. To make these changes, I worked on the base code given to us.
