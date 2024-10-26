[[Virtual Memory Management]]

Book from JT - Code: The Hidden Language of Computer Hardware and Software
Chip war

CS Foundations

Computer architecture
How do you go from 10's to complex programs?

Computer Systems: A Programmer’s Perspective
0. Preface - book is about core ideas of computer systems
Tour of Computer Systems
1. Tour of Computer Systems - trace life cycle of hello world program
1.1 Information is Bits + Context
1.2 Programs are Translated by Other Programs into Different Forms
Input .c file
Preprocessor - .i file, inserts code from .h header files to original code
Compiler - .s file, translates code into assembly language
Assembler - .o file, translates assembly language to machine language instructions
Linker - links separate precompiled object files to program, e.g. original code needs printf.o, linker gets printf.o
1.3 It Pays to Understand How Compilation Systems Work
Optimizing program performance - compiler translates different C statements into machine code e.g. switch vs if-else, pointer reference vs array index
Understanding link time errors - resolving references from imported files
Avoiding security holes - buffer overflow vulnerabilities (if you don’t restrict quantity and form of data accepted from untrusted sources)
1.4 Processors Read and Interpret Instructions Stored in Memory
Hardware organization
Buses - electrical conduits that carry information between components, fixed size (words e.g. 32bit or 64bit)
Io devices - connection to external world; controller built in motherboard, adapter plugged into motherboard slot
Main memory - collection of dynamic random access memory chips, stored as linear array of bytes
Processor - interprets or executes machine instructions from main memory; parts are main memory, register, ALU; processes are load store operate jump
Caches matter - processor to memory is slow because of the layers it needs to go through, it's faster to put a cache directly connected to processor for faster times
Cache memories/caches - temporary staging areas for information that processor is likely to need in the future
L1 and L2 cache - caches near processor that is much faster to read, vs reading main memory
SRAM - static random access memory, hardware implementation of L1 and L2 cache
DRAM - dynamic random access memory
Memory hierarchy L1 smaller faster costlier storage devices (cache inside the CPU chip), L6 larger slower cheaper storage devices (distributed file systems, web servers)
Operating system - provide programs with simple uniform interfaces across different types of hardware; consists of processes, virtual memory, files
Processes
Kernels - manages transition from one process to another
[[Thread]] - execution units, a process can have multiple
Virtual memory
Program code and data
Heap - expands and contracts at runtime, malloc and free
Shared libraries
Stack - expands and contracts at runtime, function calls
Kernel virtual memory
Systems Communicate with Other Systems Using Networks
Important themes
Amdahl’s Law - when one part is sped up, effect on overall system depends on how significant part was and how much it sped up
Concurrency and Parallelism
Concurrency - multiple simultaneous activities
Parallelism - use of concurrency to make a system run faster
3 levels
[[Thread]]-level Parallelism - multiple programs execute at the same time
Instruction-level Parallelism - processors execute multiple instructions at one time
Single Instruction, Multiple Data Parallelism - lowest-level; single instruction multiple operations
Importance of Abstractions in Computer Systems - allow programmers to use the code without having to delve into its inner workings
Program Structure and Execution
Representing and Manipulating Information - data structures
Machine-Level Representation - gdb, out of bounds memory references, buffer overflow
Processor Architecture - y86-64 (simpler x86), HCL
Optimizing Program Performance - program profiling
Memory Hierarchy - ram, ssd, cache

Running Programs
Linking - object files, import from other programs
Exceptional Control Flow - avoid nasty concurrency bugs
9. Virtual Memory (understand this - Manuel Odendahl) - VMs for memory management and protection, malloc and free, garbage collection
Virtual memory provides three important capabilities: 
(1) It uses main memory efficiently by treating it as a cache for an address space stored on disk, keeping only the active areas in main memory and transferring data back and forth between disk and memory as needed.
(2) It simplifies memory management by providing each process with a uniform address space. 
(3) It protects the address space of each process from corruption by other processes.
Physical and Virtual Addressing
Physical - main memory of computer system is organized as an array of M contiguous byte-size cells. Each byte has unique physical address, first one is 0, next is 1, next is 2. Simplest most natural way for CPU to access memory
Virtual - CPU accesses main memory by generating a virtual address which is then converted to appropriate physical address before being sent to main memory
Address translation - converting virtual address to physical address
Memory Management Unit - translates virtual addresses on the fly
Address Spaces
ordered set of nonnegative integer addresses {0,1,2..}
Linear address space - If integers are consecutive
Concept of address space makes clean distinction between data objects (bytes) and their attributes (addresses)
each data object can have multiple independent addresses, each chosen from a different address space
Each byte of main memory has a virtual address chosen from the virtual address space, and a physical address chosen from the physical address space
VM as a Tool for Caching
Definitions
Caching - processor to memory is slow, needs cache closer to processor to allow faster processing
Virtual pages - fixed-size blocks, used as transfer units between disk and main memory
Unallocated - no data, no space on disk
Cached - allocated, currently cached in physical memory
Uncached - allocated, not cached in physical memory
Page frames - physical pages, partition of physical memory
DRAM Cache Organization
DRAM Cache - VM system’s cache that caches virtual pages in main memory
Reading time DRAM is 10x slower than SRAM, disk is 100kx slower than DRAM
DRAM caches use always write-back instead of write-through - because of large access time of disk
Page Tables
Page table - array of page table entries (PTEs)
Each page in virtual address space has a PTE at a fixed offset in the page table
Each PTE consists of a valid bit and an n-bit address field
Page Hits
Page Faults - DRAM cache miss
Allocating Pages - effect on page table when operating system allocates a new page of virtual memory, e.g. as a result of calling malloc
Locality to the Rescue Again
Locality - phenomenon in which a computer program tends to access same set of memory locations for a particular time (geeks4geeks)
Working set/resident set
Thrashing - pages are swapped in and out continuously
VM as a Tool for Memory Management
Simplifying linking
Simplifying loading
Memory mapping - mapping a set of contiguous virtual pages to an arbitrary location in an arbitrary file
Simplifying sharing
Simplifying memory allocation
VM as a Tool for Memory Protection
Address Translation
aim is to give you an appreciation of the hardware’s role in supporting virtual memory, with enough detail so that you can work through some concrete examples by hand
Integrating Caches and VM
Speeding Up Address Translation with a TLB
Multi-Level Page Tables
Putting it Together: End-to-End Address Translation
Case Study: The Intel Core i7/Linux memory system
Core i7 Address Translation
Linux Virtual Memory System
Linux Virtual Memory Areas
Linux Page Fault Exception Handling
Memory Mapping - process by which Linux initializes the contents of a virtual memory area by associating it with an object on disk
Areas can be mapped to 1 of 2 types of objects
Regular file in Linux file system
Anonymous file
Shared Objects Revisited
The fork Function Revisited
The execve Function Revisited
User-Level Memory Mapping with the mmap Function
Mmap -  create new areas of virtual memory and to map objects into these areas
munmap - deletes regions of virtual memory
Dynamic Memory Allocation - vs mmap/munmap, more convenient and portable to use dynamic memory allocator when need to acquire virtual memory at run time
Heap - an area of a process’s virtual memory
Block - An allocator maintains the heap as a collection of various-size blocks
Allocated
Free
The malloc and free Functions
Malloc - returns a pointer to a block of memory of at least size bytes that is suitably aligned for any kind of data object that might be contained in the block
need to explicitly free allocated blocks
Calloc - assigns multiple blocks of memory to a single variable
Realloc - deallocates the old object pointed to by ptr and returns a pointer to a new object that has the size specified by size
Sbrk - grows or shrinks heap (set break?)
Why Dynamic Memory Allocation?
often they do not know the sizes of certain data structures until the program actually runs
Hard-coded array sizes can be a nightmare to maintain
Allocator Requirements and Goals
Requirements
Handling arbitrary request sequence - allocator cannot make assumptions about order of alloc and free requests
Making immediate responses to requests - not allowed to reorder or buffer requests to improve performance
Using only the heap - any nonscalar data (data with multiple data points) must be completely stored in the heap
Aligning blocks - must align blocks in such a way that can hold any type of data object
Not modifying allocated blocks - cannot modify or move blocks once allocated
Goals
Maximize throughput
Maximize memory utilization
Fragmentation
Occurs when otherwise unused memory is not available to satisfy allocate requests
Implementation Issues
Free block organization - how do we keep track of free blocks
Placement - how to choose appropriate free block
Splitting - after placing new block to some free block, what to do with remainder of free block
Coalescing - what do we do with a block that has just been freed
Implicit Free Lists
Organize heap as a sequence of contiguous allocated and free blocks
Free blocks linked implicitly by the size fields in the headers
Blocks = header, block size, payload, padding
Placing Allocated Blocks
Manner in which allocator performs search for free blocks to allocate new block to
First fit - first free block that fits
Next fit - start search where previous search left off
Best fit - examines every free block and chooses block with smallest size that fits
Splitting Free Blocks
Policy for how much of free block to allocate, after allocator has found free block
Using full introduces internal fragmentation
Getting Additional Heap Memory
Combine adjacent blocks
Ask kernel for more memory using sbrk
Coalescing Free Blocks
False fragmentation - lot of adjacent free blocks unused
Coalescing - merge adjacent free blocks
Immediate - coalesce each time a block is freed
Deferred - wait at some later time
Coalescing with Boundary Tags
Coalesce with next block - check header of next
Coalesce with previous block - need to go through entire list
Solution: Boundary tags - add a footer to the block which is a replica of the header, with this allocator can determine starting location and status of previous block by inspecting footer, which is always one word away from start of current block
Disadvantage: can introduce overhead if many small blocks
Optimization: store the allocated/free bit of the previous block in one of the excess low-order bits of the current block, then allocated blocks would not need footers, and we could use that extra space for payload
Putting it Together: Implementing a Simple Allocator
General Allocator Design
Basic Constants and Macros for Manipulating the Free List
Creating the Initial Free List
Freeing and Coalescing Blocks
Allocating Blocks
2 practice problems
Explicit Free Lists
Problem: Implicit free lists are linear to total number of heap blocks
Solution: Define data structure of heap explicitly - like doubly linked list
Segregated Free Lists
popular approach for reducing allocation time
Maintain multiple free lists, where each list holds blocks that are roughly same size
Types
Simple Segregated Storage
Segregated Fits
Buddy Systems
Garbage Collection
Garbage Collector Basics
Mark&Sweep Garbage Collectors
Conservative Mark&Sweep for C Programs
Common Memory-Related Bugs in C Programs
Dereferencing Bad Pointers
Reading Uninitialized Memory
Allowing Stack Buffer Overflows
Assuming That Pointers and the Objects They Point to Are the Same Size
Making Off-by-One Errors
Referencing a Pointer Instead of the Object It Points To
Misunderstanding Pointer Arithmetic
Referencing Nonexistent Variables
Referencing Data in Free Heap Block
Introducing Memory Leaks
Summary


Interaction & Communication
System-Level IO - reading and writing files
Network Programming - IP, socket, bind
[[Concurrency]] Programming - [[Thread]] execution model, semaphores, deadlocks, races!!

Error Handling

Updates
0204
Read summaries per chapter, fish out the definition of terms for what you listed out
