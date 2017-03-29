# SQL Workshop #2 Answers

### Aggregations to remember
`COUNT()`

`SUM()`

`MAX()`

`MIN()`

`ROUND(<Value>, <Precision>)`

`AVG()`

## Question 1
Select all of the customers (names, IDs, and country) who are not in the US.

If = means equals, != means not equals

## Question 2
List the average total invoice of the top 5 Cities from highest to lowest. Display the city and the average total of the city.


## Question 3
How many albums does each artist have? Include the Artist name and number of albums the artist has.


## Question 4
Display the invoices that were created in the year of 2013 and the month of January where the total price is over 2 dollars.

When selecting dates, you need to use `strftime('<DateFormat>', <ColumnName>)`.

| Format | Description |
|---|---|
|  %d | day of month: 00  |
|  %f | fraction seconds: SS.SSS  |
|  %H | hour: 00-24 |
|  %j | day of year: 001-366  |
|  %J | Julian day number  |
|  %m | month: 01-12  |
|  %M | minute: 00-59  |
|  %s | seconds since 1971-01-01  |
|  %S | seconds: 00-59  |
|  %w | day of week 0-6 with Sunday == 0  |
|  %W | week of year: 00-53  |
|  %Y | year: 0000-9999  |


## Question 5
Display every track that has "Jazz" as the genre.


## Question 6
Display the total invoice amount for each year from lowest grossing to highest grossing total.

## Resources
[More Practice](https://github.com/JeremyCSwain/Chinook-SQL-Exercise/blob/master/chinook.md)