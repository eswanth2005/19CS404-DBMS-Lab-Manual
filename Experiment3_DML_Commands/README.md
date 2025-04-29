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
-- ![image](https://github.com/user-attachments/assets/cc97fc63-e426-4a66-bff3-56132a382d12)

```
-- update products set reorder_lvl = reorder_lvl * 1.30 where quantity < 0.5* reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/844b85fc-6fb4-447f-875a-544f893fe341)



**Question 2**
---
-- ![image](https://github.com/user-attachments/assets/3b763fdc-328b-4db2-a676-4e207cbf56d0)


```
-- update products set product_name = "Premium Bread" where product_id = 5;
```

**Output:**

![image](https://github.com/user-attachments/assets/99970b78-d9a2-4ec9-99cb-833c315518ee)


**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/02f565f7-eb4f-40ac-8762-46d7e3bca327)


```
-- update Employees set salary= salary+500 , email = "updated" where job_id = "SA_REP" and commission_pct >0.15;
```

**Output:**

![image](https://github.com/user-attachments/assets/f08e7bf6-8c28-4ca7-93f7-2ca14b715df4)


**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/97de0164-ca55-497e-b158-6362fc385a65)


```
update products set category = "Household"
where product_name like "%Detergent%";
```

**Output:**

![image](https://github.com/user-attachments/assets/f2547383-27de-4bb3-a2b7-6131f96bcfa7)


**Question 5**
---
-- ![image](https://github.com/user-attachments/assets/7ec86962-4478-4ba0-8b23-8b08500a1f27)

```
-- update products set reorder_lvl = 40 where category = 'Grocery';
```

**Output:**

![image](https://github.com/user-attachments/assets/951625cc-8732-4b5b-9aa7-bbc21775ef5f)


**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/78be3128-0101-4027-b174-f4c92e5cc9ec)
.

```
-- delete from customer where CUST_COUNTRY NOT IN ('India','USA');
```

**Output:**

![image](https://github.com/user-attachments/assets/afe6e6f9-8dc0-45e6-bff2-d0d6f2428024)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/3f8dc143-c0a5-494b-add0-32fb3b847b2d)


```
-- DELETE from customer where GRADE = 2 and CUST_NAME like "M%" and PAYMENT_AMT <3000 ;
```

**Output:**

![image](https://github.com/user-attachments/assets/6cdf3f0f-88ac-4c91-a07e-18f22a5444c8)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/1008aa2d-4b38-43f1-81df-3cacc94b140c)


```
-- delete from surgeries where surgery_date = "2024-02-28";
```

**Output:**

![image](https://github.com/user-attachments/assets/ad66bb58-8995-4f7d-8c0c-bbb2a3ac7d7d)


**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/e0215afa-955d-4276-b2bf-27fa9881b960)


```
-- delete from customer where CUST_NAME like "%Holmes%";
```

**Output:**

![image](https://github.com/user-attachments/assets/a8148f5c-e9ae-4389-acd3-7584036a47a3)


**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/bf751c96-9686-49e5-8834-0f9517823030)


```
-- select CategoryName, Description FROM categories order by CategoryName;
```

**Output:**

![image](https://github.com/user-attachments/assets/23bb6dcb-be7d-42a2-bcdd-0b78e0ac1bc9)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
