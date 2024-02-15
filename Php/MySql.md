## 📔 OOPS With PHP

## 📘 Developer Responsibility
* Write good code so everyone can read and understand easily.
* the harder is to understand code and to reason about the code the more difficult it will be to add new features add to more the functionality to the * * * application. Hence it is called bad code.
* An important part of web-development is actually handle the errors. because its very common that errors happen in web-application.
* To test APi use Network tab with various Throttling options fast/slow/offline
---
## 📘 What id database

1.Database is a collection of data stored in a format(tabular Form) that can easily be accessed and related Data

2.Database store infromation in a organised manner in the form of a table 

3.A database management system can be used to handle the data in a database 

4.A database can contain duplicate records in tables if the database is not normalized and table are not indexed 

5.You can normalized the database and index the table to eliminate redundancy and enhance the speed of data search and interval operations 

---
## 📘 What is DBMS
a. A database store data in a structural format. A Database managment is responnsible to store, access and delete data fro ma database in short manner it is 	a systme that can be used to handle the data in 
a database 

b. is a software program that stores and manage databases 

c. is Responsible for managing the various database opertaions 

 1. Adding 
	
 2. accessing 

 3. Processing of Data

d. Helps to manage data in two ways 

 1. by providing an interface to manage data (php myadmin)

 2. by supporting connectivity to the other application that can be used to manage data (php mysql quries) 	
	
e. Mysql is an open source RDBMS, it was developed and distributed by MySql AB (orginization), which is now owned by oracle 	

***
**String Datatype in mysql**
 ![Screenshot (308)](https://github.com/amandavid0032/Web-Development/assets/86879390/7ef7edd8-130b-4c9f-9c29-cc5d9e69a5a4)
***
**Number Datatype  in mysql**
![Screenshot (309)](https://github.com/amandavid0032/Web-Development/assets/86879390/a634ce60-20a1-45a8-8a44-ef6f1ac11b09)
***
**Date & Time Datatye in mysql**
![Screenshot (310)](https://github.com/amandavid0032/Web-Development/assets/86879390/c1844faf-5e68-45d6-9030-de9800759630)
***
```php
// How to create the table
CREATE TABLE Table_name(
    id INT,
    name VARCHAR(50),
    birth_date DATE,
    Phone VARCHAR(20)
);
```
***
```php
USE my_new_db;
	CREATE TABLE employee(
		id int PRIMARY KEY AUTO_INCREMENT,
		Employee_name varchar(50) NOT NULL,    
		age int NOT NULL,
		gender varchar(50) NOT NULL,
		desigination varchar(50) not null,
		salary int NOT null
	)ENGINE=INNODB;
```
***
---
## 📘 Insert Query
Insert into 	// this statment is used to insert new records in a table 
	
1.insert into have two ways to insert 
	
a. insert into table(column_name1,column_ name2...) values(value1,value2,....)	
	
b. insert into table values (value1,value2,.......)

**Inserting specific values into specific columns**
```php
INSERT INTO Table_name(column_name1, column_name2, column_name3) 
VALUES (value1, value2, value3);

INSERT INTO Table_name(id, name, birth_date, Phone) 
VALUES (1, 'John Doe', '1990-05-15', '123-456-7890');
```
***
**Inserting values into all columns in the table:**
```php
INSERT INTO Table_name 
VALUES (value1, value2, value3, ...);

INSERT INTO Table_name 
VALUES (2, 'Jane Smith', '1985-09-20', '987-654-3210');

```
***
**Inserting Multiple value**
```php
INSERT INTO Table_name (column_name1, column_name2, column_name3)
VALUES 
(value1_row1, value2_row1, value3_row1),
(value1_row2, value2_row2, value3_row2),
(value1_row3, value2_row3, value3_row3);

// With table
INSERT INTO Table_name (id, name, birth_date)
VALUES 
(3, 'Alice Johnson', '1988-12-10'),
(4, 'Bob Brown', '1995-07-25'),
(5, 'Emily Davis', '1992-03-18');

```
---
## 📘 Constraints
Constraints in databases are rules or conditions applied to a table column or a group of columns.It's help to data don't come empty or what condtion is on data itss work on that base 
![Screenshot (311)](https://github.com/amandavid0032/Web-Development/assets/86879390/1ead4c19-5524-4be1-be94-a28daf15c44c)
***
**Example**
```php
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
    email VARCHAR(100) UNIQUE
);
```
## 📘 Select 
Select query always gives result in the form of result set 
	
Select is use to Display Data
```php
// Slelct all the data
SELECT * FROM table_name;

// Without condtion or choose spcific data 
SELECT column1, column2 FROM table_name;

// data with condition 
SELECT column1, column2 FROM table_name WHERE condition; 

// AS
SELECT id AS i,name AS "Sname" FROM table_name
```
***
**And**

AND Condition: The AND condition is used to retrieve rows that meet all specified conditions.
```php
SELECT column1, column2 FROM table_name WHERE condition1 AND condition2;

SELECT * FROM Employees WHERE department = 'Sales' AND salary > 50000;
```
***
**Or**

OR Condition: The OR condition is used to retrieve rows that meet at least one of the specified conditions.
```php
SELECT column1, column2 FROM table_name WHERE condition1 OR condition2;

SELECT * FROM Employees WHERE department = 'Sales' OR department = 'Marketing';
```
**In**

IN Condition: The IN condition is used to retrieve rows where a specified column value matches any value in a list.
```php
//Sql
SELECT column1, column2 FROM table_name WHERE column_name IN (value1, value2, ...);

//Example
SELECT * FROM Employees WHERE department IN (20,19); // it's search data between in this value and give only data which match this condtion

SELECT * FROM Employees WHERE department IN ('Sales', 'Marketing');

```
***
**NOT IN**

NOT IN Condition: The NOT IN condition is used to retrieve rows where a specified column value does not match any value in a list.
```php
//sql
SELECT column1, column2 FROM table_name WHERE column_name NOT IN (value1, value2, ...);

//Example
SELECT * FROM Employees WHERE department NOT IN ('Sales', 'Marketing');


SELECT * FROM Employees WHERE department NOT IN (20,19); // it's don't show data which meet this conditon
```
***
**Between**

BETWEEN: This operator selects values within a specified range, including the endpoints.
```php
SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2;

//Example
SELECT * FROM products WHERE price BETWEEN 10 AND 50;
```
***
**Not Between**

NOT BETWEEN: This operator selects values outside a specified range.
```php
SELECT column_name(s) FROM table_name WHERE column_name NOT BETWEEN value1 AND value2;

//Example
SELECT *FROM employees WHERE age NOT BETWEEN 25 AND 40;

```
***
**Like**
1.The term "like" in SQL is used in a word used to connect sentences or to coordinate words in the same clause (e.g. and, but, if). with the WHERE clause to search for a specified pattern within a column.

2.like is commonly used to select data based on patterns 

3.Like operator is often used in the where clause of the Select Statment

4.Like operator in the right way is essential to increse the query performance 

**wildCard Characters** 

a. % (Percentage sign)-> % wildcard allows you to match any string of zero or more characters 

b. _ (Underscore)-> 	_ wildcard allows you to match any single charcter
***
![Screenshot (314)](https://github.com/amandavid0032/Web-Development/assets/86879390/4aa8a09b-d5ec-4a1f-99bc-ec99ee590d7f)
***
```php
SELECT column1, column2 FROM table_name WHERE column_name LIKE pattern;

//Example
SELECT * FROM tableName where name LIKE 's%' ==> Select those chracter which start with s letters after that select all 

SELECT * FROM tableName where name NOT  LIKE 's%'

SELECT * FROM tableName where BINARY name LIKE 's%' (to make case-sensitivity)

```
***
**Regular Expression**
1.It is advance over like query for search
2.In SQL, regular expressions are used to perform more complex pattern matching operations on strings. However, not all database systems support regular expressions directly in SQL queries. 
***
![Screenshot (315)](https://github.com/amandavid0032/Web-Development/assets/86879390/0b35799d-2456-4e92-a913-196ea41b808b)
***
```php
SELECT * FROM table_name WHERE column_name REGEXP 'pattern';

//Exmple
SELECT * FROM products WHERE product_name REGEXP '^[A].*'; // check the latter in the begining of the name
```
***
**ORDER BY**

order sql query is use t set show a data in assending or desending oder by dafault it is always assending order
```php
SELECT column1, column2, OR * (For Select all the table)FROM table_name ORDER BY column1 ASC;

//Desc
SELECT *FROM employees ORDER BY  first_name dsc;

```
***
**LIMIT & OFFSET**
 The LIMIT and OFFSET clauses are used together to control the number of rows returned by a query and to specify a starting point for the result set.

Here's how they work:

LIMIT: Specifies the maximum number of rows to return in the result set.

OFFSET: Specifies the number of rows to skip before starting to return rows in the result set.

```php
SELECT * FROM table_name LIMIT number_of_rows OFFSET offset_value;

//Example
SELECT * FROM table_name LIMIT 5(offset),3(limit);
SELECT * FROM table_name LIMIT 5,3;
```
***
**SUM-MAX-MIN-COUNT**

In SQL, you can use aggregate functions like SUM, MAX, COUNT, and MIN to perform calculations on a set of values meeting certain conditions. These functions are often used in combination with the WHERE clause to specify the conditions for the calculation
**SUM:** Calculates the sum of the values in a column that meet the specified condition.
```php
SELECT SUM(column_name) FROM table_name WHERE condition;
```
**MAX:** Retrieves the maximum value from a column that satisfies the given condition.
```php
SELECT MAX(column_name)FROM table_name WHERE condition;
```
**COUNT:** Counts the number of rows that meet the specified condition.
```php
SELECT COUNT(*)FROM table_name WHERE condition;
```
**MIN:** Retrieves the minimum value from a column that satisfies the provided condition.
```php
SELECT MIN(column_name)FROM table_name WHERE condition;
```
---
## 📘 UPDATE
```php
UPDATE table_name SET column1 = value1, column2 = value2, WHERE condition;
```
***
**ROLLBACK and Commit**
a. by default in database commit is enable. 

b. Commit means Save all the changes 

c. commit and role back only works on insert, update, delete
```php
SELECT * FROM `studentrecord` ;
COMMIT;
 UPDATE studentrecord SET f_name='himinshu' WHERE id=172;
ROLLBACK;
```
---
## 📘 DELETE

In SQL, the DELETE statement is used to remove one or more rows from a table.
```php
DELETE FROM table_name WHERE condition;
```
---
## 📘 PRIMARY KEY & FOREIGEN KEY
**PRIMARY KEY**
1.A PRIMARY KEY always has uniquely identifies and data.

2.It ensures that each row in the table is uniquely identifiable and that there are no duplicate values in the specified column(s).

3.By default, a PRIMARY KEY constraint also enforces the NOT NULL constraint, meaning that the values in the specified column(s) cannot be NULL.

4.In most database systems, each table should have a PRIMARY KEY defined to uniquely identify each row.

```php
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```
***
**FOREIGEN KEY**
1.A Foreigen key is key used to link two tables together.

2.A foreigen key in one table used to point primary key in another table
```php
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```
---
## 📘 JOIN
In SQL, a JOIN operation is used to combine rows from two or more tables based on a related column between them. This related column typically represents a foreign key relationship between the tables.
1. Inner Join
2. Left Join (left outer join)
3. Right Join
4. Self Join 
5. Full Outer Join(union operator)
***
**INNER JOIN**
 INNER JOIN is a type of SQL join that retrieves records from two or more tables based on a related column or columns between them. It returns only the rows that have matching values in both tables according to the specified join condition
 ```php
SELECT columns FROM table1 INNER JOIN table2 ON table1.column = table2.column;
```
***
**Left Join**
In SQL, a JOIN operation is used to combine rows from two or more tables based on a related column between them. This related column typically represents a foreign key relationship between the tables.
and it's match the data and if data is not match give an empty value there 
```php
SELECT * FROM table1 INNER JOIN table2 ON table1.column = table2.column;


//Example
SELECT * FROM studentrecord LEFT JOIN   city_record  ON studentrecord.id=city_record.student_id 
```
![Screenshot (316)](https://github.com/amandavid0032/Web-Development/assets/86879390/e34c88b6-4f95-4808-a69d-70fe9eeb189b)
***
**Right Join**
right join return all records  from the right table(table2) and matched records from the left table(table1).
```php
SELECT * FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;

//Example
SELECT * FROM studentrecord Right JOIN city_record ON studentrecord.id=city_record.student_id;
```
![Screenshot (317)](https://github.com/amandavid0032/Web-Development/assets/86879390/c477bf96-c09f-426f-ac3b-2d8bac20dd59)

***
**Cross Join**
A CROSS JOIN is a type of SQL join that combines each row from the first table with each row from the second table, resulting in a Cartesian product of the two tables. In other words, it returns all possible combinations of rows between the two tables.
```php
SELECT columns FROM table1 CROSS JOIN table2;	
```
![Screenshot (319)](https://github.com/amandavid0032/Web-Development/assets/86879390/e79eb2b9-6893-4474-9ce7-383fe951f7a9)
***
**Multiple Join:** You can join multiple tables in a single SQL query by using multiple JOIN clauses. Here's the basic syntax for joining multiple tables:
```php
SELECT *
FROM table1 INNER JOIN table2 ON table1.column = table2.column INNER JOIN table3 ON table1.column = table3.column;
```
---
## 📘 Group By & Having clause
**1.GROUP BY:**

1.The GROUP BY clause is used to group rows that have the same values into summary rows, typically to perform aggregate functions like SUM, COUNT, AVG, etc., on each group.

2.It is often used in conjunction with aggregate functions to group the result set based on one or more columns.
```php
SELECT department, COUNT(*) AS num_employees
FROM employees
GROUP BY department;    //make a group of same condtion 
```
**2.HAVING:**

1.The HAVING clause is used to filter the rows that appear in a GROUP BY clause based on specified conditions.

2.It is similar to the WHERE clause, but while the WHERE clause filters individual rows before the grouping occurs, the HAVING clause filters groups of rows after the grouping occurs.
```php
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```
