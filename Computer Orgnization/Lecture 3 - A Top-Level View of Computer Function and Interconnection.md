---
tags:
  - sheets
  - coa
banner: pixel-banner-images/Modern high-rise urban streetscape-1.jpg
banner-x: 44
banner-y: 63
banner-fade: -15
---

## Computer Components and Function

### Von Neumann Architecture

The von Neumann architecture, developed by John von Neumann, is the foundation for contemporary computer designs. It is characterized by three key concepts:

- **Single Memory:** Data and instructions are stored in a single, shared read-write memory.
- **Addressable Memory:** The contents of memory are addressable by location, irrespective of the data type stored.
- **Sequential Execution:** Operations are executed sequentially, one instruction after another, unless explicitly altered by control flow mechanisms.

### Hardware vs. Software Approaches

- **Hardware Programming:** In this approach, the desired configuration of components is physically wired. This results in a "hardwired program" where the sequence of operations is fixed by the hardware connections.
- **Software Programming:** This approach uses a general-purpose set of hardware components (CPU, memory, I/O) and a program (a sequence of instruction codes) that dictates the operations. An instruction interpreter within the CPU decodes these codes and generates control signals to direct the hardware.

### Top-Level Computer Components

A high-level view of a computer reveals several key components connected by a system bus:

- **Central Processing Unit (CPU):** The brain of the computer, responsible for executing instructions. Key internal registers include:
    - Program Counter (PC): Holds the address of the next instruction to be fetched.
    - Instruction Register (IR): Holds the instruction currently being executed.
    - Accumulator (AC): A general-purpose register for temporary data storage.
- **Memory:** Stores both data and instructions. Key components include:
    - Memory Address Register (MAR): Holds the address of the memory location to be accessed.
    - Memory Buffer Register (MBR): Temporarily holds data being read from or written to memory.
- **I/O Module:** Manages communication with external devices. Key components include:
    - Input/Output Address Register (I/O AR): Holds the address of the I/O device.
    - Input/Output Buffer Register (I/O BR): Temporarily holds data being transferred to or from an I/O device.
- **System Bus:** The communication pathway connecting the CPU, Memory, and I/O modules. It consists of:
    - Data Bus: Carries data between modules.
    - Address Bus: Specifies the source or destination of data.
    - Control Bus: Carries control and timing signals.

## The Instruction Cycle

### Basic Instruction Cycle

The fundamental operation of a CPU is the instruction cycle, which consists of two main phases:

1. **Fetch Cycle:** The CPU retrieves an instruction from memory.
2. **Execute Cycle:** The CPU decodes and performs the action specified by the instruction.

This cycle repeats until the `HALT` instruction is encountered.

### Fetch Cycle Details

During the fetch cycle:

1. The address of the next instruction is fetched from the Program Counter (PC).
2. The PC is incremented to point to the next instruction in sequence.
3. The instruction at the address specified by the PC is loaded into the Instruction Register (IR).
4. The CPU interprets the instruction.

### Instruction Cycle State Diagram

The instruction cycle can be visualized as a state diagram, progressing through states like:

- Instruction Fetch
- Instruction Operand Address Calculation
- Instruction Operand Fetch
- Instruction Operation
- Instruction complete (fetch next instruction)

### Example of Program Execution (Hexadecimal)

Let's trace a simple sequence of operations:

**Initial State:**

- Memory:
    - Location 300: `1940` (Load AC from Memory)
    - Location 301: `5941` (Add to AC from Memory)
    - Location 302: `2941` (Store AC to Memory)
    - Location 940: `0003` (Data)
    - Location 941: `0005` (Data)
- CPU Registers:
    - PC: `300`
    - AC: (empty)
    - IR: (empty)

**Step 1: Fetch Instruction (at PC=300)**

- PC is `300`.
- Instruction `1940` is fetched from memory location `300` and loaded into IR.
- PC is incremented to `301`.

**Step 2: Execute Instruction (IR = 1940 - Load AC)**

- The instruction `1940` means "Load AC from Memory address `940`".
- The value `0003` from memory location `940` is loaded into AC.

**Step 3: Fetch Instruction (at PC=301)**

- PC is `301`.
- Instruction `5941` is fetched from memory location `301` and loaded into IR.
- PC is incremented to `302`.

**Step 4: Execute Instruction (IR = 5941 - Add to AC)**

- The instruction `5941` means "Add to AC from Memory address `941`".
- The value `0005` from memory location `941` is added to the current value in AC (`0003`).
- AC becomes `0008`.

**Step 5: Fetch Instruction (at PC=302)**

- PC is `302`.
- Instruction `2941` is fetched from memory location `302` and loaded into IR.
- PC is incremented to `303`.

**Step 6: Execute Instruction (IR = 2941 - Store AC)**

- The instruction `2941` means "Store AC to Memory address `941`".
- The value in AC (`0008`) is written to memory location `941`.

This example demonstrates the fetch-decode-execute cycle for a simple program involving loading data, arithmetic, and storing results.

### Instruction Cycle State Diagram with Interrupts

The instruction cycle can be extended to include interrupt handling:

- Instruction Fetch
- Instruction Operand Address Calculation
- Instruction Operand Fetch
- Instruction Operation
- Interrupt Check (if enabled)
- Instruction Complete (fetch next instruction, or process interrupt)

## Interrupts

### Classes of Interrupts

Interrupts are signals that alter the normal flow of program execution. They can be categorized as:

- **Program Interrupts:** Generated by conditions during instruction execution (e.g., arithmetic overflow, division by zero, illegal instruction).
- **Timer Interrupts:** Generated by an internal processor timer, used for periodic operating system tasks.
- **I/O Interrupts:** Generated by an I/O controller to signal operation completion, request service, or report errors.
- **Hardware Failure Interrupts:** Generated by hardware malfunctions (e.g., power failure, memory parity error).

### Program Flow Control with Interrupts

Interrupts allow for more efficient use of the processor, especially during I/O operations.

- **Without Interrupts:** If a program performs an I/O operation, the processor might have to wait idly until the I/O is complete.
- **With Interrupts:** While an I/O operation is in progress, the processor can switch to executing another program or task. An interrupt signal from the I/O device alerts the processor when the I/O is done, allowing it to resume or switch back.

### Transfer of Control via Interrupts

When an interrupt occurs:

1. The current state of the executing program is saved (e.g., PC, register values).
2. Control is transferred to a special program called an interrupt handler (or interrupt service routine).
3. The interrupt handler performs the necessary actions to service the interrupt.
4. Once the interrupt is handled, the saved state of the interrupted program is restored, and execution resumes from where it left off.

### Instruction Cycle With Interrupts

The instruction cycle is modified to include an "Interrupt Cycle":

1. **Fetch Cycle:** Fetch instruction.
2. **Execute Cycle:** Execute instruction.
3. **Interrupt Check:** After executing an instruction, the processor checks if any interrupts are pending and enabled.
4. **Interrupt Cycle:** If an interrupt is detected and enabled, the processor saves the current state, loads the address of the interrupt handler, and begins executing it.
5. The cycle then returns to the Fetch cycle to fetch the next instruction (either from the interrupted program or the interrupt handler).

### Program Timing with Interrupts

- **Short I/O Wait:** Without interrupts, the processor might spend significant time waiting for I/O. With interrupts, the processor can perform other tasks during the I/O wait, improving overall utilization.
- **Long I/O Wait:** Similar to short waits, interrupts allow the processor to be productive during prolonged I/O operations.

### Transfer of Control with Multiple Interrupts

Computers can handle multiple interrupts.

- **Sequential Interrupt Processing:** Interrupts are handled one after another in the order they are recognized.
- **Nested Interrupt Processing:** An interrupt handler for a higher-priority interrupt can be interrupted by an even higher-priority interrupt. The system saves the state of the current handler and switches to the new one. Once the highest-priority interrupt is resolved, the system returns to lower-priority handlers.

## I/O Function

### I/O Module Interaction

I/O modules can interact with the processor in several ways:

- **Processor-Controlled I/O:** The processor issues I/O instructions (like `IN` or `OUT`) to read data from or write data to specific I/O devices. The processor identifies the device using an address.
- **Direct Memory Access (DMA):** In DMA, an I/O module is granted permission to transfer data directly to or from main memory without continuous processor intervention. The processor initiates the transfer, and the I/O module handles the reading/writing of blocks of data from/to memory. This frees up the processor for other tasks.

## Interconnection Structures

### Computer Modules

A computer system consists of several modules:

- **CPU:** Central Processing Unit.
- **Memory:** Main memory for storing data and instructions.
- **I/O Modules:** Interface with peripheral devices.
- **System Bus:** Connects these modules.

### Bus Interconnection

A bus is a set of wires that acts as a shared communication pathway between system modules. It typically comprises three parts:

- **Data Bus:** Transfers data between modules. Its width (number of lines) determines how many bits can be transferred simultaneously, impacting performance.
- **Address Bus:** Specifies the source or destination of data. Its width determines the maximum addressable memory capacity.
- **Control Bus:** Carries control and timing signals, managing bus access and operations. Examples include read/write signals, clock signals, and interrupt requests.

### Bus Design Elements

Key considerations in bus design include:

- **Bus Width:** The number of data lines.
- **Method of Arbitration:** How multiple devices share the bus (e.g., centralized or distributed control).
- **Data Transfer Type:** Read, Write, Read-modify-write, Block transfers.
- **Timing:**
    - **Synchronous Bus:** Operations are synchronized by a clock signal. All devices operate in lockstep with the clock.
    - **Asynchronous Bus:** Operations are controlled by signals exchanged between devices, allowing for devices with different speeds to communicate effectively without a global clock dictating all timings.

### Point-to-Point Interconnect

Modern high-performance systems often use point-to-point interconnects instead of traditional shared buses. These provide dedicated communication paths between components.

- **QuickPath Interconnect (QPI):** An Intel technology that uses multiple direct, pairwise connections between components (CPU cores, memory controllers, I/O hubs). It features a layered protocol architecture for packetized data transfer, including routing and link-layer functions for flow and error control.
- **PCI Express (PCIe):** A popular high-bandwidth, point-to-point serial interconnect designed to replace older bus architectures. It offers high capacity and supports time-dependent data streams. PCIe uses a layered protocol (Transaction, Data Link, Physical) and operates with a multilane distribution for increased bandwidth.

### PCIe Protocol Layers

- **Transaction Layer (TL):** Handles the creation of packets (Transaction Layer Packets - TLPs) for read/write requests and responses. It supports memory, I/O, configuration, and message address spaces. TLPs can be split transactions (request and completion packets) or posted transactions (no response expected).
- **Data Link Layer (DLL):** Ensures reliable data transfer between directly connected devices. It adds error detection (CRC) and flow control mechanisms to TLPs, forming Data Link Layer Packets (DLLPs).
- **Physical Layer (PL):** Handles the electrical signaling and encoding/decoding of data for transmission over the physical links (lanes). It uses techniques like 8b/10b or 128b/130b encoding to ensure clock recovery and data integrity.