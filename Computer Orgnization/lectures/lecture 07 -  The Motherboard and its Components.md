---
tags:
  - coa
---

## Introduction to the Motherboard

The motherboard is the central printed circuit board that houses the main components of a computer. These components can be soldered directly to the board or installed in corresponding sockets and connectors. Motherboards are often sold separately, allowing users to customize their computer builds with their preferred processor, memory, and other components.

Key elements found on or connected to the motherboard include:

- **CPU Socket:** Where the processor is installed.
- **Memory Slots:** For installing RAM modules.
- **Bus Connectors:** For connecting various expansion cards and peripherals.
- **Power Connectors:** To receive power from the power supply.
- **Data Connectors:** For hard drives, optical drives, and floppy drives.
- **External Ports:** For connecting external devices like monitors, keyboards, and mice.

## Chipset

The chipset is a set of integrated circuits soldered onto the motherboard that significantly determines its features and capabilities. These chips cannot be changed. The chipset dictates crucial aspects of the computer system, including:

- The type of processor supported.
- The type of memory supported.
- The type of bus systems used.
- The method of data exchange with external devices.

Historically, early motherboards required multiple chips to manage system functions. The introduction of integrated chipset components, like the 82C206 by Chips and Technologies in 1986, revolutionized motherboard design by consolidating many functions into a single chip. Modern chipsets often employ a multi-chip architecture, typically involving a Northbridge and a Southbridge, though newer designs may integrate these functions.

- **Northbridge:** Connects the processor, memory, and high-speed buses (like AGP and PCI). It acts as the primary control system for these components.
- **Southbridge:** Connects to slower buses (like PCI and ISA) and I/O controllers. In modern chipsets, the Southbridge often incorporates the functionality of the Super I/O chip.
- **Super I/O Chip:** A specialized chip that integrates many common external device controllers. In newer systems, this function is typically integrated into the Southbridge.

## CPU Socket and Processor

The CPU socket is the connector on the motherboard where the processor is installed. Processors are connected via sockets to allow for user preference in installation and for easy replacement in case of failure. Intel pioneered user-installable processors and developed standards for CPU sockets and slots. A significant innovation was the Zero Insertion Force (ZIF) design, which allows processors to be installed and removed easily without tools.

## Motherboard Form Factors

Motherboard models differ in physical size, shape, mounting locations, layout, and power connectors. Several form factors have dominated the PC industry:

- **Backplane Systems:** These systems can be passive (only bus connectors) or active (containing most motherboard components except the processor). They offer easier upgrades but can be more expensive.
    
- **AT (Advanced Technology):** Coincides with the original IBM AT motherboard design.
    
- **Baby-AT:** A smaller version of the AT form factor that became very popular due to its flexibility and compatibility with various cases.
    
- **LPX (Low Profile Extended) & Mini-LPX:** A semi-proprietary design where expansion slots are located on a riser card plugged into the motherboard, allowing for shorter computer cases.
    
- **NLX (New Low Profile Extended):** An enhanced, standardized version of LPX. The NLX motherboard itself plugs into a riser card, allowing for easier removal of the motherboard without disturbing expansion cards.
    
- **ATX (Advanced Technology Extended):** Developed by Intel in the mid-1990s, ATX improved upon the AT design. Processor and memory slots are oriented at right angles to expansion slots, improving airflow from the power supply fan for better CPU cooling. Standard ATX measures approximately 305 mm × 244 mm.
    - **Micro ATX (μATX):** A smaller version of ATX (typically 244 mm × 244 mm) designed to fit in ATX cases. It follows ATX component placement principles for cooling but has a smaller footprint and may use lower wattage power supplies.
    - **Mini-ATX:** Not an official standard.
    - **FlexATX:** A smaller, more consumer-oriented ATX derivative.
- **ITX (Information Technology eXtreme):** Developed by VIA as a family of small form factor (SFF) boards for low-power, specialized uses.
    - **Mini-ITX:** 170 mm × 170 mm. Rear interfaces are compatible with ATX.
    - **Nano-ITX:** 120 mm × 120 mm.
    - **Pico-ITX:** 100 mm × 72 mm.
    - **Mobile-ITX:** 60 mm × 60 mm.
- **BTX (Balanced Technology Extended):** Announced by Intel in 2003 to improve cooling and component targeting. Its development was largely discontinued due to the trend towards dual-processor systems. BTX motherboards are not compatible with ATX designs, with I/O connectors typically located on the opposite side of the board.
    

## Bus Systems

A bus is a standardized connection for exchanging data between two or more devices within a computer (internal bus) or between a computer and peripheral devices (external bus). There are three main types of buses:

- **Data Bus:** Carries the actual data being transferred. The number of lines in the data bus determines the number of bits that can be processed simultaneously.
- **Address Bus:** Carries memory addresses or I/O port addresses to specify the source or destination of data. The number of lines determines the amount of memory the system can address.
- **Control Bus:** Carries supervisory and control signals (e.g., read/write signals, interrupt requests) to manage data flow and operations.

### Historical and Common Bus Types

- **ISA (Industry Standard Architecture):** Originally the "AT bus," it was an 8-bit bus that evolved to 16 bits. It ran at a maximum of 8 MHz with a theoretical bandwidth of 8 MB/s, though practical speeds were lower (1-2 MB/s). ISA was "intelligent" in that the CPU controlled all bus operations, leading to "wait states" when devices couldn't keep up. It remained common for compatibility until around 1999.
    
- **MCA (Micro Channel Architecture):** An advanced, patented I/O bus introduced by IBM in 1987.
    
- **EISA (Extended Industry Standard Architecture):** Developed by a consortium of companies as an alternative to MCA, offering 32-bit capabilities.
    
- **VL Bus (VESA Local Bus):** A genuine local bus introduced around 1993, it worked synchronously with the CPU's clock frequency, offering higher bandwidth (up to 160 MB/s) than ISA. It was a primitive extension of the system bus.
    
- **PCI (Peripheral Component Interconnect):** A processor-independent, general-purpose bus introduced around 1993, designed for high-speed expansion cards.
    - It supports speeds up to 33 MHz with a 32-bit bus width, yielding a maximum bandwidth of 32 bits×33.33 MHz≈133 MB/s32 bits×33.33 MHz≈133 MB/s.
    - It can communicate directly with memory.
    - Key benefits include high speed, processor independence, automatic configuration ("plug and play"), and adaptability.
    - PCI has buffer mechanisms allowing the CPU and peripherals to operate more independently.
- **AGP (Accelerated/Advanced Graphics Port):** A dedicated bus connector primarily for graphics cards, designed to meet their high data throughput requirements without saturating the PCI bus.
    
- **PCI Express (PCIe):** Introduced in 2004 as the successor to PCI and AGP.
    - It uses a serial connection architecture, allowing for high scalability through multiple "lanes" (x1, x2, x4, x8, x16).
    - Each lane offers a bandwidth of approximately 250 MB/s in both directions simultaneously.
    - A PCIe x16 slot can achieve a theoretical bandwidth of up to 16 lanes×250 MB/s/lane≈4 GB/s16 lanes×250 MB/s/lane≈4 GB/s.
    - PCIe is designed to replace both PCI and AGP, enabling smaller and cheaper devices due to its serial nature and fewer pins.