# **Graph Coloring Analysis Project**:

## Description:

​		This project looks at implementing an algorithm in multiple ways to solve a problem, analyzing the algorithms’ implementations for running time, and testing and your implementations to show they match your analysis. The project also looks at testing to determine how well the multiple implementations solve the problem.

​		The particular problem for the project is scheduling via graph coloring. For the first part of the project, different conflict graphs which can represent real world problems will be created and saved in files. For the second part of the problem, carious coloring orders will be implemented and analyzed for runtime efficiency and coloring efficiency. These efficiencies are intimately related to the data structures used for both the input graph data and the intermediate data necessary for the ordering and coloring algorithms. 

## Part 1. 

### Purpose:

​		Part 1 of the project is used to create different conflict graphs. Conflict graphs represent real-world problems. For example, one may be thought of as a set of vertices representing courses that students may take. An edge is present between two vertices (courses) in the graph if a student is taking both courses. This edge indicates they may not be scheduled at the same time. Once the graph is colored, the color of each vertex represents its timeslot and the total number of colors would represent the total number of required timeslots for that coloring. The vertices which have a conflict in this project will be determined based on graph types and a random number generator with different distributions.

### Input:

·    V = Number of vertices. (MAX = 10,000)

·    E = Number of conflicts between pairs of vertices for random graphs. (MAX = 2,000,000)

·    G = COMPLETE | CYCLE | RANDOM (with DIST below)

·    DIST = UNIFORM | SKEWED | YOURS

### Output:

·    E[] = adjacency list of distinct course conflicts (length = 2M)

·    P[] = Pointer for each course I, 1 <= I <= N denoting the starting point in E[] of the list of courses in conflict with course I. That is, the conflicts for course I are indicated in locations E[P[I]], E[P[I]+1], …, E[P[I+1]-1]. 

### Procedure:

​		The vertices for conflicts shall be chosen using a pseudo random number generator according to one of the specified distributions. These distributions are uniform, skewed, and one other of your choosing. The uniform distribution assumes each vertex is equally likely to be chosen for a conflict. The skewed distribution assumes lower numbered vertices are linearly more likely than higher numbered vertices. Graphs of these distributions are shown below.

![image-20230501223520228](/Users/charles/Library/Application Support/typora-user-images/image-20230501223520228.png)

## Part 2. 

### Input:

·    A file like the output in Part 1:

·    P[] = Pointer for each course I, 1 <= I <= N denoting the starting point in E[] of the list of courses in conflict with course I. That is, the conflicts for course I are indicated in locations E[P[I]], E[P[I]+1], …, E[P[I+1]-1]. 

·    E[] = adjacency list of distinct course conflicts (length = 2M)

### Output:

·    For each vertex the color, original degree, (and degree when deleted for the smallest last ordering). These should be printed in the order colored.

·    Total number of colors used, the average original degree, and the maximum “degree when deleted” value for the smallest last ordering, and the size of the terminal clique for the smallest last ordering.

·    Any other summary data you wish to include.

·    An output file of the format where each line is VERTEX_NUMBER, COLOR_NUMBER

### Procedure:

​		Using six different methods for ordering the vertices in the graph. One method all students are to use is the smallest last ordering given below, another is the smallest original degree last and the final one for all students is a uniform random ordering. The other orderings are of your own choosing. Then you are to assign the minimum color to each vertex in the order determined by each ordering so that it doesn’t conflict with the other vertices already colored.