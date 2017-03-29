# SQL Workshop #2 Answers

### Aggregations to remember
`COUNT()`

`SUM()`

`MAX`

`MIN`

## Question 1
List the average total invoice of the top 5 Cities from highest to lowest. Display the city and the average total of the city.

```
SELECT BillingCity, ROUND(avg(Total),2) AS AverageTotal
FROM invoices
GROUP BY BillingCity
ORDER BY avg(Total) DESC
LIMIT 5;
```

## Question 2
How many albums does each artist have? Include the Artist name and number of albums the artist owns.

```
SELECT artists.ArtistId, artists.Name, COUNT(AlbumId)
FROM artists JOIN albums ON artists.ArtistId = albums.ArtistId
GROUP BY artists.ArtistId;
```

## Question 3
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

```
SELECT *
FROM invoices
WHERE strftime('%Y', InvoiceDate) = '2013'
  	AND strftime('%m', InvoiceDate) = '01'
GROUP BY InvoiceId
HAVING Total >= 2;
```

## Question 4
Display every track that has "Jazz" as the genre.

```
SELECT tracks.Name, genres.Name
FROM tracks INNER JOIN genres ON tracks.GenreId = genres.GenreId
WHERE genres.Name = "Jazz";
```

## Question 5
Display the total invoice amount for each year from lowest grossing to highest grossing total.

```
SELECT strftime('%Y', InvoiceDate) AS year, SUM(Total)
FROM invoices
GROUP BY strftime('%Y', InvoiceDate)
ORDER BY sum(Total) ASC;
```
