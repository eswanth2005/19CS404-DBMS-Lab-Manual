# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- Increase the reorder level by 30% for products from 'Food' category having quantity in stock less than 50% of existing reorder level in the products table
name               type
--------------  ----------
product_id         INT
product_name       VARCHAR(10)
category           VARCHAR(50)
cost_price         DECIMAL(10)
sell_price         DECIMAL(10)
reorder_lvl        INT
quantity              INT
supplier_id           INT
![image](https://github.com/user-attachments/assets/3eafb686-e2af-4ca1-8d2b-133f58cbb2f5)

```sql
-- update products set reorder_lvl = reorder_lvl * 1.30 where quantity < 0.5* reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/890c3f3c-4a12-47c4-abee-3aecae03072f)


**Question 2**
---
-- Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
-- update products set product_name = "Premium Bread" where product_id = 5;
```

**Output:**

![image](https://github.com/user-attachments/assets/99970b78-d9a2-4ec9-99cb-833c315518ee)


**Question 3**
---
-- Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
![image](https://github.com/user-attachments/assets/d40e0ae6-5b3e-450a-8227-3ce0fa2f9481)


```sql
-- update Employees set salary= salary+500 , email = "updated" where job_id = "SA_REP" and commission_pct >0.15;
```

**Output:**

![image](https://github.com/user-attachments/assets/f08e7bf6-8c28-4ca7-93f7-2ca14b715df4)


**Question 4**
---
-- Write a SQL statement to Change the category to 'Household' where product name contains 'Detergent' in the products table.

Products Table 

name          type       
----------    ---------- 
product_id     INT PRIMARY KEY        
product_name   VARCHAR(10) 
category       VARCHAR(50) 
cost_price     DECIMAL(10) 
sell_price     DECIMAL(10) 
reorder_lvl    INT        
quantity       INT        
supplier_id    INT           
For example:
![image](https://github.com/user-attachments/assets/4ab4019d-f229-4531-8558-9880b711892f)

```sql
-- update products set category = "Household" where product_name like "%Detergent%";
```

**Output:**

![image](https://github.com/user-attachments/assets/f2547383-27de-4bb3-a2b7-6131f96bcfa7)


**Question 5**
---
-- Update the reorder level to 40 pieces for all products belonging to the 'Grocery' category in the products table.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
![image](https://github.com/user-attachments/assets/5e43cbb1-4869-48fc-8fae-f0a6e9640577)

```sql
-- update products set reorder_lvl = 40 where category = 'Grocery';
```

**Output:**

![image](https://github.com/user-attachments/assets/951625cc-8732-4b5b-9aa7-bbc21775ef5f)


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_COUNTRY' is neither 'India' nor 'USA'.

```sql
-- delete from customer where CUST_COUNTRY NOT IN ('India','USA');
```

**Output:**



**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
