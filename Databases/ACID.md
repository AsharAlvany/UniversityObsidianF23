Atomicity, Consistency, Isolation, Durability
- Atomicity - A transaction cannot be subdivided
- Consistency - The system is preservation goes from one usable state to another
- Isolation - Even though the db is handling multiple users the transactions appear to be unaffected by the other operations
- Durability - After the transaction commits, the changes are permanent
A set of transactions are in serializable schedule if all operations in the transactions are grouped by the transaction
When all the actions that belong to one transaction are completed before the next transaction starts
No interleaving occurs in a serializable schedule
A conflict occurs if
1. They belong to different transactions
2. They access the same data
3. And one transaction is a write
