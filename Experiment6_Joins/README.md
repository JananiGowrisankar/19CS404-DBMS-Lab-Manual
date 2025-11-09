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
<img width="1217" height="416" alt="image" src="https://github.com/user-attachments/assets/5345f0c5-7d18-4b4d-939d-db5d61c63b4d" />


```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id=c.salesman_id
WHERE c.city="New York";
```

**Output:**

<img width="1203" height="555" alt="image" src="https://github.com/user-attachments/assets/140214c1-46b9-44b0-aa73-6fc703abb72b" />


**Question 2**
---
<img width="1241" height="781" alt="image" src="https://github.com/user-attachments/assets/9a9f7a98-b6c3-4154-8fdf-5560dda904af" />


```sql
SELECT p.first_name as patient_name,t.test_name
FROM patients p
INNER JOIN test_results t ON p.patient_id=t.patient_id;
```

**Output:**

<img width="1256" height="673" alt="image" src="https://github.com/user-attachments/assets/90b3aff0-f07f-40df-ad06-cf1bb454ec74" />


**Question 3**
---
<img width="1290" height="756" alt="image" src="https://github.com/user-attachments/assets/5f1354be-0b9c-4306-a512-0f04a981ae21" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name as "Customer Name",
    c.grade,
    s.name AS Salesman,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1346" height="699" alt="image" src="https://github.com/user-attachments/assets/b3801451-5713-4ce9-af23-a738628030c8" />


**Question 4**
---
<img width="1276" height="896" alt="image" src="https://github.com/user-attachments/assets/09ec892d-d3ae-4c37-8485-f9b5fd1974c5" />


```sql
SELECT c.cust_name,c.city,c.grade,s.name as Salesman,s.city
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
ORDER BY customer_id;
```

**Output:**

!<img width="1320" height="739" alt="image" src="https://github.com/user-attachments/assets/797efcb7-578d-4aeb-a542-d0b5a4ded239" />


**Question 5**
---
<img width="1324" height="530" alt="image" src="https://github.com/user-attachments/assets/5c40d86d-220d-42ea-8304-e0d8accaf030" />

```sql
SELECT s.name as salesman_name,c.cust_name as customer_name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id=c.salesman_id;
```

**Output:**

<img width="1333" height="832" alt="image" src="https://github.com/user-attachments/assets/9de90193-a224-4d13-b90e-1d74d9175c44" />


**Question 6**
---
<img width="1277" height="630" alt="image" src="https://github.com/user-attachments/assets/9d351846-98a1-465a-9a31-44ea1bd94a1f" />


```sql
SELECT p.first_name as patient_name
FROM patients p
INNER JOIN test_results t ON p.patient_id=t.patient_id
WHERE t.test_name="Blood Pressure";
```

**Output:**

<img width="1141" height="362" alt="image" src="https://github.com/user-attachments/assets/38f4b611-4ae5-42bb-8a81-c9010c5101c2" />


**Question 7**
---
<img width="1304" height="771" alt="image" src="https://github.com/user-attachments/assets/052d009b-c748-4164-8692-ae8c918fa638" />


```sql
SELECT c.cust_name as "Customer Name",c.city,s.name as Salesman,s.commission
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
WHERE s.commission>0.12;
```

**Output:**

<img width="1359" height="695" alt="image" src="https://github.com/user-attachments/assets/19bf8daa-87ac-4321-80ce-1e564c764569" />


**Question 8**
---
<img width="1343" height="766" alt="image" src="https://github.com/user-attachments/assets/a118db85-454c-4a7c-90c8-fcabb71cd6d7" />


```sql
SELECT c.cust_name,c.city,c.grade,s.name as Salesman,s.city
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
WHERE c.grade<300
ORDER BY c.customer_id ASC;```

**Output:**

<img width="1341" height="635" alt="image" src="https://github.com/user-attachments/assets/454eeb84-a8db-4eda-991a-9d5d192b2fd5" />


**Question 9**
---
<img width="1327" height="616" alt="image" src="https://github.com/user-attachments/assets/a975ad83-f866-46af-9f76-30cf75719d08" />


```sql
SELECT p.first_name as patient_name,a.appointment_id,p.patient_id,a.doctor_id,a.appointment_date
FROM appointments a
INNER JOIN patients p ON a.patient_id=p.patient_id;
```

**Output:**

<img width="1330" height="477" alt="image" src="https://github.com/user-attachments/assets/1c11ce59-7d3e-4cf3-bc04-602b16a6b152" />


**Question 10**

---<img width="1373" height="722" alt="image" src="https://github.com/user-attachments/assets/9410db7f-d910-4a5a-b596-59ed898e8528" />


```sql
SELECT c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
ORDER BY o.ord_date ASC ;
```

**Output:**

<img width="1347" height="716" alt="image" src="https://github.com/user-attachments/assets/94e62856-1254-426f-b3f6-d28a92628e0e" />

**RESULT**
Thus, the SQL queries to implement different types of joins have been executed successfully.
