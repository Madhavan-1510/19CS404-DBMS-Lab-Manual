# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/673802e5-2d85-48b9-b33a-cfbba8705f32)


```sql
SELECT patients.first_name, surgeries.*
FROM patients
INNER JOIN surgeries
ON patients.patient_id = surgeries.patient_id
WHERE patients.date_of_birth > '1990-01-01';

```

**Output:**

![image](https://github.com/user-attachments/assets/0ef1fd70-47d9-4e16-97b9-014558b5bee1)


**Question 2**
---
![image](https://github.com/user-attachments/assets/80bbc0cc-afae-48cd-8e02-f6a7e23709ae)


```sql
SELECT orders.ord_no, 
       orders.purch_amt, 
       orders.ord_date, 
       customer.cust_name, 
       customer.city AS customer_city, 
       customer.grade, 
       salesman.name AS salesman_name, 
       salesman.city AS salesman_city, 
       salesman.commission
FROM orders
INNER JOIN customer ON orders.customer_id = customer.customer_id
INNER JOIN salesman ON orders.salesman_id = salesman.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/f1c29cef-eae4-4ef5-86d2-8c8979ace9a8)


**Question 3**
---
![image](https://github.com/user-attachments/assets/2b0765b4-6ace-4c67-af35-55df5e97274d)


```sql
SELECT customer.cust_name, 
       customer.city AS city, 
       customer.grade, 
       salesman.name AS Salesman, 
       salesman.city AS city
FROM customer
INNER JOIN salesman ON customer.salesman_id = salesman.salesman_id
WHERE customer.grade < 300
ORDER BY customer.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/53cc0c67-be05-42a1-8dfd-c0d9ae406aec)


**Question 4**
---
![image](https://github.com/user-attachments/assets/e189c50a-067e-4660-9f0b-a11f61939609)


```sql
SELECT n.nurse_id, d.department_name
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE n.first_name = 'David' AND n.last_name = 'Moore';

```

**Output:**

![image](https://github.com/user-attachments/assets/d3bc5cac-b29e-4af0-97dc-4fbc4a2e846f)


**Question 5**
---
![image](https://github.com/user-attachments/assets/7371edc8-a501-4e21-90b9-de524e1dd944)


```sql
SELECT o.ord_no, o.ord_date, o.purch_amt, c.cust_name AS "Customer Name", c.grade, s.name AS Salesman, s.commission
FROM orders o
INNER JOIN customer c ON o.customer_id = c.customer_id
INNER JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/588934c7-80ff-469a-becc-e12c8ad58893)


**Question 6**
---
![image](https://github.com/user-attachments/assets/ba0c6fb4-6508-4d0d-81ce-00f8cdbd485e)


```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';

```

**Output:**

![image](https://github.com/user-attachments/assets/09991721-4218-4666-84b0-8f075a926975)


**Question 7**
---
![image](https://github.com/user-attachments/assets/32054430-ec84-4796-a4ba-06a1ef517f6c)


```sql
SELECT c.cust_name, s.name
FROM customer c
LEFT JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city = s.city;

```

**Output:**

![image](https://github.com/user-attachments/assets/13b6632f-d7ec-4c22-bbbb-8c94fdaba5d2)


**Question 8**
---
![image](https://github.com/user-attachments/assets/e6a4febe-8b9b-401e-9d82-09d5c58c18f4)


```sql
SELECT c.cust_name AS "Customer Name", 
       c.city AS "city", 
       s.name AS "Salesman", 
       s.commission AS "commission"
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/f92c0726-dfc9-4b78-bd19-ea10805f4adf)


**Question 9**
---
![image](https://github.com/user-attachments/assets/63d4c1b4-333e-4e19-a5d4-5a128e28eeb2)


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';

```

**Output:**

![image](https://github.com/user-attachments/assets/244e6cd7-62c0-40f1-be73-9f0c98c8976b)


**Question 10**
---
![image](https://github.com/user-attachments/assets/8dc0f150-ce75-4690-b00d-ce44e6fe5a19)


```sql
SELECT c.cust_name as "Customer Name", c.city AS city, s.name AS Salesman, s.city AS city, s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city != s.city
AND s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/824623ed-1880-45ac-b36b-925ba6ed528f)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
