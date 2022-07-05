# NOTES FOR SQL

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

= equal <br>
<> not equal <br>
< less than <br>
\> greater than <br>
<= less than or equal to <br>
\>= greater than or equal to <br>

## The AND keyword

The AND keyword is used with the WHERE keyword, where multiple conditions are required to filter the output

```SQL
SELECT title, release_year
FROM films
WHERE language = 'Spanish' 
AND release_year < 2000;
```

## The OR keyword

The OR keyword is also used with the WHERE keyword and is used to filter the output by using it to specify the filtering conditions.
> Note: You need to specify the column name for every OR condition

```SQL
SELECT title
FROM films
WHERE release_year = 1994
OR release_year = 2000;
```

When combining AND and OR be sure to use parentheses to make the conditions more readable like done below.

```SQL
SELECT title
FROM films
WHERE (release_year = 1994 OR release_year = 1995)
AND (certification = 'PG' OR certification = 'R');
```  

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


