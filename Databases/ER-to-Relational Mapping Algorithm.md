Step 1: Mapping of Regular Entity Types.
![[Pasted image 20230912180252.png]]
- Begin with <u>strong</u> entities 
- The key of the entity is the key of the schema construct
- The attributes, domains, and constraints match the regular entity on a one-to-one basis
Step 2: Mapping of Weak Types.
![[Pasted image 20230912180437.png]]
- The owning strong entity will have a primary key that acts as a foreign key in the weak entity schema construct
- The primary key of the Weak Entity is the combination (superkey) of the owning foreign key and the local key (if it has one)
Step 3: Mapping of Binary 1:1 Relations
![[Pasted image 20230912180845.png]]
	Circle is in wrong place. Supposed to be in Manages
- Foreign Key ( 2 relations) approach: Choose one of the relations-say S-and include a foreign key in S the primary key of T. It is better to choose an entity type with total participation in R in the role of S.
Step 4: Mapping of Binary 1:N Relationship Types
![[Pasted image 20230912181201.png]]
- For each regular binary 1:N relationship type R, identify the relation S that represent the participating entity type at the N-side of the relationship type. Include as foreign key in S the primary key of the relation T that represents the other entity type participating in R
Step 5: Mapping of Binary M:N Relationship Types.
- For each regular binary M:N relationship type R, create a new relation S to represent R. This is a relationship relation.
- Include as foreign key attributes in S the primary keys of the relations that represent the participating entity types; their combination will form the primary key of S.![[Pasted image 20230914173657.png]]
Step 6: Mapping of Multivalued attributes.
- For each multivalued attribute A, create a new relation R
- This relation R will include an attribute corresponding to A, plus the primary key attribute K-as a foreign key in R-of the relation that represents the entity type of relationship type that has A as an attribute.
- The primary key of R is the combination of A and K. If the multivalued attribute is composite, we include its simple components.
![[Pasted image 20230914173632.png]]
**REFERENCE ARCS** - go FROM foreign key TO primary key
Step 7: Mapping of N-ary Relationship Types.
- For each n-ary relationship type R, where n>2, create a new relationship S to represent R.
- Include as foreign key attributes in S the primary keys of the relations that represent the participating entity types.
![[Pasted image 20230914173858.png]]
Step 8: Options for Mapping Specialization or Generalization
- 8A: Multiple relations-Superclass and subclasses
	- Create a relation L for C with attributes Attrs(L) = {k,a1,…an} and PK(L) = k
	- This option works for **any** specialization (total or partial, disjoint of overlapping)![[Pasted image 20230914174428.png]]
- 8B: Multiple relations-Subclass relations only
	- Create a relation Li for each subclass Si, 1 < i < m, with the attributes Attr(Li) = {attributes of Si} U {k,a1…,an} and PK(Li) = k
	- This option **only works for a specialization whose subclasses are total** (every entity in the superclass must belong to (at least) one of the subclasses)![[Pasted image 20230914174511.png]]
- 8C: Single relation with one type attribute
	- Create a single relation L with attributes Attrs(L) = {k,a1,…an} U {attributes of S1} U…U {attributes of Sm} U {t} and PK(L) = k.
	- The subclass has only one attribute different than the superclass (lots of NULL's **drawbacks**)
	- The attribute t is called a type (or discriminating) attribute that indicates the subclass to which each tuple belongs![[Pasted image 20230914174642.png]]
- 8D: Single relation with multiple type attributes
	- Create a single relation schema L with attributes Attrs(L) = {k,a1,…an} U {attributes of S1} U…U {attributes of Sm} U {t1, t2,…,tm} and PK(L) = k
	- Good for Overlapping (more expensive; easier to understand)
	- Each ti, 1 < I < m, is a Boolean type attribute indicating whether a tuple belongs to the subclass Si![[Pasted image 20230914174800.png]]
Step 9: Mapping of Union Types (Categories)
- For mapping a category whose defining superclass have different keys, it is customary to specify a new key attribute, called a surrogate key, when creating a relation to correspond to the category![[Pasted image 20230914175116.png]]
