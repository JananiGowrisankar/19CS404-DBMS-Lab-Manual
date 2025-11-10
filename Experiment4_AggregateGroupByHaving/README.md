# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="1159" height="541" alt="image" src="https://github.com/user-attachments/assets/29472da9-7848-4644-b0c2-2e198426522f" />


```sql
SELECT
PatientID,
COUNT(Medications) as AvgMedications
FROM 
MedicalRecords
GROUP BY
PatientID;
```

**Output:**

<img width="1157" height="637" alt="image" src="https://github.com/user-attachments/assets/e2e2f3e9-6694-4189-8d7d-0c2bfaeb248f" />


**Question 2**
---
<img width="1146" height="680" alt="image" src="https://github.com/user-attachments/assets/00a924bd-ef4d-4fd5-9a75-383a2e40a696" />


```sql
SELECT
Medication,
Count(Medication) AS TotalPrescriptions
FROM
Prescriptions
GROUP BY
Medication;
```

**Output:**

<img width="1157" height="802" alt="image" src="https://github.com/user-attachments/assets/a714eb01-35f8-457d-a880-dc5170d70a79" />


**Question 3**
---
<img width="879" height="546" alt="image" src="https://github.com/user-attachments/assets/8f7324c2-c487-4c6a-a1b0-225f756b8cf4" />

```sql
SELECT
MAX(purch_amt) as MAXIMUM
FROM
orders;
```

**Output:**

<img width="760" height="322" alt="image" src="https://github.com/user-attachments/assets/19d44eaf-9afe-468c-a5df-3787c5c0da95" />


**Question 4**
---
<img width="1001" height="498" alt="image" src="https://github.com/user-attachments/assets/d6b2702a-295f-4f3f-a571-35b8caf19227" />


```sql
SELECT
SUM(purch_amt) AS TOTAL
FROM
orders;
```

**Output:**

<img width="744" height="323" alt="image" src="https://github.com/user-attachments/assets/04acdc03-5f32-4125-baf9-42f2c48df058" />


**Question 5**
---
<img width="1147" height="560" alt="image" src="https://github.com/user-attachments/assets/729ebe30-9e64-4660-8810-eadcb735d7c4" />


```sql
SELECT
COUNT(GRADE) AS "COUNT"
FROM
customer
WHERE
GRADE IS NOT NULL;
```

**Output:**

<img width="753" height="324" alt="image" src="https://github.com/user-attachments/assets/776d203d-760a-4e73-af6c-cfdc8eb504c0" />


**Question 6**
---
<img width="941" height="506" alt="image" src="https://github.com/user-attachments/assets/8f539450-d422-46d3-9465-ca641c6432bd" />


```sql
SELECT
COUNT(DISTINCT city) as unique_cities
FROM
customer;
```

**Output:**

<img width="895" height="318" alt="image" src="https://github.com/user-attachments/assets/2a244a3a-5a5e-4f00-a702-c84e6b6f1d65" />


**Question 7**
---
<img width="1121" height="628" alt="image" src="https://github.com/user-attachments/assets/1f7d55e5-f88d-40a0-8338-ed9652a214a4" />


```sql
SELECT
address,
AVG(salary)
FROM
customer1
GROUP BY
address
HAVING
AVG(salary)<15000;
```

**Output:**

<img width="1062" height="643" alt="image" src="https://github.com/user-attachments/assets/a7385fcd-1095-4f48-8e95-f2b42a8a9503" />


**Question 8**
---
<img width="1183" height="563" alt="image" src="https://github.com/user-attachments/assets/9a22e41f-1b0e-45ab-a979-e32e441b0c68" />


```sql
SELECT
jdate,
MIN(workhour)
FROM
employee1
GROUP BY
jdate
HAVING
MIN(workhour)<10;
```

**Output:**

<img width="1150" height="454" alt="image" src="https://github.com/user-attachments/assets/9c597f51-1d45-4eeb-812d-5a68d4b0c487" />


**Question 9**
---
<img width="1079" height="600" alt="image" src="https://github.com/user-attachments/assets/18a8bb13-7965-4292-ba47-ffa40b4cbb99" />


```sql
SELECT Frequency,COUNT(Frequency) as TotalPrescriptions
FROM Prescriptions
GROUP BY Frequency;
```

**Output:**

<img width="1035" height="564" alt="image" src="https://github.com/user-attachments/assets/95e75162-70c8-4fed-87ce-a95a9cb10aba" />


**Question 10**
---
<img width="1132" height="540" alt="image" src="https://github.com/user-attachments/assets/5688daf8-420e-49e4-9299-02923f36efeb" />


```sql
SELECT SUM(workhour) as "Total working hours"
FROM employee1;
```

**Output:**

<img width="990" height="318" alt="image" src="https://github.com/user-attachments/assets/b4b94356-4aea-43ac-b99c-7e0f73ae7ecd" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
