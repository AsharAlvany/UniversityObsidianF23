**Functional Dependency:** The association between the variable index and the array scene is a Function Dependency
- When we use an array in an application
- We store information by an index
- We retrieve information by an index
Each normal form is a stronger constraint
- A 3rd normal form Relational Schema must already have been in 1st and 2nd normal forms
**First Normal Form:** 1NF means that only one value is stored in one cell of the relational table
- All attributes are a single value per entry
![[Pasted image 20230919180340.png]]
Sometimes that **MAY** means reassigning a new primary key
**Second Normal Form**
- All attributes depend on the whole key, that is, removing any part of the key makes the functional dependency fail. The smallest, simplest superkey.
- The Attributes are functionally dependent on the Primary Key
- The Primary Key may be one or more attributes that make up a unique set
- Each row of the table/schema there exists for each tuple in the schema a primary key (∃) for all rows of the table. (Ɐ)
![[Pasted image 20230919180806.png]]
**Third Normal Form**
- All attributes depend on nothing but the key, there is no transitive functional dependency
- A relation schema R is in third normal form (3NF) if it is in 2NF and no non-prime attribute A in R is transitively dependent on the primary key
**BC Normal Form (Boyce-Codd)**
- A relation schema R is in Boyce-Codd Normal Form (BCNF) if whenever an FD X →A holds in R, then X is a superkey of R
**4th Normal Form**
- In order to handle a table where the primary key goes to a set of attributes instead of a single attribute![[Pasted image 20230921175637.png]]
**5th Normal Form**
- Every Relational Schema in the relational model is reduced to pairs of attributes
**Join Dependency:** Where Functional Dependency is associated with the breaking down a universal table down to the normal forms, a join dependency is associated with the bringing back the broken up tables back into a universal table
![[Pasted image 20230921180955.png]]
Splitting on teacher and classes is unique enough and also affords us a savings.