# Joining Data in SQL

## The INNER JOIN 

Only includes records in which the key is located in both of the tables

### Syntax

```SQL
SELECT *
FROM left_table
INNER JOIN right_table
ON left_table.id = right_table.id;
```

### Sample Code

```SQL
SELECT p1.country, p1.continent, 
       prime_minister, president
FROM prime_minister as p1
INNER JOIN president as p2
on p1.country = p2.country;
```

## Joining multiple tables 

### Sample Code

```SQL
SELECT *
FROM left_table
  INNER JOIN right_table
    ON left_table.id = right_table.id
  INNER JOIN another_table
    ON left_table.id = another_table.id;
```

```SQL
-- Select fields
SELECT c.code, name, region, e.year, fertility_rate, unemployment_rate
  -- From countries (alias as c)
  FROM countries AS c
  -- Join to populations (as p)
  INNER JOIN populations AS p
    -- Match on country code
    ON c.code = p.country_code
  -- Join to economies (as e)
  INNER JOIN economies AS e
    -- Match on country code and year
    ON (c.code = e.code) AND (e.year = p.year);
```

## The USING keyword

If the attribute on which join is being performed; has the same name in both the tables then we can use the USING keyword to perform the join.

## SELF JOIN

```SQL
SELECT p1.country, p2.country, p1.continent
FROM countries as p1
INNER JOIN countries as p2
ON p1.continent = p2.continent;
```

## The CASE WHEN and THEN keywords

<b><u>CASE:</u></b><br>
CASE can be thought of as IF and ELSE conditional statements.

### Sample Code

```SQL
SELECT name, contient, year
    CASE WHEN year < 1900 THEN 'before 1900'
    WHEN year <= 1930 THEN 'after 1930'
    ELSE 'after 1930' END
    AS year_group
FROM table_name
ORDER BY year_group;
```



### Sample Code

```SQL
SELECT  left_table.id AS L_id,
        left_table.val as L_val,
        right_table.val as R_val

FROM left_table
INNER JOIN right_table
USING (id);
```
       

