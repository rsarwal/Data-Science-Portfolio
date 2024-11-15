# SQL Chinook Database Analysis

## Overview
This project demonstrates SQL querying skills using the Chinook database, which represents a digital media store. It includes a series of analytical queries exploring various aspects of the business, from customer demographics to sales patterns and artist performance.

## Table of Contents
- [Data Source](#data-source)
- [Queries and Analysis](#queries-and-analysis)
- [Key Findings](#key-findings)
- [Tools Used](#tools-used)
- [How to Run](#how-to-run)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Data Source
The Chinook database is a sample database available for SQL practice. It can be found at [Chinook Database GitHub Repository](https://github.com/lerocha/chinook-database).

## Queries and Analysis

### 1. US Customers
Retrieves all customers from the USA.

```sql
SELECT FirstName, LastName, Country
FROM Customer
WHERE Country = 'USA';

### 1. US Customers
This query retrieves all customers from the USA.

```sql
SELECT FirstName, LastName, Country
FROM Customer
WHERE Country = 'USA';
```

### 2. Customer Invoices
This query joins the Customer and Invoice tables to show each customer's invoice totals.

```sql
SELECT c.FirstName, c.LastName, i.Total
FROM Customer c
INNER JOIN Invoice i ON c.CustomerId = i.CustomerId;
```
### 3. Genre Sales
This query calculates total sales for each music genre.
```sql
SELECT Genre.Name AS Genre, SUM(il.UnitPrice * il.Quantity) AS TotalSales
FROM InvoiceLine il
JOIN Track ON il.TrackId = Track.TrackId
JOIN Genre ON Track.GenreId = Genre.GenreId
GROUP BY Genre.Name
ORDER BY TotalSales DESC;
```
### 4. Top 10 Spending Customers
This query identifies the top 10 customers by total amount spent.
```sql
SELECT c.FirstName, c.LastName, SUM(Invoice.Total) AS TotalSpent
FROM customer c
JOIN Invoice ON c.CustomerId = Invoice.CustomerId
GROUP BY c.CustomerId
ORDER BY TotalSpent DESC
LIMIT 10;
```
### 5. Monthly Sales
This query shows total sales for each month.
```sql
SELECT DATE_FORMAT(InvoiceDate, '%Y-%m') AS Month, SUM(Total) AS MonthlySales
FROM Invoice
GROUP BY Month
ORDER BY Month;
```
### 6. Top 5 Artists by Total Sales
This query identifies the top 5 artists by their total sales.
```sql
SELECT Artist.Name, SUM(InvoiceLine.UnitPrice * InvoiceLine.Quantity) AS TotalSales
FROM Artist
JOIN Album ON Artist.ArtistId = Album.ArtistId
JOIN Track ON Album.AlbumId = Track.AlbumId
JOIN InvoiceLine ON Track.TrackId = InvoiceLine.TrackId
GROUP BY Artist.ArtistId
ORDER BY TotalSales DESC
LIMIT 5;
```

### 7. Average Track Length by Genre
This query calculates the average track length for each genre.
```sql
SELECT Genre.Name, AVG(Track.Milliseconds)/1000 AS AvgLengthSeconds
FROM Genre
JOIN Track ON Genre.GenreId = Track.GenreId
GROUP BY Genre.GenreId
ORDER BY AvgLengthSeconds DESC;
```

### 8. Customers Who Have Spent More Than Average
This query identifies customers who have spent more than the average total spend.
```sql
WITH AvgSpend AS (
    SELECT AVG(TotalSpent) AS AvgTotalSpent
    FROM (
        SELECT CustomerId, SUM(Total) AS TotalSpent
        FROM Invoice
        GROUP BY CustomerId
    ) AS CustomerTotals
)
SELECT c.FirstName, c.LastName, SUM(i.Total) AS TotalSpent
FROM Customer c
JOIN Invoice i ON c.CustomerId = i.CustomerId
GROUP BY c.CustomerId
HAVING TotalSpent > (SELECT AvgTotalSpent FROM AvgSpend)
ORDER BY TotalSpent DESC;
```
