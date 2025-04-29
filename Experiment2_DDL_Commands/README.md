# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- In the Cusomers table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.
![image](https://github.com/user-attachments/assets/4ac69e72-2d3a-4cb1-8e45-b79ff8fbf5ec)

```sql
INSERT INTO Customers VALUES(306,'Diana Prince',"Themyscira",NULL,NULL);
INSERT INTO Customers VALUES(307,'Bruce Wayne',"Wayne Mano","Gotham",10007);
INSERT INTO Customers VALUES(308,'Peter Parker',"Queens",NULL,11375);
```

**Output:**

![image](https://github.com/user-attachments/assets/debc6422-d386-42cd-86fc-5167b8829e6e)


**Question 2**
---
-- Insert a student with RollNo 201, Name David Lee, Gender M, Subject Physics, and MARKS 92 into the Student_details table.
![image](https://github.com/user-attachments/assets/cc93b1fa-c421-4012-9fdf-b3f4f29d6e76)

```sql
-- INSERT INTO Student_details VALUES(201,'David Lee',"M","Physics",92);
```

**Output:**

![image](https://github.com/user-attachments/assets/6b1f0c55-ef07-4af1-a998-bea01b6d94ff)


**Question 3**
---
-- Insert all students from Archived_students table into the Student_details table.

cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           RollNo      INT           0                       1
1           Name        VARCHAR(100)  0                       0
2           Gender      VARCHAR(10)   0                       0
3           Subject     VARCHAR(50)   0                       0
4           MARKS       INT           0                       0
![image](https://github.com/user-attachments/assets/c8dca14a-a119-4133-b423-81ed51f1cc4f)

```sql
-- insert into Student_details(Rollno,Name,Gender, Subject,MARKS)  select Rollno,Name,Gender, Subject,MARKS from Archived_students ;
```

**Output:**

![image](https://github.com/user-attachments/assets/f7fc52e8-8425-4264-995d-4ad3e876a2a1)


**Question 4**
---
-- Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.
For example:


```sql
-- CREATE table Bonuses(BonusID int primary key,EmployeeID int, BonusAmount REAL CHECK (BonusAmount >0) , BonusDate date, Reason Text not null,
   FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID) );
```

**Output:**

![image](https://github.com/user-attachments/assets/c57f9af0-7f3a-40a9-a034-f35777346bcb)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/4b828e63-6b4b-47e3-a943-8b73dfc8493b)


```sql
-- ALTER TABLE customer rename column city to location;
```

**Output:**

![image](https://github.com/user-attachments/assets/764e10d9-33cb-43ef-b411-ef7af8c73414)


**Question 6**
---
-- Create a table named Employees with the following constraints:

EmployeeID should be the primary key.
FirstName and LastName should be NOT NULL.
Email should be unique.
Salary should be greater than 0.
DepartmentID should be a foreign key referencing the Departments table.

```sql
-- create table Employees(EmployeeID int primary key, FirstName varchar(50) NOT NULL, LastName varchar(50) not null, Email varchar(50) UNIQUE,Salary decimal(10,2) CHECK ( Salary > 0), DepartmentID int , FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID) );
```

**Output:**

![image](https://github.com/user-attachments/assets/8a5a14ce-4f84-4a9e-885f-1e7d1b136317)


**Question 7**
---
-- Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should cascade updates and deletes.
item_desc and rate should not accept NULL.

```sql
-- create table item(item_id text primary key,item_desc text not null,rate int not null, icom_id  text varchar(4), FOREIGN KEY (icom_id) references company(com_id) ON UPDATE CASCADE ON DELETE CASCADE );
```

**Output:**

![image](https://github.com/user-attachments/assets/65ac5931-8fba-49ec-a0f6-3e7aaf515c7b)


**Question 8**
---
--Create a table named Events with the following columns:

EventID as INTEGER
EventName as TEXT
EventDate as DATE

```

-- CREATE TABLE Events(EventID INTEGER, EventName TEXT,EventDate DATE);
```

**Output:**

![image](https://github.com/user-attachments/assets/06074cc7-a9da-4e90-8b70-1cf7f4836ec5)


**Question 9**
---
-- Create a table named Attendance with the following constraints:
AttendanceID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
AttendanceDate as DATE.
Status as TEXT should be one of 'Present', 'Absent', 'Leave'.

```sql
-- CREATE TABLE Attendance(AttendanceID INTEGER primary key, EmployeeID INTEGER ,AttendanceDate DATE, Status TEXT CHECK(Status IN ('Present','Absent', 'Leave')), FOREIGN KEY (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/3853019c-6df1-45a9-86f8-e478ca399938)


**Question 10**
---
-- Write a SQL query to add a new column MobileNumber of type NUMBER and a new column Address of type VARCHAR(100) to the Student_details table.

```sql
-- alter table Student_details add column MobileNumber NUMBER ;
alter table Student_details add column Address VARCHAR(100) ;
```

**Output:**

![image](https://github.com/user-attachments/assets/6c5945d7-d9e9-41cc-a91b-568e82c99970)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
