This week's topic is Depth-First Search.

## Depth-First Search (DFS)

DFS is a fundamental graph traversal algorithm used to explore and navigate through a graph or tree data structure. It operates by visiting a starting node and then exhaustively exploring as far as possible along each branch before backtracking to explore other branches. This process continues until all reachable nodes are visited, resulting in a top-down, depth-first exploration of the graph's structure.

DFS is a versatile algorithm with various applications, including graph traversal, topological sorting, pathfinding, and solving puzzles. It can be implemented using either a stack or recursion to keep track of nodes to be visited. One of its key advantages is its memory efficiency, as it doesn't require storing all neighboring nodes at once.

**Comparison with Breadth-First Search (BFS)**

- **Traversal Order**: DFS explores nodes in a depth-first order, diving as deeply as possible before backtracking. In contrast, BFS explores nodes in a breadth-first order, moving level by level.
- **Speed**: While BFS is often faster when searching for the shortest path, DFS excels in certain scenarios, especially when you want to explore all possibilities or when the depth of the tree or graph is limited.
- **Memory Usage**: BFS typically consumes more memory due to its queue-based approach, whereas DFS is memory-efficient, making it suitable for deep graphs.
- **Completeness**: Both DFS and BFS are complete algorithms, meaning they will eventually find a target node if it exists in the graph or tree. However, the time it takes to find the target may vary.
- **Application-Specific**: The choice between BFS and DFS depends on the specific problem and its requirements. BFS is well-suited for finding the shortest path, while DFS is preferred for tasks like topological sorting, cycle detection, and depth-first traversal of trees and graphs.

DFS serves as a foundational algorithm in computer science, forming the basis for various search and traversal algorithms.


**Weekly Problem**
Minimum Depth of Binary Tree (LC #111)

Given a binary tree, find its minimum depth.

The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.

Note: A leaf is a node with no children.

Example 1:

Input: root = [3,9,20,null,null,15,7]
Output: 2

Example 2:

Input: root = [2,null,3,null,4,null,5,null,6]
Output: 5

Constraints:

The number of nodes in the tree is in the range [0, 105].
-1000 <= Node.val <= 1000

https://leetcode.com/problems/minimum-depth-of-binary-tree/

**Resources**
MIT DSA lecture on DFS.

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-10-depth-first-search/

Several Grokking the Coding Interview patterns involve or are about Depth-First Search (DFS) and related concepts. 

Depth-First Search (DFS):

This pattern involves recursive or iterative depth-first traversal of a data structure, often a tree or a graph, to explore all possible paths or to perform specific tasks at each node.
LeetCode Question in Grokking: "Binary Tree Path Sum" (Question #5)

Depth-First Search (DFS) with Backtracking:

This pattern involves DFS with backtracking, which is used to find all possible solutions or combinations by exploring different choices and undoing them when necessary.
LeetCode Question in Grokking: "Subsets" (Question #1)

Topological Sort:

This pattern is used to perform topological sorting, which is mainly applied to directed graphs to find a linear ordering of nodes such that for every directed edge (u, v), node u comes before node v in the ordering.
LeetCode Question in Grokking: "Tasks Scheduling" (Question #2)

Depth-First Search (DFS) for Trees:

This pattern focuses on DFS techniques specifically designed for trees, including concepts like finding the maximum depth of a binary tree, validating a binary search tree (BST), etc.
LeetCode Question in Grokking: "Tree Depth-First Search" (Question #3)

Subsets and Permutations:

This pattern involves finding all subsets or permutations of a given set, which often requires using DFS to generate all possible combinations.
LeetCode Question in Grokking: "Subsets" (Question #1)

Depth-First Search (DFS) with Memoization:

This pattern combines DFS with memoization to optimize recursive algorithms by caching the results of subproblems to avoid redundant calculations.
LeetCode Question in Grokking: "Staircase" (Question #4)

Cyclic Graph Detection:

This pattern focuses on detecting cycles in graphs using DFS to determine whether a given graph is acyclic or has cycles.
LeetCode Question in Grokking: "Graph Cycle" (Question #6)

LeetCode problems best solved with DFS

Number of Islands (LeetCode #200)

https://leetcode.com/problems/number-of-islands/

Word Search (LeetCode #79)

https://leetcode.com/problems/word-search/

Generate Parentheses (LeetCode #22)

https://leetcode.com/problems/generate-parentheses/

Clone Graph (LeetCode #133)

https://leetcode.com/problems/clone-graph/

Graph Valid Tree (LeetCode #261)

https://leetcode.com/problems/graph-valid-tree/

Course Schedule II (LeetCode #210)

https://leetcode.com/problems/course-schedule-ii/

Surrounded Regions (LeetCode #130)

https://leetcode.com/problems/surrounded-regions/

Maximum Depth of Binary Tree (LeetCode #104)

https://leetcode.com/problems/maximum-depth-of-binary-tree/

**Solution**

======== UPDATE FOR DFS ==========
