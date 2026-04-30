## 1. Core Definitions

The following terms form the basis of understanding how data is organized and managed:

- **Data**: Known facts that can be recorded and possess implicit meaning.
    
- **Information**: Data that has been processed into a meaningful form.
    
- **Database**: A logically coherent collection of related data with inherent meaning, designed and built for a specific purpose.
    
- **Mini-world (Universe of Discourse - UoD)**: A specific part of the real world represented in the database, such as university student records.
    
- **Database Management System (DBMS)**: Software used to facilitate the creation (defining, constructing, manipulating, and sharing) and maintenance of a computerized database.
    
- **Database System**: The combined entity of the DBMS software, the stored data, and the application programs.
    
- **Meta-data**: The description of the database (data types, structures, and constraints) stored in a catalog or dictionary.
    

---

## 2. DBMS Functions and Interactions

A DBMS performs several critical operations to manage data effectively:

- **Defining**: Specifying data types, structures, and constraints.
    
- **Constructing**: Storing the actual data on a physical medium.
    
- **Manipulating**: Querying to retrieve data, updating records, and generating reports.
    
- **Sharing**: Enabling multiple users or programs to access data simultaneously.
    
- **Protection**: Safeguarding against system malfunctions (crashes) and unauthorized or malicious access.
    
- **Maintenance**: Allowing the system to evolve as requirements change over time.
    

### Interaction Terms

- **Query**: A request to retrieve specific data from the database.
    
- **Transaction**: An interaction that involves both reading from and writing to the database.
    

---

## 3. Historical Evolution of Databases

The technology has transitioned through several distinct stages:

|**Era**|**System Type**|**Key Characteristics**|
|---|---|---|
|**1960s – 1980s**|**Legacy Systems**|Hierarchical and Network models. Suffered from intermixing physical storage with conceptual relationships and lacked program-data independence.|
|**1980s – Present**|**Relational (RDBMS)**|Separated physical storage from conceptual representation; based on mathematical foundations; used **SQL** as the standard language.|
|**Late 1980s – 1990s**|**Object-Oriented (OODBMS)**|Developed for complex data like CAD and engineering design. Led to Object-Relational (ORDBMS) hybrids.|
|**1990s – Present**|**Web & XML**|Focus on e-commerce and interchanging data using **XML**, PHP, and JavaScript for dynamic web pages.|
|**2000s – Present**|**NOSQL & Big Data**|Designed for massive volumes of user-generated data (e.g., social media). Provides fast retrieval and reliable storage for non-traditional data.|

---

## 4. Modern Extensions

DBMS capabilities now extend into specialized fields including:

- **Multimedia**: Managing image, audio, and video data.
    
- **Scientific**: Supporting complex data for genetics, physics, and astronomy.
    
- **Data Analysis**: Data Warehousing and Data Mining for future trend development.
    
- **Spatial**: Managing geographic and location-based services.

### Fill in the Gaps

**I. Basic Definitions**
1. The main aim of databases is to store **(1)** data onto computers permanently.
    
2. **(2)** are known facts that can be recorded and have an implicit meaning.
    
3. Data after it has been processed becomes **(3)**.
    
4. A **(4)** is a logically coherent collection of related data with some inherent meaning.
    
5. The **(5)** (also known as the Universe of Discourse) represents the part of the real world about which data is stored.
    
6. A **(6)** is a software system that facilitates the creation and maintenance of a computerized database.
    
7. The database **(7)** or dictionary contains the description of the data (meta-data).
    
8. **(8)** includes specifying data types, structures, and constraints for the data.
    
9. The term **(9)** refers to the DBMS software together with the data and application programs.
    

**II. DBMS Operations & Functions** 10. **(10)** involves storing the data on a storage medium. 11. **(11)** includes querying, updating, and generating reports. 12. A **(12)** is a request that causes some data to be retrieved. 13. A **(13)** is an interaction that causes some data to be both read and written. 14. **(14)** functions protect the system against hardware/software malfunctions and unauthorized access.

**III. Historical Overview** 15. Early "Legacy" databases in the 1960s used the **(15)** and **(16)** models. 16. Legacy systems lacked **(17)** independence, meaning conceptual relationships were intermixed with physical storage. 17. **(18)** products emerged in the 1980s and separated physical storage from conceptual representation. 18. **(19)** is the standard data model and language for relational databases. 19. **(20)** systems were introduced in the late 80s/early 90s for complex data like CAD. 20. **(21)** is a standard used for interchanging data among various types of databases and Web pages. 21. Modern systems that manage huge amounts of user-generated data from social media are called **(22)** or **(23)** storage systems.

---

### **Answer Key**

|**No.**|**Answer**|**No.**|**Answer**|
|---|---|---|---|
|**1**|Dynamic|**13**|Transaction|
|**2**|Data|**14**|Protection|
|**3**|Information|**15**|Hierarchical|
|**4**|Database|**16**|Network|
|**5**|Mini-world|**17**|Program-data|
|**6**|DBMS|**18**|Relational|
|**7**|Catalog|**19**|SQL|
|**8**|Defining|**20**|Object-Oriented (OODBMS)|
|**9**|Database System|**21**|XML|
|**10**|Constructing|**22**|NOSQL|
|**11**|Manipulating|**23**|Big Data|
|**12**|Query|||


---

## Lecture 02  - Database Concepts & Architecture

### Fill in the Gaps

**Section 1: Introduction and Evolution**

1. In modern DBMS packages, the design is "______" with a client/server system architecture.
    
2. ___________ architectures are comprised of thousands of computers that manage data stores.
    
3. Centralized mainframe computers were replaced by distributed workstations connected to various ___________ machines, such as Web, database, and file servers.
    
4. Current ___________ environments consist of thousands of large servers managing "big data."
    

**Section 2: Data Models and Abstraction**

5. One main characteristic of the database approach is to support ___________, which refers to the suppression of details of data organization.

6. A ___________ is a collection of concepts used to describe the structure of a database.

7. The structure of a database includes data types, ___________, and constraints.

8. Most data models include basic operations for specifying ___________ and ___________ on the database.

9. Concepts that specify the dynamic aspect or behavior of an application are called ___________.

**Section 3: Categories of Data Models**

10. ___________ data models provide concepts that are close to the way many users perceive data.

11. High-level models are also referred to as ___________ or object-based data models.

12. The ___________ model is a popular high-level conceptual data model.

13. ___________ data models fall between high and low levels and are used by traditional commercial DBMS.

14. Representational models are sometimes called ___________ models because they use record structures.

15. ___________ data models describe details of how data is stored in the computer.

16. ==Physical data models represent information such as record formats and ___________.==

17. ___________ data models combine the description of data with the data values (e.g., XML).

**Section 4: Schemas, Instances, and States**

18. The description of a database is called the ___________.

19. A ___________ is an illustrative display of a database schema.

20. The actual data stored in a database at a particular moment is called the ___________.

21. Database state is also referred to as a ___________ or a current set of instances.

22. An ___________ state occurs when the database is defined for the first time.

23. The ___________ state is when the database is first populated or loaded.

24. A state that satisfies the structure and constraints of the database is a ___________.

25. Schema is sometimes called ___________, while the state is called the ___________.

26. Changes to the schema as application requirements change is known as ___________.

**Section 5: Three-Schema Architecture**

27. The goal of the Three-Schema Architecture is to separate ___________ from the physical database.

28. The -_-_-_-_-_-_-_-_--_=_----_ schema describes physical storage structures and access paths.

29. The ___________ schema describes the structure and constraints for the whole database for a community of users.

30. ___________ schemas describe various user views.

31. ___________ among schema levels are needed to transform requests and data.

32. ==Data extracted from the internal level is ___________ to match the user’s external view.==

**Section 6: Data Independence**

33. ___________ is the capacity to change the schema at one level without changing the schema at the next higher level.

34. ___________ data independence is the capacity to change the internal schema without changing the conceptual schema.

35. ___________ data independence is the capacity to change the conceptual schema without changing external schemas.

36. ==When schema changes occur, only the ___________ between levels is changed.==

**Section 7: DBMS Languages**

37. The ___________ (DDL) is used by the DBA and designers to specify conceptual and internal schemas.

38. ___________ (SDL) is used to specify the internal schema.

39. ___________ (VDL) is used to specify external schemas.

40. The ___________ (DML) is used by users to retrieve, insert, delete, or modify data.

41. ___________ is a comprehensive language that includes DDL, VDL, and DML.

42. High-level DMLs are called ___________ because they specify _what_ data to retrieve rather than _how_.

43. High-level DMLs are also known as ___________ DMLs.

44. Low-level DMLs are called ___________ because they process each record separately.

**Section 8: DBMS Components and Modules**

45. The ___________ processes schema definitions and stores them in the DBMS catalog.

46. Casual users interact with the database using an ___________ interface.

47. ==The ___________ is concerned with rearrangement of operations and elimination of redundancies.==

48. Access to the disk is controlled primarily by the ___________.

49. ==The (Buffer management) module schedules disk read/write operations.==

50. ___________ and ___________ subsystems are integrated into the runtime processor for transaction management.

---

### Answer Key

1. Modular
    
2. Distributed
    
3. Server
    
4. Cloud computing
    
5. Data abstraction
    
6. Data Model
    
7. Relationships
    
8. Retrievals; updates
    
9. User-defined operations
    
10. Conceptual
    
11. Entity-based
    
12. Entity-Relationship
    
13. Implementation
    
14. Record-based
    
15. Physical
    
16. Access paths
    
17. Self-Describing
    
18. Database Schema
    
19. Schema Diagram
    
20. Database State
    
21. Snapshot
    
22. Empty
    
23. Initial
    
24. Valid State
    
25. Intension; extension
    
26. Schema evolution
    
27. User applications
    
28. Internal
    
29. Conceptual
    
30. External
    
31. Mappings
    
32. Reformatted
    
33. Data Independence
    
34. Physical
    
35. Logical
    
36. Mapping
    
37. Data Definition Language
    
38. Storage Definition Language
    
39. View Definition Language
    
40. Data Manipulation Language
    
41. SQL
    
42. Declarative
    
43. Set-at-a-time (or set-oriented)
    
44. Record-at-a-time (or procedural)
    
45. DDL compiler
    
46. Interactive query
    
47. Query optimizer
    
48. Operating System (OS)
    
49. Buffer management
    
50. Concurrency control; backup and recovery


---


## lecture 04 

Here is a 50-question comprehensive "Fill the Gaps" exercise based on the provided slides from "Fundamentals of Database Systems" (7th Edition) by Elmasri and Navathe.

### Chapter 6: Basic SQL - Knowledge Check

1. The origin of SQL is relational predicate calculus called **________** calculus.
    
2. The term SQL originally comes from the word "**________**," which was used in the paper "SEQUEL TO SQUARE".
    
3. In the relational model, the SQL term "Table" corresponds to **________**.
    
4. The main SQL command for data definition is the **________** statement.
    
5. SQL-92 is commonly referred to as **________**.
    
6. The current standard, SQL-3, started with **________** but is not fully implemented in any RDBMS.
    
7. An SQL **________** is identified by a name and includes an authorization identifier and descriptors for each element.
    
8. Every statement in SQL must end with a **________**.
    
9. A **________** is a named collection of schemas in an SQL environment.
    
10. **________** tables are those where relations and tuples are actually created and stored as files by the DBMS.
    
11. Virtual relations created through the `CREATE VIEW` statement are called **________**.
    
12. The numeric data type for floating-point (real) numbers can be FLOAT, REAL, or **________**.
    
13. **________** is the character-string data type used for fixed-length strings.
    
14. The DATE data type components are YEAR, MONTH, and DAY in the form **________**.
    
15. The **________** data type includes both DATE and TIME fields plus decimal fractions of seconds.
    
16. The **________** data type specifies a relative value used to increment or decrement absolute date/time values.
    
17. A **________** makes it easier to change the data type for an attribute used across numerous relations and improves schema readability.
    
18. User Defined Types (UDTs) are supported for object-oriented applications using the **________** command.
    
19. The **________** constraint ensures that a primary key value cannot be duplicated.
    
20. The Entity Integrity Constraint states that a **________** value cannot be null.
    
21. In a **________** integrity constraint, the foreign key must match a primary key value or be null.
    
22. To specify a default value for an attribute, use the **________** clause.
    
23. If an attribute cannot be null, the **________** constraint is applied.
    
24. The **________** clause allows for more complex attribute restrictions, such as `Dnumber > 0 AND Dnumber < 21`.
    
25. Alternate (secondary) keys are specified in SQL using the **________** clause.
    
26. Referential triggered actions for `FOREIGN KEY` include SET NULL, CASCADE, and **________**.
    
27. The **________** option is specifically suitable for "relationship" relations.
    
28. Using the keyword **________** to name a constraint is useful for later altering.
    
29. The basic statement for retrieving information from a database is the **________** statement.
    
30. SQL allows "multiset" or "**________**" behavior, meaning a table can have duplicate tuples.
    
31. In the SELECT-FROM-WHERE structure, the **________** list contains attributes to be retrieved.
    
32. The **________** list contains the relation names required to process a query.
    
33. The **________** part of a query is a Boolean expression that identifies the tuples to be retrieved.
    
34. The logical comparison operator for "not equal to" is **________**.
    
35. When attributes in different relations have the same name, you must **________** the name with the relation name.
    
36. **________** (or tuple variables) are alternative relation names used to refer to a relation more than once in a query.
    
37. A missing `WHERE` clause results in a **________**, where all possible tuple combinations are produced.
    
38. To retrieve all attribute values of selected tuples, specify an **________** (*).
    
39. To eliminate duplicate tuples from a query result, use the keyword **________**.
    
40. Type **________** is required for set operations like UNION, EXCEPT, and INTERSECT to be valid.
    
41. The **________** operator is used for string pattern matching.
    
42. In string matching, the **________** character replaces an arbitrary number of zero or more characters.
    
43. The **________** character replaces a single character in a string pattern.
    
44. The **________** clause is used to sort query results.
    
45. To sort results in descending order, use the keyword **________**.
    
46. The three commands used to modify a database are INSERT, **________**, and UPDATE.
    
47. When using **________**, attribute values should be listed in the same order as defined in `CREATE TABLE`.
    
48. The variation of INSERT used to load a new table with data from a query result is for **________** loading.
    
49. A **________** statement without a `WHERE` clause will delete all tuples, making the table empty.
    
50. In an `UPDATE` statement, the **________** clause specifies the attributes to be modified and their new values.

### Answer Key

1. Tuple
    
2. SEQUEL
    
3. Relation
    
4. CREATE
    
5. SQL-2
    
6. SQL-1999
    
7. Schema
    
8. Semicolon
    
9. Catalog
    
10. Base
    
11. Views
    
12. DOUBLE PRECISION
    
13. CHAR(n)
    
14. YYYY-MM-DD
    
15. Timestamp
    
16. INTERVAL
    
17. Domain
    
18. CREATE TYPE
    
19. Key
    
20. Primary key
    
21. Referential
    
22. DEFAULT
    
23. NOT NULL
    
24. CHECK
    
25. UNIQUE
    
26. SET DEFAULT
    
27. CASCADE
    
28. CONSTRAINT
    
29. SELECT
    
30. Bag
    
31. Attribute
    
32. Table
    
33. Condition
    
34. <>
    
35. Qualify
    
36. Aliases
    
37. Cross product
    
38. Asterisk
    
39. DISTINCT
    
40. Compatibility
    
41. LIKE
    
42. Percent (%)
    
43. Underscore (_)
    
44. ORDER BY
    
45. DESC
    
46. DELETE
    
47. INSERT
    
48. Bulk
    
49. DELETE
    
50. SET

---

## Chapter 8: The Relational Algebra

This exercise is based on  It covers unary operations, set theory operations, and binary operations like JOIN and DIVISION as presented in the slides.

### Part 1: Fill the Gaps

1. Relational algebra is considered a **________** language because it specifies the steps to take to arrive at a result.
    
2. The **________** operation is used to select a subset of tuples from a relation that satisfy a specific condition.
    
3. The selection condition is a **________** expression specified on the attributes of the relation.
    
4. The **________** operation selects certain columns from the table and discards the rest.
    
5. Unlike the SELECT operation, the PROJECT operation eliminates **________** tuples.
    
6. The Greek letter **________** ($\sigma$) is used to denote the SELECT operation.
    
7. The Greek letter **________** ($\pi$) is used to denote the PROJECT operation.
    
8. To rename the attributes of a relation or the relation itself, the **________** ($\rho$) operation is used.
    
9. In a sequence of operations, **________** variables can be used to hold intermediate results.
    
10. The **________** of a SELECT operation is the number of tuples in the resulting relation divided by the total number of tuples in the original relation.
    
11. Operations from set theory require the participating relations to be **________** compatible.
    
12. The **________** of two relations $R$ and $S$ includes all tuples that are in $R$ or in $S$ or in both.
    
13. The **________** of $R$ and $S$ includes all tuples that are in both $R$ and $S$.
    
14. The SET DIFFERENCE operation (denoted by **________**) includes tuples that are in $R$ but not in $S$.
    
15. The **________** product (or CROSS PRODUCT) of $R$ and $S$ creates a relation with $n+m$ attributes.
    
16. If $R$ has $n_R$ tuples and $S$ has $n_S$ tuples, their Cartesian Product will have **________** tuples.
    
17. The **________** operation is a sequence of a Cartesian Product followed by a SELECT operation.
    
18. A **________** is a join where the condition involves only the equality (=) operator.
    
19. A **________** join is a version of an equijoin that eliminates the redundant second join attribute.
    
20. The **________** operation ($R \div S$) is used for queries that involve the phrase "for all" or "every."
    
21. Aggregate functions are often denoted in relational algebra using the script letter **________** ($\mathfrak{F}$).
    
22. The **________** operation allows for the calculation of functions like SUM, AVERAGE, and COUNT.
    
23. An **________** join keeps all tuples in the result, even if they do not have a matching tuple in the other relation.
    
24. A **________** join keeps every tuple in the first (left) relation, padding with NULLs if no match exists in the second.
    
25. ==The **________** operation is used to combine two relations that are only partially type-compatible.==
    

### Part 2: Multiple Choice Questions (MCQs)

26. Which operation is considered unary?
    
    a) UNION
    
    b) JOIN
    
    c) PROJECT
    
    d) INTERSECTION
    
27. The degree of a relation resulting from a PROJECT operation is:
    
    a) Equal to the number of tuples
    
    b) Equal to the number of attributes in the project list
    
    c) Always 1
    
    d) Equal to the degree of the original relation
    
28. If relation $R$ has 5 tuples and relation $S$ has 10 tuples, how many tuples are in $R \times S$?
    
    a) 15
    
    b) 5
    
    c) 50
    
    d) 2
    
29. Union, Intersection, and Set Difference are:
    
    a) Unary operations
    
    b) Binary operations
    
    c) Ternary operations
    
    d) Logical operations
    
30. Which join condition is allowed in a THETA JOIN but NOT in an EQUIJOIN?
    
    a) $A = B$
    
    b) $A < B$
    
    c) $A \neq B$
    
    d) Both b and c
    
31. The result of $R \cap S$ is the same as:
    
    a) $R - (R - S)$
    
    b) $S - (S - R)$
    
    c) $(R \cup S) - (R - S) - (S - R)$
    
    d) All of the above
    
32. The "complete" set of relational algebra operations includes:
    
    a) SELECT, PROJECT, UNION, SET DIFFERENCE, CARTESIAN PRODUCT
    
    b) SELECT, PROJECT, JOIN, DIVISION
    
    c) UNION, INTERSECTION, JOIN
    
    d) RENAME, JOIN, DIVISION
    
33. In the expression $\pi_{LNAME, FNAME, SALARY}(\sigma_{DNO=5}(EMPLOYEE))$, which operation is performed first?
    
    a) Project
    
    b) Select
    
    c) Rename
    
    d) It happens simultaneously
    
34. A relation where every tuple is unique is a:
    
    a) Multiset
    
    b) Set
    
    c) Bag
    
    d) List
    
35. The operation $R \bowtie S$ where no condition is specified usually implies:
    
    a) A Cartesian Product
    
    b) A Natural Join
    
    c) A Theta Join
    
    d) A Division
    
36. Which operation is used to find the average salary of employees per department?
    
    a) SELECT
    
    b) AGGREGATE FUNCTION ($\mathfrak{F}$)
    
    c) PROJECT
    
    d) JOIN
    
37. If you want to find employees who work on ALL projects, you use:
    
    a) JOIN
    
    b) UNION
    
    c) DIVISION
    
    d) INTERSECTION
    
38. Type compatibility (or Union compatibility) requires that:
    
    a) Both relations have the same number of attributes
    
    b) Corresponding attributes have the same domain
    
    c) Both a and b
    
    d) The relations have the same name
    
39. The result of a LEFT OUTER JOIN between $R$ and $S$ contains:
    
    a) Only matching tuples
    
    b) All tuples from $R$
    
    c) All tuples from $S$
    
    d) All tuples from both $R$ and $S$
    
40. Which operation effectively represents the "AND" logical operator in set theory?
    
    a) UNION
    
    b) INTERSECTION
    
    c) SET DIFFERENCE
    
    d) CARTESIAN PRODUCT
    
41. Which of the following is NOT an aggregate function?
    
    a) MAX
    
    b) COUNT
    
    c) SELECT
    
    d) SUM
    
42. Recursive closure operations (like finding all subordinates of a manager at all levels) are:
    
    a) Standard in basic relational algebra
    
    b) Not possible with basic relational algebra
    
    c) Performed by the PROJECT operation
    
    d) Performed by the UNION operation
    
43. An OUTER UNION is specifically designed to handle:
    
    a) Relations with identical schemas
    
    b) Partially compatible relations
    
    c) Relations with no common attributes
    
    d) Joining more than three tables
    
44. The number of attributes in the result of $R(A, B, C) \bowtie_{C=D} S(D, E)$ is:
    
    a) 3
    
    b) 4
    
    c) 5
    
    d) 2
    
45. In a NATURAL JOIN, if the two relations have no common attribute names, the result is:
    
    a) An empty relation
    
    ==b) A Cartesian Product==
    
    e) An error
    
    d) A Theta Join
    
46. Which operation is commutative ($R \cup S = S \cup R$)?
    
    a) UNION
    
    b) INTERSECTION
    
    c) CARTESIAN PRODUCT
    
    d) All of the above
    
47. Set Difference ($R - S$) is:
    
    a) Commutative
    
    b) Not commutative
    
    c) Associative
    
    d) Always empty
    
48. The SELECT operation is:
    
    a) Commutative
    
    b) Not commutative
    
    c) Only works on primary keys
    
    d) Used to combine tables
    
49. What happens to the degree of a relation during a PROJECT operation?
    
    a) It increases
    
    b) It decreases or stays the same
    
    c) It always stays the same
    
    d) It doubles
    
50. The RENAME operation is used primarily to:
    
    a) Delete data
    
    b) Change attribute names for consistency in joins or intermediate results
    
    c) Sort the table
    
    d) Define primary keys
    

---

### Answer Key

1. Procedural
    
2. SELECT
    
3. Boolean
    
4. PROJECT
    
5. Duplicate
    
6. Sigma
    
7. Pi
    
8. RENAME
    
9. Intermediate (or Assignment)
    
10. Selectivity
    
11. Union (or Type)
    
12. UNION
    
13. INTERSECTION
    
14. Minus (-)
    
15. CARTESIAN
    
16. $n_R \times n_S$
    
17. JOIN
    
18. EQUIJOIN
    
19. NATURAL
    
20. DIVISION
    
21. F
    
22. AGGREGATE (or Grouping)
    
23. OUTER
    
24. LEFT OUTER
    
25. OUTER UNION
    
26. c
    
27. b
    
28. c
    
29. b
    
30. d
    
31. d
    
32. a
    
33. b
    
34. b
    
35. b
    
36. b
    
37. c
    
38. c
    
39. b
    
40. b
    
41. c
    
42. b
    
43. b
    
44. c
    
45. b
    
46. d
    
47. b
    
48. a
    
49. b
    
50. b
----

## Lecture 07 

### Chapter 7: Advanced SQL - Knowledge Check

1. SQL uses a **________** logic for comparisons involving NULL, consisting of TRUE, FALSE, and UNKNOWN.
    
2. An individual NULL value is considered to be **________** from every other NULL value.
    
3. The comparison `Address IS NULL` returns TRUE if the address attribute is **________**.
    
4. In SQL, **________** queries are complete SELECT-FROM-WHERE blocks within the WHERE clause of another query.
    
5. The comparison operator **________** checks whether a value is one of the elements in a set or the result of a subquery.
    
6. A **________** subquery is one where a value from the outer query is used in the inner subquery.
    
7. The **________** function is used to check whether the result of a correlated nested query is empty or not.
    
8. To find if a query result contains at least one record, you use the **________** condition.
    
9. SQL’s **________** operator is used to compare a single value with all values in a set or list.
    
10. The **________** operator returns TRUE if a value is greater than at least one value in a set.
    
11. To ensure there are no duplicate tuples in a nested query, the **________** condition can be used.
    
12. The keyword **________** in the FROM clause allows for different types of table joins, such as INNER or OUTER.
    
13. A **________** JOIN keeps all tuples from the first table and fills the second table's attributes with NULLs if no match exists.
    
14. A **________** JOIN keeps all tuples from both tables, padding with NULLs where matches are missing.
    
15. Aggregate functions include COUNT, SUM, MAX, MIN, and **________**.
    
16. The **________** clause is used to partition a relation into subsets based on attribute values for aggregate calculations.
    
17. To provide a condition on a summary (aggregate) value, the **________** clause must be used.
    
18. The **________** function can be used with a single attribute to count the number of non-null values in that column.
    
19. If you want to count every row in a table, including those with NULLs, use **________**.
    
20. In a SELECT statement with GROUP BY, the attributes in the SELECT list must also appear in the **________** clause (unless they are aggregate functions).
    
21. The **________** keyword is used to name a subquery in the FROM clause, creating a "table expression."
    
22. Recursive queries in SQL often use the **________** clause to define a temporary result set.
    
23. The **________** statement is used to create a virtual table that does not physically exist in the database.
    
24. A view is considered **________** if it is computed each time it is referenced.
    
25. A **________** view is physically stored for efficiency but must be updated when the base tables change.
    
26. To remove a view from the database, use the **________** command.
    
27. A view is generally **________** only if it is defined on a single base table without aggregate functions.
    
28. The **________** command is used to add or drop columns in an existing table.
    
29. To remove an entire table and all its data from the schema, use **________**.
    
30. The **________** option in a DROP statement removes all dependent objects like views and constraints.
    
31. The **________** option in a DROP statement prevents the drop if any other objects depend on that table.
    
32. **________** are used to specify "Active" rules that the DBMS should automatically execute when certain events occur.
    
33. A trigger typically follows the **________** model (Event-Condition-Action).
    
34. In a trigger, the **________** defines when the rule should be triggered (e.g., BEFORE/AFTER INSERT).
    
35. The **________** in a trigger is a Boolean expression that determines if the action should run.
    
36. The **________** in a trigger is the procedure or SQL code to be executed.
    
37. **________** level triggers execute once for each row affected by an SQL statement.
    
38. **________** level triggers execute once for the entire SQL statement, regardless of how many rows are affected.
    
39. The keyword **________** is used in triggers to refer to the data as it was before the update.
    
40. The keyword **________** is used in triggers to refer to the data after the update.
    
41. **________** are declarative constraints that must hold true for all states of the database (e.g., `CHECK` at a schema level).
    
42. To modify a column's default value, use the `ALTER TABLE` command with the **________** clause.
    
43. The syntax `NATURAL JOIN` automatically joins tables based on columns with **________**.
    
44. If a subquery is used in the SELECT clause, it is often called a **________** subquery.
    
45. In the three-valued logic, `TRUE AND UNKNOWN` results in **________**.
    
46. In the three-valued logic, `FALSE OR UNKNOWN` results in **________**.
    
47. The keyword **________** can be used to provide descriptive names to results of aggregate functions in the SELECT list.
    
48. A **________** is an alternative name for a table or view used to shorten queries.
    
49. The **________** clause in a trigger specifies that it is a row-level trigger.
    
50. SQL triggers were officially incorporated into the **________** standard.
    


### Answer Key

1. Three-valued
    
2. Different
    
3. Null
    
4. Nested
    
5. IN
    
6. Correlated
    
7. EXISTS
    
8. EXISTS
    
9. ALL
    
10. ANY (or SOME)
    
11. UNIQUE
    
12. JOIN
    
13. LEFT OUTER
    
14. FULL OUTER
    
15. AVG
    
16. GROUP BY
    
17. HAVING
    
18. COUNT
    
19. COUNT(*)
    
20. GROUP BY
    
21. AS
    
22. WITH
    
23. CREATE VIEW
    
24. Virtual
    
25. Materialized
    
26. DROP VIEW
    
27. Updatable
    
28. ALTER TABLE
    
29. DROP TABLE
    
30. CASCADE
    
31. RESTRICT
    
32. Triggers
    
33. ECA
    
34. Event
    
35. Condition
    
36. Action
    
37. Row
    
38. Statement
    
39. OLD
    
40. NEW
    
41. Assertions
    
42. SET DEFAULT
    
43. Same names
    
44. Scalar
    
45. UNKNOWN
    
46. UNKNOWN
    
47. AS
    
48. Alias (or Synonym)
    
49. FOR EACH ROW
    
50. SQL-99 (or SQL-3)