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
---
![Question1](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL1q.png)

```sql
create table Members(MemberID INTEGER, MemberName TEXT, JoinDate DATE);
```

**Output:**

![Output1](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_1.png)

**Question 2**
---
![Question2](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl2.png)

```sql
CREATE TABLE Invoices 
(InvoiceID INTEGER UNIQUE,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate>InvoiceDate),
Amount REAL CHECK(Amount>0)
);
```

**Output:**

![Output2](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_2.png)

**Question 3**
---
![Question3](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl3.png)

```sql
CREATE TABLE Invoices 
(InvoiceID INTEGER UNIQUE,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate>InvoiceDate),
Amount REAL CHECK(Amount>0)
);
```

**Output:**

![Output3](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_3.png)

**Question 4**
---
![Question4](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl4.png)

```sql
ALTER TABLE Companies RENAME name TO first_name;
ALTER TABLE Companies ADD COLUMN mobilenumber number;
ALTER TABLE Companies ADD COLUMN DOB Date;
ALTER TABLE Companies ADD COLUMN State varchar(30);
```

**Output:**

![Output4](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_4.png)


**Question 5**
---
![Question5](https://github.com/Madhavan-1510/Files_RM/blob/main/dd5.png)

```sql
insert into Products (ProductID,ProductName,Price,Stock) select ProductID,ProductName,Price,Stock from Discontinued_products;
```

**Output:**

![Output5](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_5.png)

**Question 6**
---
![Question6](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl6.png)

```sql
ALTER TABLE Companies ADD COLUMN designation varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary number;
ALTER TABLE Companies ADD COLUMN dob date;
```

**Output:**

![Output6](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_6.png)

**Question 7**
---
![Question7](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl7.png)

```sql
CREATE TABLE Shipments
(ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers,
FOREIGN KEY(OrderID) REFERENCES Orders
);
```

**Output:**

![Output7](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_7.png)

**Question 8**
---
![Question8](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl8.png)

```sql
CREATE TABLE jobs 
(job_id INTEGER,
job_title VARCHAR(30) DEFAULT "",
min_salary NUMBER DEFAULT '8000',
max_salary NUMBER DEFAULT NULL
);
```

**Output:**

![Output8](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_8.png)

**Question 9**
---
![Question9](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl9.png)

```sql
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (306,"Diana Prince","Themyscira",NULL,NULL);
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (307,"Bruce Wayne","Wayne Manor","Gotham",10007);
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (308,"Peter Parker","Queens",NULL,11375);
```

**Output:**

![Output9](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_9.png)

**Question 10**
---
![Question10](https://github.com/Madhavan-1510/Files_RM/blob/main/ddl10.png)

```sql
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (301,"Michael Jordan","123 Maple St","Chicago",60616);
```

**Output:**

![Output10](https://github.com/Madhavan-1510/Files_RM/blob/main/DDL_10.png)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
