# TSP Solver

Adapted from dminshin's TSP solver https://github.com/dmishin/tsp-solver

The algorithm first takes in a filename and reads the file line by line and adds each line as a list inside a list. Once
the matrix has been read, the algorithm then finds the lowest cost node to travel to from the first node. This is the
startpoint and the endpoint. The algorithm then calls the solver method with the matrix list and also passes in the
start and end points. The algorithm then checks if the matrix is left
triangular (https://en.wikipedia.org/wiki/Triangular_matrix) and if it's a loop or not. The algorithm then proceeds to
use a greedy solution where each vertex belongs to its own path fragment. The algorithm then finds the two nearest
disconnected path fragments and connects the two fragments together. The algorithm repeats this until there are at least
2 path fragments. The algorithm then joins these 2 path fragments to form the path.

However, this is far from optimal which the algorithm then seeks to optimize the solution the greedy solution has
produced. The algorithm attempts to optimize the solution by rearranging the points in the solution. The algorithm does
this by selecting 4 points in the path and determines the distance between each pair of points within the set of four
which is calculated as ``ds(a, b) + ds(c, d) - (ds(a, c) + ds(b, d))``. The algorithm then rearranges the path fragments
within the path if the distance is >0. The reason why 0 is used as this determines if this already an optimal ordering
of the pairs.

After the optimizations have been done, the program then takes the solution which is stored as a list and prints out
each node within the solution in the order its visited. The algorithm then calculates the total length of the path given
the initial matrix, by iterating through the initial matrix and summing up the cost of traversing the path.




