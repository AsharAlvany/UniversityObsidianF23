**High Level - The conceptual data model**
- Closer to the user
- The realm of the application
- Pre-defined  queries
- Pre-defined views that are easy for a human to use
- **Entity-Relationship Model**
	- Each entity is a set of attributes with data types
**Mid-Level - The representational model**
* How is data associated and linked so that both end users and physical systems can work together
* Ideas -> Requirements -> Entity Model
* **Relational Model**
	* The diagram that describes a database is the Database Schema or Relational Schema or Relational Model
	* Connected by using a primary key to keep relations
**Low-Level - The physical data model**
* Closer to the machine
* An Instance
	* The current point at which the database is being used is called the **current database state**
	* Operations on the database is only concerned for that current frame
---
- **Internal Level** 
	- The bottom most level is the database hardware, the drives that store the data
	- The purpose of this level is controlling the above
- **Conceptual Level**
	- This level handles the relationships between data and record keeping
- **External Level**
	- Desired results of asking a question of the database. 
----
**Logical Data Independence**
* The conceptual schema can be updated
* Updating the definition of the data does not require a new application or new hardware.
**Physical Data Independence**
* If the hardware is reconfigured or changed, the conceptual/logical layer does not have to be changed applications do not need to be updated.
---
