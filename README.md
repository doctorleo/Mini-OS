Mini-OS
=======

Mini OS is a simple kernel written in C and Assembly which could be loaded with the GRUB bootloader on an x86 system. This kernel will display a message on the screen and then hang.

##Tools
Before writing the kernel, make sure that the following tools are available in your system.
<ul>
<li>An x86 computer (of course)</li>
<li>Linux</li>
<li>NASM assembler</li>
<li>gcc</li>
<li>ld (GNU Linker)</li>
<li>grub</li>
</ul>

##Building the kernel
The following commands will build the kernel.
<pre>
nasm -f elf32 kernel.asm -o kasm.o
gcc -m32 -c kernel.c -o kc.o
ld -m elf_i386 -T link.ld -o kernel kasm.o kc.o
</pre>

##Now run your kernel
The kernel will be run using the <code>qemu</code> emulator.
<pre>
qemu-system-i386 -kernel kernel
</pre>

##License
All other files are [MIT](http://opensource.org/licenses/MIT) Licensed.

##Author
Debashis Barman [http://www.debashisbarman.in](http://www.debashisbarman.in)


