The relational Model of Data is based on the concept of a **Relation**
- The strength of the relational approach to data management comes from the formal foundation provided by the theory of relations
- Relations are how data can be broken into subsets
- Relations can be broken up to get the original data
*How do I break up a table into its different relations?*
	Usually data is broken up into two separate tables where there is a primary key that is consistent with more data being added on to that primary key (a primary key not in its original table is usually called a foriegn key)
**Key of a Relation:** Each row has a value of a data item (or set of items) that uniquely identifies that row in the table called the *key*
**Surrogate Keys or Artificial Keys:** Sometimes row-ids or sequential numbers are assigned as keys to identify the rows in a table
**Schema of a Relationship:** Denoted by R(A1, A2, .....An) where R is the *Relationship* and $A_n$ is the *Attribute*
**Tuple:** ordered set of values, or a row (enclosed in angled brackets ‘< … >’)
**Domain:** all possible column values
**Relation state:** a subset of the Cartesian product of the domains
of its attributes
**Atomic:** All values are considered atomic or indivisible
**Null:**  A special value used to represent values that are unknown or not available
Three main types of **Constraints:**
1. **Inherit or Implicit Constraints**: These are based on the data model itself (E.g., relational model does not allow a list as a value for any attribute)
2. **Schema-based or Explicit Constraints**: They are expressed in the schema by using the facilities provided by the model. (E.g., max. cardinality ratio constraint in the ER model)
3. **Application based or semantic constraints**: These are beyond the expressive power of the model and must be specified and enforced by the application programs
1. Key Constraints: Every data table needs a key
2. Entity Integrity: Domains and types of values must be respected
	- The primary key attributes PK of each relation schema R in S cannot have null values in any tuple of r(R).
3. Referential Integrity: Table referencing rules must be respected
**Superkey**: Is a set of attributes SK of R with the following condition:
- No two tuples in any valid relation state r(R) will have the same value for SK
- That is, for any distinct tuples t1 and t2 in r(R), t1\[SK\] $\neq$ t2\[SK\]
- This condition must hold in any valid state r(R)
**Key**: A "minimal" superkey, a key is a superkey but a superkey is not a key
**Relational Database Schema**: the way that the database is designed
**INSERT** a new tuple in a relation
- Domain constraint: if one of the attribute values provided for the new tuple is not of the specified attribute domain (not right data type)
- Key constraint: if the value of a key attribute in the new tuple already exists in another tuple in the relation (primary key duplicate error)
- Referential integrity: if a foreign key value in the new tuple references a primary key value that does not exist in the referenced relation (foreign key points to a null value error)
- Entity integrity: if the primary key value is null in the new tuple
**DELETE** an existing tuple from a relation
- Referential integrity: if a foreign key value in the new tuple references a primary key value that does not exist in the referenced relation (foreign key points to a null value error)
- This happens often in a well-linked database there are a few ways to remedy this:
	- RESTRICT option: reject the deletion
	- CASCADE option: propagate the new primary key value into the foreign keys of the referencing tuples
	- SET NULL option: set the foreign keys of the referencing tuples to NULL
**MODIFY** an attribute of an existing tuple
**Foreign Key:** TIP: use foreign keys within relational tables to reference the different elements it is creating a relation between. Represent the foreign key by drawing a line with an arrow from the usage of the foreign key to where it pulls the primary key![[Pasted image 20230912174842.png]]
