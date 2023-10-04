Reference the [[User-Kernel Context Switch]]
![[Pasted image 20231004143714.png]]
**System Call Design**
Application should not call arbitrary kernel functions
*Why?*
Because then we allow the user-space unlimited access to the kernel, and the separation of privileges are no longer applicable
**Call gate** - a secure way to access Ring 0
- Any system call can only be executed through a a trap handler
![[Pasted image 20231004144639.png]]
We can intercept all system calls from Ring 3 at our system call trap handler, which checks the arguments for malicious means
![[Pasted image 20231004145654.png]]
**Page Fault** - Occurs when paging (address translation) fails
- Invalid translation
- Access violation
- Protection violation
When a page fault occurs, the CPU stores the virtual address of the fault (the location what address the instruction was trying to access) in CR2
err register stores the reason for the fault
- bit2 = 1 user-mode access
- bit1 = 1 write access
- bit0 = 1 a protection violation
- bit0 = 0 page not present
**Allocating new stack automatically**
- Sometimes we allocate a page from the stack for a program, but we need more memory for the execution
- What will happen:
1. Program will try to allocate memory outside of the stack, but there is not remaining space
2. A page fault exception will be raised and the type of exception will be documented
3. Read CR2 register to find the location of memory address fault
4. Read the error code to make sure that the error was caused by a non-present page
5. Allocate a new page for the stack
6. Executes the faulting instruction again.
Other examples of using Page Faults
- Copy-on-write
	- Share read-only pages (multiple processes of the same program)
	- Create a private copy later when the first write access happens
	- Saves memory
- Memory Swapping
