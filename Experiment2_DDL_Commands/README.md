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
-- <img width="1158" height="601" alt="image" src="https://github.com/user-attachments/assets/31e13d55-2990-4efc-aa6c-9a516c0b425e" />


```sql
alter table Student_details
add column mobilenumber number;
```

**Output:**

<img width="1222" height="370" alt="image" src="https://github.com/user-attachments/assets/7a9c2529-2f4d-44ae-959a-de4f639569c5" />

**Question 2**
---
-- <img width="1281" height="286" alt="image" src="https://github.com/user-attachments/assets/b276eb32-201e-40c9-a6be-cd169db5b6c1" />


```sql
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (201, 'David Lee', 'M', 'Physics', 92);

```

**Output:**

<img width="1279" height="254" alt="image" src="https://github.com/user-attachments/assets/fe4e1992-d0ba-402c-abf3-d2e9cf205b5e" />


**Question 3**
---
<img width="1217" height="477" alt="image" src="https://github.com/user-attachments/assets/c3843151-f09e-4c2b-a89c-c8ab554a026a" />


```sql
create table Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT);
```

**Output:**

<img width="1347" height="498" alt="image" src="https://github.com/user-attachments/assets/11ed654b-4f81-4f59-862b-9c9f58d41de1" />

**Question 4**
---
<img width="1315" height="524" alt="image" src="https://github.com/user-attachments/assets/bb4d88b3-a5a9-4667-9ccb-90a19660974b" />

```sql
CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10, 2) NOT NULL,
    discount DECIMAL(10, 2) DEFAULT 0 NOT NULL,
    CONSTRAINT products CHECK (list_price >= discount AND discount >= 0)
);

```

**Output:**

<img width="1294" height="341" alt="image" src="https://github.com/user-attachments/assets/61ddc45b-26fb-47f9-acca-fcc40d25787a" />

**Question 5**
---
<img width="1119" height="378" alt="image" src="https://github.com/user-attachments/assets/7c542df7-03ad-4cda-b738-46fec61814fb" />

```sql
INSERT INTO Customers (CustomerID, Name, Address, Email)
SELECT CustomerID, Name, Address, Email
FROM old_customers;
```

**Output:**

<img width="1269" height="332" alt="image" src="https://github.com/user-attachments/assets/ea166527-1128-4fbe-9374-8b813bde4e98" />

**Question 6**
---
<img width="1296" height="469" alt="image" src="https://github.com/user-attachments/assets/c85dd417-7a60-41da-be0a-0aafc74b3ca4" />

```sql
create table contacts(
contact_id INTEGER PRIMARY KEY,
first_name TEXT not NULL,
last_name TEXT not NULL,
email TEXT,
phone TEXT NOT NULL CHECK (length(phone)==10)
);
```

**Output:**

<img width="1220" height="397" alt="image" src="https://github.com/user-attachments/assets/16c67286-e4ee-49ee-99cc-06968ce979a0" />

**Question 7**
---
<img width="1256" height="596" alt="image" src="https://github.com/user-attachments/assets/503d70e1-8030-462b-834c-972350a0a20b" />

```sql
alter table customer
rename column city to location;
```

**Output:**

<img width="1219" height="399" alt="image" src="https://github.com/user-attachments/assets/460849bf-b641-4ddf-ac5c-fa47c2205fc5" />

**Question 8**
---
<img width="1351" height="521" alt="image" src="https://github.com/user-attachments/assets/75b39304-582f-4cab-840e-cbe8e9ceffa7" />

```sql
INSERT INTO books (ISBN, Title,Author)
VALUES ('978-1234567890', 'Introduction to AI','John Doe');

INSERT INTO books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-9876543210', 'Deep Learning', 'Jane Doe', 'TechPress', 2022);

INSERT INTO books (ISBN, Title, Author,  Year)
VALUES ('978-1122334455', 'Cybersecurity Essentials', 'Alice Smith', 2021);

```

**Output:**

<img width="1238" height="376" alt="image" src="https://github.com/user-attachments/assets/a0b7b8cd-80e7-488d-8feb-2c6761fb80e3" />

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
<img width="1250" height="380" alt="image" src="https://github.com/user-attachments/assets/13d6a88d-2c1e-4c98-9562-7d99cbfe2c4b" />

```sql
CREATE TABLE ProjectAssignments (
    AssignmentID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    ProjectID INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1349" height="339" alt="image" src="https://github.com/user-attachments/assets/41442e39-79bb-404f-bbc6-26f6db9292d9" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
