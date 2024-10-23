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
## Chapter 1 - Computer System Overview
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
## Chapter 2 - Operating System Overview
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
## Chapter 3 - Process Description and Control 
### Process Elements
**Two Essential Elements**
- **Program Code** - The instructions that make up the program. May be shared with other processes that are executing the same program.
- **Associated Data** - The data data associated with the program code
**Process Control Block** - A data structure responsible for managing the process (keeping track of its state before, during, and after an interupt).
### Process Creation
**Reasons for Process Creation**
- New Batch Job - The OS sends a new job from its batch/list.
- Interactive Logon - A user logs on to the system.
- Services - The OS creates a process to provide a service.
- Existing Process - An existing process starts another to meet its needs.
**Process Creation Terms**
- **Process Spawning** - When the OS creates one process at the request of another process.
- **Parent Process** - The original, creating process.
- **Child Process** - The created process.
**Process Creation Steps**
1. Assign a PID to the process.
2. Allocate memory for the process.
3. Initialize the process control block.
4. Set linkages between necessary tables.
5. Create or expand other data structures.
### Process Termination
**Reasons for Process Termination**
- Normal Completion - The process finished successfully.
- Time Limit - The process takes longer than expected or is reasonable.
- Memory Restrictions - The process uses too much memory or tries to access priveleged memory.
- Many other reasons.
**Needs of Process Termination**
- A process must be able to indicate its completion.
- A batch job should include a HALT instruction.
### Suspended Processes
**Reasons for Process Suspension**
- Swapping - The OS needs to release main memoru to start another process.
- User Request - The user wishes to suspend a process.
- Timing - A process that is executed periodically must wait for the right time.
- Parent Request - A child processes' parent requests its suspension.
- OS Request - The OS suspends a process because it may be causing a problem or for other reasons.
**Characteristics of a Suspended Process**
- The process is not immediatelt available for execution.
- The process may be awaiting an event.
- The process was suspended by another agent to prevent its execution.
### Process Swapping
Process swapping occurs when a process is suspended for an extended time and main memory is full. The OS will decide that the suspended process should be swapped to a storage device so other processes can be held in main memory and executed by the CPU.
### Process States
**New** - A process that has just been created but has not been loaded into main memory. Typically already has an associated process control block.
**Ready** - A process that is prepared to run.
**Running** - The process that is being executed.
**Blocked/Waiting** - A process that cannot complete until another action occurs (I/O devices, storage devices).
**Suspended** - A process that has been moved out of main memory to be executed at a later time.
**Exit** - A process that has been released because it is finished or because an agent has prevented it from finishing.
### Managing Processes
**Process Identification (PID)** - A unique numeric identifier for a process.
### System Interrupts
### Modes of Execution
**User Mode** - Less privileged mode.
- User programs execute here.
**System/Kernel Mode** - More privileged mode.
- Process , memory, and I/O management.
- Support functions like interrupt handling, accounting, and monitoring.
### Mode Switching
## Chapter 4 - Threads
### Two Aspects of a Process
**Resource Ownership** - The resources being used by a process.
- A virtual address space to hold the process image.
- Access to memory, I/O devices, and storage.
- The OS protects these assigned resources to prevent interference.
**Scheduling and Execution** - When a process undergoes its task.
- Follows a trace (execution path through programs).
- Has a process state and a dispatchin priority.
- These characteristics will change as the process executes.
### Lightweigh Processes
**Threads** - Threads can be thought of as lightweight processes.
- Threads are units of dispatching (the scheduling and execution part).
- A simple way to describe them is as a further division of a process. The way an OS can dedicate tasks over multiple processors, a single task can be divided between multiple threads.
**Multithreading** - The ability of the OS to support multiple, concurrent paths of execution within a single process.
**Single Threaded Approach** - A method that only uses a single thread of execution per process.
**Thread Benefits** - Thread benefits center around perfomance increase over processes.
- Less time to create or terminate a thread when compared to a process.
- Switching between threads is faster than switching between processes.
- Enhanced ability to communicate between programs.
	- Since each process has protected resources, it can be better to implement execution as a single process with multipl threads (no protection from internal threads) than multiple processes.
### Multithreading
**Each Thread Has:**
- An execution state (Running, Ready, etc.).
- Saved context when not running.
- An execution stack.
- Static storage for local variables.
- **Shared access** to the parent process' memory and resources.
**Thread Synchronization** - Threads share resources, so their execution order must be carefully managed.
- Ex: Two threads try to modify a linked list at the same time.
- Synchronization techniques are covered in chapters 5 and 6.
### Thread Characteristics
**Thread Execution States** - States of execution similar to a process.
- Running
- Ready
- Blocked
**Thread Operations** - The causes of different execution states.
- Spawn - When a process is spawned, so is a thread. That thread may spawn more.
- Block - When a thread needs to wait for an event.
- Unblock - A blocked thread is moved to the ready queue.
- Finish - A thread is finished executing.
### Types of Threads
**User-Level Threads (UTLs)** - Threads are only allocated in user space.
- The kernel is unaware of threads.
- The application running in user space is in charge of managing threads.
**Pros/Cons**
- ULTs can run on any device.
- But, when a ULT executes a system call and the executing thread is blocked, all process threads will be blocked.
- Can't take advantage of multiprocessor systems, since the kernel assigns one process/processor.
**Fixes** - How the disadvantages can be overcome.
- Design a program to use multiple processors.
**Kernel-Level Threads (KLTs)** - Thread management is handled by the kernel.
- Applications have no direct access to threads. They must interact with them through a kernel API.
**Pros/Cons**
- Kernel can schedule multiple threads from the same process on multiple processors.
- If one thread of a process is blocked, the kernel can shcedule a new thread from that process.
- But transferring between threads requires a switch to kernel mode.
**Combined ULT and KLT**
- The bulk of thread creation and scheduling is specified by the application.
- ULTs are mapped to an equal or fewer number of KLTs.
- Combines advantages of each while minimizing disadvantages.
### Threads in a Single-User System
**Foreground/Background Work** - One thread handles a GUI while another controls internal functioning of a program.
**Asynchronus Processing** - Secondary functionality like automatic backups can be dedicated to a single thread, removing complexity from the execution of the main program.
**Speed of Execution** - Multithreaded systems can perform more functions simultaneously, preventing downtime when waiting for slower components.
**Modular Structure** - Complex programs with many moving parts can take advantage of threads, dedicating a separate task to each.
## Chapter 5 - Concurrency
### Principles of Operating System Design
**Process Management** - Operating System design is concerned with the management of processes and threads.
**Multiprogramming** - The management of multiple processes on a single processor system.
**Multiprocessing** - The management of multiple processes within a multiprocessor.
**Distributed Processing** - The management of multiple processes running on multiple, distributed systems.
### Introduction to Concurrency
**What is Concurrency?** - A host of issues that arise when trying to run multiple processes simultaneously.
- Communication among processes.
- Sharing of and competition for resources.
- Synchronization across multiple processes.
- Processor time allocation.
**What Creates Concurrency?**
- **Multiple Applications** - Multiprogramming used to run multiple applications on a single processor.
- **Structured Applications** - Applications desgined as a set of concurrent processes.
- **OS Structure** - OSs implemented as a set of processes or threads.
### Key Concurrency Terms
**Atomic Operation** - A function implemented as multiple instructions that appear to be indivisible to other processes.
- While the process consists of multiple instructions, no other process can see or interrupt these instructions.
**Critical Section** - A section of code within a process that requires shared resources.
- Must not be executed while another process is in a corresponding section of code.
**Mutual Exclusion** - When one process is in a critical section, no other process may be in that critical section.
**Deadlock** - Two or more processes cannot continue because they are waiting on each other.
**Livelock** - Two or more processes continuously change their state in repsonse to each other, but with no meaningful result.
**Race Condition** - Multiple threads or processes share data, meaning that the final result may change depending on which process accesses the data first.
**Starvation** - A runnable process is overlooked indefinitely by the scheduler.
### Concurrency Issues
**Sharing of Global Resources**

### Common Concurrency Mechanisms
**Semaphore** - An integer value used for signaling between processes. Only three atomic operations may be performed on a sempahore:
- Initialize - Initialize the semaphore.
- Decrement - May block a process.
- Increment - May unblock a process.
**Binary Semaphore** - A semaphore of value 1 or 0.
**Mutex** - Similar to a binary semaphore, but only the process that blocks this semaphore (sets to 0) can unblock it.
**Condition Variable** - A data type that is used to block a process or thread until a particular condition is true.
**Monitor** - A programming language that wraps variables, access procedures, and initialization code within an abstract data type.
- The variable held by the monitor may only be accessed by its access procedures.
- Only one process can access the held variable at a time.
- May have a queue of processes waiting to access it.
==**Event Flags**== -
**Mailboxes and Messages** - A means for two processes to exchange information used for synchronization.
**Spinlocks** - Mutual exclusion mechanism in which a process executes in an infinite loop until the value of a lock variable is satisfied.
### Semaphores
**Strong Semaphores** - The process that has been blocked the longest is released from the queue first (FIFO).
**Weak Semaphores** - The order in which processes are removed from the queue is not specified.
### Producer/Consumer Problem
**Statement**
- One or more producers are generating data and placing it in a buffer.
- A single consumer is taking items from the buffer one at a time.
- Only one producer and consumer may access the buffer at any given time.
**Problem** - Ensure that the producer can't add data into a full buffer and the consumer can't remove data from an empty buffer.
==**Solution**== - 
### Monitors
### Synchronization
### Message Passing
**Process Interaction Requirements** - When processes interact that require...
- Synchronization - Enforces mutual exclusion.
- Communication - Exchange of information.
- Message passign meets both of these requirements.
**Primitive Pairs** - Message passing is normally done with a pair of primitive data types.
- Send(destination, message)
- Receive(source, message)
**Messageing Techniques**
- Blocking Send, Blocking Receive - Both the sender and receiver are blocked until the message is delivered.
	- Also called a rendezvous.
	- Allos for tight synchronization between processes.
- Nonblocking Send - Sender can continue but the receiver is blocked until the requested message arrives.
	- Sends one or more messages to a variety of destination as quickly as possible.
	- Most useful combination.
## Chapter 6
### Resources
**Resuable** - Resources that can be safely used by one process at a time.
**Consumable** - Resources that can be created and destroyed, not reused.
### Deadlock
**What is Deadlock?** - The permanent blocking of a set of processes that either compete for system resources or communicate with each other.
- A set of processes is deadlocked when each process in the set is blocked waiting for an event that can only be triggered by another blocked process in the set.
- Deadlock is permanent and has no efficient solution, it should be avoided.
**Deadlock Examples**
- Two processes request memory that is less than total, but together exceeds available memory. If the processes request their memory at the same time, deadlock occurs.
- One process requests and locks resource A while the other requests and locks resource B. Then, the processes try to access the other resource. Both resources are locked and held by the other process, and neither process can free its owned resource until getting the new one.
**Conditions for Deadlock** 
### Dining Philosophers
**The Problem** - 
## Chapter 7 - Memory Management
### Vocabulary
**Frame** - A fixed-length block of main memory (RAM, caches).
**Page** - A fixed-length block of secondary memory (Disks, SSDs).
**Segment** - A variable-length block that resides in secondary memory.
- An entire segment may be loaded into main memory or divided into pages and then loaded.
### Memory Management Requirements
**Relocation** - When a program is executed or resumed, it may be placed into multiple different memory locations.
- Programmers and users can't predict which location in memory the program will operate at.
- So, programs must be able to be *relocated*.
**Protection** - Each process should be protected from interference by other processes.
- Relocation means that processes can't predict which memory locations they will need to access. Mechanisms that support relocation must also support protection.
**Sharing** - Multiple processes may need to access the same memory locations.
- Ex: Processes share a data structure instead of making multiple copies of it.
**Logical Organization** - Main memory is organized linearly as a sequence of bytes.
- But, programs are written as a web of modules that reference each other and shared data.
- Segmentation is one tool that satisfies the needs of program structures in memory.
**Physical Organization**
### Logical Organization Methods
**Memory Partitioning** - Main memory is divided into fixed-length partitions into which processes may be loaded. Following are its two main methods of implementation.
**Fixed Partitioning** - Main memory is divided into static partitions at system generation time.
- Problem - A program may be too large to fit into a partition. The program then needs to be designed to use overlays.
- Problem: Wasted Space - Some processes will occupy partitions that are larger than they need.
**Dynamic Partitioning** - Main memory is divided into partitions dynamically at process run time. Each process gets a partition of the exact right size.
- Problem: Fragmentation - Memory becomes more and more fragmented as time goes on. This causes memory utilization to decline.
- Solution: Compaction - OS shifts processes so they are contiguous and all free memory is in one block. But this consumes time and CPU resources.
**Dynamic Partitioning Placement Algorithms** - Algorithms that help the OS decide where to place a new process in an array of dynamic partitions.
- **Best-fit** - Chooses the block that is closest in size to the request.
- **First-fit** - Begins to scan memory from the beginning and chooses the first available block that is large enough.
- **Next-fit** - Begins to scan memory from the location of the last placement and chooeses the next available block that is large enough.
==**Question**== - Why not organize it using job time predictions?
- Longest jobs are allocated first, shortest last.
- As shorter jobs are finished, thier free memory can be combined if they are next to each other. That way, the OS doesn't have to shift processes as often.
==**Question**== - Why not use pointers?
- Focus less on managing fragmentation.
- A process that is too big for the available partition can end in a pointer to the next free partition.
**Buddy System** - Combines fixed and dynamic partitioning.
1. Start with a single block the size of the whole main memory.
2. When a process comes along, split that block into half and one of its halves in half until the smallest block is as small as possible while still being large enough to handle the process.
3. When a new process comes along, fill one of the previous blocks that wasn't used.
4. When a process finishes, combine it with one of the larger blocks.
## Chapter 9
### CPU Burst Times
**Burst Times Prediction**
## Queuing Theory for Operating Systems
### Queue Basics
**What is a Queue?** - Objects waiting in a line.
- FIFO - First In First Out order.
### Describing Queues
**Queue Description Overview** - Queues can be described by a number of characteristics in the form **A / B / m / K / n / D**
- A - Distribution function of interarrival times.
- B - Distribution function of service times.
- m - Number of servers.
- K - Capacity of the system (max number of customers).
- n - Population size (total number of potential customers).
- D - Service discipline.
**Interarrival Rate** - The time from one arrival until the next, represented as 1/$\lambda$.
==FINISH==
## Chapter 10 - Multiprocessor, Multicors, and Real-Time Scheduling
### Classifying Multiprocessor Systems
**Loosely Coupled/Distributed Multiprocessor** - A collection of relatively autonomous systems with each processor having its own main memory and I/O.
**Functionally Specialized Processors** - One master (general purpose) processor controlls multiple specialized processor.
**Tightly Coupled Multiprocessor** - A collection of processore integrated under a single OS and sharing main memory and I/O resources.
### Parallelism
**What is Parallelism?** - 
**Independent Parallelism** - No explicit synchronization among processes.
- Separate jobs assigned to separace processors.
**Coarse/Very Coarse Grained Parallelism** - 

## Assignment 2.1 Part 2
**Consider an M/M/1 system where jobs arrive to be processed on the CPU at a rate of 6 per second. The rate at which they can be serviced is 8 per second. Show all work using the appropriate variables and formulas.**
**A. What is the arrival rate, the service rate and the traffic intensity?**
$\lambda = \frac{6 jobs}{1 second} = 6$
$\mu = \frac{8 jobs}{1 second} = 8$
$\rho = \frac{6}{8} = 0.75$

**B. What is the average number of jobs in the system?**
$N = \frac{0.75}{1-0.75} = 3$

**C. What is the probability there are 5 jobs in the system?**
$P(5) = 0.75^5(1-0.75) = 0.059$ or $5.9\%$

**D. What is the probability there are no jobs in the system?**
$P(0) = 0.75^0(1 - 0.75) = 0.25$ or $25\%$

**E. What is the average response time?**
$T = \frac{1}{8 - 6} = 0.5 seconds$

**F. What is the average wait time?**
$T = 0.75 \cdot \frac{\frac{1}{8}}{1 - 0.75} = 0.375 seconds$

## Midterm
- Scheduling
- Gant Charts
- Scheduling wait times
- CPU Burst Time Calculations
- M/M/1 Queue
- Round Robin Scheduling
- Shortest Job First
- What and why about burst times
