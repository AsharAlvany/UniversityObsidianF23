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
![[Pasted image 20231003175927.png]]
**NULL**
- Unknown value
- Unavailable or withhold
- Not applicable attribute
Truth table of NULL
- True OR (Anything) is TRUE
- False AND (Anything) is FLASE
- Unknown AND True is Unknown
- Unknown OR False is Unknown
**Join**
![[Pasted image 20231005173541.png]]
![[Pasted image 20231010175905.png]]
**EXIST** - used for nested queries or dependency queries for example
``` sql
SELECT Eid, Name FROM Professor AS P WHERE EXIST(
	SELECT RollNo FROM Student AS S WHERE S.Advisor = P.Eid AND S.Sex = 'F'
)
```
	This query will only select professors that have a female student assigned to them as an advisor
**UNIQUE** - used when building a table to mark an attribute as non-duplicate
**Aggregate Functions in SQL**
- **COUNT** - counts and returns the number of rows in a particular table based on the particular parameters passed
 ``` sql
SELECT COUNT(*) FROM Student AS S WHERE S.Sex = 'M' 
 ```
	 returns the number of males in the student table
- **SUM** - returns the aggregate of all the results
``` sql
SELECT SUM(P.Salary) FROM Professor as P
```
	returns the aggregate salaries of all the professors in the Professor table
- **MAX** - returns the maximum record of an attribute
- **MIN** - returns the minimum record of an attribute
- **AVG** - returns the average of a field
``` sql
SELECT AVG(P.Salary) FROM Professor as P
```
	returns the average salary of all the professors in the Professor table
- **GROUP BY** - when using an aggregate function, we need to use the GROUP BY clause
``` sql
SELECT P.College, COUNT(*) FROM Professor as P GROUP BY P.College ORDER BY count(*) DESC
```
	Groups all the colleges together and reports the total number of professors assigned to that college next to it sorted in descending order
```sql
SELECT P.College, P.Sex, COUNT(*) FROM Professor as P GROUP BY P.College, P.Sex ORDER BY count(*) DESC
```
	Reports all the combinations of sex and college and reports the number of professors that fall under that category sorted in descending order
- **HAVING** - used to put a floor or ceiling function