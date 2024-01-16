	 OS runs in the kernel space initially
CPU only executes one instruction at a time
*How does the OS kernel run a program in Ring 3 (user space)?*
*How does the OS kernel take back the execution to Ring 0 (kernel space)?*
*How can a user-space program let the OS kernel do a service for them (e.g., use a peripheral)?*
1. Interrupt
2. System Call
3. Fault/Exception
**Kernel**
- Runs with the highest privilege
- Configure the system (devices, memory, etc)
- Manage hardware resources (Disk, memory, network, video, etc)
- Manage other jobs (processes and threads)
- Serves as the **Trusted Computing Base (TCB)**
	- “Trusted”: if kernel is compromised, all is compromised
	- Restrict jobs outside the TCB (user space) from doing something bad
**User**
- Run with a restricted privilege (Ring 3)
- “Untrusted”: not allowed to access kernel memory
-  Not allowed to talk to hardware devices directly

**System Call** - when the User needs to run processes with kernel mediation, the following happens:
1. A function call is made from an application to the OS kernel so the application can request the OS  to do something special for them. These cause a software interrupt to allow the kernel to take over
2. The kernel takes over  to execute its own system call based on the system call parameters with access to system devices
**Cooperative multitasking** - the User space voluntarily yields the execution when the process finishes or pauses its execution
**Preemptive Multitasking** - CPU generates a timer interrupt after some time quantum. At interrupt, forcefully take back the execution to the kernel. Guaranteed kernel execution to let kernel mediate resource contention

**Trap:** An event that forces the CPU to execute some specific code in the kernel, called a "Trap Handler". A common term that includes all of the three terms:
1. **Interrupt** - Hardware interrupt (mouse click, timer interrupt)
	- System Call is a type of software interrupt
 2. **Fault** - An error that the OS may recover from and continue execution
 3. **Exception** - An error that the OS may or may not recover from (includes Faults)
	 - Must stop the current execution if not recoverable
Special exceptions: 
- **Double fault**: an exception caused while handling an exception, also caused if there is no handler for a specific exception type
- **Triple fault**: an exception caused while handling a double fault

**Interrupt descriptor table (IDT)** - 
- IDTR register stores the IDT location (linear address)![[Pasted image 20230925151948.png]]

### EXAMPLE: Interrupt Handling: Opening a File
![[Pasted image 20230925152125.png]]
![[Pasted image 20230925152137.png]]

**Controlling Interrupt**
What happens if an interrupt occurs while the system is handling an interrupt? This will cause an "infinite" interrupt. To avoid this, there is an IF flag in the EFLAGS register.
- EFLAGS contains the current state of the CPU
- cli instruction disables interrupts
- sti enables interrupts

**Resuming Execution After Interrupt Handling**
After the interrupt is handled, we want to go back to the previous execution. This is done using the iret instruction, which is stored onto the stack and then restored when we are needed to go back.

When a trap occurs the hardware automatically stores the esp, eip, EFLAGS, ss, and cs values, but this is not enough. General purpose registers are not restored so those need to be stored elsewhere.

![[Pasted image 20230927151600.png]]![[Pasted image 20230927151626.png]]

**Summary**:
![[Pasted image 20230927152834.png]]

**Process Context Switch** - also called multitasking where CPU can run multiple applications “at the same time” (but they're really "time-sharing")
The three following designs are potential types of PCS
1. Don't switch!
2. **Cooperative multitasking**: rely on processes to yield voluntarily
3. **Preemptive multitasking**: interrupt a process temporarily and resume it later
