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
<img width="1205" height="531" alt="image" src="https://github.com/user-attachments/assets/7ff81ba3-ef9c-4ddd-918b-c6cdf461020d" />


```sql
UPDATE Products
SET reorder_lvl=20
WHERE quantity<10 AND category='Snacks';
```

**Output:**

<img width="1163" height="599" alt="image" src="https://github.com/user-attachments/assets/7a820461-6dc9-44e7-acd5-16a1bacd3460" />


**Question 2**
---
<img width="1201" height="708" alt="image" src="https://github.com/user-attachments/assets/eca2e54b-7d70-49ab-9da9-1e287fdccaa9" />


```sql
UPDATE Employees
SET email='not available',
    commission_pct=0.55
WHERE department_id=110;
```

**Output:**

<img width="1171" height="417" alt="image" src="https://github.com/user-attachments/assets/a3012492-fec0-434b-9e4d-d1a0bb63f73d" />


**Question 3**
---
<img width="1184" height="682" alt="image" src="https://github.com/user-attachments/assets/66afd22e-8f0c-4184-a72c-7e2f3691b6f0" />


```sql
UPDATE purchases
SET per_unit_price=25,
total_price=25*quantity
WHERE purchase_date='2022-08-15' AND product_id=12;
```

**Output:**

<img width="1172" height="557" alt="image" src="https://github.com/user-attachments/assets/0728744a-ee06-4163-9781-80471d57d3f2" />


**Question 4**
---
<img width="1186" height="701" alt="image" src="https://github.com/user-attachments/assets/5fb76941-ffe5-4d3d-9b2d-ffd0607f78db" />


```sql
UPDATE Employees
SET salary=2*salary
WHERE department_id=20 AND job_id LIKE '%MAN';
```

**Output:**

<img width="1181" height="377" alt="image" src="https://github.com/user-attachments/assets/ec1763d9-7a7b-48f3-ac59-f11cfa026e71" />


**Question 5**
---
<img width="1186" height="594" alt="image" src="https://github.com/user-attachments/assets/12622311-872e-49fb-883d-67f59149f939" />


```sql
DELETE FROM Doctors
WHERE (specialization='Pediatrics' OR specialization='Cardiology') AND last_name='Brown';
```

**Output:**

<img width="1194" height="918" alt="image" src="https://github.com/user-attachments/assets/9bc7f623-b9c2-43ff-8056-7fba022c9934" />


**Question 6**
---
<img width="1117" height="342" alt="image" src="https://github.com/user-attachments/assets/9ee0754b-88f5-4d8f-aeef-e8f563cabe02" />


```sql
UPDATE products
SET product_name='Premium Bread'
WHERE product_id=5;
```

**Output:**

<img width="1176" height="433" alt="image" src="https://github.com/user-attachments/assets/44aa6360-cd4e-45e1-a7b3-cb7d6f4fe02f" />


**Question 7**
---
<img width="1216" height="733" alt="image" src="https://github.com/user-attachments/assets/9fc38fd4-451e-4c14-b01d-47da5f5e6ee3" />


```sql
DELETE FROM customer
WHERE CUST_CITY LIKE 'L%';
```

**Output:**

<img width="1244" height="877" alt="image" src="https://github.com/user-attachments/assets/b0495e1a-0530-4a60-97db-432c77c48981" />


**Question 8**
---
<img width="1243" height="613" alt="image" src="https://github.com/user-attachments/assets/7c2928a1-3c31-4146-a19a-4a6641bf4c02" />


```sql
DELETE FROM customer
WHERE GRADE>=2;
```

**Output:**

<img width="1227" height="488" alt="image" src="https://github.com/user-attachments/assets/518510fe-0c89-48f0-a529-58e1767fa50b" />


**Question 9**
---
<img width="980" height="452" alt="image" src="https://github.com/user-attachments/assets/c0de4708-014c-432a-bf51-f4d6f101645c" />


```sql
SELECT * FROM EmployeeInfo
ORDER BY EmpID DESC
LIMIT 5;
```

**Output:**

<img width="1231" height="315" alt="image" src="https://github.com/user-attachments/assets/7294573c-60a7-4f6d-8071-c1f2f79fc5a0" />


**Question 10**
---
<img width="1237" height="570" alt="image" src="https://github.com/user-attachments/assets/e1618e16-4a5a-4c38-8733-539f6d18e9d7" />


```sql
SELECT
ord_no,
purch_amt,
ord_date,
customer_id,
salesman_id
FROM orders
WHERE (purch_amt<200 OR ord_date<='2012-02-10' AND customer_id<=3009) or ord_no=70003;
```

**Output:**

<img width="1237" height="421" alt="image" src="https://github.com/user-attachments/assets/1c372d91-be6b-47ed-9166-b0c0d9b2c07e" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
