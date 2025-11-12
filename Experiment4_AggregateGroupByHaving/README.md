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
<img width="1232" height="656" alt="image" src="https://github.com/user-attachments/assets/605fedca-cd19-46d8-ac7b-e8334c25e981" />


```sql
SELECT Medication,count(*) as 'TotalPrescriptions' from Prescriptions
group by Medication;
```

**Output:**
<img width="1204" height="761" alt="image" src="https://github.com/user-attachments/assets/9007947a-151f-4e85-a25e-1ff3f3519289" />


**Question 2**
---
<img width="1093" height="468" alt="image" src="https://github.com/user-attachments/assets/c2c1d6b7-a125-4d4e-affc-ec6848b285ce" />


```sql
SELECT Gender,count(*) as 'TotalPatients' from Patients
group by Gender;
```

**Output:**
<img width="1230" height="456" alt="image" src="https://github.com/user-attachments/assets/7f7d3d5c-1570-4928-a167-3f7f45027fcc" />



**Question 3**
---
<img width="1221" height="512" alt="image" src="https://github.com/user-attachments/assets/1c08a457-4fde-4df2-bdc6-f477616dcbc6" />


```sql
SELECT 
  CASE 
    WHEN (strftime('%Y', 'now') - strftime('%Y', dateofbirth)) < 20 THEN 'Under 20'
    WHEN (strftime('%Y', 'now') - strftime('%Y', dateofbirth)) BETWEEN 20 AND 30 THEN '20-30'
    WHEN (strftime('%Y', 'now') - strftime('%Y', dateofbirth)) BETWEEN 31 AND 40 THEN '31-40'
    WHEN (strftime('%Y', 'now') - strftime('%Y', dateofbirth)) BETWEEN 41 AND 50 THEN '41-50'
    ELSE 'Above 50'
  END AS AgeGroup,
  COUNT(*) AS TotalPatients
FROM Patients
GROUP BY AgeGroup;
```

**Output:**

<img width="1179" height="438" alt="image" src="https://github.com/user-attachments/assets/273ca55a-079f-400a-8314-77fd9da3fda7" />


**Question 4**
---


<img width="1123" height="488" alt="image" src="https://github.com/user-attachments/assets/88f4004d-2f9b-4675-95eb-2e19619a2c2c" />


```sql
SELECT count(*) as 'employees_count' from employee
where income>50000;
```

**Output:**

<img width="1221" height="313" alt="image" src="https://github.com/user-attachments/assets/b7fa4576-d6b2-45f2-98d4-2407606756f6" />


**Question 5**
---

<img width="1196" height="476" alt="image" src="https://github.com/user-attachments/assets/e39dd7c5-065a-4bb6-8793-3d2a792667dd" />


```sql
SELECT sum(purch_amt) as 'TOTAL' from orders;

```

**Output:**

<img width="1225" height="323" alt="image" src="https://github.com/user-attachments/assets/ab29b943-4c86-44e9-876d-f8885aa27fe6" />


**Question 6**
---
<img width="1102" height="505" alt="image" src="https://github.com/user-attachments/assets/fdae2449-4818-46cf-8d3b-cb0ef44791bb" />


```sql
select max(price)-min(price) as 'price_diff' from fruits;
```

**Output:**

<img width="927" height="320" alt="image" src="https://github.com/user-attachments/assets/6b89d9aa-f2f0-4547-83d3-9ec6dfcf8fde" />


**Question 7**
---

<img width="979" height="530" alt="image" src="https://github.com/user-attachments/assets/582a94a8-0d97-4d51-ba17-380b31198379" />

```sql
SELECT name as 'fruit_name',MIN(inventory) as 'lowest_quantity' from fruits;
```

**Output:**

<img width="1073" height="313" alt="image" src="https://github.com/user-attachments/assets/b420ae7d-9166-4a6e-b458-c1365c8e767f" />


**Question 8**
---

<img width="1211" height="508" alt="image" src="https://github.com/user-attachments/assets/a4827e35-b743-43d6-bbc5-4dc018d1ca20" />


```sqlS
ELECT category_id,count(*) as 'count(product_name)' from products
group by category_id
having category_id<3;
```

**Output:**


<img width="992" height="341" alt="image" src="https://github.com/user-attachments/assets/e8007677-74a3-4783-879f-f651b710acb8" />


**Question 9**
---

<img width="1222" height="541" alt="image" src="https://github.com/user-attachments/assets/01dc50c7-0d4b-42fe-857f-81da7fdd9306" />


```sql
select city,AVG(income) from employee
group by city 
having AVG(income)>500000;
```

**Output:**

<img width="943" height="438" alt="image" src="https://github.com/user-attachments/assets/0b40c977-32ec-41b3-bcaa-a02ad2b01e30" />


**Question 10**
---
<img width="1234" height="479" alt="image" src="https://github.com/user-attachments/assets/45c55b9c-428d-4309-8cf4-4e4f1c013436" />


```sql
SELECT jdate,AVG(workhour) from employee1
group by jdate
having AVG(workhour)<10;
```

**Output:**

<img width="1209" height="345" alt="image" src="https://github.com/user-attachments/assets/6fa4a065-2639-4a4b-ab06-4968d5c1eb39" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
