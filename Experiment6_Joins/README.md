![image](https://github.com/user-attachments/assets/8c9cfd3d-6d45-4473-a68a-e6ce4abf416e)# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/b7d95be1-c257-41c6-910e-27aea32bcc31)

```
SELECT  cust_name as "Customer Name",c.city,
s.name as Salesman,s.commission from customer c
join salesman s ON c.salesman_id =
 s.salesman_id where s.commission > 0.12;
```

**Output:**

![image](https://github.com/user-attachments/assets/82786a74-44e8-4199-9157-dff4f7770d9d)


**Question 2**
---
![image](https://github.com/user-attachments/assets/c696e7e7-31d5-459c-98c8-f6fce2c45cde)


```
select p.first_name as patient_name, 
t.result_id as "result_id",
p.patient_id as "patient_id",
t.test_name as "test_name",
t.result as result,
t.test_date as "test_date"
from patients p 
inner join test_results t on 
t.patient_id = p.patient_id
where p.admission_date BETWEEN "2024-01-01"
AND "2024-01-31"
```

**Output:**

![image](https://github.com/user-attachments/assets/5bf52750-53d1-402a-84fc-a59c0fc1e7b4)


**Question 3**
---
![Screenshot 2025-04-30 003449](https://github.com/user-attachments/assets/fc8c13f4-b767-4470-8a8d-adcef4127b72)
![image](https://github.com/user-attachments/assets/8d07f3e5-8ce7-43c5-b0a2-d80bfe4b1008)

```
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/4a954fed-748c-4b1a-93b4-568ca9ede2a2)


**Question 4**
---
![image](https://github.com/user-attachments/assets/4f700afc-30e0-42fb-8243-112531b6e4a5)


```
select o.ord_no , o.purch_amt ,
c.cust_name ,c.city from  customer
c join orders o on c.customer_id = o.customer_id
where o.purch_amt between 500 and 2000 ;
```

**Output:**

![image](https://github.com/user-attachments/assets/30124ddc-4a07-4d2d-9f2a-fa09b4a87c38)


**Question 5**
---
![image](https://github.com/user-attachments/assets/b3b16b6d-64d1-40b9-97a6-adef1afda31f)


```
select c.cust_name from customer c left join
orders o on c.customer_id = o.customer_id ;```

**Output:**

![image](https://github.com/user-attachments/assets/db70e3eb-d6fb-4d24-8563-fbdab537d366)

**Question 6**
---
![image](https://github.com/user-attachments/assets/e69d165f-5f7f-4aef-a91a-34cd03e2476f)


```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/124c194b-6c43-47b8-b7e8-4a8e80fdae4e)


**Question 7**
---
![image](https://github.com/user-attachments/assets/62bf3436-3884-4f30-bcca-1914264b05d0)


```
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id
WHERE 
    t.test_name = 'Blood Pressure';

```

**Output:**

![image](https://github.com/user-attachments/assets/6fcfe5c2-603e-42ee-af83-f013a74bcd9b)


**Question 8**
---
![image](https://github.com/user-attachments/assets/f0c80dfb-8a0e-4767-8ea3-4d37d25151b0)


```
SELECT 
    c.*
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.ord_date BETWEEN '2012-08-01' AND '2012-08-30';

```

**Output:**

![image](https://github.com/user-attachments/assets/23c824af-0637-482b-b6f6-aaa16aa29a4b)


**Question 9**
---
![image](https://github.com/user-attachments/assets/f5c77917-a235-4917-a68a-e2068bc3c987)


```
select c.cust_name,
c.city,
c.grade,
s.name as "Salesman",
s.city 
from 
customer c join salesman s on c.salesman_id = s.salesman_id
order by c.customer_id ;

```

**Output:**

![image](https://github.com/user-attachments/assets/1ee84399-6350-4cc8-a918-c750bfb8bb87)

**Question 10**
---
![image](https://github.com/user-attachments/assets/fed9eab0-13c8-41c8-9806-2d9373504d6a)


```
SELECT 
    p.first_name,
    s.*
FROM 
    patients p
INNER JOIN 
    surgeries s ON p.patient_id = s.patient_id
WHERE 
    p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
    AND NOT (
        p.admission_date BETWEEN '2024-03-01' AND '2024-03-31'
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/425ee7c6-a341-42d1-97a2-5f36f5cb470d)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
