---
tags:
  - ai
---


# Artificial Intelligence Systems: Search Algorithms

## Introduction to Search Strategies

Search algorithms are fundamental to Artificial Intelligence, enabling agents to find a path from a start state to a goal state. These strategies are broadly categorized into two types:

### Blind (Uninformed) Strategies

Blind strategies do not use any information about the problem's state space beyond what is needed to systematically explore it. They do not know how close a given state is to the goal.

- **Depth-First Strategy (DFS)**: Explores the deepest node first. It typically uses a stack or recursion.
    - **Pros**: Low memory usage.
    - **Cons**: Can get stuck in deep or infinite paths.
- **Breadth-First Strategy (BFS)**: Explores the shallowest node first. It uses a queue.
    - **Pros**: Complete and optimal (for uniform cost problems).
    - **Cons**: High memory usage.
- **Depth-Limited Strategy (DLS)**: A variation of DFS that imposes a maximum depth limit.
    - **Pros**: Avoids infinite paths.
    - **Cons**: May miss a solution if the depth limit is too small.
- **Iterative-Deepening Strategy (IDS)**: Repeatedly applies DLS with increasing depth limits.
    - **Pros**: Combines DFS's memory efficiency with BFS's completeness. Complete and optimal.
    - **Cons**: Can revisit nodes multiple times.
- **Uniform-Cost Strategy (UCS)**: Expands the node with the lowest path cost. Uses a priority queue.
    - **Pros**: Complete and optimal.
    - **Cons**: Can be slow and memory-intensive.
- **Bidirectional Search Strategy**: Searches simultaneously from the start state forward and from the goal state backward, stopping when the two searches meet.
    - **Pros**: Can be significantly faster than unidirectional searches.
    - **Cons**: Requires the ability to search backward from the goal state.

### Heuristic (Informed) Strategies

Heuristic strategies use additional information about the state space to assess which node is "more promising" than others, guiding the search more efficiently towards the goal. (Note: This lecture focuses on blind strategies, but understanding this distinction is crucial).

## Key Concepts in Blind Search

### Open List (Frontier)

The Open List (or Frontier) stores all states that have been discovered but not yet processed. These are the states the algorithm might explore next. It can be thought of as a "to-do list."

### Closed List

The Closed List stores all states that have already been processed. These states have been fully explored and will not be re-checked. It can be thought of as a "done list."

## Depth-First Strategy (DFS)

DFS explores a path as deeply as possible before backtracking. The "fringe" (or open list) is managed as a stack, meaning new nodes are typically added to the front.

**Example Walkthrough:**

Consider a simple tree where the goal is to reach node `15`.

1. **Start**: Fringe = [1]
2. Expand 1: Fringe = [2, 3] (New nodes added to the front)
3. Expand 2: Fringe = [4, 5, 3]
4. Expand 4: Fringe = [8, 9, 5, 3]
5. Expand 8: Fringe = [9, 5, 3] (Assuming 8 has no children in this simplified view for demonstration)
6. Expand 9: Fringe = [5, 3]
7. Expand 5: Fringe = [10, 11, 3]
8. Expand 10: Fringe = [11, 3]
9. Expand 11: Fringe = [3]
10. Expand 3: Fringe = [6, 7]
11. Expand 6: Fringe = [12, 13, 7]
12. Expand 12: Fringe = [13, 7]
13. Expand 13: Fringe = [7]
14. Expand 7: Fringe = [14, 15] (Assuming 7 expands to 14 and 15)
15. Expand 14: Fringe = [15]
16. Expand 15: Goal reached.

**Open List / Closed List Tracking (Illustrative):**

|Step|Open List (Fringe)|Closed List|
|:--|:--|:--|
|1|[1]|[]|
|2|[2, 3]|[1]|
|3|[4, 5, 3]|[1, 2]|
|4|[8, 9, 5, 3]|[1, 2, 4]|
|5|[9, 5, 3]|[1, 2, 4, 8]|
|6|[5, 3]|[1, 2, 4, 8, 9]|
|7|[10, 11, 3]|[1, 2, 4, 8, 9, 5]|
|8|[11, 3]|[1, 2, 4, 8, 9, 5, 10]|
|9|[3]|[1, 2, 4, 8, 9, 5, 10, 11]|
|10|[6, 7]|[1, 2, 4, 8, 9, 5, 10, 11, 3]|
|11|[12, 13, 7]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6]|
|12|[13, 7]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6, 12]|
|13|[7]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6, 12, 13]|
|14|[14, 15]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6, 12, 13, 7]|
|15|[15]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6, 12, 13, 7, 14]|
|16|[]|[1, 2, 4, 8, 9, 5, 10, 11, 3, 6, 12, 13, 7, 14, 15]|

## Breadth-First Strategy (BFS)

BFS explores all nodes at the current depth level before moving to the next level. The "fringe" is managed as a queue, meaning new nodes are added to the end.

**Example Walkthrough:**

Using the same tree structure as above, aiming for node `15`.

1. **Start**: Fringe = [1]
2. Expand 1: Fringe = [2, 3] (New nodes added to the end)
3. Expand 2: Fringe = [3, 4, 5]
4. Expand 3: Fringe = [4, 5, 6, 7]
5. Expand 4: Fringe = [5, 6, 7, 8, 9]
6. Expand 5: Fringe = [6, 7, 8, 9, 10, 11]
7. Expand 6: Fringe = [7, 8, 9, 10, 11, 12, 13]
8. Expand 7: Fringe = [8, 9, 10, 11, 12, 13, 14, 15]
9. Expand 8: Fringe = [9, 10, 11, 12, 13, 14, 15] (Assuming 8 has no children relevant to path)
10. Expand 9: Fringe = [10, 11, 12, 13, 14, 15]
11. Expand 10: Fringe = [11, 12, 13, 14, 15]
12. Expand 11: Fringe = [12, 13, 14, 15]
13. Expand 12: Fringe = [13, 14, 15]
14. Expand 13: Fringe = [14, 15]
15. Expand 14: Fringe = [15]
16. Expand 15: Goal reached.

**Open List / Closed List Tracking (Illustrative):**

|Step|Open List (Fringe)|Closed List|
|:--|:--|:--|
|1|[1]|[]|
|2|[2, 3]|[1]|
|3|[3, 4, 5]|[1, 2]|
|4|[4, 5, 6, 7]|[1, 2, 3]|
|5|[5, 6, 7, 8, 9]|[1, 2, 3, 4]|
|6|[6, 7, 8, 9, 10, 11]|[1, 2, 3, 4, 5]|
|7|[7, 8, 9, 10, 11, 12, 13]|[1, 2, 3, 4, 5, 6]|
|8|[8, 9, 10, 11, 12, 13, 14, 15]|[1, 2, 3, 4, 5, 6, 7]|
|9|[9, 10, 11, 12, 13, 14, 15]|[1, 2, 3, 4, 5, 6, 7, 8]|
|10|[10, 11, 12, 13, 14, 15]|[1, 2, 3, 4, 5, 6, 7, 8, 9]|
|11|[11, 12, 13, 14, 15]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]|
|12|[12, 13, 14, 15]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]|
|13|[13, 14, 15]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]|
|14|[14, 15]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]|
|15|[15]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]|
|16|[]|[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]|

## Depth-Limited Strategy (DLS)

DLS is Depth-First Search with a cutoff depth, `k`. Nodes are not expanded beyond this depth.

- **Outcomes**:
    - Solution found.
    - Failure (no solution found within the depth limit).
    - Cutoff (search terminated due to depth limit, solution might exist deeper).

## Iterative-Deepening Strategy (IDS)

IDS performs a series of Depth-Limited Searches, incrementing the depth limit `k` with each iteration (e.g., `k=0, 1, 2, 3, ...`).

- This strategy combines the memory efficiency of DFS with the completeness of BFS.

## Bidirectional Search

This strategy involves running two searches simultaneously: one forward from the start state and one backward from the goal state. The search stops when the frontiers of the two searches intersect.

- It can be more efficient because the search space explored is roughly the product of the depths of the two searches, rather than the exponential of the total depth. If both searches have a branching factor of bb and the solution depth is dd, the time complexity is approximately O(bd/2+bd/2)O(bd/2+bd/2), which is significantly better than O(bd)O(bd).

## Uniform-Cost Strategy (UCS)

UCS expands the node with the lowest path cost first. The path cost, denoted as g(N)g(N), is the sum of the costs of all steps from the start node to node NN.

- The fringe is implemented as a priority queue, ordered by the path cost g(N)g(N).
- The first goal state reached is guaranteed to be the minimum-cost solution.

**Example Walkthrough:**

Consider a graph with costs.

Start node S. Goal node G. Edges with costs: S -> A (1), S -> B (5), S -> C (15), A -> D (2), B -> D (2), C -> G (4), D -> G (5).

1. **Initialization**: Fringe = {(S, cost=0)}
2. Expand S: Fringe = {(A, cost=1), (B, cost=5), (C, cost=15)}
3. Expand A (lowest cost): Fringe = {(B, cost=5), (C, cost=15), (D, cost=1+2=3)}
4. Expand D (lowest cost): Fringe = {(B, cost=5), (C, cost=15), (G, cost=3+5=8)}
5. Expand B (lowest cost): Fringe = {(C, cost=15), (G, cost=8), (D, cost=5+2=7)}
    - Note: D is reached again with a higher cost (7) than the previous path (3), so we don't update it if we already have a better path to D. If D was already expanded, we might re-add it if a better path is found. For simplicity here, assume we explore the lowest cost path to D first.
6. Expand G (lowest cost): Goal reached with cost 8.
    - The path is S -> A -> D -> G.

## Evaluating Search Strategies

Search strategies are evaluated based on several criteria:

- **Completeness**: Does the algorithm always find a solution if one exists?
- **Time Complexity**: How many nodes does the algorithm generate and explore? Measured in terms of the branching factor bb and depth dd of the shallowest/least-cost solution, and maximum depth mm.
- **Space Complexity**: What is the maximum number of nodes stored in memory at any given time? Also measured in terms of b,d,mb,d,m.
- **Optimality**: Does the algorithm always find a least-cost solution?

### Complexity Metrics

- bb: Branching factor (average number of successors for a node).
- dd: Depth of the shallowest/least-cost solution.
- mm: Maximum depth of the state space (can be infinite).

## Space & Time Complexity Summary

The Big-O notation (OO) describes the order of growth of time or memory usage as the problem size increases.

### Breadth-First Search (BFS)

- **Time Complexity**: O(bd)O(bd) - Explores all nodes up to depth dd.
- **Space Complexity**: O(bd)O(bd) - Needs to store all nodes at the deepest level.

### Depth-First Search (DFS)

- **Time Complexity**: O(bm)O(bm) - In the worst case, may explore all nodes up to the maximum depth mm.
- **Space Complexity**: O(mb)O(mb) - Stores only one path from the root to depth mm and some siblings, linear growth with depth.

### Depth-Limited Search (DLS)

- **Time Complexity**: O(bK)O(bK) - Explores all nodes up to the cutoff depth KK.
- **Space Complexity**: O(Kb)O(Kb) - Similar to DFS, memory grows linearly with the depth limit KK.

### Iterative-Deepening Search (IDS)

- **Time Complexity**: O(bd)O(bd) - Although nodes are revisited, the total number of nodes expanded is comparable to BFS.
- **Space Complexity**: O(bd)O(bd) - Stores only one path at a time, like DFS, but the depth is limited by the solution depth dd.

### Bidirectional Search

- **Time Complexity**: Approximated as O(bd/2)O(bd/2) if branching factors are equal in both directions. This is significantly faster than O(bd)O(bd).

## Comparison of Blind Search Strategies

| Strategy      | Completeness   | Optimality | Time Complexity | Space Complexity | Notes                                                            |     |
| :------------ | :------------- | :--------- | :-------------- | :--------------- | :--------------------------------------------------------------- | --- |
| BFS           | Yes            | Yes        | O(bd)           | O(bd)            | Optimal for equals costs; high memory usage.                     |     |
| DFS           | No (if cyclic) | No         | O(bm)           | O(mb             | Low memory usage; can get stuck in infinite paths.               |     |
| DLS           | No             | No         | $$O(bK)$$       | O(Kb)            | Avoids infinite paths; may miss solution if KK is too small.     |     |
| IDS           | Yes            | Yes        | O(bd)           | O(bd)            | Combines BFS optimality/completeness with DFS memory efficiency. |     |
| UCS           | Yes            | Yes        | O(bd)           | O(bd)            | Optimal for non-uniform costs; can be slow and memory-intensive. |     |
| Bidirectional | Yes            | Yes        | O(bd/2)         | O(bd/2)          | Faster for many problems; requires backward search capability.   |     |