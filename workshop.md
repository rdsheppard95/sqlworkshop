# SQL Workshop
## Software needed
[SQLite DB Browser](http://sqlitebrowser.org/)

## Example Database
[Chinook Database](http://www.sqlitetutorial.net/download/sqlite-sample-database/?wpdmdl=94)

## SQL SELECT Statement Layout

The general layout for SELECT statements is as follows:
```
SELECT DISTINCT columns
FROM table
JOIN table ON expression
WHERE expression
ORDER BY column
LIMIT count OFFSET offset
GROUP BY column
HAVING expression
```
Anything in capitals is a SQL keyword, while lowercase words are where the modifiers go.

## SELECT Statements
To select every row from a specific table

`SELECT * FROM invoices;`
### DISTINCT
To select distinct entries based on a column

`SELECT DISTINCT BillingCity FROM invoices;`
### LIMIT
To limit the number of results

`SELECT * FROM invoices LIMIT 100;`

To limit the number of results with a different starting point

`SELECT * FROM invoices LIMIT 100 OFFSET 50;`
### WHERE
To select rows where a certain column equals a value

`SELECT * FROM invoices WHERE BillingCity = "Stuttgart";`

To select rows where a certain column equals a value and where a certain column is greater than a value

`SELECT * FROM invoices WHERE BillingCity = "Stuttgart AND Total > 5";`

To select rows where a column equals one value or the other

`SELECT * FROM invoices WHERE BillingCity = "Stuttgart" OR BillingCity = "Dublin";`
### COUNT
Count is an example of an aggregation. Other examples include MAX and MIN.

`SELECT COUNT(*) FROM invoices;`

`SELECT COUNT(*) FROM invoices WHERE BillingCity = "Stuttgart";`
### ORDER BY
Orders the results by a specific column in ascending (smallest first) order

`SELECT * FROM invoices WHERE BillingCity = "Stuttgart" ORDER BY Total;`

Orders the results by a specific column in descending (largest first) order

`SELECT * FROM invoices WHERE BillingCity = "Stuttgart" ORDER BY Total DESC`
### GROUP BY
Groups rows based on a column, useful for aggregations

`SELECT BillingCity, max(Total) FROM invoices GROUP BY BillingCity;`
### HAVING
HAVING is used in place of WHERE for aggregate functions.
`SELECT * FROM invoices GROUP BY BillingCity HAVING COUNT(BillingCity) > 10;`

### INNER JOIN
`SELECT FirstName, LastName, Company, BillingState FROM customers INNER JOIN invoices ON customers.CustomerId = invoices.CustomerId;`

## Additional Resources
[SQLite Tutorial](http://www.sqlitetutorial.net/)

[SQL Joins](http://www.sql-join.com/sql-join-types/)
