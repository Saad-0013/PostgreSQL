# NOTES FOR SQL

### To access database 

```bash
psql --username=freecodecamp --dbname=postgres
```

### To view an existing database

```bash
\l
```

### Creating a new database in PSQL

```SQL
CREATE DATABASE database_name;
```

### The SELECT keyword

```SQL
SELECT attribute_name FROM table_name;
```

Printing multiple items

```SQL
SELECT name, city, country FROM people;
```

### The DISTINCT keyword

```SQL
SELECT DISTINCT language from world;
```
### The COUNT keyword

```SQL
SELECT COUNT(*) from people;
```

### The AS keyword

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
### The Limit keyword

Limiting the size of the output column 
```SQL
SELECT name FROM people LIMIT 10;
```

### Using COUNT and DISTINCT together

```SQL
SELECT COUNT(DISTINCT language) FROM films;
```

### The WHERE keyword

In SQL, the WHERE keyword allows you to filter based on both text and numeric values in a table. There are a few different comparison operators you can use:

= equal <br>
<> not equal <br>
< less than <br>
\> greater than <br>
<= less than or equal to <br>
\>= greater than or equal to <br>

### The AND keyword

The AND keyword is used with the WHERE keyword, where multiple conditions are required to filter the output

```SQL
SELECT title, release_year
FROM films
WHERE language = 'Spanish' 
AND release_year < 2000;
```

### The OR keyword

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

#### Example # 2

```SQL
SELECT title, release_year
FROM films
WHERE (release_year BETWEEN 1990 AND 2000)
AND (budget > 100000000)
AND (language = 'Spanish' OR language = 'French');
```

### The BETWEEN keyword

We can change multiple conditional statements to single statements using the BETWEEN keyword. 
BETWEEN is used to filter values in a specified range. 
For Example

```SQL
SELECT title
FROM films
WHERE release_year >= 1994
AND release_year <= 2000;
```

Can be written as 

```SQL
SELECT title
FROM films
WHERE release_year
BETWEEN 1994 AND 2000;
```

### The WHERE IN keyboard

If we want to specify a discontinuous range such as [1,2,5,7,8] we can use the IN keyword.

```SQL
SELECT name 
FROM table
WHERE age in (2,4,6,14,20);
```

### The IS NULL keyword

NULL represents missing values in the data.

```SQL
SELECT * 
FROM table 
WHERE birthdate IS NULL;
``` 

### The LIKE and NOT LIKE keywords

1. In SQL, the LIKE operator can be used in a WHERE clause to search for a pattern in a column. To accomplish this, you use something called a wildcard as a placeholder for some other values. There are two wildcards you can use with LIKE:

The % wildcard will match zero, one, or many characters in text. For example, the following query matches companies like 'Data', 'DataC' 'DataCamp', 'DataMind', and so on.

```SQL
SELECT name
FROM companies
WHERE name LIKE 'Data%';
```
>output: Datacamp, Datasite, DataScience

2. The _ wildcard will match a single character. For example, the following query matches companies like 'DataCamp', 'DataComp', and so on:

```SQL 
SELECT name
FROM companies
WHERE name LIKE 'DataC_mp'; 
```

```SQL
SELECT name
FROM people 
WHERE name 
LIKE '_r%';
```

## Aggregate Functions

Aggregate Functions include:
- AVG - Average
- MAX - Maximum
- MIN - Minimum
- SUM - Summation

## More on the AS keyword
```SQL
SELECT MAX(budget), MAX(duration)
FROM films;
```

Well, Now you have two columns named max, which isn't very useful!

To avoid situations like this, SQL allows you to do something called aliasing. Aliasing simply means you assign a temporary name to something. To alias, you use the AS keyword, which you've already seen earlier in this course.

For example, in the above example we could use aliases to make the result clearer:

```SQL
SELECT MAX(budget) AS max_budget,
       MAX(duration) AS max_duration
FROM films;
```

Aliases are helpful for making results more readable!

```SQL
SELECT title, (gross-budget) AS net_profit
FROM films;
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

4. SQL assumes that if you divide an integer by an integer, you want to get an integer back. So be careful when dividing!
If you want more precision when dividing, you can add decimal places to your numbers. For example,
```SQL 
SELECT (4.0 / 3.0) AS result;
```


