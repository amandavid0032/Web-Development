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
```
