**Growth of Blockchain**
- Blockchain started with Bitcoin (2006-2008)
- No one knows for sure who invented Blockchain technology (Satoshi Nakamoto was never heard of again)
- It is a type of <u>Distributed Ledger</u>
	- A type of record all the transactions carried out
	- It is a ledger that is distributed and replicated so that everyone has a copy
	- Usually it is immutable
	- Collection of blocks
		- Where the original block is called the "genesis"
- Not all distributed ledgers are blockchains (no blocks means no blockchain)
- Peer-to-peer systems, decentralized systems, append only database have influenced blockchain
**Distributed Systems**
- A distributed system is a collection of nodes connected via a network
- DS may have central control or decentralized where no node has control
- Data must be distributed, centralized, or replicated
- Replicated data must be consistent
- <u>Consistency, Availability, and Partition Theorem</u> - impossible to have all 3 
	- All data must be consistent
	- Data must be available at all times
	- There may not be any partitions
**Blockchain Architecture**
- Layered Architecture
- Network Layer, P2P Layer, Cryptography, Consensus, Execution, Applications
- Blocks
	- At the top is the pointer to the previous block (the hash of the previous block)
	- Nonce - use once to throw away
	- Timestamp
	- Merkle Root (Hash of the block)
	- The transactions that are part off the block
**How does Blockchain Work**
- Transaction is initiated between two or more parties (transfer funds)Node validates transaction and transaction is broadcast
- Transaction has to be put in a block for execution; miner nodes compete and mine for a block to put the transaction
- When the miner wins be solving a complex mathematical problem, the miner gets compensated and the block is inserted into the chain
- Transactions in the block and executed and the block is then inserted in the chain with a pointer pointing to the previous block