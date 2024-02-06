# Embedded-Linux-Syllabus
## MODULE 1: UNIX and LINUX SYSTEM PROGRAMING
#### CH1. INTRODUCTION TO UNIX/LINUX 
- Histoty of Unix/Linux
- Linux Layered Architecture
- Type of Kernels Micro and Monolithic kernel
- Different types of kernel structure
- Linux Bootup Sequence
#### CH2. FILE SYSTEM MANAGEMENTS
- File Systems Types - Extended file system (ext4)
- File Systems – VFS & File Systems Layouts
- Boot block, Super Block, Inode Block, Data block
- Inode block Structure
- Types of File - Hard link, Soft link and Regular file
- File descriptor and File descriptortable
- System calls Sequence
- System calls Vs Function Calls
- File related System Calls
#### CH3. FILE LOCKING PROGRAMMING 
- File Control Operations
- Types of File Locking
- Advisory and Mandatory File locking
- fcntl() and flock()calls
#### PROCESS MANAGEMENTS
- Program and Process
- Process Control Block (PCB)
- States Of Process
- Mode of Execution User mode and Kernel mode
- Context Switching
- Scheduling & Priority
#### CH5. PROCESS RELATED PROGRAMMING
- Process Creation by fork() amd vfork()
- Why fork() not vfork()
- Creation and Destroying Zombie Process
- Creation of Orphan Process
- wait() and waitpid() calls
- exit() and exec() ,sleep() calls
- Creating , synchronizing and performing multiprocessing concepts
- Setting and changing nice value and Prority no.
#### CH6:MEMORY MANAGEMENTS AND MMU
- Memory Policy and Hirarchy
- Memory allocation Technique
- Physical memory &Virtual Memory
- Paging & Demand paging
- Memory Mapping using TLB
- Swap in & Swap out
- Internal & External Fragmentation
## MODULE 2: LINUX INTERNALS AND INTERPROCEES COMMUNICATION
#### CH1. THREADS AND MULTI-THREAD CONCEPTS
- Threads on different O.S
- Why Threads in Linux
- Threads Vs Process
- Thread APIs
- Creation of Multithreading
- Performig Multiple operation using multi-threading
#### CH2. SIGNALS VS. INTERRUPTS
- Sources of Signals
- Diffrents type of Signals
- Actions of Signals
- Receiving a Signal
- Handling a Signal
- Signal and Sigaction System Calls
#### CH3. USER AND DAEMON PROCESS
- Creating a Daemon Process
- Characteristics of a Daemon
- Writing and Running Daemon
#### CH4 . PRIMITIVE INTERPROCESS COMM (IPCS)
- PIPES
- Creation of Half and Full-duplex pipe
- Half and Full-duplex communication
- FIFO
#### CH5 . SYSTEMS V IPCS
- Shared Memory
- Message Queues
- Semaphores
#### CH6 . NETWORK AND SOCKET PROGRAMMING
- Description of ISO/OSI Model
- Types of IP Classes (A,B,C,D and E)
- Configuring IP address on Systems
- Network addresses and Host addresses
- Types of Socket UDP Connectionless Oriented Socket
- TCP/IP Connection Oriented Socket
- Iterative Server-Client Programming
- Concurrent Server- Client Programming
- One Server and Many client Programming
## MODULE 3: LINUX KERNEL PORTING AND DRIVER PORTING ON BEAGLEBONE BLACK
#### CH1: GENESIS OF LINUX PROJECT : : INTRODUCTION
- Element 1:Tool chain (Air)
- Element 2:Boot loader (Earth)
- Element 3:Kernel (Fire)
- Element 4:User space (Water)
#### CH2: TOOLCHAIN SETUP : :INTRODUCTION TO TOOLCHAIN
- What is Toolchain
- Toolchain Components
- Building Toolchain
- Build Systems for Toolchain
- Toolchain Setup Environment
- Toolchain compilation and usage
#### CH3: BOOTLOADER COMPILATION : : INTRODUCTION TO BOOTLOADER
- What is Loader
- What is Bootloader
- 1st and 2nd Stage Bootloader
- U-Boot Bootloader Porting on New
- U-Boot Commands Lists
- Bootloader Cross-Compilation
- Downloading on Target board
- Bootloader commands and usage,
- Bootloader code customization, U-Boot
- U-Boot Image for Target Board
#### CH4: KERNEL CONFIGURATION : : LINUX KERNEL CROSS COMPILATION
- Download the kernel source code linux-xx.yy.zz.tar.bz2
- untar it with 'tar -jxvf linux-xx.yy.zz.tar.bz2
- Copy the new config as .config in kernel top level directory
- Update the the config file using make ARCH=arm menuconfig
- Compile the kernel with make ARCH=arm CROSS_COMPILE=zImage
- Generating Kernel Image uImage or zImage, dtb
- Transfer this is to the Target Board and reboot to boot with new kernel image using tftp or nfs
- Application development and Cross Compilation
#### CH5: PORTING LINUX KERNEL,U-BOOT IMAGES ON TARGET BOARD
- Sd Card partitioning and Formatting
- Wrtting uImage,U-boot.bin into Sd cards
- Extract and copy rootfs in SD-Card rootfs partition
- Configuring NFS and using rootfs over NFS
- Building the Embedded Board Using NFS
#### CH6: BUILDING THE DEVICE DRIVER AS A PART OF KERNEL(IN KERNEL TREE)
- We will add a Device driver to the kernel
- Copy the file driver.c to linux-xx.yy.zz/drivers/char/
- Edit the Kconfig file in drivers/char/
- Edit the makefile and add obj-$(CONFIG_MY_DRIVER) += driver.o
- Configure the kernel with make ARCH=arm menuconfig
- Now, compile the kernel with make ARCH=arm CROSS_COMPILE=- zImage
- Test the driver, with application Program
#### CH7: BUILDING AND RUNNING MODULES ON BEAGLEBONE BLACK
- Kernel Architecture or Model
- Role of the Device Drivers
- Writing Your first kernel module
- Module Related Commands
- Kernel Module vs Applications
- Compiling Modules
- Loading and Unloading Modules
- Module Parameters
## MODULE 4: LINUX KERNEL PROGRAMMING & CHARACTER DEVICE DRIVER
#### CH1: AN INTRODUCTION TO DEVICE DRIVERS
- Role and Definition of the Device Drivers
- Splitting the kernel into its functionalities
- Drivers have two parts -Device specific and OS specific
- Kernel Architecture or Model
#### CH2: BUILDING AND RUNNING MODULES
- Types of Modules in the kernel
- Writing Your first kernel module
- Module Related Commands
- Kernel Module vs Applications
- Compiling Modules
- Loading and Unloading Modules
- Module Parameters
- Modules and Exporting Symbols
##### Hands-On Assignments
- Lab1: Simple Hello Linux Kernel Module.
- Lab2: Write a module that can take an integer parameter when it is loaded, It should have a default value when none is specified.
- Lab3: Write a pair of modules where the second one calls a function in the first one
#### CH3: CHARACTER DEVICE DRIVER
- Allocating and Registering a Character Device
- Concept behind Major and Minor Number
- The Internal Representation of Device Numbers
- Allocating and Freeing Device Numbers
- Exchanging data between user space and kernel space
- File Operations Data structure
- Driver methods and Function Pointers
- Filling the file operations structure
- The Cdev Structure, inode Structure, file Structure
- Manual Creation of Device Files using mknod()
- Automatic Creation of Device Files using devive and class create
###### Hands-On Assignments
- Lab1: Print the major and minor numbers when Registering by Static or Dynamic method.
- Lab2: Implement a open,write,read and close entry point.
- Lab3: Print the major and minor numbers when the device is Opened and keep track of the number of times it has been opened since loading, and print out the counter every time the device is opened.
- Lab4: Modify the previous driver so that each opening of the device allocates its own data area, which is freed upon release. Thus data will not be persistent across multiple opens.
- Lab5 : Implement a lseek entry point and Keeping track of file position.
- Lab6: Dynamical Node Creation,Adapt the previous dynamic registration driver to use udev to create the device node on the fly.
#### CH4: KERNEL MEMORY ALLOCATION TECHNIQUE
- System Memory Layout - Kernel space and User space
- Concept of LOW and HIGH Memory
- Kmalloc family allocator
- The Flags Argument
- Memory zones
- vmalloc and Friends
- Memory caches
##### Hands-On Assignments
- Lab1:Testing Maximum Memory Allocation ,using kmalloc()
- Lab2:Testing Maximum Memory Allocation ,using __get_free_pages().
- Lab3: Testing Memory Allocation,using vmalloc().
- Lab4 :Memory caches Extend your chararcter driver to allocate the driver's internal buffer by using your own memory cache.Make sure you free any slabs you create.
#### CH5: ADVANCED CHARACTER DRIVER OPERATIONS
- Inpout/Output Control Device (ioctl)
- User space, the ioctl system call
- The ioctl driver method
- Generating ioctl command
- Choosing the ioctl Commands
- Using the ioctl Argum
##### Hands-On Assignments
- Lab1 : Implement a ioctl entry point along with read and write entry point.
- Lab2 : Implement read and write entry point using ioctl command.
- Lab3 : Write a character driver that has three ioctl commands:
  a)Set the process ID to which signals should be sent.
  b)Set the signal which should be sent.
  c)Send the signal.
#### CH6: KERNEL LOCKING MECHANISM CONCURRENCY AND RACE CONDITION
- Concurrency and its Managements
- Semaphores versus Mutexes
- Spinlock versus Mutexes
- Linux Semaphore Implementation
- Introduction to the Semaphore API
- Spinlocks Implementation
- Introduction to the Spinlock API
- Spinlocks and Atomic Context
##### Hands-On Assignments
- Lab1: Mutex Contention -Write three simple modules where the second and third one use a variable exported from the first one.The second (third) module should attempt to lock the mutex and if it is locked, either fail to load or hang until the mutex is available.
- Lab2: Sempahore Contention -Now do the same thing using semaphores .
#### CH7: INTERRUPT AND INTERRUPT HANDLING
- The Definition and Role of Interrupt
- Installing an Interrupt Handler
- The /proc Interface
- Implementing a Handler
- Handler Arguments and Return Value
- Installing a Shared Handler
##### Hands-On Assignments
- Lab1: Write a module that shares its IRQ with your network card. You can generate some network interrupts either by browsing or pinging.
- Lab2: Extend the previous solution to construct a character driver that shares every possible interrupt with already installed handlers.
- Lab3: Mutex Unlocking from an Interrupt. Modify the simple interrupt sharing lab to have a mutex taken out and then released in the interrupt handler.
#### CH8: TIME, DELAY AND DEFERRED WORK

- Top and Bottom Halves
- Tasklets and Workqueues Mechanisms
- Measuring Time Lapses
- Using the jiffies Counter
- The Timer API
##### Hands-On Assignments
- Lab1: Program based on Kernel Timer API
- Lab2: Program based on Jiffies and HZ
- Lab3: Program based on Taklet API
- Lab4: Prgram based on Workqueue API
- Lab5: Write a driver that puts launches a kernel timer whenever a write to the device takes place. Pass some data to the driver and have it print out. Have it print out the current->pid field when the timer function is scheduled, and then again when the function is executed.
- Lab6: Write a module that launches a periodic kernel timer function; i.e., it should re-install itself.
