## Joins
**client**

    | id  | name           | city             |
    |  1  | Anis           | Mulhouse         |
    |  2  | Mohamed        | Strasbourg       |
    |  3  | Rahma          | Lyon             |
    |  4  | Kamel          | Paris            |

**orders**

    | id | client_id | manager|
    | 1  | 1         |4       |
    | 2  | 3         |4       |
## SQL INNER JOIN Keyword

The INNER JOIN keyword selects **records that have matching values in both tables.**
**query**

    SELECT orders.client_id, client.id, client.name
    FROM orders
    INNER JOIN client ON orders.client_id = client.id

**result**

    |id   |client_id  |name  |
    |1    |1          |anis  |
    |3    |3          |rahma |
## SQL LEFT JOIN Keyword

The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.
**query**

    SELECT client.id, client.name, orders.client_id
    FROM client
    LEFT JOIN orders
    ON client.id=orders.client_id
**result**

    | id |  name         |    client_id   |
    | 1 |  anis          |       1        |
    | 2 | mahamed        |     NULL       |
    | 3 | rahma          |      3         |
    | 4 | kamel          |    NULL        |

## SQL RIGHT JOIN Keyword

The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match.


**query**

    SELECT client.id,client.name,orders.client_id
     FROM client
     RIGHT JOIN orders
      ON client.id=orders.client_id

**result**

    | id | name   | client_id  |
    | 1  | anis   |  1        |
    | 3  | rahma  | 3         |
## SQL FULL OUTER JOIN Keyword

The FULL OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.

**Note:**  FULL OUTER JOIN can potentially return very large result-sets!

**Tip:**  FULL OUTER JOIN and FULL JOIN are the same.

**query**

        SELECT client.id, client.name, orders.client_id
        FROM client
        LEFT JOIN orders
        ON client.id=orders.client_id
        
        UNION
         SELECT client.id,client.name,orders.client_id
         FROM client
         RIGHT JOIN orders
         ON client.id=orders.client_id

**result**

        | id |  name         |    client_id   |
        | 1 |  anis          |       1        |
        | 2 | mahamed        |     NULL       |
        | 3 | rahma          |      3         |
        | 4 | kamel          |    NULL        |
