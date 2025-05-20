# Experiment 6: PL/SQL – Variables, Control Structures and Loops

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

**Expected Output:**  
Greater number is: 80

**ANSWER**
```sql
DECLARE
   num1 NUMBER := 45;  -- You can change these values as needed
   num2 NUMBER := 80;
BEGIN
   IF num1 > num2 THEN
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
   ELSE
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
   END IF;
END;
```
**OUTPUT**
![OUTPUT](https://github.com/user-attachments/assets/40470541-ed93-4f8d-88c7-090163fef3b9)

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**ANSWER**
```sql
DECLARE
   n   NUMBER := 10;   -- You can change this value as needed
   i   NUMBER := 1;
   sum NUMBER := 0;
BEGIN
   WHILE i <= n LOOP
      sum := sum + i;
      i := i + 1;
   END LOOP;
   
   DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
```
**OUTPUT**
![image](https://github.com/user-attachments/assets/7a35a21d-90c9-4d18-ad0a-3c86aedd3337)

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**ANSWER**
```sql
DECLARE
   n   NUMBER := 7;      -- Number of terms to generate
   a   NUMBER := 0;      -- First term
   b   NUMBER := 1;      -- Second term
   c   NUMBER;           -- Next term
   i   NUMBER := 3;      -- Start from the 3rd term
   output_string VARCHAR2(1000);
BEGIN
   output_string := a || ', ' || b;

   WHILE i <= n LOOP
      c := a + b;
      output_string := output_string || ', ' || c;
      a := b;
      b := c;
      i := i + 1;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || output_string);
END;
```
**OUTPUT**
![image](https://github.com/user-attachments/assets/71c290df-4adc-4cb2-8041-e941a956e3de)

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

**ANSWER**
```sql
DECLARE
   n          NUMBER := 1535;   -- Original number
   reversed   NUMBER := 0;
   digit      NUMBER;
   temp       NUMBER := n;
BEGIN
   WHILE temp > 0 LOOP
      digit := MOD(temp, 10);                  -- Extract last digit
      reversed := (reversed * 10) + digit;     -- Append digit to reversed number
      temp := TRUNC(temp / 10);                -- Remove last digit
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('n = ' || n);
   DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;
```
**OUTPUT**
![image](https://github.com/user-attachments/assets/a99d311e-e0fc-452d-8510-6d9865006856)

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**ANSWER**
```sql
DECLARE
   a NUMBER := 10;
   b NUMBER := 9;
   c NUMBER := 15;
   largest NUMBER;
BEGIN
   IF a >= b AND a >= c THEN
      largest := a;
   ELSIF b >= a AND b >= c THEN
      largest := b;
   ELSE
      largest := c;
   END IF;

   DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
   DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
```
**OUTPUT**
![image](https://github.com/user-attachments/assets/82beced0-c78d-4dc3-ba11-6a8c467cf06e)


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
