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
### 1-4
- <u>Cryptography</u> - a way to maintain integrity and  (Mathematical manipulation of information that prevents the information being disclosed or altered)
- <u>Hash Function</u> - a way to encrypt information such that the goal is to select a has so that there are no collisions (where a hash Function, H, applied to D1 and D2 must result in different hash values, if D1 and D2 are not equal)
- <u>Merkle Hash</u>
	- Tree based hashing scheme
	- ===Steps:=== apply the hash to the values in the leaves of he tree, then go to the parent of node of the leaves and apply the same hash function and compute the hash of all the nodes at this level, continue until at this computing the hash of the root and this becomes the hash value of the tree.
- <u>Secure Hash Algorithms (SHA)</u>
	- Input message size $2^{64} - 1$ bits
	- Message is divided into blocks, where ea ch block is divided into 512 bits
	- There is an initialization value of 8 32 bit words
	- Compression functions takes block 0 and the initialization valued to produce an output
	- The output is combined with block 1 by the compression. This is continuously done until the final hash is created
- <u>Symmetric Key Crytography</u>
	- Each pair of entities share a key and it is the same key
	- The problem with this type of cryptography is if the communication of the key is compromised, then the cryptography is compromised (If I email the key and someone sees my key, they now have access)
- <u>Block Cipher</u>
	- Used for encryption of lengthy information
	- Break up the text/information into fixed sized blocks, encryption is applied to each block (block by block encryption), then the blocks of plaintext are input into block cipher encryption system and the output is cipher text
	- In Fiestel Cipher the decyption is reversal of encryption (not good, too simple)
	- DES (Data Encryption Standard) and AES (Advanced Encryption Standard) are block cipher. The latter has not been broken, yet.
- <u>Digital Signatures</u>
	- Combines hash function and key mechanisms
	- Hash the message and attached the hash value with the message
	- Then sign the hash value with the signer's private key
	- At the other end, the receiver will use the public key of the sender to the signed hash value
	- Compute the hash of the message to see if the same hash value is obtained
	- This proves the integrity of the message, and the signature is not forged and also ensures non-repudiation
	- ===Note:=== the message itself is not encrypted; if the message has to be protected then add a different kind of encryption to the message
---
### 1-5 Consensus Algorithms
- <u>Consensus</u> - The nodes in a distributed system have to agree for any operation. Consensus percentage/amount depends on the system
	- <u>Traditional consensus</u> - Practical Byzantine Fault Tolerance
	- <u>Lottery-based Consensus</u> - Nakamoto consensus used in Bitcoin
- <u>Fault Tolerance</u> - how the system handles nodes or links failing
	- <u>Crash Fault Tolerance</u> - deals with crash faults (benign faults)
		- CFT at least 2f + 1 required nodes for consensus
		- BFT at least 3f + 1 required nodes for consensus
		- Achieve consensus by sending out a value, and if the value is accepted by 2f+1 nodes, then consensus is achieved
	- <u>Practical Byzantine Fault Tolerance</u>
		- First phase (pre-prepare): client sends request to primary node, the node assigns a unique number to the request, request is sent to all backup replicas
		- Second phase (validation): Is the digital signature valid, make sure the current view number of the request message is valid, digest/hash of the operations request message is valid, if all elements are valid then the backup replicas accept the message
		- Third phase (prepare): exchange messages between each other (the prepare message), each backup waits for 3f+1 prepare messages from other replicas, they also have to ensure that the view of all replicas have same view number
		- Final phase (commit): each replica sends message to other replicas to commit and waits for 3f+1 commit messages from other replicas. The replicas execute the request and then send message to client
	- <u>Byzantine Fault Tolerance</u> - deals with malicious faults
	- Communication between nodes can be asynchronous, synchronous, or a mix and eventually a system becomes synchronous
	- <u>Nakamoto Consensus and PoW</u> - makes use of Hash Puzzles
		- Proof of Storage
		- Proof of Stake
		- Proof of Activity (mix of all PoW and PoS)