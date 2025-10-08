# Computer Structure

![computer_structure_von_neumann_architecture](../img/computer_structure_von_neumann_architecture.png)

![computer_structure_memory](../img/computer_structure_memory.png)

**Stack**

Stores function call data: local variables, return addresses. Grows/shrinks automatically.

**Heap**

Stores dynamically allocated memory (e.g., with malloc or new). Managed manually or by GC.

**Text (code)**

Holds the program’s machine code (instructions). Read-only for safety.

**Data (Initialized)**

Stores global/static variables that have a defined initial value.

**BSS (Uninitialized Data)**

Stores global/static variables without an initial value (zero-initialized).

**Memory-Mapped Region**

Maps files, libraries, or devices into memory. Enables shared access or efficient I/O.

**Registers**

Fast, small storage inside the CPU for current instruction data.

**Cache**

Fast memory close to the CPU that stores recently/frequently used data.

**Virtual Memory**

Abstraction layer that gives processes the illusion of a large, private memory space.

**Kernel Memory**

Reserved for the operating system; not accessible from user programs.

**Shared Memory**

Allows multiple processes to access the same memory region (used in IPC).