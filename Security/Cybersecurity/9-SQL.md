Database : an organized collection of information or data
- Accessed by multiple people simultaneously
- Store massive amounts of data
- Perform complex tasks while accessing data.

Spreadsheets:
- Designed for a single user or small team
- Store less data

## Relational database:
A structured database containing tables that are related to each other.

It consists of tables, and these tables are related to each other.
- every table has its data.

we can connect two tables if they share a common column.
The column that relate two tables to each other are called **keys**

 ### There are 2 types of keys
 - primary key : every row has a unique entry (no null or empty) - Max one per table.
 - foreign key: it is a column in a table that is a primary key in another table. (Can have an empty and duplicated values)

## SQL : Structured Query Language
A programming language used to create, interact with, and request information from a database.

**Query**: A request for data from a database table or a combination of tables.
**Log** is a record of events that occur within an organization's systems.

### Queries
- **SELECT**
Indicates which columns to return
- **FROM**
Indicates which table to query

> SELECT column FROM table;

Syntax: The rules that determine what is correctly structured in a computing language.
- SQL is not case sensitive
- * is for all

- **ORDER BY**: to sort the records based on the column
	- Default is Ascending
	- DESC: descending.
	- Multiple columns
``` sql
SELECT customerid, city, country
FROM customers
ORDER BY city DESC;
```

#### Filtering
Selecting data that match a certain condition
- **WHERE**
#### Operator
A symbol or keyword that represents an operation
- equal to =
- greater then >
- less than <
- not equal to <>
- greater than or equal to >=
- less than or equal to <=

``` sql
SELECT * FROM log_in_attempts WHERE country = 'USA';
```

- **wildcard %, _, __**
To search for a pattern 
``` sql
'a%'  -> apple123, art, a
'%a%' -> pizza, add, 1ac
'a_'  -> am, an, a7
'_a_' -> car, ban. ea7
'a__'  -> amr, ana, a70
'__a__'  -> 1tamr, maana, pla70
``` 

but wildcard patten can't be used with = operator, so we need to use LIKE

- **LIKE** 
Used with WHERE to search for a pattern in a column.
WHERE office LIKE 'East%'

``` sql
SELECT * FROM log_in_attempts WHERE country LIKE 'US%';
```

## Database Data types
- String
- Numeric
- Date and time
- NULL

**String** data consisting of an ordered sequence of characters.
numbers, letters, or symbols
**Numeric** data consisting of numbers, for mathematical operations.
**Date and time** data representing a date and/or time

- **BETWEEN**
An operator that filters for numbers or dates within a range.
``` sql
SELECT *
FROM machines
WHERE OS_patch_date
BETWEEN '2021-03-01' AND '2021-09-01';
```

> Filtering must use quotation marks for string and data, time, but not for numbers.

- **AND**
Specifies that both conditions must be met simultaneously.
``` sql
SELECT *
FROM machnies
WHERE operating_system = 'OS 1'
AND email_client = 'Email Client 1';
```

- **OR**
Specifies that either condition can be met
``` sql
SELECT *
FROM machnies
WHERE operating_system = 'OS 1'
OR email_client = 'Email Client 1';
```

- **NOT**
Negates a condition
``` sql
SELECT *
FROM machnies
WHERE NOT operating_system = 'OS 3';
```

- **JOIN**
It is the way to query 2 or more tables data.
first use the primary key from one table with the foreign key from the second table.
	- INNER JOIN
	Returns rows matching on a specified column that exists in more than one table.
``` sql
SELECT username, office, operating_system
FROM employees
INNER JOIN machine ON employees.employees_id = machine.employee_id;
```

- Outer Join: combine 2 tables without common column.
	- LEFT JOIN
	- RIGHT JOIN
	- FULL OUTER JOIN

**LEFT JOIN**: Returns all of the records of the first table, but only returns rows of the second table that match on a specified column.
``` sql
SELECT *
FROM employees
LEFT JOIN machines ON employees.device_id = machines.device_id;
```

**RIGHT JOIN**: Returns all of the records of the second table, but only returns rows of the first table that match on a specified column.
``` sql
SELECT *
FROM employees
RIGHT JOIN machines ON employees.device_id = machines.device_id;
```

**FULL OUTER JOIN**: returns all records form both tables.
``` sql
SELECT *
FROM employees
FULL OUTER JOIN machines ON employees.device_id = machines.device_id;
```

> Inner joins only return rows that match on a specified column, but outer joins also return rows that don't match on the specified column.

### Aggregate functions
- **COUNT** numbers of rows 
- **AVG** Average of numerical data in column
- **SUM** sum of numerical data

``` sql
SELECT COUNT(firstname)
FROM customers;
```