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
![image](https://github.com/user-attachments/assets/d9114a32-4836-429a-a50a-0cb81197072d)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission)
    FROM salesman
);

```

**Output:**

![image](https://github.com/user-attachments/assets/7973a7d3-7ed9-4477-a503-0505ae6307d8)


**Question 2**
---
![image](https://github.com/user-attachments/assets/322c5ac3-a8ec-4bda-8193-51ebda10b395)


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);

```

**Output:**

![image](https://github.com/user-attachments/assets/e635d7f4-f4e1-4fc8-8fba-15ccfe54d73f)


**Question 3**
---
![image](https://github.com/user-attachments/assets/1a9c8eae-81b1-4c18-96f0-009cd4dbd8dc)


```sql
SELECT grade, COUNT(*) 
FROM customer 
WHERE grade > (
    SELECT AVG(grade) 
    FROM customer 
    WHERE city = 'New York'
)
GROUP BY grade;

```

**Output:**

![image](https://github.com/user-attachments/assets/200a89c1-e3cd-484d-9474-323add496201)


**Question 4**
---
![image](https://github.com/user-attachments/assets/60c7daa4-355e-41a6-8625-396a06c3e68a)


```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

![image](https://github.com/user-attachments/assets/fd6ae860-8dc8-4054-be6f-83445e31cc81)


**Question 5**
---
![image](https://github.com/user-attachments/assets/95b97961-c54f-4227-a5b6-55fec3e80f55)


```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

![image](https://github.com/user-attachments/assets/ce6a92c6-3e36-403a-b36f-6f6b725874fc)


**Question 6**
---
![image](https://github.com/user-attachments/assets/adc2daab-bbb9-4e78-9e13-d9638d80a07d)


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi' AND AGE < 30
order by id asc;
```

**Output:**

![image](https://github.com/user-attachments/assets/3f7c11a6-7791-43f7-979a-68231aa7488d)


**Question 7**
---
![image](https://github.com/user-attachments/assets/9493c9ce-6583-4609-a6d8-c76e58323c14)


```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

![image](https://github.com/user-attachments/assets/6da3d439-2f6a-4d1f-9c7f-2a90226109f4)


**Question 8**
---
![image](https://github.com/user-attachments/assets/2233dbb8-b6b0-41d4-b097-5c931c98e19f)


```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/10544912-897e-4cc5-8699-064e35e99d02)


**Question 9**
---
![image](https://github.com/user-attachments/assets/8581f0a3-df19-47f6-ba59-d1d241acd0b5)


```sql
SELECT *
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);

```

**Output:**

![image](https://github.com/user-attachments/assets/c8196b0e-a3a0-4d8b-9f25-8c5fd01ebb56)


**Question 10**
---
![image](https://github.com/user-attachments/assets/6cface3d-2a0a-4ec2-9dfa-2785e43eac35)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

![image](https://github.com/user-attachments/assets/8af2acba-fbfe-4166-823e-156f6d951790)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
