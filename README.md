# A-star-search-program

##### CS 461
##### Spring 2021
##### Program 1
##### Due Sunday night, Feb 21

Your first programming assignment uses guided search to solve a game problem.

THE PROBLEM:

Consider the 8-puzzle: 8 tiles each numbered 1-8 on a 3x3 grid, with one space empty. Any adjacent
tile can be moved into the empty square (in effect swapping the locations of that tile and the empty
square). This can be done by moving an adjacent tile vertically or horizontally (not diagonally). Thus
the number of possible moves is at least 2 (if the empty square is in a corner) and at most 4 (if it’s in
the center). The goal is to begin with some arbitrary arrangement and end with the tiles in the following
arrangement:

123

456

78E

where ‘E’ denotes the empty square.
One complication is that permutations of the game board fall into 2 disjoint sets of odd or even parity,
only one of which can reach the goal. Thus, half of all possible tile arrangements cannot lead to a
solution. (These states aren’t reachable by a physical puzzle.) Your program must correctly detect
whether a solution is possible or not. You can either do this by finding the parity (plenty of sources
online about how to do that), or by brute-force of directly showing that no solution exists (simpler, but
slower).

Your input file is a simple text file. The first element, on a line by itself, is the number of puzzles
contained in the file. After that will be the specified number of puzzles in the above format (3 lines of
3 characters each, each character will be a digit 1-8 or an upper case ‘E’). Each puzzle is separated
from the next by a blank line. Your program will be tested on a different data file with the same format.
Given a puzzle, your program must find a solution if it exists. You should use A* search to find the
solution. Recall that A* finds the shortest path by repeatedly selecting the best candidate, determined
by which has the lowest value for

f (n)=g(n)+h(n)

where g(n) is the actual distance from the start state to that node, and h(n) is the heuristic (estimated)
cost from that node to the goal. For your heuristic function h(x), use the sum of the Manhattan (cityblock) distances for each tile from where it needs to be.
 For each puzzle, your program should print a list of the moves that should be made to reach the
solution. If there is no solution for a puzzle, your program should print a short message to that effect.

Programming notes:

• Your program may be in Python, Java, C, C++, or C#.

• Here’s a useful statistic: The longest possible shortest path for a solvable 8-puzzle has length
31. 

• You will probably want to avoid any loops (returning to a state you have already visited) in your
search.

• Note that the shortest path may not be unique; there may be more than one solution with the
same (minimum) length. Everyone’s code should agree on which puzzles are unsolvable, and
the length of the shortest path for those having a solution. (The code you write should be your
own, of course, but comparing results with classmates is fine.) 
