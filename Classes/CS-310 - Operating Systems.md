---
title: CS-310 - Operating Systems
parent:
  - "[[Class]]"
aliases: 
tags:
  - cs-class
---
### CS-310 - Operating Systems
### Class Overview
**Instructor** - Dr. Nathan P. Johnson
- njohnson3@bellarmine.edu
- 502-386-2224
- Office Hours - 
**Location** - Pasteur 002
**Time** - T/R 12:15-1:30 PM
## Day One
**Methodology**
- Homework assignments as quizzes.
- Homework will ask for source of answer.
- Notes must be taken and turned in.
**Operating System Overview**
- Bootloader starts first
### Ch. 1 - Computer System Overview Lecture
**Explaining Operating Systems**
	Operating systems...
- Use hardware resources
- Provide services to users
- Manage secondary memory and devices
**Basic Computer Elements**
- Processor/CPU
	- Main controller of the computer
	- Performs data processing functions.
- I/O Modules
	- Moves data between computer and external devices like...
	- Storage, communications equipment, terminals.
- Main Memory
	- Volatile - Always temporary, only exists when computer is running.
	- Also called real memory or primary memory.
- System Bus
	- A set of wires that connects all of the devices in a computer.
**Microprocessor**
- The microprocessor is what made handhelp computing possible.
- Fastest general purpose processor, on a single chip.
## Lecture 1 - Computer System Overview (Chapter 1)
### Parts of a Computer
**Processor/CPU** - Main controller of a computer.
- A CPU often includes...
	- MAR - Memory Address Register
	- MBR - Memory Buffer Register
	- I/O AR - I/O Address Register
	- I/O BR - I/O Buffer Register
- Microprocessors are the technology underlying CPUs.
	- They are processors on a single chip, or even multiple processors in one.
	- These are the fastest general purpose processors.
**GPU** - Single-Instruction Multiple Data (SIMD) processor.
- Is able to perform the same function many times simultaneously.
- Used for general numeric processing.
**Main Memory**
**System Bus**
**I/O Modules**
**Digital Signal Processors (DSPs)** - Deal with streaming signals like audio or video.
**Systen on a Chip (SoC)** - The recent trend in computer technology is including some or all of the above components on a single chip.
### How Computers Work
**Instruction Execution** - A program consists of a set of instructions stored in memory.
1. Processor reads instructions from memory.
	- Instructions start with an op-code.
	- Then instructions consist of data or a pointer to data in memory.
2. Processor executes the instruction.
**Interrupts** - Interrupts the operation of a processor to improve processor utilization.
- Most I/O devices are slower than the processor, so the processor does other things while waiting on them. When the I/O device is ready, it can interrupt the other task of the CPU.
- **Program** - A program meets a condition that results in an interrupt.
- **Timer** - A timer within the processor interrupts the processor to perform schedules tasks.
- **I/O** - An I/O device completes an operation and returns a result to the processor.
- **Hardware Failure** - A power or memory failure results in an interrupt to the currently executing application.
**How Interrupts Work**
**Memory**
- The major constraints of memory are...
	- Amount - This one is obvious.
	- Speed - Must be able to keep up with the processor.
	- Expense - How much a given amount of memory costs to buy and run.
**Principle of Locality** - Memory references by the processor tend to cluster.
- Data is organized so that the memory closest to the chip is fastest and has the most calls.
**Cache Memory** - Right next to or on the processor.
- Invisible to the OS, only used by the processor.
- Processor must access chaches at least once per instruction cycle.
- Should be small and fast to exploit principle of locality.
**Secondary Memory** - External, nonvolatile.
- Persists after power loss.
- Hard disks, SSDs, etc.
**Cache Memory**
**Memory Access**
**Least Recently Used (LRU) Algorithm** - Cache Block Replacement
- When a new block is needed, but none is available, this algorithm finds the oldest block to replace.
- Must use hardware mechanisms.
**Direct Memory Access (DMA)**
**Symmetric Multiprocessors (SMP)**
## Lecture 2 - Operating System Overview (Chapter 2)
### Operating System Basics
**Definitions of Operating System**
- A program that controls the execution of applications.
- An interface between applications and hardware.
- Software that manages hardware resources.
**OS Objectives**
- Conveniency - Make it easy to use hardware resources.
- Efficiency - Use hardware resources in an efficient way.
- Evolution - Respond and adapt to new hardware standards.
**OS Notes**
- The operating system, as a software or software suite, is executed on the processor like other applications. This means that it will be forced to relenquish control of the cpu and rely on the cpu to return control.
- Some crucial OS functions, like the kernel, stay in main memory.
- The OS and processor jointly control main memory.
### Evolution of Operating Systems
**Serial Processing** - Before the OS.
- Not an operating system, programmers had to interact directly with hardware.
- Computers consisted of a console, indicator lights, toggle switches, some input device, and a printer.
**Simple Batch Systems** - The first form of an OS.
- Designed to avoid wasting computation time between programs.
- Programmers don't have direct access, they give programmed jobs (on card or tape) to an operator who batches them with other jobs.
- Jobs are executed sequentially.
- Includes a monitor, which was software to handle each job.
- Includes modes of operation, which limit memory access for security and stability.
- Includes a timer to prevent one job from monopolizing on processor time.
- Improves efficiency of use time, even though some resources are now used by the monitor.
**Batch Systems, More on Monitors** - The monitor controls the sequence of events in a batch system.
- **Resident Monitor** - Part of the monitor that is always in memory.
- Other parts of the monitor include commonly used functions and utilities.
- **Job Control Language (JCL)** - A language used to intruct the monitor.
	- Included in jobs in addition to the jobs other instructions, which may be in a different language.
	- Prefixed by the character '$'.
**Batch Systems, Modes of Operation** - Essential memory protection.
- User Mode - Where user jobs are executed.
	- Some areas of memory are protected/blocked.
	- Some instructions may not be exeucted.
- Kernel Mode - Where the monitor works.
	- All areas of memory are available.
	- All instructions may be executed.
**Multiprogrammed Batch Systems** - Further reducing idle time.
- For each job, and often multiple times per job, a simple batch system will have to wait for I/O devices.
- This system can load multiple jobs into memory, so when one job is waiting on I/O, another can be executed.
**Time Sharing Systems** - Eliminate the middle-man.
- Instead of multiple jobs being compiled by an intermediary, the users with different jobs can now simultaneously access the same processor and resources.
- Job control language is replaced by a terminal/cli.
### Hardware-Software Structure
**Software Levels**
1. Application Programs
2. Libraries/Utilities
3. Operating System
**Hardware Levels**
1. Execution Hardware
2. Storage
3. System Bus
4. Memory and I/O Devices
### OS Interfaces
**Instruction Set Architecture (ISA)** - Translates software instructions to hardware signals.
**Application Binary Interface (ABI)** - Defines a standard for binary communication across programs.
**Application Programming Interface (API)** - Supplements the ISA with high level language library calls.
## Lecture 3 - Process Description and Control (Chapter 3)
