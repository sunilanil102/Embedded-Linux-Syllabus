# Startup code 
A start-up code is called prior to the main function, which is written in asm, The basic function of startup code is captured below
1) Declaration of the Stack area
2) Declaration of the Heap area.
3) Vector table.
4) Reset handler code.
5) Other exception handler code.

Start-up code for C programs usually consists of the following actions, performed in the order described:

1) Disable all interrupts.
2) Copy any initialized data from ROM to RAM.
3) Zero the uninitialized data area.
4) Allocate space for and initialize the stack.
5) Initialize the processor’s stack pointer.
6) Create and initialize the heap.
7) Enable interrupts.
8) Call the main.
