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

1. In modern DBMS packages, the design is ___________ with a client/server system architecture.
    
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

16. Physical data models represent information such as record formats and ___________.

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

28. The ___________ schema describes physical storage structures and access paths.

29. The ___________ schema describes the structure and constraints for the whole database for a community of users.

30. ___________ schemas describe various user views.

31. ___________ among schema levels are needed to transform requests and data.

32. Data extracted from the internal level is ___________ to match the user’s external view.

**Section 6: Data Independence**

33. ___________ is the capacity to change the schema at one level without changing the schema at the next higher level.

34. ___________ data independence is the capacity to change the internal schema without changing the conceptual schema.

35. ___________ data independence is the capacity to change the conceptual schema without changing external schemas.

36. When schema changes occur, only the ___________ between levels is changed.

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

47. The ___________ is concerned with rearrangement of operations and elimination of redundancies.

48. Access to the disk is controlled primarily by the ___________.

49. The ___________ module schedules disk read/write operations.

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
    

---

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