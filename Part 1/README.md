# "HELLO WORLD" 
The assembler(NASM) compiles the assembly code(of length 512 bytes) into machine code, and then the BIOS (inside qemu) loads the first sector (first 512 bytes with boot signature i.e.,0xAA55) into memory during boot. The transition from BIOS to code marks the beginning of the boot process. If everything goes you will see "Hello World"
