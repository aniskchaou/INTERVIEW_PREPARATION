
## SQL Aliases

SQL aliases are used to give a table, or a column in a table, a temporary name.

**Aliases are often used to make column names more readable.**

An alias only exists for the duration of the query.

### Alias Column Syntax

    SELECT  _column_name_  AS  _alias_name_  
    FROM  _table_name;_

### Alias Table Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_ AS  _alias_name;_
## Alias for Columns Examples

The following SQL statement **creates two aliases, one for the CustomerID column and one for the CustomerName column:**

### Example

    SELECT  CustomerID  AS  ID, CustomerName  AS  Customer  
    FROM  Customers;
The following SQL statement creates an alias named "Address" that combine four columns (Address, PostalCode, City and Country):

### Example

    SELECT  CustomerName, Address +  ', '  + PostalCode +  ' '  + City +  ', '  + Country  AS  Address  
    FROM  Customers;



**Note:**  To get the SQL statement above to work in MySQL use the following:

    SELECT  CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country)  AS  Address  
    FROM  Customers;
## Alias for Tables Example

The following SQL statement selects all the orders from the customer with CustomerID=4 (Around the Horn). We use the "Customers" and "Orders" tables, and give them the table aliases of "c" and "o" respectively (Here we use aliases to make the SQL shorter):

### Example

    SELECT  o.OrderID, o.OrderDate, c.CustomerName  
    FROM  Customers  AS  c, Orders  AS  o  
    WHERE  c.CustomerName="Around the Horn"  AND  c.CustomerID=o.CustomerID;
**Aliases can be useful when:**

-   There are **more than one table** involved in a query
-   **Functions are used** in the query
-   **Column names are big or not very readable**
-   **Two or more columns** are combined together
## The SQL INSERT INTO Statement

The INSERT INTO statement is used to insert new records in a table.

### INSERT INTO Syntax

It is possible to write the INSERT INTO statement in two ways.



    INSERT  INTO  _table_name_  (_column1_, _column2_, _column3_, ...)  
    VALUES  (_value1_, _value2_, _value3_, ...);
or

    INSERT  INTO  _table_name_  
    VALUES (_value1_, _value2_, _value3_, ...);
The following SQL statement inserts a new record in the "Customers" table:

### Example

    INSERT  INTO  Customers (CustomerName, ContactName, Address, City, PostalCode, Country)  
    VALUES  ('Cardinal',  'Tom B. Erichsen',  'Skagen 21',  'Stavanger',  '4006',  'Norway');
## The SQL UPDATE Statement

The UPDATE statement is used to modify the existing records in a table.

### UPDATE Syntax

    UPDATE  _table_name_  
    SET  _column1_ = _value1_, _column2_ = _value2_, ...  
    WHERE  _condition_;
## UPDATE Table

The following SQL statement updates the first customer (CustomerID = 1) with a new contact person  _and_  a new city.

### Example

    UPDATE  Customers  
    SET  ContactName =  'Alfred Schmidt', City=  'Frankfurt'  
    WHERE  CustomerID =  1;
**Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!**
## The SQL DELETE Statement

The DELETE statement is used to delete existing records in a table.

### DELETE Syntax

    DELETE  FROM  _table_name_ WHERE  _condition_;
## SQL DELETE Example

The following SQL statement deletes the customer "Alfreds Futterkiste" from the "Customers" table:

### Example

    DELETE  FROM  Customers  WHERE  CustomerName='Alfreds Futterkiste';
## The SQL SELECT INTO Statement

The SELECT INTO statement copies data from one table into a new table.

### SELECT INTO Syntax

Copy all columns into a new table:

    SELECT  *  
    INTO  _newtable_  [IN  _externaldb_]  
    FROM  _oldtable  
    _WHERE  _condition_;
## SQL SELECT INTO Examples

The following SQL statement creates a backup copy of Customers:

    SELECT  *  INTO  CustomersBackup2017  
    FROM  Customers;

The following SQL statement uses the IN clause to copy the table into a new table in another database:

    SELECT  *  INTO  CustomersBackup2017  IN  'Backup.mdb'  
    FROM  Customers;

The following SQL statement copies only a few columns into a new table:

    SELECT  CustomerName, ContactName  INTO  CustomersBackup2017  
    FROM  Customers;
**Tip:**  SELECT INTO can also be used to create a new, empty table using the schema of another. Just add a WHERE clause that causes the query to return no data:

    SELECT  *  INTO  _newtable_  
    FROM  _oldtable_  
    WHERE  1  =  0;
## SQL JOIN

A JOIN clause **is used to combine rows from two or more tables, based on a related column between them.**
### Example

    SELECT  Orders.OrderID, Customers.CustomerName, Orders.OrderDate  
    FROM  Orders  
    INNER  JOIN  Customers  ON  Orders.CustomerID=Customers.CustomerID;
## Different Types of SQL JOINs

Here are the different types of the JOINs in SQL:

-   **(INNER) JOIN**: Returns records that have matching values in both tables
-   **LEFT (OUTER) JOIN**: Returns all records from the left table, and the matched records from the right table
-   **RIGHT (OUTER) JOIN**: Returns all records from the right table, and the matched records from the left table
-   **FULL (OUTER) JOIN**: Returns all records when there is a match in either left or right table

## The SQL UNION Operator

The UNION operator is used to combine the result-set of two or more SELECT statements.

-   Each SELECT statement within UNION must have the same number of columns
-   The columns must also have similar data types
-   The columns in each SELECT statement must also be in the same order

### UNION Syntax

    SELECT  _column_name(s)_  FROM  _table1_  
    UNION  
    SELECT  _column_name(s)_  FROM  _table2_;

### UNION ALL Syntax

The UNION operator selects only distinct values by default. To allow duplicate values, use UNION ALL:

    SELECT  _column_name(s)_  FROM  _table1_  
    UNION  ALL  
    SELECT  _column_name(s)_  FROM  _table2_;
## SQL UNION Example

The following SQL statement returns the cities (only distinct values) from both the "Customers" and the "Suppliers" table:

### Example

    SELECT  City  FROM  Customers  
    UNION  
    SELECT  City  FROM  Suppliers  
    ORDER  BY  City;
The following SQL statement returns the cities (duplicate values also) from both the "Customers" and the "Suppliers" table:

### Example

    SELECT  City  FROM  Customers  
    UNION  ALL  
    SELECT  City  FROM  Suppliers  
    ORDER  BY  City;
## The SQL GROUP BY Statement

The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

**The GROUP BY statement is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.**

### GROUP BY Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _condition_  
    GROUP  BY  _column_name(s)  
    _ORDER  BY  _column_name(s);_

## SQL GROUP BY Examples

The following SQL statement lists the number of customers in each country:

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country;



The following SQL statement lists the number of customers in each country, sorted high to low:

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country  
    ORDER  BY  COUNT(CustomerID)  DESC;
## The SQL HAVING Clause

The HAVING clause was added to SQL **because the WHERE keyword could not be used with aggregate functions.**

### HAVING Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _condition_  
    GROUP  BY  _column_name(s)  
    _HAVING  _condition  
    _ORDER  BY  _column_name(s);_
## SQL HAVING Examples

The following SQL statement lists the number of customers in each country. Only include countries with more than 5 customers:

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country  
    HAVING  COUNT(CustomerID) >  5;



The following SQL statement lists the number of customers in each country, sorted high to low (Only include countries with more than 5 customers):

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country  
    HAVING  COUNT(CustomerID)  >  5  
    ORDER  BY  COUNT(CustomerID)  DESC;
## SQL HAVING Examples

The following SQL statement lists the number of customers in each country. Only include countries with more than 5 customers:

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country  
    HAVING  COUNT(CustomerID) >  5;



The following SQL statement lists the number of customers in each country, sorted high to low (Only include countries with more than 5 customers):

### Example

    SELECT  COUNT(CustomerID), Country  
    FROM  Customers  
    GROUP  BY  Country  
    HAVING  COUNT(CustomerID)  >  5  
    ORDER  BY  COUNT(CustomerID)  DESC;
## SQL EXISTS Examples

The following SQL statement returns TRUE and lists the suppliers with a product price less than 20:

### Example

    SELECT  SupplierName  
    FROM  Suppliers  
    WHERE  EXISTS  (SELECT  ProductName  FROM  Products  WHERE  Products.SupplierID = Suppliers.supplierID  AND  Price <  20);
## The SQL ANY and ALL Operators

The ANY and ALL operators are used with a WHERE or HAVING clause.

The ANY operator returns true if any of the subquery values meet the condition.

The ALL operator returns true if all of the subquery values meet the condition.

### ANY Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _column_name operator_  ANY  
    (SELECT  _column_name_ FROM  _table_name_  WHERE  _condition_);

### ALL Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _column_name operator_  ALL  
    (SELECT  _column_name_ FROM  _table_name_ WHERE  _condition_);
## SQL Comments

Comments are used to explain sections of SQL statements, or to prevent execution of SQL statements.
## Single Line Comments

Single line comments start with --.
## Multi-line Comments

Multi-line comments start with /* and end with */.

Any text between /* and */ will be ignored.