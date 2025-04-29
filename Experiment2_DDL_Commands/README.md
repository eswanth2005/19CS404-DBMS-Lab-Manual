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
-- ![image](https://github.com/user-attachments/assets/880fc67c-6f85-412b-9ff5-77205243a57a)

```
INSERT INTO Customers VALUES(306,'Diana Prince',"Themyscira",NULL,NULL);
INSERT INTO Customers VALUES(307,'Bruce Wayne',"Wayne Mano","Gotham",10007);
INSERT INTO Customers VALUES(308,'Peter Parker',"Queens",NULL,11375);
```

**Output:**

![image](https://github.com/user-attachments/assets/debc6422-d386-42cd-86fc-5167b8829e6e)


**Question 2**
---
![image](https://github.com/user-attachments/assets/5daf55ef-dde3-43a7-a59d-fd63d61ab095)

```
INSERT INTO Student_details VALUES(201,'David Lee',"M","Physics",92);
```

**Output:**

![image](https://github.com/user-attachments/assets/6b1f0c55-ef07-4af1-a998-bea01b6d94ff)


**Question 3**
---
![image](https://github.com/user-attachments/assets/d24de01c-95c4-4b57-8416-c57385c3e5f7)

```
insert into Student_details(Rollno,Name,Gender, Subject,MARKS)  select Rollno,Name,Gender, Subject,MARKS from Archived_students ;
```

**Output:**

![image](https://github.com/user-attachments/assets/f7fc52e8-8425-4264-995d-4ad3e876a2a1)


**Question 4**
---
![image](https://github.com/user-attachments/assets/452b5bd9-733f-4c19-8d02-4aac33988c80)


```
CREATE table Bonuses(BonusID int primary key,EmployeeID int, BonusAmount REAL CHECK (BonusAmount >0) , BonusDate date, Reason Text not null,
   FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID) );
```

**Output:**

![image](https://github.com/user-attachments/assets/c57f9af0-7f3a-40a9-a034-f35777346bcb)


**Question 5**
---
![image](https://github.com/user-attachments/assets/4b828e63-6b4b-47e3-a943-8b73dfc8493b)


```
ALTER TABLE customer rename column city to location;
```

**Output:**

![image](https://github.com/user-attachments/assets/764e10d9-33cb-43ef-b411-ef7af8c73414)


**Question 6**
---
![image](https://github.com/user-attachments/assets/8e797b90-56e3-467b-baf7-e501043f50eb)

```
create table Employees(EmployeeID int primary key, FirstName varchar(50) NOT NULL, LastName varchar(50) not null, Email varchar(50) UNIQUE,Salary decimal(10,2) CHECK ( Salary > 0), DepartmentID int , FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID) );
```

**Output:**

![image](https://github.com/user-attachments/assets/8a5a14ce-4f84-4a9e-885f-1e7d1b136317)


**Question 7**
---
![image](https://github.com/user-attachments/assets/bb10daf5-88b4-436d-b076-0a530382f324)


```
create table item(item_id text primary key,item_desc text not null,rate int not null, icom_id  text varchar(4), FOREIGN KEY (icom_id) references company(com_id) ON UPDATE CASCADE ON DELETE CASCADE );
```

**Output:**

![image](https://github.com/user-attachments/assets/65ac5931-8fba-49ec-a0f6-3e7aaf515c7b)


**Question 8**
---
![image](https://github.com/user-attachments/assets/3032d001-7269-4f7f-b6ee-278059abeedf)


```
CREATE TABLE Events(EventID INTEGER, EventName TEXT,EventDate DATE);
```

**Output:**

![image](https://github.com/user-attachments/assets/06074cc7-a9da-4e90-8b70-1cf7f4836ec5)


**Question 9**
---
![image](https://github.com/user-attachments/assets/d10b44f0-c2be-4bf9-89e8-64ba0dafb45c)


```
-CREATE TABLE Attendance(AttendanceID INTEGER primary key, EmployeeID INTEGER ,AttendanceDate DATE, Status TEXT CHECK(Status IN ('Present','Absent', 'Leave')), FOREIGN KEY (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/3853019c-6df1-45a9-86f8-e478ca399938)


**Question 10**
---
![image](https://github.com/user-attachments/assets/9aa043b8-e286-420e-ac7b-81d6313792c0)


```
 alter table Student_details add column MobileNumber NUMBER ;
alter table Student_details add column Address VARCHAR(100) ;
```

**Output:**

![image](https://github.com/user-attachments/assets/6c5945d7-d9e9-41cc-a91b-568e82c99970)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
