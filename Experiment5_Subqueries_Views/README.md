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
<img width="1273" height="739" alt="image" src="https://github.com/user-attachments/assets/f4e3b0ee-92d9-43c2-94c0-8f049061bc6f" />


```sql
Select salesman_id,name from salesman
where salesman_id IN(
SELECT salesman_id
from customer 
group by salesman_id 
having count(customer_id)>1);
```

**Output:**
<img width="1267" height="477" alt="image" src="https://github.com/user-attachments/assets/0ec31b71-99b9-477b-9968-89864abf80ef" />


**Question 2**
---
<img width="1076" height="497" alt="image" src="https://github.com/user-attachments/assets/f3e6fc85-2e7e-4569-8889-e73965598e0d" />


```sql
Select * from medications
where dosage IN(
SELECT MIN(dosage) from medications);
```

**Output:**


<img width="1250" height="411" alt="image" src="https://github.com/user-attachments/assets/4a8345bf-f02c-42ba-9dc0-3c032efcd10a" />


**Question 3**
---
<img width="1233" height="748" alt="image" src="https://github.com/user-attachments/assets/54a55eb6-7443-4ddd-9648-ca469fdf3c7e" />


```sql
select ord_no,purch_amt,ord_date,customer_id,salesman_id from orders
where salesman_id = (
select salesman_id from salesman
where name = 'Paul Adam');
```

**Output:**

<img width="1288" height="387" alt="image" src="https://github.com/user-attachments/assets/f8acbfb1-6e10-425d-b779-da4be0d00548" />


**Question 4**
---

<img width="1281" height="666" alt="image" src="https://github.com/user-attachments/assets/f5d03156-c2ed-4993-b294-38db43585e6a" />


```sql
SELECT student_name, grade
FROM grades g
WHERE grade = (
    SELECT MAX(grade)
    FROM grades
    WHERE subject = g.subject
);

```

**Output:**


<img width="935" height="441" alt="image" src="https://github.com/user-attachments/assets/7191aa61-7696-4824-bc3f-d50a19736f30" />


**Question 5**
---
<img width="1253" height="830" alt="image" src="https://github.com/user-attachments/assets/2426409e-6480-4fb0-8a08-4a8df7778d63" />


```sql
select ord_no,purch_amt,ord_date,salesman_id from orders
where salesman_id = (
select salesman_id from salesman
where commission = (select max(commission)from salesman));
```

**Output:**


<img width="1186" height="476" alt="image" src="https://github.com/user-attachments/assets/3b189ce6-448a-410d-9dab-7a47e0278434" />


**Question 6**
---

<img width="1288" height="671" alt="image" src="https://github.com/user-attachments/assets/13b62500-f592-45e6-8ebf-94205800ab40" />

```sql
SELECT student_name, grade
FROM grades g
WHERE grade = (
    SELECT MIN(grade)
    FROM grades
    WHERE subject = g.subject
);

```

**Output:**


<img width="1200" height="525" alt="image" src="https://github.com/user-attachments/assets/5282c192-5925-4647-8a1b-1845e3c82ee0" />


**Question 7**
---

<img width="1281" height="677" alt="image" src="https://github.com/user-attachments/assets/fa09759d-c2f2-425e-8df4-a8eb2e90749b" />


```sql
SELECT id, name, age, city, income
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

<img width="1258" height="535" alt="image" src="https://github.com/user-attachments/assets/b423dfe1-15fd-47df-8ff0-f10069e853be" />



**Question 8**
---

<img width="1197" height="605" alt="image" src="https://github.com/user-attachments/assets/43d5136e-1be7-44b5-9014-86efdda0d09f" />


```sql
SELECT id, name, age, city, income
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);

```

**Output:**


<img width="1273" height="438" alt="image" src="https://github.com/user-attachments/assets/f1a6b771-25a1-445f-9933-e06ddcf51e0b" />


**Question 9**
---

<img width="1204" height="625" alt="image" src="https://github.com/user-attachments/assets/8f072c72-c7e1-4124-bb13-0eb5694ea4c7" />


```sql
SELECT id, name, age,address,salary
FROM CUSTOMERS
WHERE age < 30 and address = 'Delhi'
order by id asc
LIMIT 10;

```

**Output:**


<img width="1274" height="380" alt="image" src="https://github.com/user-attachments/assets/03a06796-aca8-4661-ab30-4354667c9715" />


**Question 10**
---

<img width="1274" height="643" alt="image" src="https://github.com/user-attachments/assets/1960613a-762c-4a56-9b04-3a5c6ac2e102" />


```sql
SELECT student_id, student_name, subject, grade
FROM grades g
WHERE grade = (
    SELECT MAX(grade)
    FROM grades
    WHERE subject = g.subject
);

```

**Output:**

<img width="1317" height="457" alt="image" src="https://github.com/user-attachments/assets/a5ec3427-c045-4732-845e-b9db71b8cd42" />




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
