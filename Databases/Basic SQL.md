Data Types:
![[Pasted image 20230928173320.png]]
![[Pasted image 20230928173354.png]]
Terminology
- **Schema** is the relational model. One database on the BDMS
- **Catalog** is when a DBMS may have multiple schema. The set of multiple databases is referred to as the catalog
**Altering** a table the "alter" keyword is used to
- add attributes
```SQL
alter table MEDDLING_KIDS add Hair_Color VarChar(16);
```
- and drop attributes
```SQL
alter table MEDDLING_KIDS drop WearsAscot;
```
- **Primary Key**
	- Specifies one or more attributes that make up the primary key of a relationship
- **Unique**
	- Specifies alternate keys called CANDIDATE keys in the relational model
- Foreign Key
	- Default operation: reject update on violation
	- Attach referential triffered action clause
		- Options include SET NULL, CASCADE, and SET DEFAULT
- **Constraint**
	- Name a constraint
	- Useful for later altering
Types of command structure
- SELECT-FROM-WHERE
```SQL
SELECT Pnumber, Dnum, Lname, Address, Bdate FROM PROJECT, DEPARTMENT, EMPLOYEE WHERE Dnum=Dnumber AND Mgr_ssn=Ssn AND Plocation='Stafford';
```
- SELECT-FROM-AS-WHERE
	- To rename data-tables
If the where keyword is not used then the resulting effect is the CROSS PROUCT