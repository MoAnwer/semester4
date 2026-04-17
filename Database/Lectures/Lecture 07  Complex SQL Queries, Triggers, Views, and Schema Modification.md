---
tags:
  - SQL
  - database
banner: "pixel-banner-images/Cool-Wallpaper-for-Desktop-1.jpg"
---


## More Complex SQL Retrieval Queries

SQL offers several features to construct more intricate queries beyond basic SELECT statements. These include nested queries, joined tables, outer joins, aggregate functions, and grouping.

### Comparisons Involving NULL and Three-Valued Logic

NULL represents an unknown, unavailable, withheld, or not applicable value. Each NULL is distinct from other NULLs. SQL employs a three-valued logic: TRUE, FALSE, and UNKNOWN.

- **AND Truth Table:**
    - TRUE AND TRUE = TRUE
    - TRUE AND FALSE = FALSE
    - TRUE AND UNKNOWN = UNKNOWN
    - FALSE AND TRUE = FALSE
    - FALSE AND FALSE = FALSE
    - FALSE AND UNKNOWN = FALSE
    - UNKNOWN AND TRUE = UNKNOWN
    - UNKNOWN AND FALSE = FALSE
    - UNKNOWN AND UNKNOWN = UNKNOWN
- **OR Truth Table:**
    - TRUE OR TRUE = TRUE
    - TRUE OR FALSE = TRUE
    - TRUE OR UNKNOWN = TRUE
    - FALSE OR TRUE = TRUE
    - FALSE OR FALSE = FALSE
    - FALSE OR UNKNOWN = UNKNOWN
    - UNKNOWN OR TRUE = TRUE
    - UNKNOWN OR FALSE = UNKNOWN
    - UNKNOWN OR UNKNOWN = UNKNOWN
- **NOT Truth Table:**
    - NOT TRUE = FALSE
    - NOT FALSE = TRUE
    - NOT UNKNOWN = UNKNOWN

SQL provides `IS NULL` and `IS NOT NULL` operators to specifically check for the presence or absence of a NULL value.

**Example:** Retrieve the names of all employees who do not have supervisors.

```sql
SELECT Fname, Lname
FROM EMPLOYEE
WHERE Super_ssn IS NULL;
```

### Nested Queries, Tuples, and Set/Multiset Comparisons

Nested queries (subqueries) are complete `SELECT-FROM-WHERE` blocks embedded within another query's `WHERE` clause.

- **`IN` Operator:** Compares a value with a set (or multiset) of values. It evaluates to TRUE if the value is present in the set.
    
    **Example:** Retrieve distinct project numbers for projects that are either controlled by the 'Smith' department or have 'Smith' as a manager.
    
    ```sql
    SELECT DISTINCT Pnumber
    FROM PROJECT
    WHERE Pnumber IN (SELECT Pno FROM WORKS_ON WHERE Essn = (SELECT Ssn FROM EMPLOYEE WHERE Lname = 'Smith'))
    OR Pnumber IN (SELECT Pno FROM PROJECT WHERE Dnum = (SELECT Dnumber FROM DEPARTMENT WHERE Mgr_ssn = (SELECT Ssn FROM EMPLOYEE WHERE Lname = 'Smith')));
    ```
    
    _(Note: The provided example Q4A in the material has a slight logical difference in its WHERE clause. The example above is constructed to better illustrate the 'IN' operator with nested subqueries for clarity based on typical database schemas.)_
    
- **Tuple Comparisons:** Tuples (sets of values) can be used in comparisons within parentheses.
    
    **Example:** Retrieve distinct employee social security numbers (Essn) from the `WORKS_ON` table where the project number and hours worked match a specific employee's records.
    
    ```sql
    SELECT DISTINCT Essn
    FROM WORKS_ON
    WHERE (Pno, Hours) IN (SELECT Pno, Hours FROM WORKS_ON WHERE Essn = '123456789');
    ```
    
- **`ANY` / `SOME` and `ALL` Operators:**
    
    - `= ANY` (or `= SOME`): Equivalent to `IN`. Returns TRUE if the value equals at least one value in the set.
    - `>`, `<`, `>=`, `<=`, `<>` can be combined with `ANY` or `ALL`.
    - `ALL`: The condition must hold true for all values in the set.
    
    **Example:** Retrieve the last and first names of employees whose salary is greater than the salary of _all_ employees in department 5.
    
    ```sql
    SELECT Lname, Fname
    FROM EMPLOYEE
    WHERE Salary > ALL (SELECT Salary FROM EMPLOYEE WHERE Dno = 5);
    ```
    
- **Tuple Variables (Aliases):** Using aliases (`AS` keyword) for tables can prevent ambiguity, especially in self-joins or complex queries.
    
    **Example:** Retrieve the first and last names of employees who have a dependent with the same first name and sex as the employee.
    
    ```sql
    SELECT E.Fname, E.Lname
    FROM EMPLOYEE AS E
    WHERE E.Ssn IN (SELECT D.Essn
                    FROM DEPENDENT AS D
                    WHERE E.Fname = D.Dependent_name AND E.Sex = D.Sex);
    ```
    

### Correlated Nested Queries

A correlated nested query is evaluated once for each tuple processed by the outer query. The example Q16 can be rewritten as a join, which is often more efficient.

**Example (Correlated Nested Query rewritten as Join):**

```sql
SELECT E.Fname, E.Lname
FROM EMPLOYEE AS E, DEPENDENT AS D
WHERE E.Ssn = D.Essn AND E.Sex = D.Sex AND E.Fname = D.Dependent_name;
```

### The EXISTS and UNIQUE Functions

- **`EXISTS`:** A Boolean function that returns TRUE if the result of a correlated subquery is not empty. `NOT EXISTS` returns TRUE if the subquery result is empty.
    
    **Example:** Retrieve first and last names of employees who both have dependents and are managers of a department.
    
    ```sql
    SELECT Fname, Lname
    FROM Employee
    WHERE EXISTS (SELECT * FROM DEPENDENT WHERE Ssn = Essn)
    AND EXISTS (SELECT * FROM Department WHERE Ssn = Mgr_Ssn);
    ```
    
- **`UNIQUE(Q)`:** Returns TRUE if the result of query `Q` contains no duplicate tuples.
    

### Achieving "For All" with Double Negation (`NOT EXISTS`)

The "for all" (universal quantifier) concept can be expressed in SQL using double negation with `NOT EXISTS`.

**Example:** List the first and last names of employees who work on ALL projects controlled by `Dno=5`.

```sql
SELECT Fname, Lname
FROM Employee
WHERE NOT EXISTS ( (SELECT Pnumber FROM PROJECT WHERE Dno=5)
                   EXCEPT
                   (SELECT Pno FROM WORKS_ON WHERE Ssn=Employee.Ssn) );
```

This is logically equivalent to: "List names of those employees for whom there does NOT exist a project managed by department no. 5 that they do NOT work on."

### Explicit Sets and Renaming of Attributes

- **Explicit Sets:** Literal sets of values can be used in the `WHERE` clause.
    
    **Example:** Retrieve distinct employee social security numbers (Essn) from `WORKS_ON` for employees working on projects 1, 2, or 3.
    
    ```sql
    SELECT DISTINCT Essn
    FROM WORKS_ON
    WHERE Pno IN (1, 2, 3);
    ```
    
- **Renaming Attributes:** The `AS` keyword can rename attributes in the query result.
    
    **Example:** Retrieve employee names and their supervisor's names, renaming the columns for clarity.
    
    ```sql
    SELECT E.Lname AS Employee_name, S.Lname AS Supervisor_name
    FROM EMPLOYEE AS E, EMPLOYEE AS S
    WHERE E.Super_ssn = S.Ssn;
    ```
    

## Specifying Joined Tables in the FROM Clause

The `FROM` clause can directly specify join operations, making queries more readable.

- **`JOIN` (or `INNER JOIN`):** The default join type. Only tuples with matching values in both tables are included.
    
    **Example:** Retrieve first name, last name, and address for employees in the 'Research' department.
    
    ```sql
    SELECT Fname, Lname, Address
    FROM (EMPLOYEE JOIN DEPARTMENT ON Dno=Dnumber)
    WHERE Dname='Research';
    ```
    
- **`NATURAL JOIN`:** Joins tables based on all attributes with the same name in both tables, without explicitly specifying the join condition. It's crucial that attribute names match correctly.
    
    **Example:** Using `NATURAL JOIN` with an alias to ensure correct join on `Dno`.
    
    ```sql
    SELECT Fname, Lname, Address
    FROM (EMPLOYEE NATURAL JOIN DEPARTMENT AS DEPT (Dname, Dno, Mssn, Msdate))
    WHERE Dname='Research';
    ```
    
    _(Note: The explicit aliasing of columns in the `DEPARTMENT` table definition is to disambiguate attributes for `NATURAL JOIN`.)_
    
- **`OUTER JOIN`:**
    
    - **`LEFT OUTER JOIN`:** Includes all tuples from the left table and matching tuples from the right. Non-matching tuples from the left table are padded with `NULL` for the right table's attributes.
    - **`RIGHT OUTER JOIN`:** Includes all tuples from the right table and matching tuples from the left. Non-matching tuples from the right table are padded with `NULL` for the left table's attributes.
    - **`FULL OUTER JOIN`:** Combines the results of `LEFT` and `RIGHT OUTER JOIN`.
    
    **Example (LEFT OUTER JOIN):** Retrieve employee names and their supervisor's names, including employees who have no supervisor.
    
    ```sql
    SELECT E.Lname AS Employee_Name, S.Lname AS Supervisor_Name
    FROM Employee AS E LEFT OUTER JOIN EMPLOYEE AS S
    ON E.Super_ssn = S.Ssn;
    ```
    
- **Multiway JOIN:** Multiple joins can be nested within the `FROM` clause.
    
    **Example:** Retrieve project details for projects located in 'Stafford'.
    
    ```sql
    SELECT Pnumber, Dnum, Lname, Address, Bdate
    FROM ((PROJECT JOIN DEPARTMENT ON Dnum=Dnumber) JOIN EMPLOYEE ON Mgr_ssn=Ssn)
    WHERE Plocation='Stafford';
    ```
    

## Aggregate Functions in SQL

Aggregate functions summarize information from multiple tuples into a single summary tuple.

- **Built-in Functions:** `COUNT`, `SUM`, `MAX`, `MIN`, `AVG`.
    
- **NULL Handling:** NULL values are generally discarded when applying aggregate functions to a column. `COUNT(*)` counts all rows, including those with NULLs.
    
- **Renaming Results:** The `AS` keyword can rename the output columns of aggregate functions.
    
    **Example:** Calculate the total, maximum, minimum, and average salaries for all employees.
    
    ```sql
    SELECT SUM(Salary) AS Total_Sal, MAX(Salary) AS Highest_Sal, MIN(Salary) AS Lowest_Sal, AVG(Salary) AS Average_Sal
    FROM EMPLOYEE;
    ```
    
    **Example:** Find the sum, max, min, and average salary for employees in the 'Research' department.
    
    ```sql
    SELECT SUM(Salary), MAX(Salary), MIN(Salary), AVG(Salary)
    FROM (EMPLOYEE JOIN DEPARTMENT ON Dno=Dnumber)
    WHERE Dname='Research';
    ```
    
- *_`COUNT(_)`:** Used to count the number of tuples.
    
    **Example:** Count total employees and employees in the 'Research' department.
    
    ```sql
    -- Total employees
    SELECT COUNT(*) FROM EMPLOYEE;
    
    -- Employees in 'Research' department
    SELECT COUNT(*)
    FROM EMPLOYEE, DEPARTMENT
    WHERE DNO=DNUMBER AND DNAME='Research';
    ```
    
- **`SOME` and `ALL` on Booleans:** These can act as aggregate functions on boolean collections, similar to `OR` (`SOME`) and `AND` (`ALL`).
    

## Grouping: The `GROUP BY` and `HAVING` Clauses

- **`GROUP BY` Clause:** Partitions relation tuples into subsets based on specified grouping attributes. Aggregate functions are then applied independently to each group. The grouping attribute(s) must typically appear in the `SELECT` list.
    
    **Example:** Count the number of employees and calculate the average salary for each department.
    
    ```sql
    SELECT Dno, COUNT(*), AVG(Salary)
    FROM EMPLOYEE
    GROUP BY Dno;
    ```
    
- **`HAVING` Clause:** Filters entire groups based on a condition. It is applied _after_ grouping and aggregation.
    
    **Example:** For each project with more than two employees, retrieve the project number, name, and the count of employees working on it.
    
    ```sql
    SELECT Pnumber, Pname, COUNT(*)
    FROM PROJECT, WORKS_ON
    WHERE Pnumber = Pno
    GROUP BY Pnumber, Pname
    HAVING COUNT(*) > 2;
    ```
    
- **Combining `WHERE` and `HAVING`:**
    
    - The `WHERE` clause filters individual tuples _before_ grouping.
    - The `HAVING` clause filters groups _after_ aggregation.
    
    **Example:** For each department that has more than five employees, retrieve the department number and the count of employees earning more than $40,000.
    
    ```sql
    SELECT Dnumber, COUNT(*)
    FROM DEPARTMENT, EMPLOYEE
    WHERE Dnumber = Dno AND Salary > 40000
    GROUP BY Dnumber
    HAVING COUNT(*) > 5;
    ```
    
    _(Note: The provided example Q28 in the material uses a subquery in the WHERE clause, which is another valid way to achieve this. The above is a more direct translation of the requirement using `WHERE` and `HAVING`.)_
    

### Use of `WITH` Clause

The `WITH` clause (Common Table Expression or CTE) allows defining temporary, named result sets that can be referenced within a single SQL statement. This can improve readability and simplify complex queries, effectively acting like a temporary view.

**Example (Alternative for Q28):**

```sql
WITH BIGDEPTS (Dno) AS
( SELECT Dno
  FROM EMPLOYEE
  GROUP BY Dno
  HAVING COUNT(*) > 5)
SELECT Dno, COUNT(*)
FROM EMPLOYEE
WHERE Salary > 40000 AND Dno IN BIGDEPTS
GROUP BY Dno;
```

### Use of `CASE`

The `CASE` construct allows conditional logic within SQL statements, returning different values based on specified conditions. It can be used in `SELECT`, `WHERE`, `UPDATE`, and `INSERT` statements.

**Example (Conditional Salary Update):**

```sql
UPDATE EMPLOYEE
SET Salary =
    CASE
        WHEN Dno = 5 THEN Salary + 2000
        WHEN Dno = 4 THEN Salary + 1500
        WHEN Dno = 1 THEN Salary + 3000
        ELSE Salary -- No change for other departments
    END;
```

### Recursive Queries in SQL

Recursive queries are used for hierarchical data, such as employee-supervisor relationships. They typically involve a `WITH RECURSIVE` clause, defining a base case and a recursive step.

**Example:** Retrieve all supervisees of an employee at any level.

```sql
WITH RECURSIVE SUP_EMP (SupSsn, EmpSsn) AS
( SELECT SupervisorSsn, Ssn
  FROM EMPLOYEE
  UNION
  SELECT E.Ssn, S.EmpSsn
  FROM EMPLOYEE AS E, SUP_EMP AS S
  WHERE E.SupervisorSsn = S.EmpSsn)
SELECT * FROM SUP_EMP;
```

This query iteratively builds the `SUP_EMP` table until no new relationships can be added.

### Expanded Block Structure of SQL Queries

A typical SQL query follows this structure:

```sql
SELECT <attribute and function list>
FROM <table list>
[WHERE <condition>]
[GROUP BY <grouping attribute(s)>]
[HAVING <group condition>]
[ORDER BY <attribute list> ];
```

## Specifying Semantic Constraints as Assertions and Actions as Triggers

Beyond basic relational model constraints (like primary keys), SQL allows for more complex constraints and automated actions.

### `CREATE ASSERTION`

Used to define global constraints that cannot be expressed with `CHECK` constraints on individual tables. An assertion specifies a query that selects any tuples violating the desired condition.

**Example:** Ensure no employee earns more than their manager.

```sql
CREATE ASSERTION SALARY_CONSTRAINT
CHECK (NOT EXISTS (SELECT *
                   FROM EMPLOYEE E, EMPLOYEE M, DEPARTMENT D
                   WHERE E.Salary > M.Salary
                   AND E.Dno = D.Dnumber
                   AND D.Mgr_ssn = M.Ssn));
```

### `CREATE TRIGGER`

Triggers are automated rules that execute predefined actions when specific events (e.g., `INSERT`, `UPDATE`, `DELETE`) occur on a table, provided a certain condition is met. A trigger has three components:

1. **Event(s):** The operation(s) that activate the trigger (e.g., `INSERT`, `UPDATE OF Salary`).
2. **Condition:** A `WHEN` clause that must be true for the action to execute.
3. **Action:** The SQL statement(s) to be executed.

**Example:** Prevent an employee's salary from being updated if it's higher than their supervisor's salary.

```sql
CREATE TRIGGER SALARY_VIOLATION
BEFORE INSERT OR UPDATE OF Salary, Supervisor_ssn ON EMPLOYEE
FOR EACH ROW
WHEN (NEW.SALARY > (SELECT Salary FROM EMPLOYEE WHERE Ssn = NEW.Supervisor_Ssn))
-- Assuming INFORM_SUPERVISOR is a stored procedure or function
CALL INFORM_SUPERVISOR(NEW.Supervisor_Ssn, New.Ssn);
```

_(Note: The exact syntax for triggers can vary between different SQL implementations.)_

## Views (Virtual Tables) in SQL

A view is a virtual table based on the result set of a stored SQL query. It does not store data itself but presents data from one or more underlying base tables.

### Specification of Views in SQL

- **`CREATE VIEW` Command:** Defines a view.
    
    **Example 1 (Simple View):**
    
    ```sql
    CREATE VIEW WORKS_ON1 (Fname, Lname, Pname, Hours) AS
    SELECT E.Fname, E.Lname, P.Pname, W.Hours
    FROM EMPLOYEE E, PROJECT P, WORKS_ON W
    WHERE E.Ssn = W.Essn AND P.Pnumber = W.Pno;
    ```
    
    **Example 2 (View with Aggregation):**
    
    ```sql
    CREATE VIEW DEPT_INFO(Dept_name, No_of_emps, Total_sal) AS
    SELECT D.Dname, COUNT(E.Ssn), SUM(E.Salary)
    FROM DEPARTMENT D JOIN EMPLOYEE E ON D.Dnumber = E.Dno
    GROUP BY D.Dname;
    ```
    
- **Using Views:** Views can be used in `FROM` clauses like regular tables.
    
- **Up-to-date:** Views are always up-to-date, reflecting the current state of the base tables.
    
- **`DROP VIEW` Command:** Removes a view definition.
    

### View Implementation, View Update, and Inline Views

- **Query Modification:** The DBMS modifies the view query into a query on the base tables. This can be inefficient for complex views.
- **View Materialization:** The view's result is physically stored (materialized). This improves query performance but requires mechanisms to keep the materialized view consistent with base table updates.
    - **Update Strategies:**
        - **Immediate Update:** Updates the view as soon as base tables change.
        - **Lazy Update:** Updates the view when queried.
        - **Periodic Update:** Updates the view at regular intervals.
- **View Update:**
    - Updates on simple views (single table, no aggregates) can often be mapped to base table updates.
    - Updates involving aggregates or joins are generally not directly updatable.
    - The `WITH CHECK OPTION` clause ensures that updated tuples remain within the view's definition.
- **Inline View:** A view defined directly within the `FROM` clause of a query.

### Views as Authorization Mechanism

Views can restrict user access to specific rows or columns of base tables, acting as a security mechanism.

**Example:** Create a view showing only employees from department 5 for a specific user.

```sql
CREATE VIEW DEPT5EMP AS
SELECT *
FROM EMPLOYEE
WHERE Dno = 5;
```

## Schema Modification in SQL

Database Administrators (DBAs) use specific commands to alter the database schema.

### The `DROP` Command

Used to remove schema elements like tables, domains, or constraints.

- **`CASCADE`:** Removes the element and all dependent objects (e.g., dropping a schema with `CASCADE` removes all tables, views, etc., within it).
- **`RESTRICT`:** Prevents the drop if dependent objects exist.

**Example:**

```sql
DROP SCHEMA COMPANY CASCADE;
```

### The `ALTER TABLE` Command

Used to modify existing tables. Common actions include:

- Adding or dropping columns.
- Changing column definitions.
- Adding or dropping table constraints.

**Example (Add Column):**

```sql
ALTER TABLE COMPANY.EMPLOYEE ADD COLUMN Job VARCHAR(12);
```

### Adding and Dropping Constraints

Named constraints can be added or dropped from tables.

**Example (Drop Constraint):**

```sql
ALTER TABLE COMPANY.EMPLOYEE DROP CONSTRAINT EMPSUPERFK CASCADE;
```

### Dropping Columns and Modifying Default Values

- **Dropping Columns:** Can use `CASCADE` or `RESTRICT`. `CASCADE` removes the column from views, etc., that reference it.
    
    **Example:**
    
    ```sql
    ALTER TABLE COMPANY.EMPLOYEE DROP COLUMN Address CASCADE;
    ```
    
- **Default Values:** Default values for columns can be set, altered, or dropped.
    
    **Example:**
    
    ```sql
    ALTER TABLE COMPANY.DEPARTMENT ALTER COLUMN Mgr_ssn DROP DEFAULT;
    ALTER TABLE COMPANY.DEPARTMENT ALTER COLUMN Mgr_ssn SET DEFAULT '33344
    ```