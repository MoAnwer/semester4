---
tags:
  - database
  - SQL
---

In SQL, **Multiset** or **Bag** behavior refers to ==a data model where collections of rows 
(tables) can contain duplicates and do not have a defined inherent order==. 

### Core Characteristics

- **Duplicates Allowed:** Unlike a mathematical set, where each element must be unique, a bag allows multiple instances of the same row. The number of times a row appears is known as its **multiplicity**.
- **Unordered:** Like sets, the order of elements in a bag is irrelevant. `{A, A, B}` is considered the same bag as `{A, B, A}`. 

### Why SQL Uses Bag Semantics

Standard SQL defaults to bag semantics for efficiency and functional reasons:

- **Performance:** Duplicate elimination (e.g., using `DISTINCT`) is computationally expensive, often requiring a sort or hash operation.
- **Aggregates:** Preserving duplicates is necessary for correct calculations like `SUM()` or `AVG()`. For instance, calculating the average of five scores requires all five values, even if some are identical. 

### Multiset as a Data Type

Some modern SQL dialects (like Oracle and Informix) support a `MULTISET` collection data type. This allows you to store an unordered collection of values with duplicates within a single column, essentially creating a "table within a cell".


```sql
SELECT E.Fname, E.Lname, S.Fname, S.Lname
FROM EMPLOYEE AS E, EMOLPYEE AS S
WHERE E.Super_ssn = S.Ssn;

UPDATE EMPLOYEE
SET SALARY = SALARY * 1.1
WHERE DNO IN (
	SELECT DNUMBER
	FROM  DEPARTMENT
	WHERE DNAME = 'Research'
);
```