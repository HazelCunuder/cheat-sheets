# SQL CheatSheet

## Table of Content

## Introduction

What's SQL? It stands for Structured Query Language.

It allows to organize, sort and manipulate data from a relational database.

### Relational Databases

- Collection of 2D tables, similar to Excel spreadsheets.

***Example***: A relational db for the Department of Motor Vehicles

| Id | Make/Model | # Wheels | # Doors | Type |
|:---:|:---:|:---:|:---:|:---:|
|1|Ford Focus| 4 | 4 | Sedan |
|2|Tesla Roadster| 4| 2 | Sports |

You could also find related db with names of all registered drivers, driving license types etc...

Goal of SQL is answering specific question about the data.

## Basic commands

- Create a new table: `CREATE table`
- Delete a table: `DROP table`
- Delete a line from table: `DELETE line`
- Update a line: `UPDATE line`

CRUD = Create, Read, Update, Delete

## Queries

- `SELECT` --> Statement that declares the data we are looking for, where to find it in the db and maybe how to transform it before returning.

Using it returns a copy of the original table, but only with the requested columns.

- You can do `SELECT * FROM *tablename*` to select all columns in the table.

### Queries with Constraints

- `WHERE` allows you to add conditions to your query.

- Multiple keywords can be used to make more complex conditions:
  - `AND`
  - `OR`
  - `IN`
  - `BETWEEN`
  - `NOT`
  - As well as numerical operators.

Makes result more manageable to understand and returns results faster.

- You can use special operators in order to do pattern matching and case insensitive string comparison
  - `=` Case sensitive STRICT string comparison.
  - `!= or <>` Case sensitive STRICT string inequality comparison.
  - `LIKE` Case insensitive STRICT string comparison.
  - `NOT LIKE` Case insensitive STRICT string inequality comparison.
  - `%` Used anywhere in a string to match a sequence of zero or more chars (only with LIKE and NOT LIKE) (e.g. col_name LIKE "%AT%", will accept any string with "at" in it)
  - ` -` Used anywhere in a string to match a sequence of a single char (only with LIKE and NOT LIKE) (e.g. col_name LIKE "AN_", will accept AND, but not AN)

- Better to use dedicated libraries for full text search.

## Filter and sort Query results

- Data is unique, but result of query may not be.
  - `DISTINCT` removes duplicate column values.

### Ordering results

- You can use `ORDER BY` to order the result in either `ASC`ending or `DESC`ending order.
  - Sorts by alphanumerical order based on the value.

### Limiting results to subset

- `LIMIT` reduces the number of rows to return.
- `OFFSET` specifies where to begin counting the rows from.

## Multitable queries

### Database normalization

- Minimize duplicate data in any table and allows for data to grow independently from one another.
  - Makes query a bit more complex since you may need to find data from different parts of the db.

- If we need to answer a question about an entity whose data spans multiple tables, we need a way to combine all the data and pull only the info we need.

## Multi-table queries with `JOIN`s

- If tables share info about one entity, they need a ***primary key*** which will identify the *unique* entity all across the database.
  - The key can be anything as long as it is ***unique***

- `JOIN` is a clause used to combine data from rows of 2 different tables using the previously mentionned key. Utiilizing `ON` to specify the key.
  - `INNER JOIN` matches rows from 1st and 2nd table to create a result row with combined columns from both tables.
  - If data is asymmetric across both table, we have 3 JOIN clauses to ensure the needed data isn't left out. (May need to add logic for NULL cases)
    - `LEFT JOIN` includes rows from A regardless of where matching row is found in B
    - `RIGHT JOIN` is same as previous, but reversed.
    - `FULL JOIN` means that rows from both tables are kept, regardless of if there's a matching row on the other table.

## Nulls

- Try to avoid NULL returns as much as possible
  - An alternative is having data type appropriate default values.

- If NULL is unavoidable, we can test for NULL values by using a WHERE clause and using either the `IS NULL` or  `IS NOT NULL` constraint.

## Queries with expressions

- You can also use expressions to write more complex logic on column values in a query. They can be used to transform the values when the query is executed.

- Use of expression can save time, by not needing to post process the data, but it can make the query harder to read. So you can use the `AS` keyword to give the expression a descriptive alias.

## Queries with aggregates

- SQL also accepts functions that allows you to summarize info about a group of rows or data.
  - Without specified grouping, each aggregate function is going to run on the whole set of result rows and return a single value.
  - Just like normal expression, it's better to give them an alais to keep the result easier to read and process.

### Common aggregate functions

- `COUNT(*), COUNT(column)`: Count number of rows in group if no column name is specified, otherwise count number of rows in group with non-NULL values in column.
- `MIN(column), MAX(column)`: Find smallest or largest numerical value in specified column for all rows in group.
- `AVG(column), SUM (column)`: Find average or sum of all numerical value in specified column for all rows in group.

### Grouped aggregate functions

- You can also apply the aggregate functions to individual groups of data within the group.
  - Creates as many results as there are unique groups, defined by `GROUP BY`clause.

- We can use `HAVING` in order to filter grouped rows with conditions. It goes hand in hand with the previously mentioned GROUP BY clause, to allow us to filter grouped rows from the result set.
  - `HAVING` clause constraints are written in the same way as `WHERE`clause constraints.
