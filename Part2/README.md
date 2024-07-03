# READING FROM THE DISK 
1. The BIOS loads the first sector of the floppy disk image and that is known as boot sector. In that we have the bootloader which basically is responsible for loading the operating system. We have to divide the floppy disk into 2 sections the boot loader one and kernel one.
2. Bootloader: Remains small (usually within the first sector) and is responsible for loading the kernel.
Kernel: Contains the core OS functionality. It’s loaded by the bootloader and resides elsewhere on the disk.
3. Logical Block Addressing (LBA): Each sector is assigned a unique block number to Cylinder-Head-Sector (CHS): Identifies sectors based on the cylinder,head and sector number. 
4. Kernel consists of the OS that we build earlier which basically prints "Hello world". In Makefile file, we basically make a floppy disk img fat 12 where bs = 512 and count = 2880 and truncate it from first sector(to divide it into 2 separate parts). Now if we write on the 512 it will also overwrite the fat 12 predefined, So we have to define them. Since the x86 BIOS works with CHS (Cylinder-Head-Sector) addressing, we will need to implement a function to convert LBA to CHS.
5. The BIOS locates the sector in LBA scheme so it loads our bootloader.asm it transfer the control to bootloader where we have converted the lba to chs which then read from the read disk using chs scheme. 
