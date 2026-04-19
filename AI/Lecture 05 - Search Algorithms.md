---
tags:
  - ai
---
## Introduction to Search Algorithms

Search algorithms are fundamental to Artificial Intelligence (AI) for problem-solving. They systematically explore possible solutions to find a path from an initial state to a goal state.

### Type of Search Algorithms

Search algorithms can be broadly categorized into two main types:

- **Uninformed Search Strategies (Blind Search):** These algorithms only have access to the information provided by the problem model, which includes the initial state, available actions, transition model, goal state(s), and solution path. They explore the search space without any additional knowledge about the problem's structure or the proximity to the goal.
    - Examples include: Depth-First Search (DFS), Breadth-First Search (BFS), Depth-Limited Search (DLS), Iterative Deepening Search (IDS), and Uniform-Cost Search (UCS).
- **Informed Search Strategies (Heuristic Search):** These algorithms utilize additional information beyond the basic problem formulation. This extra knowledge, often in the form of a heuristic function, allows them to estimate the cost or promise of exploring a particular action or state. This helps them prioritize more promising paths.
    - Examples include: Greedy Best-First Search (GBFS) and A* Search.

### Tree Search Algorithm Outline

Most search algorithms follow a general pattern:

1. Initialize a **frontier** (a data structure, often a priority queue) with the starting state.
2. While the frontier is not empty: a. Choose a node from the frontier based on the specific search strategy. b. If the chosen node contains the goal state, return the solution. c. Otherwise, expand the node by generating its children (successor states) and add them to the frontier.

## Informed Search Strategies

Informed search strategies aim to improve efficiency by using additional knowledge to guide the search. This is achieved by defining an **evaluation function**, f(n)f(n), which estimates the desirability of considering node nn next. Nodes with better f(n)f(n) values are prioritized.

### Uniform-Cost Search (UCS)

Uniform-Cost Search prioritizes nodes based on the **path cost** from the initial state to the current node, denoted as g(n)g(n).

- **Evaluation Function:** f(n)=g(n)f(n)=g(n)
    
- **Mechanism:** UCS uses a priority queue ordered by the path cost g(n)g(n). It always selects and expands the node with the lowest accumulated path cost from the root.
    
- **Goal Direction:** UCS is not inherently goal-directed because it only considers the cost to reach a node, not the estimated cost to reach the goal from that node.
    
- **Properties:** UCS is complete and optimal (finds the shallowest goal with the lowest path cost).
    
- **Example:** Consider a simple graph: S -> A (cost 1) S -> B (cost 5) A -> G (cost 10) B -> G (cost 5)
    
    1. Frontier: {(S, g=0)}
    2. Expand S: Frontier: {(A, g=1), (B, g=5)}
    3. Expand A (lowest g): Frontier: {(B, g=5), (G, g=11)} (G is child of A, cost 1+10=11)
    4. Expand B (lowest g): Frontier: {(G, g=11), (G, g=10)} (G is child of B, cost 5+5=10)
    5. Expand G (lowest g, cost 10): Goal found.

### Heuristic Function (h(n)h(n))

To make search more goal-directed, we introduce a **heuristic function**, h(n)h(n).

- **Definition:** h(n)h(n) is the estimated cost from node nn to the goal state.
- **Properties:**
    - h(goal)=0h(goal)=0.
    - If h(n1)<h(n2)h(n1​)<h(n2​), it suggests that it is likely cheaper to reach the goal from n1n1​ than from n2n2​.
- **Requirement:** A heuristic function cannot be derived solely from the basic problem formulation components (initial state, actions, transition model, goal state, solution path). It requires additional, problem-specific knowledge.

### Evaluation Function (f(n)f(n))

The evaluation function f(n)f(n) combines path cost and heuristic estimates to guide the search:

- f(n)=g(n)f(n)=g(n) (Uniform-Cost Search)
- f(n)=h(n)f(n)=h(n) (Greedy Best-First Search)
- f(n)=g(n)+h(n)f(n)=g(n)+h(n) (A* Search)

## Greedy Best-First Search (GBFS)

Greedy Best-First Search prioritizes nodes based on their estimated cost to the goal, using the heuristic function h(n)h(n). It attempts to expand the node that _appears_ closest to the goal.

- **Evaluation Function:** f(n)=h(n)f(n)=h(n)
- **Mechanism:** GBFS uses a priority queue ordered by the heuristic value h(n)h(n). It always selects and expands the node with the smallest estimated cost to the goal. It largely ignores the actual path cost g(n)g(n) incurred so far.
- **Comparison to UCS:** GBFS is the complement of UCS, using h(n)h(n) instead of g(n)g(n).
- **Versions:**
    - **Tree GBFS:** Suitable for simple tree structures. Does not explicitly handle repeated states.
    - **Graph GBFS:** Handles graphs by keeping track of visited states to avoid cycles and redundant work.
- **Properties:**
    - **Not Complete:** Can fail to find a solution if the search space is infinite or very deep.
    - **May Loop Forever:** Without tracking visited states (in the tree version), it can get stuck in cycles.
    - **Not Optimal:** Ignores the actual path cost, potentially leading to suboptimal solutions (solutions with high actual cost).
- **Complexity:**
    - Time Complexity: O(bm)O(bm) in the worst case, where bb is the branching factor and mm is the depth of the shallowest goal.
    - Space Complexity: O(bm)O(bm) in the worst case, as it may need to store all generated nodes.

## A* Search

A* Search combines the strengths of Uniform-Cost Search and Greedy Best-First Search by considering both the cost to reach a node (g(n)g(n)) and the estimated cost from that node to the goal (h(n)h(n)).

- **Evaluation Function:** f(n)=g(n)+h(n)f(n)=g(n)+h(n)
- **Idea:** f(n)f(n) estimates the total cost of the cheapest solution path that goes through node nn. The algorithm prioritizes nodes with the lowest f(n)f(n) value.
- **Mechanism:**
    - **Tree Version:** Similar to UCS and GBFS, it expands nodes with the lowest f(n)f(n) in a priority queue. It does not explicitly check for repeated states.
    - **Graph Version:** Maintains both a frontier and an explored set. When expanding a node, its children are added to the frontier. If a child is already in the frontier or explored set, A* updates it only if the new path to it is cheaper.
- **Properties:**
    - **Complete:** Yes, if the branching factor bb and the depth of the shallowest goal mm are finite, and costs are positive. The number of nodes with a finite cost is finite.
    - **Optimal:** Yes, if the heuristic function h(n)h(n) is **admissible**.
    - **Efficiency:** Generally much more efficient than UCS or GBFS alone, especially with a good heuristic. The number of nodes explored depends on the accuracy of the heuristic. If h(n)h(n) is perfect (h(n)=h∗(n)h(n)=h∗(n)), A* only expands nodes on the optimal path. If h(n)=0h(n)=0, A* behaves like UCS.

### Admissible Heuristic (h(n)≤h∗(n)h(n)≤h∗(n))

A heuristic function h(n)h(n) is **admissible** if it never overestimates the true cost (h∗(n)h∗(n)) to reach the goal state from node nn.

- **Implication:** If h(n)h(n) is admissible, then f(n)=g(n)+h(n)f(n)=g(n)+h(n) never overestimates the true cost of the cheapest solution passing through nn. This is crucial for A*'s optimality.

### Consistent Heuristic (Monotonicity)

A heuristic function h(n)h(n) is **consistent** (or monotonic) if for every node nn and every child n′n′ generated by action aa, the following holds:

h(n)≤h(n′)+c(n,a,n′)h(n)≤h(n′)+c(n,a,n′)

where c(n,a,n′)c(n,a,n′) is the actual cost of action aa that transforms node nn into node n′n′.

- **Relationship to Admissibility:** Consistency is a stronger condition than admissibility. If a heuristic is consistent, it is also admissible.
- **Implication for Graph Search:** Consistency guarantees that when A* expands a node, it has found the optimal path to that node. This prevents the need to re-evaluate nodes if a cheaper path is found later, thus ensuring optimality in the graph version of A* without needing to check for better paths to already explored nodes.
- **Property of f(n)f(n):** Consistency ensures that f(n)f(n) never decreases as you move further from the root towards the goal: f(n)≤f(n′)f(n)≤f(n′).

### A* Complexity

- **Time and Space Complexity:** Not straightforward to express simply as O(bm)O(bm). It depends heavily on the accuracy of the heuristic function h(n)h(n) compared to the true cost h∗(n)h∗(n). A tighter heuristic leads to fewer explored nodes and better performance. In the worst case, it can still be expo