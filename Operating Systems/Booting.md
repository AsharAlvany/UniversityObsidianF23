**QEMU** - quick emulator, virtual computer software

*What happens when your computer is booted?*
**BIOS** - Basic Input Output Service
* Enables basic device access (keyboard, mouse)
* BIOS config utility (boot sequence, etc)
* Located on the persistent ROM (read-only-memory) on the motherboard
* Copies code from ROM to DRAM to the physical address: 0xffff0
* Run code from DRAM that loads and runs the boot sector from the disk
* Read the first sector from the boot disk (512 bytes)
* Load it to DRAM at 0x7c00yay 
* Run it: set the instruction pointer to 0x7c00

**i8086** - Intel 8086
* 44 years old, 5MHz
* 16-bit processor
* All registers are 16-bit

*Why is all the BIOS code the same?*
To promote backward compatibility

The 8086 could access 1MB of memory, but it had 16-bit registers, which means that 2 registers would be populated

**Memory Segmentation**
![[Pasted image 20230828150053.png]]

**Real Mode**
- Use physical memory directly
- No memory protection
- \[0x0008:0x3400] jumps directly to \[0x3480]

**Protected Mode**
* \[0x0008:0x3400] jumps to GDT\[1].base + 0x3400
* Selector 0x0008 >> 3 = index 1
	* 1 because each entry in the GDT is 8 bits
* Access is only allowed if 0x3400 < GDT\[1].limit
* Otherwise raises an exception
* GDT is a list of **segment descriptors**
![[Pasted image 20230830145503.png]]
![[Pasted image 20230830145918.png]]
* To calculate **Segments in Protected Mode**
	* Segment End = base + limit * {4KB (0x1000) if G = 1 || 1B if G = 0}
* To find if Segment Access is allowed take the \[selector:offset] = GDT\[index].base + offset if this value is within bounds of Segment End (use technique above and the table provided) then the access is allowed
* To find **Privilege Level** check the last two bits of the segment selector register (%cs)
	* %cs = 0x8 (01000) -> last 2 bits are zero -> kernel
	* %cs = 0x13 (10011) -> last 2 bits are 3 -> user
* *Can we change our Privilege Level?*
	* Only if we stay the same or go down
---
### Examples
![[Pasted image 20230828150702.png]]

---
**Boot from disk**
1. Load the boot sector from the first 512B from boot disk
	* Boot sector - located at "obj/boot/boot"
		* MBR
		* The first sector of disk partition
		* contains the bootloader
		* Ends with 0x55aa
2. Load that to 0x7c00 and run
3. Boot loader takes control and BIOS ends
4. Enable Protected Mode (4GB memory access)
5. Load the other parts of the OS

**A20 Mode**
Address \[seg:offset] is clipped when A20 is disabled (ignores the address line at bit 20)
When A20 is enabled, the extra bit is not ignored

**JOS Bootloader**
1. Enable A20
2. Enable Protected mode
	- After:
		- boot.S runs ljmp (long jump or far jump) 
		- This applies the new segment assigned by the Global Descriptor Table (GDT)
3. Read kernel image (ELF)
4. Run kernel
Do all these in 510 bytes

