---
banner: "pixel-banner-images/Modern high-rise urban streetscape-1.jpg"
tags:
  - coa
  - computer-history
banner-repeat: false
---
## History of Computers by Generation

### First Generation: Vacuum Tubes (1946-1957)

- **Key Technology:** Vacuum tubes.
- **Characteristics:** Large, expensive, high power consumption, generated significant heat.
- **Example:**
    - **ENIAC (Electronic Numerical Integrator and Computer):**
        - Completed in 1946.
        - First general-purpose electronic digital computer.
        - Used for ballistic trajectory calculations and later for hydrogen bomb feasibility studies.
        - Major drawback: manual programming via switches and cables.
        - Specifications: Occupied 1500 sq ft, weighed 30 tons, consumed 140 kW, capable of 5000 additions per second.
        - Memory: 20 accumulators, each holding a 10-digit decimal number.
- **Key Concept:** The stored-program concept, attributed to John von Neumann and implemented in machines like EDVAC and the IAS computer, allowed programs to be stored in memory alongside data.
    - **IAS Computer:** A prototype for subsequent general-purpose computers, completed in 1952.
        - Memory: 1000 words, each 40 bits.
        - Memory Format: Words could be data (40-bit binary numbers) or instructions (two 20-bit instructions, each with an 8-bit opcode and a 12-bit address).
        - Key Registers:
            - MBR (Memory Buffer Register): Holds data to/from memory or I/O.
            - MAR (Memory Address Register): Holds the address for memory access.
            - IR (Instruction Register): Holds the opcode of the instruction being executed.
            - IBR (Instruction Buffer Register): Holds the right half of an instruction word.
            - PC (Program Counter): Holds the address of the next instruction.
            - AC (Accumulator): Holds operands and results of ALU operations.
            - MQ (Multiplier-Quotient): Holds operands and results, especially for multiplication and division.

### Second Generation: Transistors (1958-1964)

- **Key Technology:** Transistors (invented in 1947 at Bell Labs).
- **Characteristics:** Smaller, cheaper, less heat dissipation than vacuum tubes, solid-state.
- **Impact:** Led to more complex arithmetic/logic units, higher-level programming languages, and system software.
- **Example:**
    - **UNIVAC I (Universal Automatic Computer):** First successful commercial computer (1951).
    - **IBM 700/7000 Series:** Introduced in the mid-1950s, with later models (e.g., 7094) incorporating transistors. These machines established IBM's dominance.
    - **DEC PDP-1:** Introduced in 1957, marking the beginning of the minicomputer era.

### Third Generation: Integrated Circuits (1965-1971)

- **Key Technology:** Integrated Circuits (ICs) - multiple transistors and other components fabricated on a single semiconductor chip.
- **Characteristics:** Further miniaturization, increased speed, reduced cost, improved reliability.
- **Key Concept:** Moore's Law (1965) observed that the number of transistors on a chip doubles approximately every 18 months.
- **Examples:**
    - **IBM System/360 Family:** A landmark series of compatible computers.
    - **DEC PDP-8:** A highly successful minicomputer.
- **Components:** ICs consist of gates (for logic functions) and memory cells (for data storage), interconnected on a chip.

### Fourth Generation: Large Scale Integration (LSI) (1972-1977)

- **Key Technology:** LSI - Thousands of transistors on a single chip.
- **Impact:** Led to the development of microprocessors.
## Key Technological Advancements

- **Vacuum Tubes:** Enabled the first electronic computers but were bulky, power-hungry, and unreliable.
- **Transistors:** Replaced vacuum tubes, leading to smaller, more reliable, and more efficient computers.
- **Integrated Circuits (ICs):** Allowed for the miniaturization of electronic components by fabricating multiple transistors and other elements on a single chip.
- **Moore's Law:** An observation that the number of transistors on an IC doubles approximately every 18 months, driving exponential growth in computing power and density.
- **Semiconductor Memory:** Replaced earlier, slower memory technologies, offering increased speed and capacity.
- **Microprocessors:** A complete CPU fabricated on a single chip, revolutionizing personal computing and embedded systems.
- **Multicore Processors:** Integrating multiple CPUs onto a single chip to leverage parallel processing.

## Computer Organization and Architecture Concepts

### Von Neumann Architecture

- A computer architecture characterized by a stored-program concept where both instructions and data are stored in the same memory.
- Consists of:
    - Central Processing Unit (CPU)
    - Main Memory (M)
    - Input/Output (I/O) Equipment
    - Interconnections (buses)

### IAS Computer Structure and Operation

- **Structure:** CPU (ALU, Control Unit, Registers), Main Memory, I/O.
- **Registers:** MBR, MAR, IR, IBR, PC, AC, MQ.
- **Memory Formats:** 40-bit words, capable of holding data or two instructions.
- **Operation:** Involves fetch, decode, and execute cycles. The PC guides instruction fetching, and the IR holds the current instruction for decoding. Data is processed using registers like AC and MQ.

### Instruction Set Architectures (ISA)

- **CISC (Complex Instruction Set Computer):** Features a large set of complex instructions that can perform multiple operations in a single step (e.g., x86 architecture).
    - Example CISC compilation: `add mem(B), mem(C), mem(A)`
- **RISC (Reduced Instruction Set Computer):** Features a smaller set of simpler, faster instructions, often requiring more instructions to perform complex tasks (e.g., ARM architecture).
    - Example RISC compilation:
        
        ```
        load mem(B), reg(1);
        load mem(C), reg(2);
        add reg(1), reg(2), reg(3);
        store reg(3), mem(A);
        ```
        

### Performance Factors

- **Instruction Set Architecture:** The complexity and efficiency of the instructions a processor can execute.
- **Compiler Technology:** How effectively a compiler translates high-level code into machine instructions.
- **Processor Implementation:** The design and technology used to build the processor (e.g., clock speed, number of cores, pipeline depth).
- **Cache and Memory Hierarchy:** The use of multiple levels of memory (registers, cache, main memory, secondary storage) to reduce average memory access time.

### Performance Balance

- The practice of adjusting computer system organization and architecture to compensate for performance mismatches between components (e.g., processor vs. memory speed).
- Techniques include wider data paths, efficient cache structures, improved memory interfaces, and higher-speed buses.

### Microprocessor Speed and Evolution

- **Clock Speed:** The rate at which the processor executes instructions, measured in Hz (Hertz).
- **Transistor Count:** Increases with each generation, enabling greater complexity and performance.
- **Feature Size:** The minimum feature size (in nanometers or micrometers) on the chip, smaller sizes allow for more transistors and higher speeds.
- **Bus Width:** The number of bits that can be transferred simultaneously between the processor and memory.
- **Addressable Memory:** The maximum amount of memory a processor can access.
- **Cache:** Small, fast memory located on or near the processor to store frequently accessed data, reducing latency.
- **Parallelism:** Techniques like pipelining, superscalar execution, and multicore processing to execute multiple instructions or operations concurrently.

## Embedded Systems

- **Definition:** Computer systems with a dedicated function, often part of a larger system.
- **Characteristics:**
    - Specific application requirements and constraints.
    - Wide range of system sizes and complexities.
    - Varying environmental conditions.
    - May have strict real-time or reliability requirements.
- **Examples:** Automotive systems, consumer electronics, industrial control, medical devices.
- **Organization:** Typically includes a processor, memory, I/O interfaces, and may integrate specialized hardware like FPGAs or ASICs.
- **ARM Architecture:** Widely used in embedded systems due to its low power consumption, small die size, and good performance-to-power ratio.

## Performance Assessment

### Benchmarks

- **Definition:** A collection of programs designed to test and evaluate the performance of computer systems in specific application areas.
- **Purpose:** To provide a representative and objective measure of performance for comparison and research.
- **SPEC (System Performance Evaluation Corporation):** An industry consortium that defines and maintains benchmark suites.
    - **SPEC CPU2006:** A widely used suite for processor-intensive applications, consisting of floating-point and integer programs.

### Amdahl's Law

- **Concept:** Describes the theoretical speedup achievable by parallelizing a task. It highlights that the overall speedup is limited by the sequential portion of the task.
- **Formula:** $$Speedup=1/(1−f)+f/​N$$​ where:
    - ff is the fraction of the task that can be parallelized.
    - NN is the number of processors.
- **Implication:** Even with a large number of processors, speedup is limited if a significant portion of the task cannot be parallelized.

### Little's Law

- **Concept:** A fundamental queuing theory principle relating the average number of items in a stable system to the average arrival rate and the average time an item spends in the system.
- **Formula:** L=λ×WL=λ×W where:
    - LL is the average number of items in the system.
    - λλ is the average arrival rate of items.
    - WW is the average time an item spends in the system.
- **Application:** Useful for analyzing the performance of systems with queues, such as computer systems and networks.