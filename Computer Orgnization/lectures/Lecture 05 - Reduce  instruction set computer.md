---
tags:
  - coa
banner:
---
### **The Evolution of Programming Languages & Computer Architecture**

1. **Shift in Costs**: As hardware costs have significantly decreased, the relative and absolute costs of software have risen, primarily due to a chronic shortage of programmers.
    
2. **Software Reliability Issues**: Beyond cost, software often suffers from long-term unreliability, with programs frequently exhibiting new bugs even after years of operation.
    
3. **Rise of High-Level Languages (HLLs)**: To combat these issues, more powerful HLLs were developed. They allow for concise algorithm expression, handle low-level details automatically via compilers, and support structured or object-oriented design.
    
4. **The Semantic Gap**: A gap exists between the complex operations of HLLs and the simpler operations of computer architecture. This gap can lead to execution inefficiency, large program sizes, and complex compilers.
    
5. **CISC Strategy (Complex Instruction Sets)**: Designers initially tried to close the "semantic gap" by making hardware more complex (e.g., larger instruction sets). The goal was to simplify compiler writing and improve efficiency through microcode.
    
6. **The Shift Toward Simplicity (RISC)**: Research into how instructions are actually executed led some to suggest a different path: making architectures simpler (RISC) rather than more complex to better support HLLs.
    
7. **Dynamic vs. Static Measurement**: Studies show that understanding performance requires **dynamic measurement** (counting events during actual program execution) rather than **static measurement** (counting lines in the source code), as the latter does not reflect actual workload.    
## Instruction Execution Characteristics

1. **high-level languages (HLLs):** 
	 - allow the programmer to express algorithms more concisely. 
	 - allow the compiler to take care of details that are not important in the programmer’s expression of algorithms.
	 - often support naturally the use of structured programming and/or object-oriented design.

2. _**semantic gap**_: the difference between the operations provided in HLLs and those provided in computer architecture. Designers responded with architectures intended to close this gap. Key features:
	- _include large instruction sets_ .
	- _dozens of addressing modes_. 
	- _various HLL statements implemented in hardware._

An example of the latter is the CASE machine instruction on the **VAX**. Such complex instruction sets are intended to: 
- Ease the task of the compiler writer. 
- Improve execution efficiency, _because complex sequences of operations can be implemented in microcode._
- Provide support for even more complex and sophisticated HLLs.

Meanwhile, a number of studies have been done over the years to determine the characteristics and patterns of execution of machine instructions generated from HLL programs. The results of these studies inspired some researchers to look for a different approach: namely, _to make the architecture that supports the HLL simpler_, rather than more complex. 

To understand the line of reasoning of the RISC advocates, we begin with a brief review of instruction execution characteristics. The aspects of computation of interest are as follows: 

- _Operations performed:_ These determine the functions to be performed by the processor and its interaction with memory. 
- _Operands used:_ The types of operands and the frequency of their use determine the memory organization for storing them and the addressing modes for accessing them. 
- _Execution sequencing:_ This determines the control and pipeline organization. 

In the remainder of this section, we summarize the results of a number of studies of high-level-language programs. All of the results are based on _dynamic measurements._ That is, measurements are collected by _executing the program and counting the number of times some feature has appeared or a particular property has held true_. In contrast, _static measurements merely perform these counts on the source text of a program.They give no useful information on performance_, because they are not weighted relative to the number of times each statement is executed. 

 



### **Analysis of HLL Program Behavior and Performance**

1. **Dominance of Assignment Statements**: Studies show that assignment statements occur most frequently in HLL programs, highlighting the high importance of simple **data movement**.
    
2. **Frequency of Control Statements**: Conditional statements (like `IF` and `LOOP`) are also highly prevalent, which emphasizes the need for efficient **sequence control mechanisms** (compare and branch instructions) in an instruction set.
    
3. **Optimal Support**: By identifying which statements occur most often, designers can determine which operations should be supported in an "optimal" fashion within the machine instruction set.
    
4. **Static vs. Dynamic Frequency**: The research focuses on **dynamic behavior** (_how often statements occur during actual execution_) rather than _static counts in the source code, providing a more accurate picture of performance_.
    
5. **Weighted Impact**: To understand the true performance cost, the frequency of HLL statements must be weighted by the number of **machine instructions** and **memory references** they actually generate.
    
6. **The "Machine-Instruction Weighted" Metric**: By multiplying the statement frequency by the number of machine instructions produced by the compiler, researchers can estimate the relative time spent on each HLL statement type.
    
7. **Memory Reference Importance**: Measuring the memory references caused by each statement serves as another critical surrogate measure for **execution time** and system load.
    
8. **The Significance of Procedure Calls**: While assignment and conditional statements are more frequent, the results suggest that **procedure call/return** operations are actually the most time-consuming in typical HLL programs.
    
9. **CISC Architecture Context**: These findings are representative of contemporary **Complex Instruction Set Computer (CISC)** architectures, such as the VAX, PDP-11, and Motorola 68000.
    
10. **Guidance for Future Design**: This data provides a roadmap for architects looking for more efficient ways to support HLLs, potentially leading toward simpler or more specialized architectures (like RISC) that prioritize high-impact operations.

### **Analysis of Procedure Calls and Returns**

- **Performance Bottleneck**: _Procedure calls and returns_ are identified as the _most time-consuming operations_ in compiled High-Level Language (HLL) programs, making their optimization critical for system performance.
    
- **Key Efficiency Factors**: Two primary factors influence the efficiency of these operations:
    
    1. The number of **parameters and variables** handled by each procedure.
        
    2. The **depth of nesting** (how many procedures call other procedures).
        
- **Small Operand Requirements**: Research by Tanenbaum and the Berkeley RISC team revealed that the vast majority of procedures are quite simple:
    
    - **98%** of calls involve fewer than **six arguments**.
        
    - **92%** of procedures use fewer than **six local scalar variables**.
        
- **Localized References**: Most data access (operand references) is concentrated within a very small number of local scalar variables per procedure.
    
- **Narrow Nesting Window**: Studies on execution patterns show that programs rarely engage in long, uninterrupted sequences of calls. Instead, they operate within a "narrow window" of invocation depth.
    
- **Conclusion on Locality**: These findings reinforce the principle of **locality**, suggesting that hardware can be optimized by providing fast access to a small, local set of variables rather than preparing for massive, complex data structures during every call.


Based on the text, here is a concise English summary of the core principles that characterize **RISC (Reduced Instruction Set Computer)** architectures:

### **The RISC Design Strategy**

- **Shift in Strategy**: Instead of making hardware complex to match High-Level Languages (HLLs), RISC focuses on optimizing the performance of the most time-consuming features found in typical programs.
- **Optimization of Operands**:
    - **Large Register Sets**: RISC architectures use a high number of registers (or advanced compiler optimization) to store data.
    - **Reducing Memory Access**: Since studies show a high frequency of "assignment" statements and "local scalar" variables, keeping data in registers rather than slow main memory significantly boosts speed.
- **Efficient Pipelining**:
    - **Addressing Branches**: Because HLL programs have many conditional branches and procedure calls, standard pipelines often waste time fetching instructions that are never executed.
    - **Refined Design**: RISC prioritizes specialized pipeline designs to handle these frequent "jumps" in code without losing efficiency.
- **High-Performance Primitives**:
    - **Simple Instructions**: The instruction set consists of basic, high-performance "primitives" rather than complex commands.
        
    - **Predictability**: These simple instructions have predictable costs in terms of execution time, code size, and **energy dissipation**, allowing for more consistent and efficient hardware performance.

# The Use of Large Register File

**Registers** are the key to accelerating computer performance and how designers—through both software and hardware—compete to utilize them most effectively.

Here is a simplification of the core concepts:

### 1. Why are Registers the Fastest?

Registers are the _fastest data storage devices available_, surpassing both Cache and RAM for three reasons:

- **Physical Proximity**_: Registers are located directly on the processor chip_, right next to the Arithmetic Logic Unit (ALU) and Control Unit.
    
- **Small Size**: Because they consist of a small set of storage units, access to them is nearly instantaneous.
    
- **Short Addressing**: Since there are few registers (e.g., 32), a register "address" consists of very simple numbers, unlike the long and complex addresses used for memory.
    

### 2. The Strategy: "Minimizing Memory Dependency"

Because registers are so fast, a _designer’s primary goal is to keep the most frequently used variables inside these registers_. This minimizes **Register-Memory operations** (moving data back and forth), which are the main bottleneck in performance.

### 3. Two Approaches to the Problem (Software vs. Hardware)

There are two main ways to achieve this goal:

#### I. The Software Approach

- **The Idea**: Relying on the **Compiler**.
- **How it works**: The compiler uses sophisticated algorithms to analyze the code and decide which variables are "most important" to keep in the limited number of available registers.
    
- **Challenge**: Requires highly intelligent software to perform complex program analysis.
    

#### **II. The Hardware Approach**

- **The Idea**: Simply **increasing the number of registers** in the processor.
    
- **How it works**: By providing more registers, the hardware can hold more variables for longer periods without needing to move them to slow memory.
    
- **Examples**: This approach was pioneered by the **Berkeley RISC** group and is utilized in **Pyramid** systems and the popular **SPARC** architecture.

---

### **The Importance of Register Windows**

The significance of this technology lies in its ability to **eliminate the performance bottleneck** caused by frequent procedure calls. By using hardware to manage local variables and parameter passing, it drastically reduces slow memory access (Save/Restore operations), allowing high-level language programs to execute with near-instantaneous transitions between functions.

This text explains one of the cleverest innovations in the world of processors: **Register Windows**. The core idea is to solve the "bureaucratic" overhead that occurs inside the processor during procedure calls.

Here is a simplified breakdown of this technology:

#### **1. The Problem: Procedure Call Overhead**

In traditional processors, when "Procedure A" calls "Procedure B," several slow steps must occur:
- **Saving**: Register data from Procedure A must be emptied and saved into main memory (RAM).
- **Execution**: The registers are then used for Procedure B’s data.
- **Restoring**: Upon completion, Procedure A’s data must be reloaded from memory back into the registers.
    This "Save & Restore" process is time-consuming because it relies on slow external memory.
#### **2. The Solution: Register Windows**

Instead of having a single set of registers that must be constantly swapped, the processor features a **large file of physical registers** divided into "windows."

- Every procedure is assigned its own private "window" of registers.
    
- When a call occurs, the processor doesn't save data to memory; it simply **"slides"** to the next available window.
    

#### **3. The Genius of "Overlapping"**

To make passing parameters between procedures lightning-fast, designers overlapped the edges of these windows. Each window is divided into three fixed-size areas:

1. **Parameter Registers (In)**: To receive data from the calling procedure.
    
2. **Local Registers**: To store variables unique to the current procedure.
    
3. **Temporary Registers (Out)**: To prepare data for the next procedure to be called.
    

**The Secret:** The "Output" registers of Procedure A are **physically the same** as the "Input" registers of Procedure B. This means parameter passing happens in "zero time" because the data does not move; only the window pointer changes.

#### **4. What if the Windows Fill Up? (Circular Buffer)**

Since the number of registers is finite, they are organized as a **Circular Buffer**:

- The processor keeps the most recent activations (e.g., the last 8 calls) in hardware.
    
- If the program's nesting depth exceeds the number of windows, the processor only then moves the oldest window to memory to make room.
    
- Because studies show that call depth fluctuates within a narrow range, the need to access memory becomes extremely rare.

The **Register Windows** technique (used in **SPARC** and **Itanium** architectures) transforms procedure calls from a heavy, memory-dependent "software" task into an instantaneous "hardware" task based on window switching. This achieves massive speed gains when executing high-level programming languages.

---
## **Circular Buffer**

This text explains the precise mechanics of how the **Circular Buffer** works and how it manages function "congestion" inside the processor using **Pointers**.

Here is a simplified explanation:

### **1. Key Pointers (The Circuit Controllers)**

To track its current state and activity, the processor uses two pointers (think of them as clock hands):

- **CWP (Current Window Pointer):** Points to the window currently in use (the active function). Any instruction referencing a register is automatically directed to this window.
    
- **SWP (Saved Window Pointer):** Points to the window most recently saved in memory (RAM). This pointer acts as a "boundary" that cannot be crossed.
    


### **2. The "Full" Scenario (The Overlap Conflict)**

Imagine a circle with only 6 windows ($w0$ to $w5$):
- Currently, **Procedure D** is running in window $w3$.
- If **D calls E**, the $CWP$ moves to $w4$. Everything runs smoothly.
- **The Big Problem:** If **E attempts to call F**, the $CWP$ moves to $w5$. Here, window $w5$ overlaps with the first window, $w0$ (which belongs to **Procedure A**).
- If we allowed **F** to run, it would overwrite the data belonging to **Procedure A**!


### **3. The Solution: The Interrupt**

When the two pointers meet ($CWP = SWP$), the processor realizes the "circle is full" and takes the following actions:

- **Temporary Pause:** A program **Interrupt** occurs.    
- **Freeing Space:** The data from the old function (**A**) is moved to memory (RAM) to empty the window.
- **Updating the Pointer:** The $SWP$ is incremented (moved forward), and now the new function (**F**) can operate safely.

### **4. The Return Process**

The same logic applies in reverse. When functions finish and return, if the processor reaches a window whose data was previously moved to memory, another interrupt occurs to **Restore** that data back into the registers so the program can continue.


### **5. By the Numbers (Why is this system genius?)**

You might think these interrupts happen often, but the reality is quite the opposite:

- **Efficiency:** A study found that having just **8 windows** means the processor only needs to access memory (Save/Restore) in **1%** of calls or returns!
- Most of the time, functions "swim" within the circle without ever hitting the boundaries.

**Real-World Examples:**

- **Berkeley RISC** computers use 8 windows.
- **Pyramid** computers employ 16 windows.

The **Circular Buffer** is "intelligent crisis management." It allows the processor to run at maximum speed within the "register circle" and only resorts to slow memory when the circle overflows with functions—a rare occurrence thanks to the natural behavior of software.

---

## Graph Coloring

- **The Goal**: The core task of the compiler is to decide which variables (symbolic registers) should be assigned to the limited physical registers of the CPU at any given moment to maximize speed.

- **The Graph Coloring Technique**: RISC compilers use this topological method to manage registers efficiently. It works as follows:
    - **Nodes**: Each variable or "symbolic register" in the program is represented as a node.
    - **Edges (Interference)**: A line is drawn between two nodes _if they are "live" at the same time_. This means they _conflict and cannot share the same physical register._
    - **Colors**: These represent the actual physical registers available in the CPU.
- **The Assignment Process**: The compiler tries to color the graph so that no two connected nodes share the same color.
    - Variables with the **same color** are assigned to the **same physical register** because they never run at the same time.
    - **Spilling**: If a node cannot be colored (due to too many conflicts), it is "spilled" into **memory**, requiring Load/Store instructions to access it.

### **Key Findings: Hardware vs. Software Trade-off**

The text highlights a critical balance between the number of registers and the sophistication of the compiler:
1. **Diminishing Returns**: With even simple optimization, there is little benefit to having more than **64 registers**.
2. **The Power of Sophisticated Compilers**: If the compiler uses advanced graph coloring, performance barely improves beyond **32 registers**.
3. **Shared vs. Split**: In machines with very few registers (e.g., 16), it is faster to have one shared pool of registers rather than splitting them specifically for Integers and Floating-point numbers.

While **Register Windows** _(the hardware approach) solves the call/return problem_, **Graph Coloring** (the software approach) allows a processor with fewer registers to perform just as well by intelligently _recycling those registers among different variables._

---

## RISC Characteristics


#### One instruction per cycle

While CISC use _microinstructions_ on CISC machines; The first characteristic listed is that there is _one machine instruction per machine cycle._

- A _machine cycle_: defined to be the time it takes to fetch two operands from registers, perform an ALU operation, and store the result in a register.

the RISC machine instructions can be _hardwired_. 
#### Register-to-register operations

- A second characteristic is that most operations should be register to register,  with only simple **LOAD and STORE** operations accessing memory. 
- This simplifies **instruction set and therefore the control unit**.
####  Simple addressing modes
- A third characteristic is the use of _simple addressing modes._ Almost all RISC instructions use simple register addressing. Several additional modes, such as displacement and PC-relative, may be included. Other, more complex modes can be synthesized in software from the simple ones. Again, this design feature simplifies the instruction set and the control unit.
#### Simple instruction formats 
- Generally only one or a few formats are used Instruction length is fixed and aligned on word boundaries Opcode decoding and register operand accessing can occur simultaneously

##### More  classic RISC

the following are considered typical of a classic RISC: 

1.  A single instruction size. 
2.  That size is typically _4 bytes._
3.  A small number of data addressing modes, _typically less than five._
4.  _No indirect addressing_ that requires you to make one memory access to get  the address of another operand in memory. 
5.  _No operations that combine load/store with arithmetic_ (e.g.,add from memory, add to memory). 
6.  No more than one memory-addressed operand per instruction. 
7.  Does not support arbitrary alignment of data for load/store operations. 
8.  Maximum number of uses of the memory management unit (MMU) for a data address in an instruction. 
 
---
# The Effects of Pipelining in RISC

### 1. Core Concept

_Pipelining_ enhances performance by allowing multiple instructions to be processed **simultaneously** in different stages, rather than waiting for one instruction to finish before starting the next.

### 2. Pipelining Stages

- **Two-Stage Pipeline**: Overlaps **Instruction Fetch (I)** and **Execute (E)**. Theoretically doubles the _execution rate._
- **Three-Stage Pipeline**: Adds a **Memory (D)** stage. It allows up to three instructions to overlap, potentially tripling performance.
- **Four-Stage Pipeline**: Further splits the Execute stage into **E1 (Register Read)** and **E2 (ALU Operation/Register Write)**. This maximizes throughput by having four instructions in flight at once.


### 3. Performance Hurdles (The "Stalls")

Even with pipelining, maximum speedup is often hindered by:

- _Memory Conflicts_: When two stages need to access _a single-port memory_ at the same time, one must wait.
- _Branch Instructions_: Jumping to a new part of the code breaks the sequential flow, _requiring the pipeline to be cleared._
- _Data Dependencies_: When an instruction needs a result from a previous instruction that hasn't finished yet.

### 4. The RISC Solution: NOOP

To solve these hurdles without complex hardware, the _compiler_ or assembler inserts a **NOOP (No Operation)** instruction. This acts as a "spacer" to create a delay, ensuring the correct data is ready or the branch is resolved before the next instruction proceeds.


The simplicity and fixed length of **RISC instructions** make them perfect for pipelining. By breaking execution into 3 or 4 equal steps, the processor can complete (ideally) **one instruction every clock cycle**, even though each individual instruction takes multiple cycles to finish.

---

# Optimizing of Pipelining

- _Delayed branch_
	- Does not take effect until **after** _execution of following instruction_
	- The instruction location immediately following the branch is referred to as the _delay slot_.
- _Delayed Load_
	- Register to be target is locked by processor
	- Continue execution of _instruction stream until register required_
	- Idle until load is complete
	- Re-arranging instructions can allow useful work while loading
- _Loop Unrolling_
	- Replicate body of loop a number of times Iterate loop fewer times
	- Reduces loop overhead
	- _Increases instruction parallelism_
	- Improved register, data cache, or TLB locality


---

# Instruction pipeline

The MIPS architecture leverages a simplified instruction set to achieve highly efficient **pipelining**. While first-generation RISC processors aimed for a speed of **one instruction per clock cycle**, modern processors use two main strategies to execute **multiple instructions** simultaneously:


### 1. Superscalar Architecture

- **The Concept:** This approach **replicates** the pipeline stages. By having multiple "lanes," the processor can handle two or more instructions at the same stage at the very same time.
- **Limitations:** * **Dependencies:** Instructions in different pipelines may rely on each other, causing delays.
    - **Logic Overhead:** Complex logic is needed to coordinate and manage these dependencies.

### 2. Super-pipelined Architecture

- **The Concept:** This approach increases the number of stages by making them **finer and smaller**. With more stages, more instructions can stay in the pipeline at once, which increases parallelism.
- **Limitation:** * **Overhead:** Moving instructions through a higher number of stages creates extra "transfer overhead" at every step.

| **Feature**       | **Superscalar**                         | **Super-pipelined**                       |
| ----------------- | --------------------------------------- | ----------------------------------------- |
| **Strategy**      | Parallel "lanes" (Horizontal growth)    | More/finer stages (Vertical growth)       |
| **Main Benefit**  | Multiple instructions at the same stage | More instructions in the pipeline overall |
| **Main Drawback** | Complex coordination logic              | Transfer overhead between stages          |

---
![[Pasted image 20260422130420.png]]



---

# The 8 Stages of MIPS R4000 Pipeline

 **8 stages of the MIPS R4000 pipeline**, which is a classic example of _Super-pipelining_:

### The 8 Stages of MIPS R4000 Pipeline

1. **IF1 (Instruction Fetch 1):** The processor sends the virtual address to the instruction cache and the translation lookaside buffer (TLB).
    
2. **IF2 (Instruction Fetch 2):** The instruction is retrieved from the cache, and the physical address is generated.
    
3. **RF (Register File):** The instruction is **decoded**, and the required data (operands) are fetched from the registers.
    
4. **EX (Execute):** The ALU performs the actual operation (like addition or address calculation).
    
5. **TC (Tag Check):** The processor checks the "cache tags" to ensure the required data is actually in the cache before trying to read or write it.
    
6. **DC1 (Data Cache 1):** The virtual address for the data is presented to the data cache.
    
7. **DC2 (Data Cache 2):** The data cache outputs the requested data.
    
8. **WB (Write Back):** The final result is written back into the destination register.
    

---

### **Why use 8 stages? (The "Super-pipeline" Benefit)**

- **Higher Frequency:** By breaking the process into smaller pieces, each piece is very fast. This allows the CPU to run at a much higher **Clock Speed** (MHz/GHz).
    
- **Increased Parallelism:** At any given moment, 8 different instructions are in different stages of completion, significantly increasing the amount of work done per second.
    

### **The Role of Register Windows (The Hardware Edge)**

While the pipeline handles _execution_, the **Overlapping Register Windows** (from the other image) handle _communication_. They ensure that when functions call each other, the data is already waiting in the registers (via the overlap), preventing the pipeline from stalling due to slow memory access.

This combination of a **deep pipeline** (8 stages) and **register windows** is what made the R4000 one of the most powerful RISC processors of its time.