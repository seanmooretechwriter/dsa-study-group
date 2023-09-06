This week's topic is Breadth-First Search.

## Breadth-First Search (BFS)

Breadth-First Search (BFS) is a fundamental graph traversal algorithm that explores nodes in layers, starting from the initial node and moving outward to its neighbors before visiting their neighbors. It operates by systematically visiting all nodes at a given level before proceeding to the next level.

### Key Characteristics and Usage

- **Queue-Based Approach**: BFS uses a queue data structure to maintain the order of nodes to be visited. This ensures that nodes are visited in the order of their proximity to the starting node, allowing BFS to guarantee the shortest path to a target node in an unweighted graph.

- **Completeness**: BFS is a complete algorithm, meaning it will always find a target node if it exists in the graph. It systematically explores all possible paths in a breadth-first manner.

- **Connected Components**: In undirected graphs, BFS can be used to determine connected components, helping identify groups of nodes that are connected to each other.

- **Memory Usage**: While BFS is powerful in finding shortest paths and exploring connected components, it tends to be less memory-efficient than Depth-First Search (DFS) because it requires storing all neighboring nodes at each level in the queue.

- **Common Applications**: BFS is commonly used in algorithms related to graphs, such as finding the shortest path between two nodes, solving puzzles, and traversing a tree or graph level by level. It serves as a foundational algorithm in computer science and forms the basis for more advanced graph algorithms.

- **Iterative or Recursive**: BFS can be implemented either iteratively, using a queue, or recursively. The iterative approach is more common in practice due to its efficiency and simplicity.

BFS is a versatile and widely used algorithm for solving various graph-related problems. Its ability to find the shortest path makes it invaluable in applications like route planning, network analysis, and more.

### Comparison with Depth-First Search (DFS)

 - Traversal Order: Unlike DFS, which explores nodes in a depth-first manner, BFS traverses nodes in a breadth-first order, visiting all neighboring nodes before diving deeper.

 - Speed: BFS is generally slower when compared to DFS in various scenarios, particularly when finding the shortest path is not a priority. DFS can be faster in situations where you don't need to explore all possible paths exhaustively.

 - Memory Usage: DFS tends to consume more memory when used with recursion due to its call stack, while BFS is memory-efficient and preferable for shallow graphs or trees.

 - Completeness: Both DFS and BFS are complete algorithms, meaning they will eventually find a target node if it exists. However, the time taken to locate the target may differ, with DFS possibly taking less time in certain cases.

 - Application-Specific: The choice between DFS and BFS should align with the specific problem at hand. DFS is well-suited for finding the shortest path and can be adapted for tasks like topological sorting, cycle detection, and depth-first traversal of trees and graphs. Conversely, BFS is more appropriate for tasks where breadth-first exploration is required.


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

**Resources**
MIT DSA lecture on BFS.

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-9-breadth-first-search/

Several Grokking the Coding Interview patterns involve or are about Breadth-First Search (BFS) and related concepts. 

Tree Breadth-First Search (BFS):

This pattern focuses on traversing a binary tree in a breadth-first manner, level by level. It involves using a queue to process nodes at each level.

Problems like "Binary Tree Level Order Traversal," "Minimum Depth of Binary Tree," and "Binary Tree Zigzag Level Order Traversal" fall under this pattern.

Graph Breadth-First Search:

This pattern extends BFS to traverse graphs, not just trees. It involves maintaining a visited set or array to avoid revisiting nodes and using a queue for traversal.
Problems like "Breadth-First Search," "Word Ladder," and "Bipartite Graph" can be solved using this pattern.

Topological Sort (Graph):

This pattern is a variant of BFS that helps solve directed graph problems where we need to determine a valid order of tasks or prerequisites.

The "Topological Sort" pattern includes problems like "Course Schedule," "Alien Dictionary," and "Task Scheduling."

Connect Level Order Siblings:

This pattern is about connecting the sibling nodes of a tree level by level, akin to BFS traversal.
The "Connect All Level Order Siblings" problem fits this pattern.

These patterns cover a range of problems involving tree and graph traversal, shortest paths, and topological ordering. While some are directly related to BFS, others incorporate BFS-like ideas to efficiently solve problems.

LeetCode problems best solved with BFS

Binary Tree Level Order Traversal (Problem #102) 

[https://leetcode.com/problems/binary-tree-level-order-traversal/](https://leetcode.com/problems/binary-tree-level-order-traversal/)
    
Maximum Depth of Binary Tree (Problem #104) 

[https://leetcode.com/problems/maximum-depth-of-binary-tree/](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
    
Minimum Depth of Binary Tree (Problem #111) 

[https://leetcode.com/problems/minimum-depth-of-binary-tree/](https://leetcode.com/problems/minimum-depth-of-binary-tree/)
    
Word Ladder (Problem #127) 

[https://leetcode.com/problems/word-ladder/](https://leetcode.com/problems/word-ladder/)
    
Binary Tree Zigzag Level Order Traversal (Problem #103) 

[https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)
    
Course Schedule (Problem #207) 

[https://leetcode.com/problems/course-schedule/](https://leetcode.com/problems/course-schedule/)
    
Alien Dictionary (Problem #269) 

[https://leetcode.com/problems/alien-dictionary/](https://leetcode.com/problems/alien-dictionary/)
    
Bipartite Graph (Problem #785) 

[https://leetcode.com/problems/is-graph-bipartite/](https://leetcode.com/problems/is-graph-bipartite/)
    
Shortest Path in Binary Matrix (Problem #1091) 

[https://leetcode.com/problems/shortest-path-in-binary-matrix/](https://leetcode.com/problems/shortest-path-in-binary-matrix/)
    
Open the Lock (Problem #752) 

[https://leetcode.com/problems/open-the-lock/](https://leetcode.com/problems/open-the-lock/)
    
Rotting Oranges (Problem #994) 

[https://leetcode.com/problems/rotting-oranges/](https://leetcode.com/problems/rotting-oranges/)
    
Number of Islands (Problem #200) 

[https://leetcode.com/problems/number-of-islands/](https://leetcode.com/problems/number-of-islands/)
    
Jump Game IV (Problem #1345) 

[https://leetcode.com/problems/jump-game-iv/](https://leetcode.com/problems/jump-game-iv/)
    
Perfect Squares (Problem #279) 

[https://leetcode.com/problems/perfect-squares/](https://leetcode.com/problems/perfect-squares/)
    
Is Graph Bipartite? (Problem #785) 

[https://leetcode.com/problems/is-graph-bipartite/](https://leetcode.com/problems/is-graph-bipartite/)
    
Snake and Ladders (Problem #909) 

[https://leetcode.com/problems/snakes-and-ladders/](https://leetcode.com/problems/snakes-and-ladders/)
    
Cousins in Binary Tree (Problem #993) 

[https://leetcode.com/problems/cousins-in-binary-tree/](https://leetcode.com/problems/cousins-in-binary-tree/)
    
The Maze II (Problem #505) 

[https://leetcode.com/problems/the-maze-ii/](https://leetcode.com/problems/the-maze-ii/)
    
The Maze III (Problem #499) 

[https://leetcode.com/problems/the-maze-iii/](https://leetcode.com/problems/the-maze-iii/)
    
Cheapest Flights Within K Stops (Problem #787) 

[https://leetcode.com/problems/cheapest-flights-within-k-stops/](https://leetcode.com/problems/cheapest-flights-within-k-stops/)

**Solution**

```
/**
 * 
 * 1.) The function minimumDepthOfBinaryTree takes a treeRoot as input, which is the 
 * root node of a binary tree.
 * 
 * 2.) The code checks if the treeRoot is falsy, which means the tree is empty. In that 
 * case, it returns 0, indicating a depth of 0. 
 * 
 * 3.) treeDepth is used to keep track of the current depth of traversal.
 * 
 * 4.) The treeLevelQueue is initialized with the treeRoot. This queue will be used for a 
 * Breadth-First Search (BFS) traversal of the tree.
 * 
 * 5.) The main while loop runs as long as there are nodes in the treeLevelQueue.
 * 
 * 6.) Inside the loop, the treeDepth is incremented for each level.
 * 
 * 7.) The number of nodes at the current level is stored in numberOfNodesAtCurrentLevel.
 * 
 * 8.) A nested loop runs for each node at the current level.
 * 
 * 9.) The front node is dequeued from the treeLevelQueue using shift() and stored 
 * in currentNode.
 * 
 * 10.) If the currentNode is a leaf node (both left and right children are null), the 
 * function returns treeDepth. This is because the minimum depth of the tree has 
 * been found.
 * 
 * 11.) If the currentNode has a left child, it's enqueued in the treeLevelQueue.
 * 
 * 12.) If the currentNode has a right child, it's also enqueued in the treeLevelQueue.
 * 
 * 13.) The loop continues until all nodes at the current level are processed.
 * 
 * 14.) The process continues for the next levels until the treeLevelQueue becomes empty.
 * 
 * 15.) If the function completes without returning earlier, it implies an invalid 
 * tree structure.

 * In this code, BFS is used to traverse the binary tree level by level. The queue 
 * (treeLevelQueue) holds the nodes at the current level, and child nodes are enqueued 
 * to be processed in the next level. The treeDepth variable keeps track of the current 
 * level, and the traversal continues until a leaf node is encountered, at which point 
 * the depth is returned. This code snippet essentially finds the minimum depth of a 
 * binary tree using BFS traversal.
 * 
 */

const minimumDepthOfBinaryTree = treeRoot => {
  if (!treeRoot) {
    return 0 // If the tree is empty, depth is 0
  }

  let treeDepth = 0
  const treeLevelQueue = [treeRoot] // Initialize a queue with the root node

  while (treeLevelQueue.length > 0) {
    treeDepth++ // Increment depth for each level
    const numberOfNodesAtCurrentLevel = treeLevelQueue.length // Number of nodes at the current level

    // Traverse the nodes at the current level
    for (let i = 0; i < numberOfNodesAtCurrentLevel; i++) {
      const currentNode = treeLevelQueue.shift() // Dequeue the front node

      // If the current node is a leaf node, return the depth
      if (!currentNode.left && !currentNode.right) {
        return treeDepth
      }

      // Enqueue the child nodes for the next level
      if (currentNode.left) {
        treeLevelQueue.push(currentNode.left)
      }
      if (currentNode.right) {
        treeLevelQueue.push(currentNode.right)
      }
    }
  }
  // This line should never be reached for valid binary trees
}

// Example usage
const root = new TreeNode(
  3,
  new TreeNode(9),
  new TreeNode(20, new TreeNode(15), new TreeNode(7))
)

log('minimumDepthOfBinaryTree(', root, ')): ', minimumDepthOfBinaryTree(root)) // Output: 2

// Example usage 1
const root1 = new TreeNode(
  1,
  new TreeNode(
    2,
    new TreeNode(
      3,
      new TreeNode(4, new TreeNode(5), new TreeNode(6)),
      new TreeNode(7, new TreeNode(8), new TreeNode(9))
    ),
    new TreeNode(
      10,
      new TreeNode(11, new TreeNode(12), new TreeNode(13)),
      new TreeNode(14, new TreeNode(15), new TreeNode(16))
    )
  ),
  new TreeNode(
    17,
    new TreeNode(
      18,
      new TreeNode(19, new TreeNode(20), new TreeNode(21)),
      new TreeNode(22, new TreeNode(23), new TreeNode(24))
    ),
    new TreeNode(
      25,
      new TreeNode(26, new TreeNode(27), new TreeNode(28)),
      new TreeNode(29, new TreeNode(30), new TreeNode(31))
    )
  )
)

log('minimumDepthOfBinaryTree(', root1, ')): ', minimumDepthOfBinaryTree(root1)) // Output: 4

// Example usage 2
const root2 = new TreeNode(
  50,
  new TreeNode(
    30,
    new TreeNode(
      20,
      new TreeNode(10, new TreeNode(5), new TreeNode(15)),
      new TreeNode(25, new TreeNode(22), new TreeNode(27))
    ),
    new TreeNode(
      40,
      new TreeNode(35, new TreeNode(33), new TreeNode(37)),
      new TreeNode(45, new TreeNode(42), new TreeNode(47))
    )
  ),
  new TreeNode(
    70,
    new TreeNode(
      60,
      new TreeNode(55, new TreeNode(53), new TreeNode(57)),
      new TreeNode(65, new TreeNode(63), new TreeNode(67))
    ),
    new TreeNode(
      80,
      new TreeNode(75, new TreeNode(73), new TreeNode(77)),
      new TreeNode(90, new TreeNode(85), new TreeNode(95))
    )
  )
)

log('minimumDepthOfBinaryTree(', root2, ')): ', minimumDepthOfBinaryTree(root2)) // Output: 3
```

