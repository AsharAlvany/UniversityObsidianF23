Binary Locks
- Every data item can be locked or unlocked
- Enforces mutual exclusion
- Locks can be shared
- Two phase locking 
	- Acquisition, expand, grow
	- Relinquish, contract, shrink
- If there is a conflict the last transaction to arrive will fail