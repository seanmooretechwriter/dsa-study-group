This week's topic is Depth-First Search.

## Depth-First Search (DFS)

Depth-First Search serves as a foundational algorithm in computer science and is the basis for various search and traversal algorithms. It excels in scenarios where systematic exploration of a graph's structure is required, making it invaluable in applications like maze-solving, puzzle-solving, and more.

### Key Characteristics and Usage

- **Depth-First Exploration**: DFS explores nodes by following a single branch as deeply as possible before backtracking to explore other branches. It starts at the initial node and dives deep into each branch, only backtracking when no unvisited nodes are left.

- **Stack or Recursion**: DFS can be implemented using either a stack or recursion to keep track of nodes. This stack-based approach allows DFS to explore the depth of the graph effectively.

- **Shortest Path Considerations**: Unlike BFS, DFS does not guarantee the shortest path to a target node, especially in unweighted graphs. Its focus is on systematic exploration rather than finding the shortest path.

- **Completeness**: DFS is a complete algorithm, meaning it will eventually find a target node if it exists in the graph. However, the time taken to find the target may vary based on the search strategy.

- **Memory Efficiency**: DFS is generally more memory-efficient than BFS because it doesn't require storing all neighboring nodes at once. Instead, it keeps track of a stack of nodes, which is memory-efficient, especially for deep graphs.

- **Applications**: DFS is commonly used for tasks like topological sorting, cycle detection, and depth-first traversal of trees and graphs. It is particularly elegant for tree structures.

- **Iterative and Recursive**: DFS can be implemented both iteratively (using a stack) and recursively. The recursive approach is often preferred for trees due to its elegance.

Depth-First Search (DFS) is a fundamental graph traversal algorithm that operates differently than Breadth-First Search (BFS). While BFS explores nodes in layers, DFS takes a different approach.

### Comparison with Breadth-First Search (BFS)

- **Traversal Order**: DFS explores nodes in a depth-first order, diving as deeply as possible before backtracking. In contrast, BFS explores nodes in a breadth-first order, moving level by level.
- **Speed**: While BFS is often faster when searching for the shortest path, DFS excels in certain scenarios, especially when you want to explore all possibilities or when the depth of the tree or graph is limited.
- **Memory Usage**: BFS typically consumes more memory due to its queue-based approach, whereas DFS is memory-efficient, making it suitable for deep graphs.
- **Completeness**: Both DFS and BFS are complete algorithms, meaning they will eventually find a target node if it exists in the graph or tree. However, the time it takes to find the target may vary.
- **Application-Specific**: The choice between BFS and DFS depends on the specific problem and its requirements. BFS is well-suited for finding the shortest path, while DFS is preferred for tasks like topological sorting, cycle detection, and depth-first traversal of trees and graphs.

DFS serves as a foundational algorithm in computer science, forming the basis for various search and traversal algorithms.

## Weekly Problem
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

## Resources

MIT DSA lecture on DFS.

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-10-depth-first-search/

**DFS vs. BFS visualizer**

https://codepen.io/mit6006/full/dgeKEN

**Grokking the Coding Interview patterns**

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

## DFS LeetCode problems

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

## Solution

**DFS using stack:**

```
/**
 * 1.) The function minDepthDFSStack takes a root node as input, which is the
 *     root of a binary tree.
 * 
 * 2.) It first checks if the root is falsy (null or undefined), which signifies
 *     an empty tree. In such cases, it returns 0 to indicate a depth of 0.
 * 
 * 3.) The stack data structure is used for a Depth-First Search (DFS) traversal
 *     of the binary tree. It initializes with an object containing the root node
 *     and a depth of 1.
 * 
 * 4.) The variable 'min' is initialized with Infinity to keep track of the minimum
 *     depth found during traversal.
 * 
 * 5.) The while loop continues as long as there are nodes in the stack to process.
 * 
 * 6.) In each iteration of the loop, a node and its depth are popped from the stack.
 * 
 * 7.) If the node is a leaf node (both left and right children are null), the
 *     depth is compared with the current minimum depth ('min'), and the minimum
 *     depth is updated accordingly.
 * 
 * 8.) If the node has a right child, it is pushed onto the stack with an increased
 *     depth.
 * 
 * 9.) If the node has a left child, it is pushed onto the stack with an increased
 *     depth. Note that the left child is pushed after the right child, ensuring
 *     a Depth-First traversal.
 * 
 * 10.) The loop continues until all nodes in the stack are processed.
 * 
 * 11.) Finally, the function returns the minimum depth found during traversal.
 * 
 * 12.) For an empty tree, the function returns 0.
 * 
 * In this code, DFS is used to traverse the binary tree depth-first. The stack
 * data structure stores nodes to be processed, and child nodes are pushed onto
 * the stack for deeper traversal. The minimum depth is determined by finding the
 * first leaf node encountered, and this value is updated as needed.
 */

const minDepthDFSStack = root => {
  if (!root) {
    return 0
  }
  const stack = [{ node: root, depth: 1 }]
  let min = Infinity
  while (stack.length > 0) {
    const { node, depth } = stack.pop()
    if (!node.left && !node.right) {
      min = Math.min(min, depth)
    }
    if (node.right) {
      stack.push({ node: node.right, depth: depth + 1 })
    }
    if (node.left) {
      stack.push({ node: node.left, depth: depth + 1 })
    }
  }
  return min
}

log('minDepthDFSStack(): ', minDepthDFSStack(tree))

```

**DFS using recursion (stack[trace] in memory):**

```
function minDepthDFS (root) {
  if (!root) {
    return 0 // Base case: empty tree has depth 0
  }

  if (!root.left && !root.right) {
    return 1 // Node with no children has depth 1
  }

  let min = Infinity

  if (root.left) {
    min = Math.min(min, minDepthDFS(root.left))
  }

  if (root.right) {
    min = Math.min(min, minDepthDFS(root.right))
  }

  return min + 1 // Add 1 to account for the current node
}

log('minDepthDFS: ', minDepthDFS(tree))

```

**Tree code to call DFS functions:**

```

const tree = new TreeNode(3)
tree.left = new TreeNode(9)
tree.right = new TreeNode(20)
tree.right.left = new TreeNode(15)
tree.right.right = new TreeNode(7)

```