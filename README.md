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
