# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.
### Program: 
<img width="851" height="701" alt="image" src="https://github.com/user-attachments/assets/33228833-68be-4eae-b2c5-7f9599c3bd0a" />


**Expected Output:**  
Greater number is: 80

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.
### Program: 
<img width="835" height="717" alt="image" src="https://github.com/user-attachments/assets/de1d82da-1249-4c65-828d-2c0415a6a92d" />



**Expected Output:**  
Sum of first 10 natural numbers is: 55

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
### Program: 
<img width="826" height="526" alt="image" src="https://github.com/user-attachments/assets/d2fd1e15-0422-4441-ab15-abd2ae45b3b3" />
<img width="682" height="389" alt="image" src="https://github.com/user-attachments/assets/8e7a9bfc-7331-4280-ac70-05f40f95857a" />


**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
### Program: 
<img width="831" height="445" alt="image" src="https://github.com/user-attachments/assets/ab639dd2-ccef-43c4-b1ef-89b2ac6dcaa9" />
<img width="679" height="263" alt="image" src="https://github.com/user-attachments/assets/ea70b3a6-f889-4926-addb-df42105ffdd7" />


**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
### Program: 
<img width="827" height="467" alt="image" src="https://github.com/user-attachments/assets/5e6ea3bc-2b88-4e52-84a1-e91293abe179" />
<img width="680" height="275" alt="image" src="https://github.com/user-attachments/assets/8a6f039b-acef-4cca-8165-16f7b9f2f54c" />

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.





