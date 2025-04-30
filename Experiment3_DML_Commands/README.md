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
![Question1](https://github.com/user-attachments/assets/01b72022-5fb0-4ba7-998e-c1221417570e)

```sql
UPDATE EMPLOYEES
SET email='not available',commission_pct=0.55 where department_id= 110;
```

**Output:**

![Output1](https://github.com/user-attachments/assets/22d56edd-6c39-4aec-afd0-b3b8e235a666)

**Question 2**
---
![Question2](https://github.com/user-attachments/assets/0db22fab-7ab2-4c2a-888d-86ce1de0973f)

```sql
update Products
set quantity=1.1*quantity;
```

**Output:**

![Output2](https://github.com/user-attachments/assets/28ca6b06-908e-4397-9b88-ebe5257cb5e3)

**Question 3**
---
![Question3](https://github.com/user-attachments/assets/390a8859-0b2d-4fe5-b65c-476eebbb8c1a)

```sql
update employees
set email='Unavailable';
```

**Output:**

![Output3](https://github.com/user-attachments/assets/8864c9cb-2eea-4b83-9855-98a7640dc8ed)


**Question 4**
---
![Question4](https://github.com/user-attachments/assets/af7159f1-a7fb-41de-8f01-0a9cb1aae537)

```sql
update employees
set hire_date='2024-01-24' where department_id=50;
```

**Output:**

![Output4](https://github.com/user-attachments/assets/19009921-7ff2-496a-a848-2ce3497127ca)


**Question 5**
---
![Question5](https://github.com/user-attachments/assets/d684734c-d5be-420b-8086-648c123c5dc8)


```sql
delete from customer
where GRADE<2;
```

**Output:**

![Output5](https://github.com/user-attachments/assets/134454ad-4a72-4dcb-8e6d-7431a16fc194)

**Question 6**
---
![Question6](https://github.com/user-attachments/assets/071cefff-07b9-4545-81a1-97c69a97fde9)


```sql
SELECT EMPID,EMPPOSITION,DATEOFJOINING,SALARY FROM EMPLOYEEPOSITION 
WHERE SALARY BETWEEN 50000 AND 100000;
```

**Output:**

![Output6](https://github.com/user-attachments/assets/23aeb669-5f05-45a1-8bfd-6c3d651a4a26)

**Question 7**
---
![Question7](https://github.com/user-attachments/assets/7d6e4e75-6e1d-4c74-8b9b-327134636c2f)


```sql
SELECT * FROM EMPLOYEEINFO WHERE EMPFNAME LIKE 'S%';
```

**Output:**

![Output7](https://github.com/user-attachments/assets/684f8f49-956b-4e62-a74b-f911b8fb0428)


**Question 8**
---
![Question8](https://github.com/user-attachments/assets/678d04bd-1749-4ba0-b7fa-4f3d39184eeb)


```sql
SELECT ID,VALUE1,
CASE
WHEN VALUE1%2!=0 THEN 'Odd'
ELSE 'Even'
END AS parity
FROM Calculations;
```

**Output:**

![Output8](https://github.com/user-attachments/assets/edcc426e-8afa-4798-94db-1f7fd39f380e)


**Question 9**
---
![Question9](https://github.com/user-attachments/assets/c80b59b6-f450-4edc-b1ad-d8717fbcfa8f)


```sql
SELECT CUSTOMER_ID,CUST_NAME,CITY,GRADE,SALESMAN_ID FROM CUSTOMER WHERE GRADE IS NULL;
```

**Output:**

![Output9](https://github.com/user-attachments/assets/127955ab-3780-4b7d-a2dc-d1b8c274a05e)

**Question 10**
---
![Question10](https://github.com/user-attachments/assets/fb1586e5-7972-4aa7-b2c3-2869a4b45a07)

```sql
SELECT ID,ROUND(DECIMAL,3) AS rounded_value
FROM CALCULATIONS;
```

**Output:**

![Output10](https://github.com/user-attachments/assets/e9f33e22-2e04-4373-bf97-2fc90fc24f3e)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
