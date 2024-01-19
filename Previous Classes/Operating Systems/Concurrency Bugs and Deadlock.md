*Why do we need a lock?*
Many writers and one reader?
Yes
Two writers and two readers?
Yes
One writer and many readers?
Not always
Large critical sections wastes time, so we can break them down (sometimes)
Use a lock only if it is required
- Determine the case when you do not need a lock (Atomic read, only one writer)
- Use a small critical section (determine where you need to share a variable, wrap only the code that updates the shared variable)
Deadlock
- Multiple locks waiting on each other, which means neither make any progress
- Only happens when
	- Mutual exclusion
		- Solution: Do not use locks, replace them with atomic primitives `compare_and_swap()`. Only possible to update one variable.
	- Hold-and-wait- threads hold resources allocated to them while waiting for additional resources
		- Solutions: acquire all locks atomically at once
	- No preemption - resources cannot be forcibly removed from threads that are holding them
		- Solutions: trylock or a lock function with a timer
