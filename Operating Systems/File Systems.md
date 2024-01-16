Virtualization of persistent storage
Two key abstraction
- **File**
	- Sequence of persistent bytes that can be read/written
	- Logical storage unit with contiguous logical address space
		- A logical file address = logical address of the first block + offset within the block
	- A file has many **attributes**
		- Name: only information kept in human-readable formats
		- Identifier: unique number identifies each file within the file system
		- Location: pointer to the file location on the devices
		- Size: current file size
		- Protection: controls who can do the reading, writing, and executing
		- Time, date, user identification: used for data protection, security, and usage monitoring
		- **Inode** an on-disk meta-data structure that contains a files attributes (except file name)
		- Every file has a unique inode
		- Maps each file to their location on a disk
		- Inode number is the file identification number within the file system
		- Access a file by finding its inode. We need a mapping between the file name and the files inode number. This mapping will be stored in the directory
		- Opening a file: Search for the directory once, fetch the directory's inode and keep it in memory. find a free entry in the FD table, update teh FD entry to point to the file's inode, set the offset value in the FD entry. Subsequent file operations use the FD
- **Directory**
	- A directory is a file
How to allocate files?
- Allocate the required number of blocks contiguously
	- Simple. little overhead, good performance, for sequential access, easy calculation for random access
	- External fragmentation, may not be able to grow a file, need compaction
	- Indexed Allocation - non-contiguously, keep index table to locate the blocks of a file (similar to a page table), no external fragmentation, the index table is stored in the inode
	How big is the index table?
	- Assume a max file size is 1MB, block size is 512 bytes, and index table entry size 8 bytes
	- The size of the index table is -> max file size / block * table entry size
	$$ 1MB / 512 bytes = 1024 \cdot 1024 / 512 = 2048 = 2k \ entries $$
- Allocate using Dynamic Allocation
	- Small file use direct block pointers (single level index table)
	- Large file use indirect block pointers
	- Overhead only grows when the file size grows
Find free disk blocks by using a bitmap which is an unsigned integer array
Superblock is a special block to contain information about the file system. While mounting the superblock is read first. 
- In JOS, Block 1 us the superblock
- Block 2 is the bitmap
- Block 0 typically contains boot loader and partition tables