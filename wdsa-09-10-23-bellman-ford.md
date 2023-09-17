This week's topic is Shortest weighted paths & Bellman Ford.

## Shortest Weighted Paths:

- **Definition**: Shortest weighted paths refer to finding the most efficient routes between points in a graph where each edge has a weight or cost associated with it. These paths aim to minimize the total weight or cost between two points.

- **Use Case**: Imagine you have a network of cities connected by roads, and each road has a different length or travel time. Shortest weighted paths can help you find the quickest or shortest route from one city to another, taking into account the varying distances or travel times on the roads.

## Bellman-Ford Algorithm:

- **Inventors and Origin**: The Bellman-Ford algorithm is named after its inventors, Richard Bellman and Lester Ford. Richard Bellman developed the algorithm in the 1950s as part of his work in dynamic programming and operations research.

- **Year of Invention**: The algorithm was developed in the 1950s.

- **Purpose**: The Bellman-Ford algorithm was designed to find the shortest paths in a weighted graph, even when the graph contains negative-weight edges. This is a crucial capability because it addresses a limitation of the earlier Dijkstra's algorithm, which could not handle negative-weight edges.

- **Languages and Usage**: Initially, the Bellman-Ford algorithm was implemented in mathematical and computational research. It was later adapted for use in various programming languages such as Fortran, C, and more, making it widely accessible for solving real-world problems.

## Real-World Scenarios:

1. **Network Routing**: In computer networks, the Bellman-Ford algorithm can be used to find the shortest path for data packets to travel from one node to another, considering varying link costs or congestion.

2. **Flight Scheduling**: In the airline industry, the algorithm can help airlines determine the most cost-efficient routes for flights, considering factors like distance, fuel costs, and air traffic.

## Historical Context:

Before the Bellman-Ford algorithm, the primary method for finding shortest paths in graphs was Dijkstra's algorithm, developed by Edsger Dijkstra in 1956. However, Dijkstra's algorithm had a limitation: it could not handle graphs with negative-weight edges. This limitation was a significant problem because real-world scenarios often involve situations where some paths have negative weights, such as cost savings or shortcuts.

The Bellman-Ford algorithm was developed to overcome this limitation. It works for graphs with negative-weight edges and can also detect the presence of negative-weight cycles, providing valuable information about the graph's structure.

In summary, the Bellman-Ford algorithm was created to address the shortcomings of earlier algorithms like Dijkstra's when dealing with graphs containing negative-weight edges. It has since found applications in various fields where finding the shortest paths with varying costs is essential.

## Weekly Problem

Find the City With the Smallest Number of Neighbors at a Threshold Distance (LC #1334)

There are n cities numbered from 0 to n-1. Given the array edges where edges[i] = [fromi, toi, weighti] represents a bidirectional and weighted edge between cities fromi and toi, and given the integer distanceThreshold.

Return the city with the smallest number of cities that are reachable through some path and whose distance is at most distanceThreshold, If there are multiple such cities, return the city with the greatest number.

Notice that the distance of a path connecting cities i and j is equal to the sum of the edges' weights along that path.

Example 1:

Input: n = 4, edges = [[0,1,3],[1,2,1],[1,3,4],[2,3,1]], distanceThreshold = 4

Output: 3

Explanation: The figure above describes the graph. 

The neighboring cities at a distanceThreshold = 4 for each city are:

City 0 -> [City 1, City 2] 
City 1 -> [City 0, City 2, City 3] 
City 2 -> [City 0, City 1, City 3] 
City 3 -> [City 1, City 2] 

Cities 0 and 3 have 2 neighboring cities at a distanceThreshold = 4, but we have to return city 3 since it has the greatest number.

Example 2:

Input: n = 5, edges = [[0,1,2],[0,4,8],[1,2,3],[1,4,2],[2,3,1],[3,4,1]], distanceThreshold = 2

Output: 0

Explanation: The figure above describes the graph. 

The neighboring cities at a distanceThreshold = 2 for each city are:

City 0 -> [City 1] 
City 1 -> [City 0, City 4] 
City 2 -> [City 3, City 4] 
City 3 -> [City 2, City 4]
City 4 -> [City 1, City 2, City 3] 

The city 0 has 1 neighboring city at a distanceThreshold = 2.

Constraints:

2 <= n <= 100
1 <= edges.length <= n * (n - 1) / 2
edges[i].length == 3
0 <= fromi < toi < n
1 <= weighti, distanceThreshold <= 10^4
All pairs (fromi, toi) are distinct.

https://leetcode.com/problems/find-the-city-with-the-smallest-number-of-neighbors-at-a-threshold-distance/

## Resources

MIT DSA lectures on weighted-shortest-paths & Bellman Ford.

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-11-weighted-shortest-paths/

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/problem-session-5/

https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-12-bellman-ford/

## Bellman Ford LeetCode problems


## Solution

```

/**
 * Bellman-Ford Algorithm:
 *
 * The Bellman-Ford algorithm is used to find the shortest path from a single source
 * vertex to all other vertices in a graph, including graphs with negative-weight
 * edges and negative-weight cycles. Here's how it works:
 *
 * @param {number} n - The number of vertices in the graph.
 * @param {number[][]} edges - An array of edges represented as [u, v, w], where u and v
 *                            are vertices, and w is the edge weight.
 * @param {number} distanceThreshold - The maximum allowed distance between cities.
 * @returns {number} - The city with the smallest number of neighbors at a threshold distance.
 *
 * Algorithm Steps:
 *  1. Initialize a distance matrix with maximum values.
 *  2. Initialize the diagonal with zeros (distance to itself).
 *  3. Populate the distance matrix with edge weights from the input edges.
 *  4. Apply the Bellman-Ford algorithm to find the shortest paths.
 *  5. Iterate through cities and count reachable cities within the threshold.
 *  6. Find the city with the smallest number of reachable neighbors.
 *
 * Time Complexity: O(n^3) - Cubic time complexity, where n is the number of vertices.
 * Space Complexity: O(n^2) - Quadratic space complexity due to the distance matrix.
 *
 * Example:
 * Input: n = 4, edges = [[0,1,3],[1,2,1],[1,3,4],[2,3,1]], distanceThreshold = 4
 * Output: 3
 *
 * This algorithm finds the city with the smallest number of neighbors at a threshold distance.
 */
const findTheCity = (n, edges, distanceThreshold) => {
  // Initialize a distance matrix with maximum values
  const distances = Array(n)
    .fill()
    .map(() => Array(n).fill(Infinity))

  // Initialize the diagonal with zeros (distance to itself)
  for (let i = 0; i < n; i++) {
    distances[i][i] = 0
  }

  // Populate the distance matrix with edge weights
  for (const [u, v, w] of edges) {
    distances[u][v] = w
    distances[v][u] = w
  }

  // Bellman-Ford algorithm to find the shortest paths
  for (let k = 0; k < n; k++) {
    for (let i = 0; i < n; i++) {
      for (let j = 0; j < n; j++) {
        if (distances[i][j] > distances[i][k] + distances[k][j]) {
          distances[i][j] = distances[i][k] + distances[k][j]
        }
      }
    }
  }

  let minCities = n
  let result = -1

  // Iterate through cities and count reachable cities
  for (let i = 0; i < n; i++) {
    let reachableCities = 0
    for (let j = 0; j < n; j++) {
      if (distances[i][j] <= distanceThreshold) {
        reachableCities++
      }
    }
    if (reachableCities <= minCities) {
      minCities = reachableCities
      result = i
    }
  }

  return result
}

let n = 4
let edges = [
  [0, 1, 3],
  [1, 2, 1],
  [1, 3, 4],
  [2, 3, 1]
]
let distanceThreshold = 4

log('findTheCity: ', findTheCity(n, edges, distanceThreshold))

n = 6 // Number of vertices
edges = [
  [0, 1, 3],
  [0, 2, 8],
  [0, 3, 12],
  [1, 2, 2],
  [1, 4, 10],
  [2, 3, 1],
  [2, 5, 5],
  [3, 5, 6],
  [4, 5, 4]
] // Edges represented as [u, v, w], where u and v are vertices, and w is the edge weight.

distanceThreshold = 15 // Threshold distance

const result = findTheCity(n, edges, distanceThreshold)

console.log(
  `The city with the smallest number of neighbors within a threshold of ${distanceThreshold} is City ${result}.`
)

```