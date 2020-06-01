
**What is an index?**  
A database index is a data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and the use of more storage space to maintain the extra copy of data.
**What is the difference between primary key and unique constraints?**  
Primary key cannot have NULL value, the unique constraints can have NULL values. There is only one primary key in a table, but there can be multiple unique constrains. The primary key creates the cluster index automatically but the Unique key does not.
1.  **What do you mean by data definition language?**  
    Data definition language or DDL allows to execute queries like CREATE, DROP and ALTER. That is, those queries which define the data.
  

  
5.  **What do you mean by data manipulation language?**  
    Data manipulation Language or DML is used to access or manipulate data in the database.  
    It allows us to perform below listed functions:
    -   Insert data or rows in database
    -   Delete data from database
    -   Retrieve or fetch data
    -   Update data in database.
**What is the difference between CHAR and VARCHAR2 datatype in SQL?**  
Both of these datatypes are used for characters but varchar2 is used for character strings of variable length whereas char is used for character strings of fixed length.
**6. What is a primary key?**

A primary key is a combination of fields which uniquely specify a row. This is a special kind of unique key, and it has implicit NOT NULL constraint. It means, Primary key values cannot be NULL.

**7. What is a unique key?**

A Unique key constraint uniquely identified each record in the database. This provides uniqueness for the column or set of columns.

A Primary key constraint has automatic unique constraint defined on it. But not, in the case of Unique Key.

There can be many unique constraint defined per table, but only one Primary key constraint defined per table.
**20. What is subquery?**

A subquery is a query within another query. The outer query is called as main query, and inner query is called subquery. SubQuery is always executed first, and the result of subquery is passed on to the main query.
**22. What is a stored procedure?**

Stored Procedure is a function consists of many SQL statement to access the database system. Several SQL statements are consolidated into a stored procedure and execute them whenever and wherever required.
**24. What is the difference between DELETE and TRUNCATE commands?**

DELETE command is used to remove rows from the table, and WHERE clause can be used for conditional set of parameters. Commit and Rollback can be performed after delete statement.

TRUNCATE removes all rows from the table. Truncate operation cannot be rolled back.
**26. What is a constraint?**

Constraint can be used to specify the limit on the data type of table. Constraint can be specified while creating or altering the table statement. Sample of constraint are.

-   NOT NULL.
-   CHECK.
-   DEFAULT.
-   UNIQUE.
-   PRIMARY KEY.
-   FOREIGN KEY.
### 12) What is a unique key?

Unique key constraint uniquely identifies each record in the database. This key provides uniqueness for the column or set of columns.

The Unique key cannot accept a duplicate value.

The unique key can accept only on Null value.

----------

### 13) What is the difference between primary key and unique key?

Primary key and unique key both are the essential constraints of the SQL, but there is a small difference between them

Primary key carries unique value but the field of the primary key cannot be Null on the other hand unique key also carry unique value but it can have a single Null value field.
### 43) What are the set operators in SQL?

SQL queries which contain set operations are called compound queries.

**Union**, Union All,  **Intersect**  or  **Minus**  operators are the set operators used in the SQL.

----------

### 44) What is the difference between BETWEEN and IN condition operators?

The BETWEEN operator is used to display rows based on a range of values. The values can be numbers, text, and dates as well. BETWEEN operator gives us the count of all the values occurs between a particular range.

The IN condition operator is used to check for values contained in a specific set of values. IN operator is used when we have more than one value to choose.
### 49) What is ACID property in a database?

ACID property is used to ensure that the data transactions are processed reliably in a database system.

A single logical operation of a data is called transaction.

ACID is an acronym for Atomicity, Consistency, Isolation, Durability.
### 56) What is the usage of NVL() function?

The NVL() function is used to convert NULL value to the other value. NVL() function is used in Oracle it is not in SQL and MySQL server.

Instead of NVL() function MySQL have IFNULL() and SQL Server have ISNULL() function.

----------

### 57) Which function is used to return remainder in a division operator in SQL?

The MOD function returns the remainder in a division operation.

----------

### 58) What are the syntax and use of the COALESCE function?

The syntax of COALESCE function:

1.  COALESCE(exp1, exp2, .... expn)

The COALESCE function is used to return the first non-null expression given in the parameter list.