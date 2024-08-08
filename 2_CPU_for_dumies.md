## What is the CPU?
Central Processing Unit (CPU): 
The CPU is the primary component of a computer that performs most of the processing inside a computer. 
It executes instructions from programs and is often referred to as the "brain" of the computer.


## CPU Processors and CPU Cores
CPU Processor: The processor refers to the entire CPU chip, which can contain multiple cores.
It includes one or more cores, as well as other components such as cache memory and control units.
A single processor can have multiple cores, but it is considered one physical chip.

CPU Cores: A core is an individual processing unit within the CPU. 
Modern CPUs can have multiple cores, allowing them to perform multiple tasks simultaneously (parallel processing). 
For example, a quad-core CPU has four independent cores.

Hence, a quad-core processor will have 1 processor and 4 cores.
A dual quad-core processor will have 2 processors, each with 4 cores.

The most common processor and core combinations in modern laptops and mobile devices are:
- Quad-core processors: These are very common in both laptops and mobile devices. They offer a good balance of performance and power efficiency for a wide range of tasks.
- Hexa-core and Octa-core processors: These are becoming more common, especially in higher-end devices, providing even more performance for demanding applications.

### Examples,
- For Apple MacBook Air, the default is 1 processor (M1/M2/M3) with 8 cores (4 low performance and 4 high performance).
- For Apple iPhone 14 Pro, the default is 1 processor (Apple A15 Bionic) with Hexa-core (6 cores: 2 high-performance + 4 high-efficiency).
- Multiple cores are typically used in servers and high-end workstations. (like the Dell PowerEdge R740)


## CPU Transistor size
Transistor size, often referred to as the process node or technology node, is a key characteristic in semiconductor manufacturing. 
It indicates the smallest feature size of the transistors used in a CPU and is typically measured in nanometers (nm). 
Common process nodes in modern CPUs include 7nm, 10nm, and 14nm, among others.

### Why is it important?
- Performance: Smaller transistors can switch on and off faster, improving the overall speed and performance of the CPU. Reduces the distance that electrical signals must travel, further enhancing speed and efficiency.
- Power Efficiency: Smaller transistors require less power to operate, leading to lower power consumption and reduced heat generation. Enhanced power efficiency is particularly beneficial for mobile devices, where battery life is a critical factor.
- Density: Smaller transistors allow for more transistors to be packed into the same die area, increasing the overall transistor density. Higher density enables more cores and cache memory to be integrated into the CPU, enhancing parallel processing capabilities and performance.
- Cost: Advanced manufacturing processes with smaller transistors are more expensive and complex to develop and produce. However, over time, as manufacturing techniques mature, the cost per transistor decreases.
- Thermal Management: With higher density, effective thermal management becomes crucial to avoid overheating. Smaller transistors help manage heat better due to lower power consumption, but high-performance CPUs still require sophisticated cooling solutions.

### Examples,
- Intel i7 processors have 14nm transistor size.
- Apple 14 Bionic and AMD Ryzen 5000 use 7nm transistor size.
- Apple 15 Bionic and M1 use 5nm transistor size.
- Apple M3 has 3nm (~25 Billion transistors in the CPU). 


## CPU Caches
- Registers: Small, fast storage locations within the CPU used to hold data that the CPU is currently processing. 
They are the fastest type of memory but are very limited in size.
Different types include arithmetic, floating point, special instruction, vector registers (SIMD (Single Instruction, Multiple Data)).

The caches are made up of SRAM (Static Random Access Memory), which is faster and more expensive than the DRAM (Dynamic Random Access Memory) used in main memory.
- L1 Cache (Level 1): The smallest and fastest cache located within the CPU core.
It is divided into two parts: 1) L1i, the instruction cache (stores instructions), and the L1d, or data cache (stores data).
Typical Size: 16 KB to 128 KB per core
Access Time: Approximately 1 to 3 clock cycles. (roughly, ~1 nanosecond)

NOTE: Time can be calculated by the formula, time (in sec) = clock cycles used / clock speed of the CPU. 

- L2 Cache (Level 2): It is larger than L1 but slower.
L2 cache is usually located on the CPU chip but outside the core.
It serves as a bridge between the fast L1 cache and the slower main memory.
Typical Size: 256 KB to 1 MB per core.
Access Time: Approximately 3 to 10 clock cycles. (~3.33 nanoseconds)


- L3 Cache (Level 3): Even larger and slower than L2.
L3 cache is shared among all cores in the CPU.
It helps reduce the latency between the CPU and the main memory (the last level of CPU caching between CPU and memory).
Typical Size: 4 MB to 64 MB, shared among all cores in a CPU.
Access Time: Approximately 10 to 30 clock cycles. (~10 nanoseconds)

### Why is there a difference between L1, L2, and L3?
While L1, L2, and L3 caches are all made of SRAM, their differences in speed are due to several factors beyond the type of memory they use. 

- Proximity: L1 cache is the fastest because it is closest to the CPU cores, minimizing the distance data must travel.
- Size: L1 cache is the smallest, allowing for quicker access and less complexity in data lookup.
- Design Complexity: L1 cache is designed with speed in mind, using simpler structures compared to L2 and L3 caches (that are more associative = more relations between data).
- Purpose: Each cache level serves a distinct purpose, with L1 focused on speed, L2 providing a larger secondary cache, and L3 acting as a shared cache to reduce main memory accesses.

NOTE: 
Cache Synchronization Problem: This occurs in multi-core systems where each core has its own cache. 
When one core updates data in its cache, the other cores' caches may become outdated, leading to inconsistency. 
Solutions like cache coherence protocols (e.g., MESI) ensure that all caches have consistent data.


## Clock Speed
Clock Speed: The speed at which a CPU executes instructions, measured in GHz (gigahertz). 
Higher clock speeds generally mean a faster CPU, but efficiency and architecture also play crucial roles in performance.
For most new-age devices, the common clock speeds are 2.9GHz, or 3.2GHz.

Around the mid-2000s, increases in clock speed began to plateau due to thermal and power consumption limits. Clock speeds have not increased as dramatically since then.
Instead of merely increasing clock speeds, CPU manufacturers have focused on improving efficiency and parallelism. 
This includes increasing the number of cores, enhancing instruction-level parallelism, and integrating specialized processing units (e.g., GPUs, AI accelerators)


## 32-bit v 64-bit
32-bit and 64-bit refer to the width of the data paths (data busses), registers, and memory addresses that the CPU can handle. 
This directly influences the amount of data the processor can process at once and the amount of memory it can access.

32-bit CPUs can transmit 32-bits at once, have 32-bit wide registers, and access 2^32 = 4GB RAM.
64-bit CPUs can transmit 64-bits at once, have 64-bit wide registers, and access 2^64 = 18 million TB RAM

We moved from 8-bits to 16 to 32 and finally to 64.
Why No 128-bit?
- Memory Addressing: Even the most demanding applications today do not require the vast memory space provided by 128-bit addressing.
- Data Processing: The performance needs of current applications are met by 64-bit architectures.
- Software Overhaul: Transitioning to a 128-bit architecture would require a complete overhaul of existing software, compilers, and operating systems.


A CPU processor's simplified block diagram.
![Microprocessor Block Diagram](https://www.tutorialspoint.com/computer_logical_organization/images/microprocessor_blockdiagram.jpg)

A simplified CPU architecture diagram.
![CPU Architecture Diagram](https://miro.medium.com/v2/resize:fit:1200/0*5dVxHUhXoshujAhL)

An Example of dual-core and quad-core processors.
![Dual-core vs Quad-core CPU Architecture](https://phoenixnap.com/kb/wp-content/uploads/2023/04/dual-core-vs-quad-core-cpu-architecture.png)
