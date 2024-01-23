### 1-1
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
---
### 1-2 Decentralized Systems
**Decentralization**
- In a <u>centralized system</u>, multiple users access a main system/database through a central server
- In a <u>decentralized system</u> there is no center system/database and each node manages its own data where data may be replicated (almost immutable, almost secular)
- In a <u>distributed system</u> data is distributed to nodes and the user queries the system from a node. The nodes communicate with each other to answer a query. (Think of a library system looking for books from different branches, or nodes)
- Centralized systems are subject to single points of failure while decentralized systems are more fault tolerant (due to redundancy)
**Decentralization Ecosystem**
- Communication Layer (through the internet protocol), Storage (file systems and big data systems), Execution Platform (Blockchains such as Bitcoin, Ethereum, Hyperledger), Decentralized Applications (Decentralized Finance and Decentralized Web)
- Examples of Decentralized Applications: Smart Contracts, Autonomous Agents, Decentralized Autonomous Organizations, Next Generation Web
**Blockchain Hyperledger**
- Every peer on the channel in the Hyperledger has a copy of all the blocks together with its own database which records the states and the results of executing the transactions
- <u>Hyperledger</u> is a ===Distributed and Replicated Decentralized Ledger===
- Each block has a pointer to the previous block, which is the hash of the contents of the previous block
- Each block executes a different set of transactions
- An attacker cannot insert a new block between two blocks and the history of the transactions is maintained
- Each user can get a certificate from a CA and to access a resource the user would show their certificate to the resource manager which then decrypts the certificate using the public key of the CA
- Each user/peer will be given a private and public keys by the CA for submitting/executing transactions and ensuring ===authenticity===
**Public Key Cryptography**
- Asymmetric keys are used to create a mathematically related key pair
	- A secret private key and a public key
	- Use of these keys allows protection of the authenticity of a message by creating a digital signature of a message using the private key, which can be verified using the public key.
- This type of cryptography is widely used