# SQL CheatSheet

## Table of Content

- [Introduction](#introduction)
  - [Relational Databases](#relational-databases)
- [Basic commands](#basic-commands)
- [Queries](#queries)
  - [Queries with Constraints](#queries-with-constraints)
- [Filter and sort Query results](#filter-and-sort-query-results)
  - [Ordering results](#ordering-results)
  - [Limiting results to subset](#limiting-results-to-subset)
- [Multitable queries](#multitable-queries)
  - [Database normalization](#database-normalization)
- [Multi-table queries with JOINs](#multi-table-queries-with-joins)
- [Nulls](#nulls)
- [Queries with expressions](#queries-with-expressions)
- [Queries with aggregates](#queries-with-aggregates)
  - [Common aggregate functions](#common-aggregate-functions)
  - [Grouped aggregate functions](#grouped-aggregate-functions)
- [Execution order of a query](#execution-order-of-a-query)
  - [Order of execution](#order-of-execution)
- [Inserting rows](#inserting-rows)
  - [Schemas](#schemas)
  - [Inserting new data](#inserting-new-data)
- [Updating rows](#updating-rows)
  - [Taking care](#taking-care)
- [Deleting Rows](#deleting-rows)
  - [Taking extra care](#taking-extra-care)
- [Create new tables](#create-new-tables)
  - [Table data types](#table-data-types)
  - [Table constraints](#table-constraints)
- [Altering tables](#altering-tables)
  - [Adding columns](#adding-columns)
  - [Removing column](#removing-column)
  - [Renaming table](#renaming-table)
- [Dropping tables](#dropping-tables)
- [Subqueries](#subqueries)

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

## Execution order of a query

- Each query begins finding data and then filters it into something that can be processed as quickly as possible.

### Order of execution

1. `FROM` and `JOIN`: Execute first to detemrmine total working set of data to query? Also includes subqueries in the clause. --> May create temporary tables to contain columns and rows being joined.

2. `WHERE`: Once we have the data we'll work on, `WHERE` constraints are applied to the rows and it discards rows that don't meet the constraints. Can only access columns requested in the `FROM` clause.

3. `GROUP BY`: Remaining rows after where constraint are applied are grouped based on common values in column specified in `GROUP BY` clause. Many unique rows as there are unique values in that column.  Only use if there are aggregated functions in the query.

4. `HAVING`: If query has `GROUP BY` clause --> `HAVING` clause applied to grouped rows and discard ones not matching.

5. `SELECT`: Expression in select are computed.

6. `DISTINCT`: Remove duplicate values.

7. `ORDER BY`: If order specified, apply it now. Since it happens after SELECT, you can ref aliases here.

8. `LIMIT/OFFSET`: Rows that fall outside of range specified are discarded.

## Inserting rows

### Schemas

- A db schema is what describes the structure of each table and the datatypes that each table can contain.

### Inserting new data

- `INSERT INTO` statement: used to declare which table to write into, the colums of data we put into it and the rows to insert.

- In general, each row of data you insert need to contain values for every column in the table. --> You can add multiple rows at once.

- If you have incomplete data, you can specify the column you want to insert the data into (ONLY IF TABLE CONTAINS COLUMNS WITH DEFAULT VALUES)
  - Number of values need to match --> nb of columns specified.

- Can use mathematical and string expressions with inserted values. Can be used to format data a certain way.

## Updating rows

- `UPDATE` --> Modify existing data, specify exactly which table, column and row to update.

- `SET`: Select the columns and rows you want to update.

- `WHERE`: Can be used to put a condition on the update.

### Taking care

- You ***will*** make mistakes at some point, so be very careful with `UPDATE` statements.

> ALWAYS WRITE CONSTRAINT FIRST AND TEST IT WITH A `SELECT` QUERY.

## Deleting Rows

- `DELETE FROM`: Statement to delete data from db, needs a condition with `WHERE`statement (If you want to wipe an entire table, you can forego the `WHERE` constraint)

### Taking extra care

> Same recommendations as before, but even more so if you don't have a backup. READ TWICE, DELETE ONCE.

## Create new tables

- If you have new entities and relationships to add to your db, you can create a new table with `CREATE TABLE`.
  - You can skip creating a new table if one with that name already exists by adding `IF NOT EXISTS` to the `CREATE TABLE` statement.

- The structure is defined by its schema.
  - Each column has a name, a datatype, and an optional constraint on value being inserted, as well as a potential default value (indicated with `DEFAULT`)

### Table data types

| BOOLEAN, INTEGER | FLOAT, DOUBLE, REAL | CHARACTER(num_chars), VARCHAR(num_chars), TEXT | DATE, DATETIME | BLOB |
| :---: | :---: | :---: | :---: | :---: |
| Whole int values, in some implementations, bool is represented as int 0 and 1 | Stores precise numerical data | Stores strings (CHAR and VARCHAR specified with max number of chars to make it more space efficient) | Stores date and timestamps (may cause problems when working accross timezones) | Stores binary data in blobs, opaque to the db |

### Table constraints

| PRIMARY KEY | AUTOINCREMENT | UNIQUE | NOT NULL | CHECK(expression) | FOREIGN KEY |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Values in column are unique and value can be used to id a single row in table | Only for int values, value automatically increases with each row insertion, not supported everywhere | Values in column have to be unique (doesn'tt have to be a key) | Value cannot be null | Run a more complex expression to test valid values | Checks if value in the column match another value in another table |

## Altering tables

- Possible to update table schema over time by using `ALTER TABLE`statement.

### Adding columns

Similar syntax to creating new rows. MySQL allows to specify where precisely to insert column.

```sql
ALTER TABLE mytable
ADD column DATATYPE OptionalTableConstraint
  DEFAULT default_value;
```

### Removing column

You remove columns by using the `DROP` statement. Some db don't support this feature, so need to create new db and migrate the data over to the new db.

```sql
ALTER TABLE mytable
DROP column_to_be_deleted;
```

### Renaming table

- `RENAME TO`: Allows you to change table name if need to

```sql
ALTER TABLE mytable
RENAME TO new_table_name;
```

## Dropping tables

- `DROP TABLE`: allows you to remove an entire table and all its data and metadata. Unlike `DELETE` it also removes the table schema from the db.

```sql
DROP TABLE IF EXISTS mytable;
```

- If other table dependant on colums in table you are removing --> Need to update all dependant tables first, or remove them as well.

## Subqueries

- Can be referenced anywhere a normal table can be referenced.

- In `FROM`clause, you can `JOIN` subqueries with other tables.

- You can also test expressions against the results of a subquery.

- Executed in same order as described before.

> Each subquery need to be in parenthesis to establish proper hierarchy.
