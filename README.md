
# DAA (TA2) 

Generate a number "n" between [5-10], create a matrix of size (n x n)

Populate the locations with "0" and "1"

Apply logic to declare: 
1. If the complete graph is cyclic.
2. If only part of the graph is cyclic. 
3. The cycle in terms of vertices. 

#### Constraint: The cycle should be of minimum "3" vertices or maximum "n" vertices.

## Explanation

By using random.randint() we get a random number between the ranges 5 and 10. This number is assigned to the variable "n" which is the size of the matrix.

Using the NumPy library and the random.randint() method again, we populated a (n x n) matrix, randomly with only 0 and 1 values.

Inorder to convert this matrix into a graph, we had to first convert it into an Adjacency List. This step was necessary because the graph that would be formed by the matrix of ramdom 0's and 1's would be directed.

Now this Adjacency List was passed into the actual logic of the program where we were expected to find a cycle. There is a cycle in a graph only if there is a back edge present in teh graph. Depth First Traversal can be used to detect a cycle in a Graph, because DFS for a connected graph produces a tree.

So in this program using DFS, we check if the graph is disconnected and if it happens to be disconnected, then we get the DFS forest and check for a cycle in individual trees by checking the back edges. To detect a back edge we had to keep track of vertices cirrently in the recursion stack of function fot the DFS traversal. We come to the conclusion that the graph has a cycle if a vertex is reached that is already in the recursion stack.

### Steps:
1. Create the graph using the adjacency list.
2. Create a recursive function that initializes the current vertex, visited array, and recursion stack.
3. Mark the current node as visited and also mark the index in the recursion stack.
4. Find all the vertices which are not visited and are adjacent to the current node and recursively call the function for those vertices
    - If the recursive function returns true, return true.
    - If the adjacent vertices are already marked in the recursion stack then return true.
5. Create a wrapper function, that calls the recursive function for all the vertices, and
    - If any function returns true return true.
    - Else if for all vertices the function returns false return false.








## Test Case-1 (No Cycle) 

![No Cycle](https://user-images.githubusercontent.com/107600168/202187205-746ba502-e1e9-47ba-a18d-7b890c7a8fd4.png)

## Test Case-2 (Complete graph is cyclic)

![Complete graph is cyclic](https://user-images.githubusercontent.com/107600168/202187422-f9d82da5-ab97-4dad-8add-53ce89d3a84f.png)

## Test Case-3 (Partial graph is cyclic)

![Partial graph is cyclic](https://user-images.githubusercontent.com/107600168/202187785-c9d3d8d1-1068-4c28-8411-dad08e8528ec.png)

## Author

- [@AaronRocque1182](https://github.com/AaronRocque1182)


