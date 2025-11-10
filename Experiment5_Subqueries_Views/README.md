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
<img width="1268" height="786" alt="image" src="https://github.com/user-attachments/assets/430bdb47-eb38-4172-bdbb-d2b6662caf6a" />


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission) FROM salesman
);
```

**Output:**

<img width="1090" height="410" alt="image" src="https://github.com/user-attachments/assets/96cc1cbd-d07f-4dd4-8b76-fcc884e5ef2f" />

**Question 2**
---
<img width="1279" height="781" alt="image" src="https://github.com/user-attachments/assets/0a00b5e7-4a66-4dd7-ac86-7bfd2aa082e2" />


```sql
SELECT
o.ord_no,
o.purch_amt,
o.ord_date,
o.customer_id,
o.salesman_id
FROM
orders o
JOIN salesman s on o.salesman_id=s.salesman_id
WHERE s.city="New York";
```

**Output:**

<img width="1261" height="453" alt="image" src="https://github.com/user-attachments/assets/9343a7e9-f2ad-409a-8432-26c036281d3a" />


**Question 3**
---
<img width="1208" height="656" alt="image" src="https://github.com/user-attachments/assets/5bd02b3c-3a1e-4c58-bdd6-334a3cb910fb" />


```sql
SELECT * FROM CUSTOMERS
WHERE SALARY<2500;
```

**Output:**

<img width="1255" height="422" alt="image" src="https://github.com/user-attachments/assets/e58fcc35-d7d3-4104-b13a-be1362dc08e4" />


**Question 4**
---
<img width="1138" height="541" alt="image" src="https://github.com/user-attachments/assets/89eb195a-69e2-44a9-80ba-cac77d77d3f6" />


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

<img width="1108" height="434" alt="image" src="https://github.com/user-attachments/assets/8726b9e9-32f2-4f5a-be95-3b9b4039118e" />


**Question 5**
---
<img width="1106" height="444" alt="image" src="https://github.com/user-attachments/assets/0a86c35f-63d4-4f03-baa3-c0a9c6e5d65b" />


```sql
SELECT
department_id,
department_name
FROM
Departments
WHERE LENGTH(department_name)>
(
    SELECT AVG(LENGTH(department_name))
    FROM Departments
);
```

**Output:**

<img width="775" height="366" alt="image" src="https://github.com/user-attachments/assets/4e92ce3d-3a78-4094-8e1c-52cc71f0cb31" />


**Question 6**
---
<img width="1245" height="615" alt="image" src="https://github.com/user-attachments/assets/2979f562-3dbc-44bc-bcb6-6287b318ba45" />

```sql
SELECT g.student_name, g.grade
FROM GRADES g
JOIN (
    SELECT subject, MAX(grade) AS max_grade
    FROM GRADES
    GROUP BY subject
) m ON g.subject = m.subject AND g.grade = m.max_grade;

```

**Output:**

<img width="1033" height="409" alt="image" src="https://github.com/user-attachments/assets/623b8170-95d2-4924-835a-ee487b427263" />


**Question 7**
---
<img width="1175" height="708" alt="image" src="https://github.com/user-attachments/assets/69257e09-f63b-4f75-9f8c-9c2d03ae0d03" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;

```

**Output:**

<img width="1183" height="555" alt="image" src="https://github.com/user-attachments/assets/e41b121d-2120-43ac-b8f3-84d5b7193da8" />


**Question 8**
---
<img width="1071" height="506" alt="image" src="https://github.com/user-attachments/assets/0f94b19a-4528-41eb-9ccb-ca41c3824b28" />


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

<img width="828" height="434" alt="image" src="https://github.com/user-attachments/assets/9b0fac01-7dd5-4c65-9bf2-872d87444efc" />


**Question 9**
---
<img width="1174" height="672" alt="image" src="https://github.com/user-attachments/assets/97a932e8-aecf-4faa-9dd7-b179b6bbea9f" />

```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;
```

**Output:**

<img width="1239" height="407" alt="image" src="https://github.com/user-attachments/assets/c93dc056-862b-45fb-812e-fb537efe46d0" />


**Question 10**
---
<img width="1275" height="733" alt="image" src="https://github.com/user-attachments/assets/4c0311f1-6a92-48d1-af2b-c7cc31e227d2" />


```sql
SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id=s.salesman_id
WHERE s.name="Paul Adam";
```

**Output:**

<img width="1251" height="370" alt="image" src="https://github.com/user-attachments/assets/6a89e089-40aa-4230-922b-989a3ead037e" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
