# NOTES FOR POSTGRESQL from FreeCodeCamp

## To access database 

```bash
psql --username=freecodecamp --dbname=postgres
```

## To view an existing database

```bash
\l
```

## Creating a new database in PSQL

```SQL
CREATE DATABASE database_name;
```

## The SELECT keyword

```SQL
SELECT attribute_name FROM table_name;
```

Printing multiple items

```SQL
SELECT name, city, country FROM people;
```

## The DISTINCT keyword

```SQL
SELECT DISTINCT language from world;
```
## The COUNT keyword

```SQL
SELECT COUNT(*) from people;
```

## The AS keyword

1. The AS keyword can be used to create an alias of the table that will only exist for the duration of the querry.
2. The AS command is used to rename a column or table with an alias.
3. An alias only exists for the duration of the query.

```SQL
SELECT CUSTOMER_NAME AS CUSTOMER
FROM Table_Name;
```

If the alias name contains a space then we use the square bracket

```SQL
SELECT CUSTOMER_NAME AS [CUSTOMER NAME]
FROM Table_Name;
```
## The Limit keyword

Limiting the size of the output column 
```SQL
SELECT name FROM people LIMIT 10;
```

## Using COUNT and DISTINCT together

```SQL
SELECT COUNT(DISTINCT language) FROM films;
```

## The WHERE keyword

In SQL, the WHERE keyword allows you to filter based on both text and numeric values in a table. There are a few different comparison operators you can use:

= equal
<> not equal
< less than
/> greater than
<= less than or equal to
/>= greater than or equal to

# Notes about SQL

1. SQL stand for Structured Query Language 
2. It is used for interacting with data stored in a relational database
    - You can think of a relational database as a collection of tables 
        - A table is a set of rows and columns
            - Each Row is called a record of the table
            - Each column is called a field of the table 
3. Keywords in SQL are not case sensitive
```SQL
SELECT name 
from table_name;
```
can also be written as
```SQL
select name
from table_name;
```


