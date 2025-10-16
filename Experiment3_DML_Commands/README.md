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
<img width="1016" height="483" alt="image" src="https://github.com/user-attachments/assets/c08d8cc9-3ef0-4678-931d-b69b387e221f" />

```sql
UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%';
```

**Output:**

<img width="1271" height="332" alt="image" src="https://github.com/user-attachments/assets/f4473d44-b6d4-435e-a52e-9dac7bf60929" />

**Question 2**
---
<img width="1227" height="650" alt="image" src="https://github.com/user-attachments/assets/87a47e91-8d29-4297-9ed5-29232eaaac20" />

```sql
UPDATE Employees
SET email = 'not available',
    commission_pct = 0.55
WHERE department_id = 110;
```

**Output:**

<img width="1245" height="393" alt="image" src="https://github.com/user-attachments/assets/33907ddb-bb39-45ce-837a-d9afba6ea5df" />

**Question 3**
---
<img width="1156" height="582" alt="image" src="https://github.com/user-attachments/assets/dac04f84-64f1-4902-b10a-217c72816d81" />

```sql
UPDATE Products
set category = 'Household'
where product_name LIKE '%Detergent%';
```

**Output:**

<img width="1233" height="549" alt="image" src="https://github.com/user-attachments/assets/077c8797-ef8a-4eb5-93a4-91384c07b1e8" />

**Question 4**
---
<img width="1087" height="327" alt="image" src="https://github.com/user-attachments/assets/f9ed1e26-d196-4626-8ab8-2e33277c6da9" />

```sql
update Products
set sell_price = sell_price*1.10
where category= 'Bakery';
```

**Output:**

<img width="1253" height="478" alt="image" src="https://github.com/user-attachments/assets/e9ceb3f4-438d-4bfb-90c3-47ef02b5eb22" />

**Question 5**
---
<img width="1193" height="568" alt="image" src="https://github.com/user-attachments/assets/a7dc7435-c67c-4aa2-8c4f-95e114cff9a8" />

```sql
UPDATE Products
SET reorder_lvl = 40
WHERE category = 'Grocery';
```

**Output:**

<img width="1224" height="454" alt="image" src="https://github.com/user-attachments/assets/4c5d85e0-5135-41b3-9e26-a9228cf66622" />

**Question 6**
---
<img width="1146" height="203" alt="image" src="https://github.com/user-attachments/assets/25542420-0c0b-443e-a911-dcc31bbf993a" />

```sql
delete from Doctors
where specialization = 'Cardiology';
```

**Output:**

<img width="1225" height="404" alt="image" src="https://github.com/user-attachments/assets/c9dcfc98-6e86-4891-ae49-86b4ab4aa64e" />

**Question 7**
---
<img width="1241" height="701" alt="image" src="https://github.com/user-attachments/assets/32f7b31f-f3a5-4881-bb10-d0ec49bde558" />

```sql
delete from Customer
where grade < 2;
```

**Output:**

<img width="739" height="560" alt="image" src="https://github.com/user-attachments/assets/79b78187-0394-4508-b1e6-ee55e0c8ea8e" />

**Question 8**
---
<img width="1262" height="647" alt="image" src="https://github.com/user-attachments/assets/31c0c3c4-77db-4b97-a2b8-6ca0a4595532" />

```sql
delete from Customer 
where WORKING_AREA = 'New York';
```

**Output:**

<img width="1217" height="779" alt="image" src="https://github.com/user-attachments/assets/2db8a244-2b10-4c47-a787-ed541fa6e17a" />

**Question 9**
---
<img width="1273" height="532" alt="image" src="https://github.com/user-attachments/assets/bbc0667c-abe0-4a1a-8a7e-bdf97dfd4b3f" />

```sql
delete from Customer 
where grade % 2 =1;
```

**Output:**

<img width="1234" height="461" alt="image" src="https://github.com/user-attachments/assets/00025107-b51d-4ed0-b0f6-6a6b38133a12" />

**Question 10**
---
<img width="1235" height="516" alt="image" src="https://github.com/user-attachments/assets/7a68064f-e82e-4f98-bcb9-137d2e4aa6eb" />

```sql
delete from Customer 
where ( GRADE = 3 or AGENT_CODE = 'A008')
AND OUTSTANDING_AMT <5000;
```

**Output:**

<img width="1221" height="427" alt="image" src="https://github.com/user-attachments/assets/63bcfb24-e8ee-41b4-bfcd-f6d43cf3868a" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
