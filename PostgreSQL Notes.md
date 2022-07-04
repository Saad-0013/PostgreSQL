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

# Notes about SQL

1. SQL stand for Structured Query Language 
2. It is used for interacting with data stored in a relational database
    - You can think of a relational database as a collection of tables 
        - A table is a set of rows and columns
            - Each Row is called a record of the table
            - Each column is called a field of the table 
            



