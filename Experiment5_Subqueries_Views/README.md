# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/1ec4cc5a-4bca-4cd3-b6c8-9d6bf3b99b4c)


```
SELECT * FROM CUSTOMERS 
WHERE SALARY > 4500;

```

**Output:**

![image](https://github.com/user-attachments/assets/5064701d-8e45-48d1-86dc-94ce7deb85e6)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8b96cbab-659f-4538-b087-2bd1efa45f06)

```
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/6fd9db10-91fc-44d2-b0ff-370869037591)


**Question 3**
---

![image](https://github.com/user-attachments/assets/82091753-7884-48f5-a278-1be8910d49b1)

```
SELECT name FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);

```

**Output:**

![image](https://github.com/user-attachments/assets/150101c0-2533-42fc-a60b-07beed478b20)

**Question 4**
---
![image](https://github.com/user-attachments/assets/fee776d8-983a-40a2-8acd-fd1fa5ea7cb7)

```
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**
![image](https://github.com/user-attachments/assets/f69f16d8-939e-4d32-ab61-60f2849b9e58)


**Question 5**
---
![image](https://github.com/user-attachments/assets/7fe7c750-8ec7-4e68-ae2f-f1a67c7cfbcc)


```
SELECT ord_no, purch_amt, ord_date, 
customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**

![image](https://github.com/user-attachments/assets/a70f5af3-3538-424a-98e4-cc0a75969ddf)


**Question 6**
---
![image](https://github.com/user-attachments/assets/85109539-010a-45d6-9f74-91fa4107ba5e)


```
SELECT * FROM CUSTOMERS
WHERE SALARY = 1500;

```

**Output:**

![image](https://github.com/user-attachments/assets/3cd0cedd-073c-4116-b065-d3f6face40e9)


**Question 7**
---
![image](https://github.com/user-attachments/assets/087a1f5e-6c9f-4564-a6de-47d81ff2acac)


```
SELECT ord_no, purch_amt, ord_date, 
customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

![image](https://github.com/user-attachments/assets/2ed5e119-9a94-42bc-8a62-0216aed4f94b)


**Question 8**
---
![image](https://github.com/user-attachments/assets/33b23fdf-abd4-4910-a336-ec17e4b49c7a)

```
SELECT id, name, city,
email, phone
FROM customer
WHERE city != (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/76d4ef58-7fbd-4e54-906d-c61a20e272e2)


**Question 9**
---
![image](https://github.com/user-attachments/assets/f8254381-ddb9-4e62-955d-40c288cfbc9e)


```
SELECT * FROM CUSTOMERS WHERE AGE < 30;
```

**Output:**

![image](https://github.com/user-attachments/assets/4346f387-b193-40de-a9e6-dd2024b21d04)


**Question 10**
---
![image](https://github.com/user-attachments/assets/0cd2f709-b783-4f5e-a889-a0d49b0bebc4)


```
SELECT o.ord_no, o.purch_amt, o.ord_date,
o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/b30cae6a-91c2-4718-8e7f-b765669ae277)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
