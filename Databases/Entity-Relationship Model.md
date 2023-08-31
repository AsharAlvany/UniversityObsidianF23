#### The Design Process
* Read the problem
* Check with the *requirements* of the end-user
	* If the end-user makes a requirement it does not matter if the requirement does not make sense
* Document all requests and decisions
* Put boundaries and limits based on the "Mini-world" - you can't put the entire worlds into your scope
* These boundaries and limits include the *Assumptions*
	* Write down all assumptions and definitions
	* Database Designer must trim the universe to fit it all into the database
* Items and people often become entities
* Descriptions and properties become the attributes - use these to form logical *relationships* and *groupings*
* Start drawing and be ready for the idea to change as the problem is further investigated
#### The Entity
Entities are shown as a rectangular box surrounded by a cloud of
Attributes in ovals and each Entity will represent a construct in the database schema
The building block of the Model is the Entity
A **Weak Entity** is an entity that cannot exist without its owning Entity
- a Weak Entity is usually a record
Each Entity has attributes
**Domains** values for the information, like type-checking
**Constraint** only a range or set of values are permitted
Single value attributes: simple attribute
![[Pasted image 20230829175019.png]]
Primary key attribute: unique attribute
![[Pasted image 20230829175045.png]]
Multivariate attributes: the value can be represented by a set
![[Pasted image 20230829175104.png]]
Compound attributes: Attributes that can be made smaller attributes
![[Pasted image 20230829175125.png]]
Derived attributes: The value has been calculated by other attributes
![[Pasted image 20230829175144.png]]
**Example**
![[Pasted image 20230829175500.png]]
![[Pasted image 20230829175511.png]]
#### Relationships
**Relationships** are the interactions between two or more entities
* Represented by a diamond with a single border
* Dependent on entities, may have their own attributes (usually some sort of ratio), never have their own key
![[Pasted image 20230829180125.png]]
- Relationships also have a **degree** - the number of entities involved in a relationship
- A relationship is a *ownership, aggregation, association, generalization, usage, connectivity*
- The ratio of degrees between entities on a relationship is called the cardinality ratio
- **Total Participation**-all entities in one set are in a relationship to another entity. Denoted with a double line
- **Partial Participation**-Some entities in one set are in a relationship to another entity. One entity is not fully dependent upon the other.
#### Specialization
- An Extended ER Diagram has the ability to show sub-classes
- Entities can have subclasses. Each subclass has all the attributes of the original Entity
- If a subclass cannot have a shared role with any other subclass, the specialization is called **disjoint**, and the symbol “d” is used.
- If a subclasses can have shared roles with any other subclass, the specialization is called **overlapping**, and the symbol “o” is used.
![[Pasted image 20230829182007.png]]
- Types of specification
	- Predicate-defined ( or condition-defined) : based on some predicate.
	- Attribute-defined: shows the name of the attribute next to the line drawn from the superclass toward the subclasses
	- User-defined: membership is defined by the USER on an entity by-entity basis
#### Generalization
* Generalization is the reverse of specialization process
* Several Entitles with common features are generalized into a superclass and subclass structure
* Given electrical tape, duct tape, and duck tape within our scope, we can create a superclass called "tape"
![[Pasted image 20230831175230.png]]
#### Union
* Represented by a circle with a U
* Taking multiple entities and creating a reference
* The entities do not have a similar key attribute
* Not a n-ary relationship...they do not interact with each-other in this relationship
* Yet they all link to another entity through a common relationship
![[Pasted image 20230831175751.png]]
