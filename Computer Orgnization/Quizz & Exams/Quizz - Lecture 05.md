Here is a **50-question exam** (Multiple Choice & True/False) based *exclusively* on the content of the provided lecture notes ("Lecture 05 - Reduce instruction set computer.pdf"). The questions cover CISC, RISC, performance characteristics, register windows, graph coloring, pipelining, and superscalar concepts.

---

## Part 1: Multiple Choice Questions (MCQs)
*Choose the best answer for each question.*

**1.** According to the lecture, what has caused a shift in costs from hardware to software?
a) Hardware is becoming more reliable  
b) A chronic shortage of programmers  
c) Software is easier to test  
d) High-Level Languages are declining  



**2.** The "semantic gap" refers to the difference between:
a) Memory speed and processor speed  
b) HLL operations and computer architecture operations  
c) Static and dynamic measurement  
d) RISC and CISC power consumption  


**3.** Which instruction set characteristic was intended to close the semantic gap in CISC?
a) Simple addressing modes  
b) Large instruction sets and dozens of addressing modes  
c) Fixed instruction length  
d) Register-to-register operations only  

**4.** The CASE machine instruction mentioned in the notes was found on which architecture?
a) SPARC  
b) MIPS  
c) VAX  
d) Pyramid  

**5.** Studies show that the most frequently occurring statement type in HLL programs is:
a) Procedure calls  
b) Conditional statements (IF/LOOP)  
c) Assignment statements  
d) GOTO statements  

**6.** Which HLL operation is identified as the *most time-consuming* in typical programs, despite being less frequent?
a) Assignment statements  
b) Arithmetic operations  
c) Procedure call/return  
d) Memory load operations  

**7.** Tanenbaum and the Berkeley RISC team found that what percentage of procedure calls involve fewer than six arguments?
a) 92%  
b) 78%  
c) 98%  
d) 65%  

**8.** According to locality studies, most data access is concentrated in:
a) Global arrays  
b) A small number of local scalar variables per procedure  
c) Memory-mapped I/O  
d) Instruction cache  

**9.** Which of the following is a core RISC design strategy?
a) Make hardware complex to match HLLs  
b) Optimize performance of the most time-consuming program features  
c) Implement every HLL statement in microcode  
d) Use many indirect addressing modes  

**10.** Why are registers faster than cache or RAM? (Select the one NOT listed)
a) Physical proximity to ALU  
b) Small size allows near-instant access  
c) They use longer addresses for precision  
d) Short addressing (small number of registers)

**11.** The "Software Approach" to register optimization relies on:
a) Increasing the number of physical registers  
b) The compiler using sophisticated algorithms  
c) Hardware-managed register windows  
d) Removing all memory operations  

**12.** The "Hardware Approach" (e.g., Berkeley RISC) uses:
a) A small number of registers  
b) Graph coloring only  
c) A large register file  
d) No registers at all  

**13.** What problem do Register Windows primarily solve?
a) ALU latency  
b) Procedure call overhead (save/restore)  
c) Instruction fetch conflicts  
d) Power dissipation  

**14.** In a Register Window, parameters are passed from one procedure to another using:
a) Memory stack  
b) Overlapping registers (OUT of caller = IN of callee)  
c) Dedicated communication ports  
d) Compiler-generated temporary variables  

**15.** Each Register Window is typically divided into three areas. Which is NOT one of them?
a) Parameter Registers (IN)  
b) Local Registers  
c) Global Shared Registers  
d) Temporary Registers (OUT)  

**16.** Register windows are organized as a circular buffer to:
a) Increase the number of ALUs  
b) Handle nesting deeper than available windows  
c) Simplify compiler design  
d) Eliminate all memory access  

**17.** With 8 register windows, what percentage of calls/returns require memory access (save/restore)?
a) 50%  
b) 25%  
c) 10%  
d) 1%  

**18.** In the circular buffer, when the Current Window Pointer (CWP) meets the Saved Window Pointer (SWP), the processor:
a) Continues silently  
b) Generates an interrupt and saves the oldest window to memory  
c) Shuts down  
d) Doubles the clock speed  

**19.** Graph coloring is a technique used by compilers to:
a) Design user interfaces  
b) Assign symbolic variables to physical registers  
c) Color the processor die  
d) Optimize branch prediction  

**20.** In graph coloring, an edge between two nodes (variables) means:
a) They are never used  
b) They are "live" at the same time and cannot share a register  
c) They are constants  
d) They must be stored in memory  

**21.** If a node cannot be colored (too many conflicts), the compiler performs:
a) Spilling (moves variable to memory)  
b) Register renaming  
c) Loop unrolling  
d) Delayed branch  

**22.** The lecture’s key finding on hardware vs. software trade-off states that with advanced graph coloring, performance barely improves beyond how many registers?
a) 16  
b) 32  
c) 64  
d) 128  

**23.** A classic RISC characteristic is:
a) One instruction per machine cycle  
b) Multiple memory-addressed operands per instruction  
c) Indirect addressing required  
d) Variable instruction length  

**24.** In RISC, a "machine cycle" is defined as the time to:
a) Access disk  
b) Fetch two operands from registers, perform ALU op, store result  
c) Execute a microinstruction  
d) Load from main memory  

**25.** Most RISC operations should be:
a) Memory-to-memory  
b) Register-to-register with simple LOAD/STORE for memory  
c) Complex string operations  
d) Implicitly addressed  

**26.** How many data addressing modes are typically found in a classic RISC?
a) More than 20  
b) Less than five  
c) Exactly 12  
d) Zero  

**27.** Which feature is NOT supported by classic RISC?
a) Fixed instruction size (e.g., 4 bytes)  
b) Operations that combine load/store with arithmetic (e.g., add from memory)  
c) Register-to-register operations  
d) Simple displacement addressing  

**28.** A two-stage pipeline (Fetch + Execute) theoretically:
a) Halves the execution rate  
b) Doubles the execution rate  
c) Quadruples power  
d) Has no effect  

**29.** To solve pipeline hazards without complex hardware, RISC compilers insert:
a) More registers  
b) NOOP (No Operation) instructions  
c) Complex microcode  
d) Indirect jumps  

**30.** Delayed branch means:
a) Branch takes effect immediately  
b) Branch does not take effect until after executing the following instruction (delay slot)  
c) Branches are forbidden  
d) The pipeline is always flushed  

**31.** Loop unrolling is used to:
a) Increase loop overhead  
b) Reduce loop overhead and increase instruction parallelism  
c) Decrease code size  
d) Prevent pipelining  

**32.** A superscalar architecture achieves parallelism by:
a) Increasing clock frequency only  
b) Replicating pipeline stages (multiple lanes)  
c) Using a single long pipeline  
d) Removing all registers  

**33.** A super-pipelined architecture increases parallelism by:
a) Adding more parallel lanes  
b) Using more registers  
c) Increasing the number of pipeline stages (making them finer)  
d) Decreasing the number of stages  

**34.** Which architecture is cited as using register windows (hardware approach)?
a) Intel 8086  
b) SPARC  
c) ARM (original)  
d) MIPS  

**35.** According to the notes, what is the primary drawback of super-pipelining?
a) Complex coordination logic  
b) Transfer overhead between stages  
c) No support for loops  
d) Cannot be used with RISC  

**36.** What does the "delayed load" technique do?
a) Stops all execution until load completes  
b) Locks the target register and continues execution until the register is required  
c) Eliminates all loads  
d) Converts loads to stores  

**37.** The Berkeley RISC group pioneered which approach?
a) Graph coloring only  
b) Hardware register windows  
c) Microprogrammed CISC  
d) Variable-length instructions  

**38.** The MIPS architecture is known for:
a) Extremely complex instructions  
b) Simplified instruction set enabling efficient pipelining  
c) No pipelining support  
d) Large number of addressing modes  

**39.** A classic RISC does NOT support:
a) Fixed instruction length  
b) Indirect addressing (memory access for address of another operand)  
c) PC-relative addressing  
d) Load and store instructions  

**40.** According to the notes, Pyramid computers employed how many register windows?
a) 4  
b) 8  
c) 16  
d) 32  

---

## Part 2: True / False
*Write T for True or F for False.*

**41.** The semantic gap led CISC designers to make hardware simpler.  
**42.** Static measurement (counting source lines) accurately reflects actual program workload.  
**43.** Conditional statements (IF/LOOP) are less frequent than procedure calls in HLL programs.  
**44.** Procedure call/return is the most time-consuming operation in compiled HLL programs.  
**45.** 92% of procedures use fewer than six local scalar variables (according to Tanenbaum/Berkeley RISC).  
**46.** Registers are slower than cache because they are farther from the ALU.  
**47.** The software approach to register optimization relies on the compiler (graph coloring).  
**48.** In register windows, the OUT registers of the caller are physically the same as the IN registers of the callee.  
**49.** A circular buffer for register windows requires memory access on every procedure call.  
**50.** RISC architectures typically use a single instruction size (e.g., 4 bytes) and simple addressing modes.

---

## Answer Key

**MCQs:**
1. b  
2. b  
3. b  
4. c  
5. c  
6. c  
7. c  
8. b  
9. b  
10. c  
11. b  
12. c  
13. b  
14. b  
15. c  
16. b  
17. d  
18. b  
19. b  
20. b  
21. a  
22. b  
23. a  
24. b  
25. b  
26. b  
27. b  
28. b  
29. b  
30. b  
31. b  
32. b  
33. c  
34. b  
35. b  
36. b  
37. b  
38. b  
39. b  
40. c  

**True/False:**
41. F  
42. F  
43. F  
44. T  
45. T  
46. F  
47. T  
48. T  
49. F  
50. T