# BootROM 
1) The BootROM is the first software to run in the APU.
2) The main tasks of the BootROM are to configure the system, copy the Boot Image FSBL/User code from the boot device to the OCM (SRAM)
# First Stage Bootloader
The First Stage Bootloader (FSBL) starts after the boot. The BootROM loads FSBL into the OCM.
The FSBL is responsible for:Initializing with the PS configuration data that AMD hardware configuration tools provide (see Zynq PS Configuration).
1) Programming the PL using a bitstream (if provided).
2) Loading second stage bootloader or bare-metal application code into DDR memory.
3) Handoff to the second stage bootloader or bare-metal application.
# Second Stage Bootloader (Uboot)
U-Boot is an open source bootloader that is frequently used in the Linux community, and used by AMD for the MicroBlaze™ processor and the AMD Zynq™ 7000 processor for Linux.

A bootloader initializes hardware that the Linux Kernel does not necessarily initialize (such as the serial port and DDR). System providers often put U-Boot into flash memory. U-Boot is an example of a Second Stage Bootloader.
