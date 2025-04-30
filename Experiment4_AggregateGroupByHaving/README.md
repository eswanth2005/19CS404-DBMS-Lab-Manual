# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/89c3d41b-36fe-454f-b6b7-e5c5aa3f5599)


```
select date(AppointmentDateTime) as AppointmentDate,count(*) as
TotalAppointments from Appointments group by AppointmentDateTime;
```

**Output:**

![image](https://github.com/user-attachments/assets/bbf259b5-9906-4a4e-99f2-2cd738d6d31c)


**Question 2**
---
![image](https://github.com/user-attachments/assets/d6a66be1-30eb-48c8-b389-b452792b33e0)

```
select InsuranceCompany, count(*) as TotalExpiredPatients
from Insurance group by InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/084492e0-3ad7-4a0b-ae14-3c882b904aab)


**Question 3**
---
![image](https://github.com/user-attachments/assets/35456eaf-2d6d-4c05-902c-b5ae8cf09799)


```
select sum(inventory) as total from fruits where unit = 'LB';
```

**Output:**

![image](https://github.com/user-attachments/assets/8d538ed7-98f7-4c04-b1ba-ff2e797589df)


**Question 4**
---
![image](https://github.com/user-attachments/assets/12c477ab-0a43-4614-90da-30cc8739e9c2)


```
select name, length(name) as length from customer 
group by name having length(name)= (select max(length(name)) from customer ) LIMIT 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/0abe5f4a-15fc-4550-880f-53ff01b9e2ef)


**Question 5**
---
![image](https://github.com/user-attachments/assets/883691fa-c822-4d5d-bbb8-ffc37d36c8f6)


```
select count(name) as employees_count from employee where income>50000;
```

**Output:**

![image](https://github.com/user-attachments/assets/aaa9432e-ea40-4779-8a37-29f7f7975cfb)

**Question 6**
---
![image](https://github.com/user-attachments/assets/58a01113-f185-4baa-ab58-3842027c24ea)

```
select address, SUM(salary) from customer1 group by address HAVING SUM(salary)>2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/2c895f12-a969-4fa0-b8cc-c7b6963fd87b)


**Question 7**
---
![image](https://github.com/user-attachments/assets/e6727e29-7fc9-4e57-a5f8-e36d65e56993)

```
select occupation , MIN(workhour) from employee1 group by occupation having  MIN(workhour) > 8;
```

**Output:**
![image](https://github.com/user-attachments/assets/7ca9889a-4a14-43d1-97cd-e105ba84ec75)


**Question 8**
---
![image](https://github.com/user-attachments/assets/7f7d3e72-99ed-48f8-af74-0b73a5b4790b)


```
select category_id, AVG(Price) from products
group by category_id having AVG(Price) BETWEEN 10 and 15;
```

**Output:**

![image](https://github.com/user-attachments/assets/abde0b0f-1c11-439c-9433-52a390986a37)


**Question 9**
---
![image](https://github.com/user-attachments/assets/89a55507-b9d9-4453-923f-9f96caf00984)


```
select max(price) - min(price) as price_diff from fruits; 
```

**Output:**

![image](https://github.com/user-attachments/assets/15a7f196-f5be-409c-b0fd-309f1ffa747b)


**Question 10**
---
![image](https://github.com/user-attachments/assets/6aef6dba-6b54-4ff7-aeac-196c485bbb06)

```
select Gender,count(*) as TotalPatients from Patients group by Gender;
```

**Output:**

![image](https://github.com/user-attachments/assets/a52dd1a7-796e-4de1-b263-b1a0eece00d7)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
