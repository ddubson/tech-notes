# Processes

* A **process** is the operating system's abstraction for a running program.
* Multiple processes can run concurrently on the same system and each process appears to have exclusive use of the hardware.
* Concurrency of processes means the operating system switches between processes, known as **context switching**

## Context Switching![](/assets/os-processes-1.png)Structure of Process in Memory

* When processes are loaded into memory, they are broken down into many small sections. There are six main sections:
  * **.text** section
    * Corresponds to .text portion of the binary exec file.
    * Contains the machine instructions to get things done.
    * Marked read-only and will cause segmentation fault if written to.
    * Size is fixed at runtime when the process is loaded.
  * **.data** section
    * Store global initialized variables.
    * e.g. int a = 0;
    * Size is fixed at runtime.
  * **.bss **section
    * Below stack section \(.bss\) used to store global noninitialized variables
    * e.g. int a;
    * Size of the section is fixed at runtime.
  * **Heap **section
    * Store dynamically allocated variables 
    * Grows from lower-addressed memory to the higher addressed memory.
    * Allocation of memory is controlled through malloc and free
  * **Stack** section
    * Keeps track of function calls \(recursively\)
    * grows from the higher-addressed memory to lower addressed memory
    * Local variables exist in the stack section.
  * **Environment/Arguments** section
    * Store a copy of system-level variables that may be required by the process during runtime.
    * Section is writable.

![](/assets/proc-2.png)

![](/assets/processes-2.png)

\#\#\# Buffers

```
• Refer to storage place used to receive and hold data until it can be handled by a process.

• Each process has its own set of buffers --&gt; done by allocating the memory within the .data and .bss section of the process memory.

• Once allocated the buffer is fixed length.
```

\#\#\# Strings in Memory

```
• Strings are continuous arrays of character data in memory

• The string is referenced in memory by its first character.

• The string is terminated by a null character \(\o in C\)
```

\#\#\# Pointers

```
• Hold the address of other pieces of memory
```

Pointers are saved in 4 bytes \(DWORD\) of contiguous memory since memory addresses are 32 bits in length

---

![](/assets/proc-1.png)

## Load and Execute Process

The following steps describe, in sequence, what happens when a computer user runs a program at a command prompt:

* The operating system \(OS\) searches for the program’s filename in the current disk directory. if it cannot find the name there, it searches a predetermined list of directories \(called paths\) for the file name. If the OS fails to find the program filename, it issues an error message.
* If the program file is found, the OS retrieves basic information about the program’s file from the disk directory, including the file size and its physical location on the disk drive.
* The OS \(determines the next available location in memory and loads the program file into memory. It allocates a block of memory to the program and enters information about the program’s size and location into a table \(sometimes called a descriptor tab\). Additionally, the OS may adjust the values of pointers within the program so they contain addresses of program data.
* The OS executes a branching instruction that causes the CPU to begin execution of the program’s first machine instruction. As soon as the program begins running, it is called a **process**. The OS assigns the process an identification number \(process ID\), which is used to keep track of it while running.
* The pivcess runs by itself. It ¡s the OS’s job to track the execution of the process and to respond to requests for system resources. Examples of resources are memory. disk files, and input-output devices.
* When the process ends, its handle is removed and the memory it used is released so it can be used by other programs.



