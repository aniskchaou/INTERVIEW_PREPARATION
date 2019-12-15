## What is SQL?

 -   SQL stands for **Structured Query Language**
 -   SQL lets you access and manipulate databases
 -   SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987
 - SQL keywords are NOT case sensitive: select is the same as SELECT
## The SQL SELECT Statement

### SELECT Syntax

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_;

or

    SELECT * FROM  _table_name_;
### Example

    SELECT CustomerName, City FROM Customers;

## The SQL SELECT DISTINCT Statement

The SELECT DISTINCT statement is used to return only distinct (different) values.

    SELECT  DISTINCT  _column1_, _column2, ..._  
    FROM  _table_name_;
### Example

    SELECT  DISTINCT  Country  FROM  Customers;
## The SQL WHERE Clause

The WHERE clause is used to filter records.
### WHERE Syntax

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_  
    WHERE  _condition_;
### Example

    SELECT  *  FROM  Customers  
    WHERE  Country='Mexico';
## Operators in The WHERE Clause
**=**
Equal

**>**
Greater than

**<**
Less than



**> =**

Greater than or equal



**<=**

Less than or equal

**<>**

Not equal.  **Note:**  In some versions of SQL this operator may be written as !=
## SQL  IN  Operator
The IN operator is a shorthand for multiple OR conditions.

### IN Syntax

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _column_name_  IN  (_value1_, _value2_, ...);

or:

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _column_name_  IN  (_SELECT  STATEMENT_);
**Example**
selects all customers that are located in "Germany", "France" or "UK"

    SELECT * FROM Customers  
    WHERE Country IN ('Germany', 'France', 'UK');
selects all customers that are NOT located in "Germany", "France" or "UK"

    SELECT * FROM Customers  
    WHERE Country NOT  IN ('Germany', 'France', 'UK');
selects all customers that are from the same countries as the suppliers

    SELECT * FROM Customers  
    WHERE Country IN (SELECT Country FROM Suppliers);
## The SQL BETWEEN Operator
The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  _column_name_ BETWEEN  _value1_  AND  _value2;_
### Example

    SELECT  *  FROM  Products  
    WHERE  Price  BETWEEN  10  AND  20;
## The SQL LIKE Operator
The LIKE operator is used in a WHERE clause to search ***for a specified pattern in a column.***
-   **% - The percent sign represents zero**, one, or multiple characters
-   _ - The underscore represents a single character

    SELECT  _column1, column2, ..._  
    FROM  _table_name_  
    WHERE  _columnN_  LIKE  _pattern_;

**Example**
selects all customers with a CustomerName starting with "a"

    SELECT * FROM Customers  
    WHERE CustomerName LIKE  'a%';

selects all customers with a CustomerName ending with "a"

    SELECT * FROM Customers  
    WHERE CustomerName LIKE  '%a';
selects all customers with a CustomerName that have "or" in any position

    SELECT * FROM Customers  
    WHERE CustomerName LIKE  '%or%';
selects all customers with a ContactName that starts with "a" and ends with "o"

    SELECT * FROM Customers  
    WHERE ContactName LIKE  'a%o';
selects all customers with a CustomerName that does NOT start with "a"

    SELECT * FROM Customers  
    WHERE CustomerName NOT  LIKE  'a%';

## The SQL AND, OR and NOT Operators

The WHERE clause can be combined with AND, OR, and NOT operators.
### AND Syntax

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_  
    WHERE  _condition1_  AND  _condition2_  AND  _condition3 ..._;
**Exemple**
selects all fields from "Customers" where country is "Germany" AND city is "Berlin"

    SELECT * FROM Customers  
    WHERE Country='Germany'  AND City='Berlin';

### OR Syntax

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_  
    WHERE  _condition1_  OR  _condition2_  OR  _condition3 ..._;
**Exemple**
selects all fields from "Customers" where city is "Berlin" OR "München"

    SELECT * FROM Customers  
    WHERE City='Berlin'  OR City='München';

### NOT Syntax

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_  
    WHERE  NOT  _condition_;

### Example

selects all fields from "Customers" where country is NOT "Germany"

    SELECT * FROM Customers  
    WHERE  NOT Country='Germany';
selects all fields from "Customers" where country is NOT "Germany" and NOT "USA"

    SELECT * FROM Customers  
    WHERE  NOT Country='Germany'  AND  NOT Country='USA';
## The SQL ORDER BY Keyword

The ORDER BY keyword is used to sort the result-set in ascending or descending order.

    SELECT  _column1_, _column2, ..._  
    FROM  _table_name_  
    ORDER  BY  _column1, column2, ..._ ASC|DESC;
**Example**

    SELECT * FROM Customers  
    ORDER  BY Country DESC;
**ORDER BY Several Columns**

    SELECT * FROM Customers  
    ORDER  BY Country ASC, CustomerName DESC;
## The SQL MIN() and MAX() Functions
### MIN() Syntax

    SELECT  MIN(_column_name_)  
    FROM  _table_name_  
    WHERE  _condition_;

### MAX() Syntax

    SELECT  MAX(_column_name_)  
    FROM  _table_name_  
    WHERE  _condition_;
## MIN() Example

The following SQL statement **finds the price of the cheapest product**:

### Example

    SELECT  MIN(Price)  AS  SmallestPrice  
    FROM  Products;
## MAX() Example

The following SQL statement **finds the price of the most expensive product**:

### Example

    SELECT  MAX(Price)  AS  LargestPrice  
    FROM  Products;
## The SQL COUNT(), AVG() and SUM() Functions

The COUNT() function returns the number of rows that matches a specified criteria.

The AVG() function returns the average value of a numeric column.

The SUM() function returns the total sum of a numeric column.

## COUNT() Example

The following SQL statement finds the number of products:

### Example

    SELECT  COUNT(ProductID)  
    FROM  Products;


**Note:**  NULL values are not counted.

----------

## AVG() Example

The following SQL statement finds the average price of all products:

### Example

    SELECT  AVG(Price)  
    FROM  Products;

## SUM() Example

The following SQL statement finds the sum of the "Quantity" fields in the "OrderDetails" table:

### Example

    SELECT  SUM(Quantity)  
    FROM  OrderDetails;

## The SQL SELECT TOP Clause

The SELECT TOP clause **is used to specify the number of records to return**.

    **Note:** Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses ROWNUM.
**SQL Server / MS Access Syntax:**

    SELECT  TOP  _number_|_percent_  _column_name(s)_  
    FROM  _table_name  
    _WHERE  _condition_;

**MySQL Syntax:**

    SELECT  _column_name(s)_  
    FROM  _table_name  
    _WHERE  _condition_  
    LIMIT  _number_;

**Oracle Syntax:**

    SELECT  _column_name(s)_  
    FROM  _table_name_  
    WHERE  ROWNUM <=  _number_;
The following SQL statement selects the first three records from the "Customers" table:

### Example

    SELECT  TOP  3  *  FROM  Customers;



The following SQL statement shows the equivalent example using the LIMIT clause:

### Example

    SELECT  *  FROM  Customers  
    LIMIT  3;
## SQL  NULL Values
A field with a NULL value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.
### Example
The following SQL lists all customers with a NULL value in the "Address" field:



    SELECT  CustomerName, ContactName, Address  
    FROM  Customers  
    WHERE  Address  IS  NULL;
The following SQL lists all customers with a value in the "Address" field:


    SELECT  CustomerName, ContactName, Address  
    FROM  Customers  
    WHERE  Address  IS  NOT  NULL;
