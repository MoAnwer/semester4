---
tags:
  - ai
  - sheets
---

### Data, Information, and Knowledge

- **Data:** Raw, uninterpreted facts.
- **Information:** Data that has been given meaning and context.
- **Knowledge:** A collection of information that is useful and can be applied. It is acquired through experience or education and allows for understanding and problem-solving.

### Knowledge Representation (KR)

- **Goal:** To create a clear, precise, and unambiguous representation of facts and knowledge that enables computers to "think," infer new facts, and solve problems.
- **Process:** Transforming a problem into a simpler language using syntactic and semantic rules.

### Knowledge Representation Methods

- First-Order Logic (FOL)
- Semantic Networks
- Frames
- Production Rule Systems

### First-Order Logic (FOL)

- **Expressiveness:** More expressive than propositional logic. It allows for reasoning about objects, their properties, and their relationships.
- **Core Components:**
    - **Objects:** Individual entities (e.g., people, houses).
    - **Variables:** Represent objects (e.g., X,Y,ZX,Y,Z).
    - **Predicates/Relations:** Describe relationships between objects (e.g., `Likes(Ali, Yasser)`).
    - **Functions:** Map objects to objects (e.g., `MotherOf(Yasser)`).
    - **Constants:** Specific objects (e.g., `George`, `3`, `Green`).
- **Syntax:** Uses symbols for constants, predicates, functions, variables, connectives (¬,∧,∨,⇒,⇔¬,∧,∨,⇒,⇔), equality (==), and quantifiers (∀∀ for all, ∃∃ there exists).
- **Example:**
    - "George is a monkey and he is curious": $$Monkey(George) \land Curious(George)$$
    - "Monkeys are curious": $$∀m:Monkey(m)⇒Curious(m).$$
    - "There exists at least one monkey that is curious": ∃m:Monkey(m)∧Curious(m)∃m:Monkey(m)∧Curious(m).
- **Knowledge Engineering in FOL:** A systematic process involving identifying tasks, gathering knowledge, defining vocabulary, encoding general and specific knowledge, creating queries, and debugging.

### Semantic Networks

- **Structure:** A graph where nodes represent objects, concepts, or events, and labeled directed arcs represent relationships between them.
- **Nodes:** Represent entities.
- **Arcs:** Define binary relations between nodes.
- **Example:** `mother(Sue, John)`, `age(John, 5)`.
- **Inheritance:** A key reasoning mechanism. The `ISA` relation links a class to its superclass, allowing properties (like `hasPart`) to be inherited.
- **Advantages:** Easy to visualize, related knowledge is clustered, efficient space usage (objects represented once, relationships via pointers).
- **Disadvantages:** Inheritance can be problematic with multiple sources or exceptions, informal definitions can lead to issues, lack of standardization.

### Frames

- **Structure:** An extension of semantic networks. A frame represents an entity as a set of slots (attributes) and associated values (fillers). Frames can be implicitly linked because slot values can be other frames.
- **Components:** Frame name, attributes (slots), and values (fillers).
- **Example (Book Frame):**
    - Title: `AI: A Modern Approach`
    - Author: `Russell & Norvig`
    - Year: `2003`
- **Inheritance:** Similar to Object-Oriented Programming. A frame can inherit properties from parent frames (e.g., `Hotel Room` inheriting from `Room`).
- **Advantages:** Groups related knowledge, expressive, easy to add properties, supports default information.
- **Disadvantages:** Lack of standardization, can be interpreted differently by different users, no built-in reasoning mechanisms.

### Production Rules Systems
- **Structure:** A procedural representation of knowledge, often used in expert systems. Knowledge is encoded as `IF-THEN` rules.
- **Components:**
    - **Condition (Antecedent) Part:** The `IF` part.
    - **Conclusion (Action/Consequent) Part:** The `THEN` part.
- **Rule Structure:**
    - Can have multiple antecedents combined with `AND` or `OR`.
    - `IF <antecedent 1> AND <antecedent 2> THEN <consequent>`
    - The antecedent often involves an object and its value linked by an operator (e.g., `IF 'traffic light' IS green THEN go`).
- **System Components:**
    - **Global Knowledge Base:** Stores the initial problem state.
    - **Set of Production Rules:** Contains the `IF-THEN` rules.
    - **Control Strategy:** Cycles through matching facts against rules, selecting a rule, and executing it.
- **Inference Mechanisms:**
    - **Forward Chaining:** Starts with facts and applies rules to derive new facts or conclusions. Useful for monitoring or generating results from data.
    - **Backward Chaining:** Starts with a goal and works backward, seeking rules and facts that support that goal. Useful for diagnosis or finding specific answers.

#### Example: Forward Chaining

- **Knowledge Base (KB):**
    - Rule 1: `If A and B and C then D`
    - Rule 2: `If B and C then G`
    - Rule 3: `If B and D then F`
    - Rule 4: `If B and C and D then E`
    - Rule 5: `If A and B then C`
    - Rule 6: `If G and D then Z`
- **Working Memory (Initial Facts):** `A, B`
    
- **Execution Trace:**
    - **Cycle 1:** `Rule 5` (`If A and B then C`) matches. Add `C` to Working Memory.
        - Working Memory: `A, B, C`
    - **Cycle 2:** `Rule 5` (`A and B` -> `C`) still matches but `C` is already present. `Rule 1` (`A and B and C` -> `D`) matches. Add `D`. `Rule 2` (`B and C` -> `G`) matches. Add `G`.
        - Working Memory: `A, B, C, D, G`
    - **Cycle 3:** `Rule 3` (`B and D` -> `F`) matches. Add `F`. `Rule 4` (`B and C and D` -> `E`) matches. Add `E`. `Rule 6` (`G and D` -> `Z`) matches. Add `Z`.
        - Working Memory: `A, B, C, D, G, F, E, Z`
    - **Cycle 4:** No new rules can be fired. Stop.

#### Example: Backward Chaining (Goal: G)

1. **Goal:** Prove `G`.
2. Look for rules that conclude `G`. `Rule 2` (`If B and C then G`) is found.
3. **Subgoals:** Prove `B` and `C`.
4. Check Working Memory for `B`. `B` is present (True).
5. **Subgoal:** Prove `C`.
6. Look for rules that conclude `C`. `Rule 5` (`If A and B then C`) is found.
7. **Subgoals:** Prove `A` and `B`.
8. Check Working Memory for `A`. `A` is present (True).
9. Check Working Memory for `B`. `B` is present (True).
10. Since `A` and `B` are true, `C` is true (from `Rule 5`).
11. Since `B` and `C` are true, `G` is true (from `Rule 2`).
12. **Conclusion:** `G` is provable.