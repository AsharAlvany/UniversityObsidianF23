Which on-disk structures may be updated for an append to a file?
- Data blocks
- Bitmap for data blocks
- Inodes
What happens if the system crashes in the middle of disk structures?
- The file system can be in an inconsistent state
Solution?
- We need to transition the FS from one state to another state atomically
- Lock and unlock is not applicable, not possible to prevent power loss
File System Checker
- After crash, scan the entire disk for inconsistencies and resolve them
- Not always obvious how to fix file system image, Don't know "correct" state, just consistent one
Journaling - alternative to FSCK
- Goals - just do some recovery, not the entire disk. correct state better than a consistent state
- Logging
- Transaction
- During writes (transaction either fails or succeeds)
	- Record all writes to the journal (log)
	- Record “done”
	- Do the real writes
	- Clear “done”
	- During recovery (after crash)
	- If “done” in log, replay all writes in log
	- If no ”done”, ignore log