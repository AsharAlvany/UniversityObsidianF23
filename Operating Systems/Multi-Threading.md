CPU speed capped by frequency/power - although the size of transistors are continuously decreasing, the amount of heat and power that is produced is still increasing which means that the power that we can squeeze out of one chip is limited by the heat that is produced
**Concurrency** - a method of increasing the performance of an application by running multiple functions as separate jobs at the same time using threads and processes
The following are two options of implementing concurrency
- **Processes** - run multiple functions concurrently as separate instances (have their own memory and their own computation) (eg. webserver, web browsers)
	- Each process runs in an isolated environment
	- Processes do not share memory
	- `env_create()` creates a new PRIVATE memory space for a new process
	- `fork()` creates a new process by copying an existing memory space
	- PROS
		- Do not have to modify program to achieve parallelism, just run multiple processes or `fork()`
	- CONS
		- Use additional memory for new data
		- Cannot directly read memory of other processes (IPC is available, but slow)
- **Threads** - run multiple functions concurrently within the same process (shared data and memory)
	- Creates a SHARE memory space and run concurrently
	- `fork()` is a naive design because it copies all physical pages creating latency. Copy-on-write on the other hand does not copy physical pages, creates a new page dir/table with the same mappings with read-only permission provide a private copy when write on a COW page occurs
	- Thread creation
		- Get a new execution environment with the same memory space
		- Assign the same page directory/tables (assign the same CR3)
		- Create a new stack and storage for registers (execution context)
		- This uses less memory than COW `fork()`
	- A thread's execution could be inconsistent (other threads may intervene), this is called a **Race Condition**
		![[Pasted image 20231011150404.png]]
		![[Pasted image 20231011150504.png]]
		- The root cause of a **data race** is that a thread may get the previous version of shared data before the previously running thread properly stores that
		- **Solution**: make all load to data wait until previous load-store finishes, we can do this via mutual exclusion
	- **Mutual Exclusion** - combine multiple instructions as a chunk also known as a critical section let only one chunk execute at a time and block other executions where next execution can only happen after finishing all the previous critical section execution
	- The problem with mutual exclusion is that if it used too often then the purpose of multi threading is nullified. Ensure that the critical section is as short as possible to maximize benefit of having concurrency
	- Enabling MUTEX:
		- cli is the clear interrupt bit that makes sure that the CPU will never interrupt until it runs the sti, set interrupt bit.
		1. Check if here;s any other execution in the critical section
		2. If not, acquire the lock
		3. If not, acquire the lock
			- Other cannot get into the critical section while it is in use
		4. Run the critical section
		5. Unlock and allow other executions to run their critical sections
		![[Pasted image 20231011152150.png]]