# Data-Science-Portfolio
# SQL Chinook Database Analysis

## Overview
This project analyzes the Chinook database using SQL queries. The Chinook database represents a digital media store, including tables for artists, albums, media tracks, invoices, and customers.

## Data Source
The Chinook database is a sample database available for SQL practice. It can be found at [Chinook Database GitHub Repository](https://github.com/lerocha/chinook-database).

## Queries and Analysis

### 1. US Customers- This query retrieves all customers from the USA.

```sql
SELECT FirstName, LastName, Country
FROM Customer
WHERE Country = 'USA';
