---
tags:
  - ai
  - sheets
---

### Search Problem Components

A search problem is defined by the following components:

    Initial state(s): The starting point of the problem.
    Actions: Possible moves or operations available in each state.
    Transition model: Describes the result of performing a given action in a specific state. It answers the question: "What state results from performing a given action in this state?".
    Goal state(s): The desired end condition or solution.
    Solution path: A sequence of actions that leads from the initial state to a goal state.
    Path cost: A function that assigns a cost to a path. The optimal solution is the path with the lowest cost. Typically assumed to be the sum of non-negative step costs.

State Space & State Space Graph

    State Space: The set of all states reachable from the initial state by any sequence of actions.
    State Space Graph: A representation of the state space as a directed graph.
        Nodes represent states.
        Links between nodes represent actions.

A state space can be represented by a four-tuple [N,A,S,GD][N,A,S,GD]:

    NN: Set of nodes (states) in the graph.
    AA: Set of arcs (actions) between nodes.
    SS: Non-empty subset of NN containing the start state(s).
    GDGD: Non-empty subset of NN containing the goal state(s). Goal states can be described by:
        A measurable property of the states.
        A property of the solution path.

Examples

    Vacuum World:
        States: Agent location and dirt location. The number of states grows exponentially with the size of the world.
        Actions: L (Left), R (Right), S (Suck).
        Transition Model: Describes the outcome of each action.
    8-Puzzle:
        States: Locations of tiles. The 8-puzzle has 181,440 states (9!/2)(9!/2). The 15-puzzle has approximately 10131013 states, and the 24-puzzle has approximately 10251025 states.
        Actions: Move blank left, right, up, down.
        Path Cost: 1 per move.
    Romania:
        Initial State: Arad.
        Actions: Go from one city to another.
        Transition Model: Moving from city A to city B results in being in city B.
        Goal State: Bucharest.
        Path Cost: Sum of edge costs (total distance traveled).
    Traveling Salesperson:
        Nodes (NN): Represent cities.
        Arcs (AA): Labeled with weights indicating the cost of traveling between connected cities.
        Start State(s): A home city.
        Goal State(s): An entire path contains a complete circuit with minimum cost.
        Complexity: (n−1)!(n−1)! different cost-weighted paths can be generated, where nn is the number of cities. For example, with 5 cities, there are (5−1)!=4!=24(5−1)!=4!=24 possible paths.

State Space Search Strategies

    Data-Driven Search (Forward Chaining): Start searching from the given data of a problem instance toward a goal.
        Suggested when:
            Data is given in the initial problem statement.
            Few ways to use the given facts.
            Large number of potential goals.
            Difficult to form a goal or hypothesis.
    Goal-Driven Search (Backward Chaining): Start searching from a goal state to facts or data of the given problem.
        Appropriate when:
            A goal is given or can be easily formulated.
            Large number of rules to produce new facts.
            Problem data is not given but acquired by the problem solver.

Search: Basic Idea

    Begin at the start state and expand it by generating all possible successor states.
    Maintain a frontier (list of unexpanded states).
    At each step, pick a state from the frontier to expand.
    Repeat until a goal state is reached.
    Try to expand as few states as possible.

Search Tree

    A "What-if" tree of sequences of actions and outcomes.
    Represents "thinking" about possibilities rather than acting in the world.
    Root node: Corresponds to the starting state.
    Children of a node: Correspond to the successor states of that node's state.
    Path: A sequence of actions.
    Solution: A path ending in the goal state.
    Nodes vs. States: A state is a representation of the world, while a node is a data structure that is part of the search tree. A node must keep a pointer to its parent, path cost, and possibly other information.

Tree Search Algorithm Outline

    Initialize the frontier using the starting state.
    While the frontier is not empty:
        Choose a frontier node according to the search strategy and remove it from the frontier.
        If the node contains the goal state, return the solution.
        Else, expand the node and add its children to the frontier.

Handling Repeated States

To prevent infinite loops and improve efficiency:

    Every time you expand a node, add that state to the explored set.
    Do not put explored states on the frontier again.
    Every time you add a node to the frontier, check whether it already exists with a higher path cost. If yes, replace that node with the new one.

Algorithm Data Structures

    State List (LS): Lists the states in the current path being tried. Contains the solution path if the goal is found.
    New State List (NSL): Contains nodes awaiting evaluation.
    Dead Ends (DE): Lists states whose descendants have failed to contain a goal node.
    Current State (CS): A state currently under consideration.

Blind vs Heuristic Strategies

    Blind (Uninformed) Strategies: Do not exploit any information contained in a state.
    Heuristic (Informed) Strategies: Exploit information to assess that one node is "more promising" than another.
