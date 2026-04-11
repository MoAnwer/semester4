---
tags:
  - sheets
  - coa
banner: "pixel-banner-images/Modern high-rise urban streetscape-1.jpg"
banner-x: 44
banner-y: 63
banner-fade: -15
---

## Computer Components and Function

# Computer Function and Interconnection

## Introduction to Computer Architecture

The contemporary computer design is largely based on the **von Neumann architecture**, conceptualized by John von Neumann. Its core principles are:

- **Single Memory:** Data and instructions are stored in a single read-write memory.
- **Addressable Memory:** Memory contents are addressable by location, regardless of the data type.
- **Sequential Execution:** Instructions are executed sequentially unless explicitly modified.

### Hardware vs. Software Approaches to Programming

- **Hardware Programming (Hardwired Program):** This involves physically connecting components in a specific configuration to perform a sequence of arithmetic and logic functions. This is inflexible as changes require rewiring.
- **Software Programming:** This uses instruction codes interpreted by a general-purpose arithmetic and logic unit. Control signals are generated based on these instructions, making the system programmable and adaptable.

## Computer Components: Top-Level View

A computer system consists of several key modules interconnected by a system bus:

- **Central Processing Unit (CPU):** The brain of the computer, responsible for fetching, decoding, and executing instructions. Key internal registers include:
    - **Program Counter (PC):** Holds the address of the next instruction to be fetched.
    - **Instruction Register (IR):** Holds the instruction currently being executed.
    - **Memory Address Register (MAR):** Holds the address of the memory location to be accessed.
    - **Memory Buffer Register (MBR):** Holds the data being transferred to or from memory.
    - **Accumulator (AC):** A general-purpose register for temporary storage during computations.
- **Main Memory:** Stores both instructions and data. It is organized into addressable locations.
- **I/O Modules:** Handle communication with external devices. They have their own registers, such as:
    - **Input/Output Address Register (I/O AR):** Holds the address of an I/O device.
    - **Input/Output Buffer Register (I/O BR):** Holds data being transferred to or from an I/O device.
- **System Bus:** Connects the CPU, Main Memory, and I/O Modules, facilitating data, address, and control signal transfers.

## The Instruction Cycle

The fundamental operation of a computer is the **instruction cycle**, which consists of two main phases:

1. **Fetch Cycle:**
    - The Program Counter (PC) holds the address of the next instruction.
    - The CPU fetches the instruction from memory at the address specified by the PC.
    - The PC is incremented to point to the next instruction in sequence.
    - The fetched instruction is loaded into the Instruction Register (IR).
2. **Execute Cycle:**
    - The CPU decodes the instruction in the IR.
    - The CPU performs the action specified by the instruction (e.g., arithmetic operation, data transfer, control flow change).

This cycle repeats until the program is halted.

### Instruction Cycle State Diagram

The instruction cycle can be further broken down into states:

- Instruction fetch
- Operand fetch (if the instruction requires data from memory)
- Instruction operation (performing the actual computation or data manipulation)
- Operand store (writing results back to memory)

### Example of Program Execution

Let's trace a simple program execution using hypothetical machine characteristics:

**Hypothetical Machine Characteristics:**

- **Instruction Format:** Opcode (4 bits) and Address (16 bits).
- **Opcodes:**
    - `0001`: Load AC from Memory
    - `0010`: Store AC to Memory
    - `0101`: Add to AC from Memory
- **Registers:** PC, IR, AC.

**Example Program:** Load a value from memory address 940 into the Accumulator (AC), then add a value from memory address 941 to the AC.

**Initial State:**

- Memory:
    - Location 300: `1940` (Instruction: Load AC from 940)
    - Location 301: `5941` (Instruction: Add to AC from 941)
    - Location 302: `2940` (Instruction: Store AC to 940)
    - Location 940: `0003` (Data value)
    - Location 941: `0005` (Data value)
- CPU Registers:
    - PC: `300`

**Execution Steps:**

1. **Fetch Instruction 1:**
    - PC (`300`) points to memory location 300.
    - Instruction `1940` is fetched.
    - PC is incremented to `301`.
    - IR holds `1940`.
2. **Execute Instruction 1 (Load AC from 940):**
    - Opcode `0001` (Load AC) is recognized.
    - Address `940` is used.
    - The value `0003` from memory location 940 is loaded into AC.
    - CPU Registers: PC=`301`, IR=`1940`, AC=`0003`.
3. **Fetch Instruction 2:**
    - PC (`301`) points to memory location 301.
    - Instruction `5941` is fetched.
    - PC is incremented to `302`.
    - IR holds `5941`.
4. **Execute Instruction 2 (Add to AC from 941):**
    - Opcode `0101` (Add to AC) is recognized.
    - Address `941` is used.
    - The value `0005` from memory location 941 is added to AC.
    - AC becomes `0003 + 0005 = 0008`.
    - CPU Registers: PC=`302`, IR=`5941`, AC=`0008`.
5. **Fetch Instruction 3:**
    - PC (`302`) points to memory location 302.
    - Instruction `2940` is fetched.
    - PC is incremented to `303`.
    - IR holds `2940`.
6. **Execute Instruction 3 (Store AC to 940):**
    - Opcode `0010` (Store AC) is recognized.
    - Address `940` is used.
    - The value in AC (`0008`) is stored into memory location 940.
    - Memory Location 940 now contains `0008`.
    - CPU Registers: PC=`303`, IR=`2940`, AC=`0008`.
7. **Fetch Next Instruction:**
    - PC (`303`) would now fetch the next instruction, continuing the cycle.

## Interrupts

Interrupts are signals that alter the normal sequential flow of program execution, typically indicating an event that requires immediate attention.

### Classes of Interrupts:

- **Program Interrupts:** Generated by conditions arising from instruction execution (e.g., arithmetic overflow, division by zero, illegal instruction).
- **Timer Interrupts:** Generated by an internal processor timer, allowing the OS to perform periodic tasks.
- **I/O Interrupts:** Generated by an I/O controller to signal completion, request service, or report errors.
- **Hardware Failure Interrupts:** Generated by hardware malfunctions (e.g., power failure, memory parity error).

### Program Flow Control with Interrupts

Without interrupts, a program runs sequentially. With interrupts:

- A user program can be interrupted by an event.
- Control is transferred to an **Interrupt Handler** (a special routine).
- After the interrupt is processed, control may return to the interrupted program.
- This allows the processor to handle I/O operations concurrently with program execution, improving efficiency.

### Instruction Cycle With Interrupts

The instruction cycle is modified to include an **Interrupt Cycle**:

- **Fetch Cycle:** Fetches the next instruction.
- **Execute Cycle:** Executes the instruction.
- **Interrupt Check:** After executing an instruction, the processor checks if any interrupts are pending.
    - If interrupts are **disabled**, the cycle continues to fetch the next instruction.
    - If interrupts are **enabled** and an interrupt is pending, the **Interrupt Cycle** is initiated.
- **Interrupt Cycle:**
    - Control is transferred to the interrupt handler.
    - The current state of the interrupted program is saved.
    - The interrupt handler is executed.
    - The saved state is restored, and control returns to the interrupted program.

### Transfer of Control via Interrupts

When an interrupt occurs, the processor:

1. Saves the current PC value.
2. Loads the PC with the starting address of the interrupt handler.
3. Executes the interrupt handler.
4. Restores the saved PC value to resume the interrupted program.

### Multiple Interrupts and Nesting

- **Sequential Interrupt Processing:** Interrupts are handled one after another.
- **Nested Interrupt Processing:** A higher-priority interrupt can interrupt a lower-priority interrupt handler. This requires saving the state of the interrupted handler as well.

## Input/Output (I/O) Functions

I/O modules allow the CPU to communicate with external devices. Key aspects include:

- **Data Exchange:** I/O modules can exchange data directly with the processor or, in some cases, directly with memory.
- **Device Identification:** The processor identifies specific devices through I/O module addresses.
- **I/O Instructions:** The processor uses special I/O instructions (rather than memory-referencing instructions) to interact with I/O devices.
- **Direct Memory Access (DMA):** A powerful I/O technique where an I/O module is granted authority to transfer data directly to or from main memory without continuous CPU intervention. This significantly relieves the processor of I/O responsibilities.

## Interconnection Structures: The Bus

The **bus** is the primary interconnection mechanism in a computer system, providing communication pathways among the CPU, memory, and I/O modules.

### Types of Buses:

1. **Data Bus:**
    - Carries data between modules.
    - Its **width** (number of lines, e.g., 32, 64, 128 bits) determines how many bits can be transferred simultaneously, significantly impacting performance.
2. **Address Bus:**
    - Specifies the source or destination of data on the data bus.
    - Its **width** determines the maximum addressable memory capacity.
    - Used to select a particular module and then a specific location (memory or I/O port) within that module.
3. **Control Bus:**
    - Manages access to and use of the data and address lines.
    - Carries **command signals** (specifying operations like read, write) and **timing signals** (indicating data validity).

### Bus Operation:

- Modules share the data and address lines, necessitating control mechanisms.
- The processor places an address on the address bus and a command on the control bus.
- The addressed module responds via the data bus.

### Computer Modules (General Structure):

A typical computer system comprises modules that interact via buses:

- **CPU:** Executes instructions.
- **Memory:** Stores data and instructions.
- **I/O Modules:** Interface with external devices, possessing internal data ports and external data ports.
- **Internal Data Bus:** Connects CPU, Memory, and I/O modules.
- **External Data Bus:** Connects to external I/O devices.
- **Control and Interrupt Signals:** Manage communication flow and event notifications.