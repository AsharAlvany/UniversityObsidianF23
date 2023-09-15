**Three Goals**
1. **Transparency:** user applications do not need to know the system' global internal state
	- Program A is loaded at 0x804800, can program B be loaded at 0x804900
2. **Efficiency:** do not waste memory
	-  Manage memory fragmentation
3. **Protection:** isolate a user application from other user applications 
The main technique that allows virtual memory is **Paging**
* Have an indirect table that maps *virtual addresses* to *physical addreses* using paging tables
* Paging is a method of implementing virtual memory
* Split memory into multiple 4KB (4096)
	* Last 3 digits of a page address are zero in hexadecimal (4096 = 0x10000)
* Use an indirect map between a virtual page and a physical page

| Virtual | Physical |
| --- | --- |
| 0x81815000 | 0x32000|

* Physical pages may not be contiguous
* Register **CR3** points towards the **Page Directory**
* We access a page table by a 32-bit linear (or virtual) address ![[Pasted image 20230911145524.png]]![[Pasted image 20230911145614.png]]
* The page number is split into an upper 10 bits that contain the page directory that points to a specific table and then the index of the page directory points to a page table and then the lower 10 bits of the page number points to the index within the page table then the table points to the physical memory location (before adding the offset from the final 12 bits from the original 32 bit virtual address)![[Pasted image 20230911150027.png]]
* **Summary:** First 5 bits give you the virtual page number, and last 3 bits give you the offset. Mapping of virtual page number and append the offset is the physical address![[Pasted image 20230911150438.png]]
* To enable paging, the flag needs to be raised through CR0 and the page directory address (physical) needs to be stored in CR3
* Without optimization the lookup time (from virtual memory to physical address) is 601 cycles
* Through the use of CPU cache (Translation Lookaside Buffer (TLB)) we can reduce this time down to 4 cycles, if there is a TLB hit
	* TLB stores data without tables and instead has direct data lookup for virtual memory addresses
	* One way to handle TLB is through temporal efficiency, "if something was accessed recently it's likely that it will be accessed again soon", with temporal eviction, "if something has not been used in a while, evict it to make space for newly accessed data", or random eviction
	* Another way to handle TLB is through spatial efficiency "if something was accessed recently it is likely that the area around it will be used next"
There are times when the values in the TLB are invalidated because the mapping changes
- virtual memory addresses mapping changes
- a new process uses the same virtual memory address through CR3
**PTE** - Page Table Entry where the top 20 bits is the physical address and the bottom 12 are flags
![[Pasted image 20230913145331.png]]
Both the page table ENTRY and the page table DIRECTORY have permission bits that need to be checked
First the CPU tries to access the directory and checks the permission bits then the entry permissions
![[Pasted image 20230913150312.png]]
	There are some page permissions that cannot be accomplished
**Internal Fragmentation** - waster of memory within a block
**External Fragmentation** - There is enough available memory for a new block to be used for a program, but there is not enough *contiguous* memory
**N-to-1 mapping** - mapping multiple virtual addresses to a single physical address
Why? To accomplish different things at the same physical address
**Page Directory** - 4KB, 1024 entries, 4 byte entry
![[Pasted image 20230913152356.png]]
kern is SHARED among the processes but each process could run different application programs