
## The SQL CREATE DATABASE Statement

The CREATE DATABASE statement is used to create a new SQL database.

### Syntax

    CREATE  DATABASE  _databasename_;

### Example

    CREATE  DATABASE  testDB;
## The SQL DROP DATABASE Statement

The DROP DATABASE statement is used to drop an existing SQL database.

### Syntax

    DROP  DATABASE  _databasename_;

## The SQL BACKUP DATABASE Statement

The BACKUP DATABASE statement is used in SQL Server to create a full back up of an existing SQL database.

### Syntax

    BACKUP  DATABASE  _databasename_  
    TO  DISK  =  '_filepath_';



## The SQL BACKUP WITH DIFFERENTIAL Statement

A differential back **up only backs up the parts of the database that have changed since the last full database backup.**

### Syntax

    BACKUP  DATABASE  _databasename_  
    TO  DISK  =  '_filepath_'  
    WITH  DIFFERENTIAL;



## BACKUP DATABASE Example

The following SQL statement creates a full back up of the existing database "testDB" to the D disk:

### Example

    BACKUP  DATABASE  testDB  
    TO  DISK  =  'D:\backups\testDB.bak';
## The SQL CREATE TABLE Statement
The CREATE TABLE statement is used to create a new table in a database.

### Syntax

    CREATE  TABLE  _table_name_ (  
    _column1 datatype_,  
    _column2 datatype_,  
    _column3 datatype_,  
    ....  
    );
The datatype parameter specifies the type of data the column can hold (e.g. varchar, integer, date, etc.).
## SQL CREATE TABLE Example

The following example creates a table called "Persons" that contains five columns: PersonID, LastName, FirstName, Address, and City:

### Example

    CREATE  TABLE  Persons (  
    PersonID int,  
    LastName varchar(255),  
    FirstName varchar(255),  
    Address varchar(255),  
    City varchar(255)  
    );
## The SQL DROP TABLE Statement

The DROP TABLE statement is used to drop an existing table in a database.

### Syntax

    DROP  TABLE  _table_name_;
**Example**
## SQL DROP TABLE Example

The following SQL statement drops the existing table "Shippers":

### Example

    DROP  TABLE  Shippers;



## SQL TRUNCATE TABLE

The TRUNCATE TABLE statement is used to **delete the data inside a table, but not the table itself.**

### Syntax

    TRUNCATE  TABLE  _table_name_;
## SQL ALTER TABLE Statement

The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

----------

## ALTER TABLE - ADD Column

To add a column in a table, use the following syntax:

    ALTER  TABLE  _table_name_  
    ADD  _column_name datatype_;

The following SQL adds an "Email" column to the "Customers" table:

### Example

    ALTER  TABLE  Customers  
    ADD  Email varchar(255);



----------

## ALTER TABLE - DROP COLUMN

To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column):

    ALTER  TABLE  _table_name_  
    DROP  COLUMN  _column_name_;

The following SQL deletes the "Email" column from the "Customers" table:

### Example

    ALTER  TABLE  Customers  
    DROP  COLUMN  Email;



----------

## ALTER TABLE - ALTER/MODIFY COLUMN

To change the data type of a column in a table, use the following syntax:

**SQL Server / MS Access:**

    ALTER  TABLE  _table_name_  
    ALTER  COLUMN  _column_name datatype_;

**My SQL / Oracle (prior version 10G):**

    ALTER  TABLE  _table_name_  
    MODIFY  COLUMN  _column_name datatype_;

**Oracle 10G and later:**

    ALTER  TABLE  _table_name_  
    MODIFY  _column_name datatype_;
## SQL Constraints

SQL constraints are used to specify rules for the data in a table.



The following constraints are commonly used in SQL:

-   **[NOT NULL]** Ensures that a column cannot have a NULL value

    CREATE  TABLE Persons (  
    ID int NOT  NULL,  
    LastName varchar(255) NOT  NULL,  
    FirstName varchar(255) NOT  NULL,  
    Age int  
    )

-   **[UNIQUE]**  - Ensures that all values in a column are different

       CREATE  TABLE Persons (  
    ID int NOT  NULL,  
    LastName varchar(255) NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    UNIQUE (ID)  
    );

-   **[PRIMARY KEY]**  - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
-   **[FOREIGN KEY]**  - Uniquely identifies a row/record in another table
-   **[CHECK]**  - Ensures that all values in a column satisfies a specific condition

    CREATE  TABLE Persons (  
    ID int NOT  NULL,  
    LastName varchar(255) NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    CHECK (Age>=18)  
    );

-   **[DEFAULT]**  - **Sets a default value for a column** when no value is specified

    CREATE  TABLE Persons (  
    ID int NOT  NULL,  
    LastName varchar(255) NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    City varchar(255) DEFAULT  'Sandnes'  
    );

-   **[INDEX]**  - Used to create and retrieve data from the database very quickly

## SQL PRIMARY KEY Constraint
### SQL PRIMARY KEY on CREATE TABLE

The following SQL creates a PRIMARY KEY on the "ID" column when the "Persons" table is created:

**MySQL:**

    CREATE  TABLE  Persons (  
    ID int  NOT  NULL,  
    LastName varchar(255)  NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    PRIMARY  KEY  (ID)  
    );
To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

    CREATE  TABLE  Persons (  
    ID int  NOT  NULL,  
    LastName varchar(255)  NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    CONSTRAINT  PK_Person  PRIMARY  KEY  (ID,LastName)  
    );
### SQL PRIMARY KEY on ALTER TABLE

To create a PRIMARY KEY constraint on the "ID" column when the table is already created, use the following SQL:

**MySQL / SQL Server / Oracle / MS Access:**

ALTER  TABLE  Persons  
ADD  PRIMARY  KEY  (ID);

To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

    ALTER  TABLE  Persons  
    ADD  CONSTRAINT  PK_Person  PRIMARY  KEY  (ID,LastName);

## DROP a PRIMARY KEY Constraint

To drop a PRIMARY KEY constraint, use the following SQL:

**MySQL:**

    ALTER  TABLE  Persons  
    DROP  PRIMARY  KEY;

**SQL Server / Oracle / MS Access:**

    ALTER  TABLE  Persons  
    DROP  CONSTRAINT  PK_Person;
## SQL FOREIGN KEY Constraint
## SQL FOREIGN KEY on CREATE TABLE

The following SQL creates a FOREIGN KEY on the "PersonID" column when the "Orders" table is created:

**MySQL:**

    CREATE  TABLE  Orders (  
    OrderID int  NOT  NULL,  
    OrderNumber int  NOT  NULL,  
    PersonID int,  
    PRIMARY  KEY  (OrderID),  
    FOREIGN  KEY  (PersonID)  REFERENCES  Persons(PersonID)  
    );

**SQL Server / Oracle / MS Access:**

    CREATE  TABLE  Orders (  
    OrderID int  NOT  NULL  PRIMARY  KEY,  
    OrderNumber int  NOT  NULL,  
    PersonID int  FOREIGN  KEY  REFERENCES  Persons(PersonID)  
    );

To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns, use the following SQL syntax:

**MySQL / SQL Server / Oracle / MS Access:**

    CREATE  TABLE  Orders (  
    OrderID int  NOT  NULL,  
    OrderNumber int  NOT  NULL,  
    PersonID int,  
    PRIMARY  KEY  (OrderID),  
    CONSTRAINT  FK_PersonOrder  FOREIGN  KEY  (PersonID)  
    REFERENCES  Persons(PersonID)  
    );
## DROP a FOREIGN KEY Constraint

To drop a FOREIGN KEY constraint, use the following SQL:

**MySQL:**

    ALTER  TABLE  Orders  
    DROP  FOREIGN  KEY  FK_PersonOrder;

**SQL Server / Oracle / MS Access:**

    ALTER  TABLE  Orders  
    DROP  CONSTRAINT  FK_PersonOrder;
## AUTO INCREMENT Field

Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

Often this is the primary key field that we would like to be created automatically every time a new record is inserted.



## Syntax for MySQL

The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

    CREATE  TABLE  Persons (  
    Personid int  NOT  NULL  AUTO_INCREMENT,  
    LastName varchar(255)  NOT  NULL,  
    FirstName varchar(255),  
    Age int,  
    PRIMARY  KEY  (Personid)  
    );

MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.

By default, the starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.

To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:

    ALTER  TABLE  Persons AUTO_INCREMENT=100;

## Rename MySQL database

To rename the mysql database, you need to follow the following syntax:

 

    RENAME DATABASE old_db_name TO new_db_name;

# SQL SELECT Database

In MySQL database, you need to select a database first before executing any query on table, view etc. To do so, we use following query:

     USE DATABASE database_name;

# SQL TRUNCATE TABLE

A truncate SQL statement is used to remove all rows (complete data) from a table. It is similar to the DELETE statement with no WHERE clause.

----------

#### TRUNCATE TABLE Vs DELETE TABLE

Truncate table is faster and uses lesser resources than DELETE TABLE command.


#### TRUNCATE TABLE Vs DROP TABLE

Drop table command can also be used to delete complete table but it deletes table structure too. TRUNCATE TABLE doesn't delete the structure of the table.

----------

Let's see the syntax to truncate the table from the database.

 

    TRUNCATE  TABLE table_name;

For example, you can write following command to truncate the data of employee table

     TRUNCATE  TABLE Employee;

**Note:**  The rollback process is not possible after truncate table statement. Once you truncate a table you cannot use a flashback table statement to retrieve the content of the table.
# SQL COPY TABLE

If you want to copy a SQL table into another table in the same SQL server database, it is possible by using the select statement.


For example, you can write following command to copy the records of hr_employee table into employee table.

  

    SELECT * INTO admin_employee FROM hr_employee;

#### Note: SELECT INTO is totally different from INSERT INTO statement.
# SQL SELECT FIRST

The SQL first() function is used to return the first value of the selected column.

    SELECT  FIRST(column_name) FROM table_name;


# SQL SELECT LAST

The last() function is used to return the last value of the specified column.


  `SELECT  LAST (column_name) FROM table_name;`


# SQL SELECT RANDOM

The SQL SELECT RANDOM() function returns the random row. It can be used in online exam to display the random questions.

    1.  SELECT  column  FROM  table
    2.  ORDER  BY RAND ( )
    3.  LIMIT 1

# SQL SELECT AS

**SQL AS**  is used to assign temporarily a new name to a table column.

It makes easy presentation of query results and allows the developer to label results more accurately without permanently renaming table columns.



    1.  SELECT day_of_order AS  "Date"
    2.  Customer As  "Client",
    3.  Product,
    4.  Quantity,
    5.  FROM orders;

# SQL SELECT DATE

SQL SELECT DATE is used to retrieve a date from a database. If you want to find a particular date from a database, you can use this statement.

**For example:**  let's see the query to get all the records after '2013-12-12'.

    1.  SELECT * FROM
    2.  table-name  WHERE your date-column >= '2013-12-12'

Let's see the another query to get all the records after '2013-12-12' and before '2013-12-13' date.


# SQL Composite Key

A composite key is a combination of two or more columns in a table that can be used to uniquely identify each row in the table when the columns are combined uniqueness is guaranteed


    1.  CREATE  TABLE SAMPLE_TABLE
    2.  (COL1 integer,
    3.  COL2 varchar(30),
    4.  COL3 varchar(50),
    5.  PRIMARY  KEY (COL1, COL2));

## The SQL CASE Statement

The CASE statement goes through conditions and returns a value when the first condition is met (like an IF-THEN-ELSE statement). 

    SELECT OrderID, Quantity,  
    CASE  
    WHEN Quantity > 30  THEN  'The quantity is greater than 30'  
    WHEN Quantity = 30  THEN  'The quantity is 30'  
    ELSE  'The quantity is under 30'  
    END  AS QuantityText  
    FROM OrderDetails;
## SQL CREATE VIEW Statement

In SQL, a view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

    CREATE  VIEW [Brazil Customers] AS  
    SELECT  CustomerName, ContactName  
    FROM Customers  
    WHERE  Country = 'Brazil';
# MySQL  CAST()  Function


### Example

Convert a value to a DATE datatype:

    SELECT  CAST("2017-08-29"  AS  DATE);

# MySQL  COALESCE()  Function


### Example

Return the first non-null value in a list:

SELECT  COALESCE(NULL,  NULL,  NULL,  'W3Schools.com',  NULL,  'Example.com');

