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
--
<img width="1204" height="389" alt="image" src="https://github.com/user-attachments/assets/36553fc0-9bd0-4b54-b9a4-98c504ae29a0" />


```sql
Create Table Attendance(
AttendanceID INTEGER Primary Key,
EmployeeID INTEGER,
AttendanceDate Date,
Status TEXT CHECK(Status IN('Present', 'Absent', 'Leave')),
Foreign Key(EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1163" height="310" alt="image" src="https://github.com/user-attachments/assets/21bc3fa7-04bc-4db5-8834-8999a638bab0" />


**Question 2**
---
<img width="1159" height="437" alt="image" src="https://github.com/user-attachments/assets/4acbdc3d-72b9-41d1-9d5c-c9f7873d1cbb" />


```sql
Create Table Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT
);
```

**Output:**

<img width="1193" height="419" alt="image" src="https://github.com/user-attachments/assets/94b9ad1e-18f2-4a1d-bdfd-0e81696807d0" />


**Question 3**
---
<img width="1192" height="461" alt="image" src="https://github.com/user-attachments/assets/88e04df5-82b6-4e0a-8fe9-a4b7ad1d99a9" />


```sql
create table Employees(
EmployeeID Integer Primary Key,
FirstName TEXT Not Null,
LastName TEXT Not NUll,
Email TEXT UNIQUE,
Salary Integer Check(Salary>0),
DepartmentID Integer,
Foreign Key(DepartmentID) REFERENCES Departments(DepartmentID)
)
```

**Output:**

<img width="1200" height="473" alt="image" src="https://github.com/user-attachments/assets/fc0e685c-14ca-44d7-b1b2-9c1de145c6bb" />


**Question 4**
---
<img width="1201" height="551" alt="image" src="https://github.com/user-attachments/assets/005b0284-da50-4f4c-bcfa-f9208d8afb26" />


```sql
Insert into Employee(EmployeeID,Name,Position,Department,Salary) Values(5,'George Clark','Consultant',Null,Null);
Insert into Employee(EmployeeID,Name,Position,Department,Salary) Values(7,'Noah Davis','Manager','HR',60000);
Insert into Employee(EmployeeID,Name,Position,Department,Salary) Values(8,'Ava Miller','Consultant','IT',Null);
```

**Output:**

<img width="1198" height="334" alt="image" src="https://github.com/user-attachments/assets/a1985d83-cdaa-4ad2-a1f4-4e5013195947" />


**Question 5**
---
<img width="1180" height="414" alt="image" src="https://github.com/user-attachments/assets/0bf2e59a-330a-4aba-be13-1f33f973a0f4" />


```sql
Insert into Employee(EmployeeID,Name,Position) Values(4,'Emily White','Analyst');
```

**Output:**

<img width="1180" height="337" alt="image" src="https://github.com/user-attachments/assets/ca810565-b06e-4a7b-8888-37f300fc3a39" />


**Question 6**
---
<img width="927" height="392" alt="image" src="https://github.com/user-attachments/assets/0fc79578-1eec-4509-9a6c-e84b7ef6750b" />


```sql
Insert into Employee(EmployeeID,Name,Department, Salary)
Select EmployeeID,Name,Department,Salary 
From Former_employees;
```

**Output:**

<img width="1234" height="344" alt="image" src="https://github.com/user-attachments/assets/3a9dea98-a3d0-423d-93e0-a810106508bc" />


**Question 7**
---
<img width="1209" height="353" alt="image" src="https://github.com/user-attachments/assets/5f1a247c-f107-4e8a-98db-de4ff1210745" />


```sql
Create Table Shipments(
ShipmentID Integer Primary Key,
ShipmentDate Date,
SupplierID Integer,
OrderID Integer,
Foreign Key(SupplierID) References Suppliers(SupplierID),
Foreign Key(OrderID) References Orders(OrderID)
)
```

**Output:**

<img width="1206" height="280" alt="image" src="https://github.com/user-attachments/assets/ce4c7a66-7625-4a6f-b9fc-89b2494d4e30" />


**Question 8**
---
<img width="1182" height="402" alt="image" src="https://github.com/user-attachments/assets/036b4aa7-6271-4db3-8eaf-bcee5a545946" />


```sql
Create Table Department(
DepartmentID Integer Primary Key,
DepartmentName Text Not NUll Unique,
Location Text
)
```

**Output:**

<img width="1180" height="309" alt="image" src="https://github.com/user-attachments/assets/5c78626e-1950-4af5-a592-4b91f58eda4a" />


**Question 9**
---
<img width="1221" height="342" alt="image" src="https://github.com/user-attachments/assets/e1821642-a9b3-4869-90a5-cb053a9d289a" />


```sql
CREATE TABLE jobs(
    job_id int PRIMARY KEY,
    job_title varchar(100) DEFAULT NULL,
    min_salary int DEFAULT 8000 ,
    max_salary int DEFAULT NULL
);
```

**Output:**

<img width="1155" height="356" alt="image" src="https://github.com/user-attachments/assets/23fd351f-e519-4193-ab1e-5badc30eddeb" />


**Question 10**
---
<img width="1133" height="420" alt="image" src="https://github.com/user-attachments/assets/a3611664-340a-408d-9c47-0c012a8a7931" />


```sql
CREATE TABLE Members(
    MemberID INTEGER,
    MemberName TEXT,
    JoinDate DATE
);
```

**Output:**

<img width="1160" height="402" alt="image" src="https://github.com/user-attachments/assets/5e4032a8-c427-4556-9fd9-e77de40a427a" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
