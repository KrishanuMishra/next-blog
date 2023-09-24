---
title: "Database Management System - NPTEL"
subtitle: "This is an article enlisting what and how I prepared for my NPTEL - DBMS Exam."
date: "2023-09-19"
---

- [Why DBMS?](#why-dbms)
- [Levels of Abstraction](#levels-of-abstraction)
- [Schema \& Instance](#schema--instance)
- [Data Models](#data-models)
- [Keys](#keys)
- [Relational Query Operations](#relational-query-operations)
  - [Select](#select)
  - [Projection](#projection)
  - [Set Difference](#set-difference)
  - [Union](#union)
  - [Intersection](#intersection)
  - [Cartesian Product](#cartesian-product)
  - [Types of Joins](#types-of-joins)
    - [1. Inner Join](#1-inner-join)
    - [2. Left Join (or Left Outer Join)](#2-left-join-or-left-outer-join)
    - [3. Right Join (or Right Outer Join)](#3-right-join-or-right-outer-join)
    - [4. Full Outer Join](#4-full-outer-join)
    - [5. Cross Join](#5-cross-join)
- [Structured Query Language](#structured-query-language)
  - [Creating Table](#creating-table)
  - [Update Tables](#update-tables)
  - [Select Clause](#select-clause)
  - [Where Clause:](#where-clause)
  - [From Clause](#from-clause)
  - [Rename Operator:](#rename-operator)
  - [String Operations:](#string-operations)
  - [Aggregate Functions:](#aggregate-functions)
  - [Nested Subqueries:](#nested-subqueries)
  - [Deletion:](#deletion)
  - [Insertion:](#insertion)
  - [Joins:](#joins)


## Why DBMS?
A Database Management System (DBMS) surpasses file systems due to its robust features.
- Data Integrity
- Access control and encryption.
- Querying and indexing, data retrieval is efficient.
- Concurrent access with locking and transaction mechanisms.
- Minimizes redundancy by normalization, optimizing storage.
- It scales both vertically and horizontally, and performance tuning tools enhance efficiency.
- Built-in backup and recovery System

## Levels of Abstraction

- Physical Abstraction:
    - Describes how data is stored in DB.

- Logical Abstraction:
    - Describes the data store and relationship among data. 

- View Abstraction:
    - Hides details of data types and also for security

## Schema & Instance

**Schema** &rarr; Logical and Physical structure of Database.

**Instance** &rarr; Actual data of the tabel.


|   Name   | CustomerID | AccountNO |  MobileNo   |
|----------|------------|-----------|-------------|
| Krishanu |    123     |   901923  |  ~~9461001212~~ |
| Pavan Laha | 7628     |   917322  |  9830100291 |


## Data Models

| Language           | Use Case                                                                                                          |
|--------------------|------------------------------------------------------------------------------------------------------------------|
| DDL (Data Definition Language) | Defines and manages the structure of the database.                                                             |
| DML (Data Manipulation Language) | Manipulates and interacts with the data in the database.                                                        |
| DQL (Data Query Language) | Retrieves data from the database.                                                                               |
| DCL (Data Control Language) | Manages access control and permissions for data within the database.                                             |
| TCL (Transaction Control Language) | Manages transactions within the database.                                                                         |
| SQL (Structured Query Language) | Universal language for interacting with relational databases.


## Keys

| Key Type               | Description                                                                                                                                                                          |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Primary Key (PK)**   | Uniquely identifies each record in a table. It must contain unique values and cannot have NULL values. A table can have only one primary key.                                 |
| **Foreign Key (FK)**   | Establishes relationships between tables. It refers to the primary key of another table and helps maintain referential integrity.                                              |
| **Unique Key**         | Similar to a primary key, it ensures that each value in a column is unique. However, it can allow NULL values. A table can have multiple unique keys.                         |
| **Super Key**          | A set of one or more attributes that, taken collectively, can uniquely identify a record. It may include more attributes than necessary to uniquely identify records.          |
| **Candidate Key**      | A minimal super key - it is a super key with no unnecessary attributes.                                                                                                              |
| **Alternate Key**      | A candidate key that is not selected as the primary key.                                                                                                                              |
| **Composite Key**      | A key composed of multiple attributes (columns) used together to uniquely identify records.                                                                                        |
| **Surrogate Key**      | A system-generated unique identifier assigned to each record. It has no business meaning and is typically an auto-incremented integer.                                          |
| **Natural Key**        | A key that has a business meaning and is derived from the application data.                                                                                                          |
| **Compound Key**       | Similar to a composite key, but it may include attributes that are not related to the uniqueness of records.                                                                       |
| **Non-Key Attribute**  | An attribute that is not part of any key.                                                                                                                                            |


## Relational Query Operations

|A|B|C|D|
|-|-|-|-|
|1|1|1|7|
|1|2|5|7|
|2|2|12|3|
|2|2|23|10|

### Select


&sigma;~A=B^D>5~(r)

|A|B|C|D|
|-|-|-|-|
|1|1|1|7|
|2|2|23|10|

### Projection

π~A,C~(r)

|A|C|
|-|-|
|1|1|
|1|2|
|2|2|
|2|2|

 ### Set Difference

 Use venn Diagram to understand this.

 Table - 'r'
| A  | B  |   
|--- |--- |   
| a  | 1  |   
| a  | 2  |   
| b  | 1  | 

 Table - 's'
| A  | B  |   
|--- |--- |   
| a  | 2  |   
| b  | 3  |   


Table - 'r - s'
| A  | B  |   
|--- |--- |   
| a  | 1  |   
| b  | 1  | 

### Union
Table - 'r U s'
| A  | B  |   
|--- |--- |   
| a  | 1  |   
| a  | 2  |   
| b  | 1  | 
| b  | 3  |

### Intersection

Table - 'r &cap; s'

| A  | B  |   
|--- |--- |   
| a  | 2  |

### Cartesian Product

Table - 'r X s'

| r.A  | r.B  | s.A  | s.B  |
|--- |--- |--- |--- |
| a  | 1  | a  | 2  |
| a  | 1  | b  | 3  |
| a  | 2  | a  | 2  |
| a  | 2  | b  | 3  |
| b  | 1  | a  | 2  |
| b  | 1  | b  | 3  |

### Types of Joins

#### 1. Inner Join

An inner join returns only the rows that have matching values in both tables.

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| 3          | Bob Johnson  | 103          | Finance        |

| DepartmentID | DepartmentManager |
|--------------|-------------------|
| 101          | Sarah Johnson     |
| 102          | Mark Davis        |

Inner Join Result:

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |

#### 2. Left Join (or Left Outer Join)

A left join returns all the rows from the left table and the matched rows from the right table. The result will contain NULL in the right side if there is no match.

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| 3          | Bob Johnson  | 103          | Finance        |

| DepartmentID | DepartmentManager |
|--------------|-------------------|
| 101          | Sarah Johnson     |
| 104          | Michael Brown     |

Left Join Result:

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| 3          | Bob Johnson  | 103          | Finance        |

#### 3. Right Join (or Right Outer Join)

A right join returns all the rows from the right table and the matched rows from the left table. The result will contain NULL in the left side if there is no match.

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |

| DepartmentID | DepartmentManager |
|--------------|-------------------|
| 101          | Sarah Johnson     |
| 102          | Mark Davis        |
| 103          | Laura Lee        |

Right Join Result:

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| NULL       | NULL         | 103          | Finance        |

#### 4. Full Outer Join

A full outer join returns all the rows when there is a match in one of the tables. It combines the results of both left and right joins.

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| 3          | Bob Johnson  | 103          | Finance        |

| DepartmentID | DepartmentManager |
|--------------|-------------------|
| 101          | Sarah Johnson     |
| 104          | Michael Brown     |

Full Outer Join Result:

| EmployeeID | EmployeeName | DepartmentID | DepartmentName |
|------------|--------------|--------------|----------------|
| 1          | John Doe     | 101          | Sales          |
| 2          | Jane Smith   | 102          | Marketing      |
| 3          | Bob Johnson  | 103          | Finance        |
| NULL       | NULL         | 104          | Michael Brown  |

#### 5. Cross Join

A cross join returns the Cartesian product of both tables. It combines each row from the first table with every row from the second table.

| Category | Product |
|----------|---------|
| Electronics | Laptop |
| Electronics | Smartphone |
| Clothing | T-Shirt |
| Clothing | Jeans |
| Furniture | Chair |
| Furniture | Table |

Cross Join Result:

| Category | Product |
|----------|---------|
| Electronics | Laptop |
| Electronics | Smartphone |
| Clothing | T-Shirt |
| Clothing | Jeans |
| Furniture | Chair |
| Furniture | Table |

## Structured Query Language

### Creating Table
``` sql
create table course(
    course_id varchar(8),
    title varchar(50),
    dept_name varchar(10),
    credits numeric(2,0)
);
```

### Update Tables

Inserting values in tables:
```sql
insert into course values('1012','DBMS','Computer Science',4.0);

update instructor set salary = case
    when salary<=1000000 then salary*1.05
    else salary *1.03
    end
```
Delete:
```sql
delete from course;
```
Drop Table:
```sql
drop table course;
```
Alter:
```sql
alter table r add A D;
alter table r drop A;
```
Basic Query Structure:
```sql
select A1,A2,A3 from r1,r2,r3 where P;
```

### Select Clause
 - Use distinct for selecting only distinct values and not any duplicates
 - Use all to select all tuples.
 - Use * to select all attributes
 - Use can also say Hello World
```sql
select distinct dept_name from instructor;
select all dept_name from instructor;
select * dept_name from instructor;
select "Hello World"; 
select "437" as Foo; 
```

- Arithemetics in select clause:
```sql
select ID,name,salary/12 from instructor;
select ID,name,salary/12 as monthly_salary from instructor;
```

### Where Clause:

```sql
select name from instuctors where dept_name='Comp.Sci.';
-- Logical Opeartors in Where clause:
select name from instuctors where dept_name='Comp.Sci.' and salary > 80000;
select name from instuctors where dept_name='Comp.Sci.' and salary between 80000 and 100000;
```

### From Clause

```sql
-- Cartesian product using 'from':
select * from instructor,teaches;
-- Cartesian Product under conditions:
select * from instructor,teaches where instructor.ID = teaches.ID and instructor.dept_name = 'Art'; 
```

### Rename Operator:

```sql
-- using as to not repeat name of tables repeatedly:
select distinct T.name from instructor as T, instructor as S where T.salary > S.salary;
```

### String Operations:

```sql
-- % char matches any substring
-- _ char matches any char
select name from instructors where name like '%dar%';
-- 'Intro%' matches any string begging with Intro
-- '%Comp%' matches string containing Comp
-- '___' matches string of length 3
-- '___%' matches string of length atleast 3

select distinct name from instructors order by name desc;
select distinct name from instructors order by name asc;
```

```sql
select name from instructors where salary is null;
```

### Aggregate Functions:
```sql
select avg(salary) from instructors where dept_name = 'Comp. Sci.';
select count(distinct ID) from teaches where semester = 'Spring' and year = 2010;
-- Find number of tuples in relation:
select count(*) from course; 
select dept_name,ID,avg(salary) from instructor group by dept_name; 
```

### Nested Subqueries:
```sql
-- Find courses offered in Spring and Fall of 2023:
select distinct course_id from courses where semester = 'Spring' and year=2023 and course_id in (select course_id from course where semester ='Fall' and year=2023);

-- Find courses offered in Spring but not in Fall of 2023:
select distinct course_id from courses where semester = 'Spring' and year=2023 and course_id not in (select course_id from course where semester ='Fall' and year=2023);
```

### Deletion:

```sql
delete from instructor where dept_name in (select dept_name from department where building = 'Watson');
```

### Insertion:

```sql
insert into student from select ID,name,dept_name,0 from instructor;
```

### Joins:
```sql
-- Cross Join:
-- Explicit:
select * from employee from cross join department;
-- Implicit:
select * from employee,department;

--Inner Join:
course inner join  prereq;

--Outer Join:
-- Left Join:
course natural left outer join  prereq;
-- Right Join:
course natural right outer join  prereq;

```
