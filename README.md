# oracal pratical for BCA 2nd year 

#### Question 1. create database ems.
```sql
CREATE DATABASE EMS;
```
#### Question 2. use database 

```sql
USE DATABASE ems;
```
#### Question 3. Create table emp and instert records 


```sql
CREATE TABLE emp (
    dep_id INT,
    dep_name VARCHAR(50),
    Location VARCHAR(50),
    emp_id INT PRIMARY KEY,
    Name VARCHAR(255),
    Job VARCHAR(50),
    ManagerID INT,
    Salary DECIMAL(10, 2),
    Commission DECIMAL(10, 2),
    HireDate DATE
);

INSERT INTO emp VALUES
(10, 'IT', 'Mumbai', 101, 'ram Kumar', 'Software Engineer', 201, 13000.00, NULL, '2023-01-15'),
(20, 'IT', 'Mumbai', 102, 'Priya Sharma', 'Software Engineer', 201, 70000.00, NULL, '2001-02-20'),
(30, 'HR', 'Delhi', 103, 'Rahul Singh', 'HR Manager', NULL, 80000.00, 5000.00, '2023-03-10'),
(40, 'HR', 'Delhi', 104, 'Ananya Gupta', 'ANAYLST', 103, 55000.00, NULL, '2023-04-05'),
(50, 'Finance', 'Bangalore', 105, 'Rajesh Patel', 'Manager', 301, 80000.00, 3000.00, '2023-05-12'),
(60, 'Marketing', 'Chennai', 106, 'Neha Kapoor', 'Manager', 302, 60000.00, 2000.00, '2023-06-25'),
(70, 'Admin', 'Pune', 107, 'Vikram Joshi', 'Clerk', 7698, 50000.00, NULL, '2023-07-10');


 > select * from emp;
+--------------+----------------+-----------+------------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location  | emp_id     | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+-----------+------------+--------------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai    |        101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|           20 | IT             | Mumbai    |        102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
|           30 | HR             | Delhi     |        103 | Rahul Singh  | HR Manager        |      NULL | 80000.00 |    5000.00 | 2023-03-10 |
|           40 | HR             | Delhi     |        104 | Ananya Gupta | ANAYLST           |       103 | 55000.00 |       NULL | 2023-04-05 |
|           50 | Finance        | Bangalore |        105 | Rajesh Patel | Manager           |       301 | 80000.00 |    3000.00 | 2023-05-12 |
|           60 | Marketing      | Chennai   |        106 | Neha Kapoor  | Manager           |       302 | 60000.00 |    2000.00 | 2023-06-25 |
|           70 | Admin          | Pune      |        107 | Vikram Joshi | Clerk             |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------------+----------------+-----------+------------+--------------+-------------------+-----------+----------+------------+------------+
```
#### 4.Display all the employees’ details that belong to department 10.

```sql
SELECT * FROM emp WHERE dep_id = 10;
 
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
| dep_id       | DepartmentName | Location | emp_id     | Name      | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai   |        101 | ram Kumar | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
1 row in set (0.001 sec)
```

#### Question 5.Display employees name along with their Salary who are MANAGER.

```sql
> SELECT Name, Salary FROM emp WHERE job = 'MANAGER';
+--------------+----------+
| Name         | Salary   |
+--------------+----------+
| Rajesh Patel | 80000.00 |
| Neha Kapoor  | 60000.00 |
+--------------+----------+
2 rows in set (0.001 sec)AND manager_id = 7698;

```

#### Question 6. Display the employees who are getting Salary between 10000 and 25000.
```sql 
> SELECT * FROM emp WHERE Salary BETWEEN 12000 AND 25000;
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | emp_id     | Name      | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai   |        101 | ram Kumar | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
1 row in set (0.001 sec)
```
#### Question 7. Display the annual Salary of employees of dept. 30.
```sql
SELECT Name, Salary * 12 AS annual_salary FROM emp WHERE dep_id = 30;
+-------------+---------------+
| Name        | annual_salary |
+-------------+---------------+
| Rahul Singh |     960000.00 |
+-------------+---------------+

```

#### Question 8. Display employees that are CLERK and managed by 7698.
```sql
SELECT * FROM emp WHERE job = 'CLERK' AND ManagerID = 7698;
+--------------+----------------+----------+------------+--------------+-------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | emp_id     | Name         | Job   | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+--------------+-------+-----------+----------+------------+------------+
|           70 | Admin          | Pune     |        107 | Vikram Joshi | Clerk |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------------+----------------+----------+------------+--------------+-------+-----------+----------+------------+------------+
```

#### Question 9. Display employees of department 10 and 20.
```sql

```

#### Question 10. Display employees that are not managers.
```sql

```

#### Question 11. Display employees whose name begins with Character ‘R’.
```sql
SELECT * FROM emp WHERE dep_id = 10 OR dep_id = 20;
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | emp_id     | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai   |        101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|           20 | IT             | Mumbai   |        102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+


```

#### Question 12. Display employees that are analyst but getting salary greater than 10000.
```sql
SELECT * FROM emp WHERE Job <> 'MANAGER';
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | emp_id     | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai   |        101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|           20 | IT             | Mumbai   |        102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
|           30 | HR             | Delhi    |        103 | Rahul Singh  | HR Manager        |      NULL | 80000.00 |    5000.00 | 2023-03-10 |
|           40 | HR             | Delhi    |        104 | Ananya Gupta | ANAYLST           |       103 | 55000.00 |       NULL | 2023-04-05 |
|           70 | Admin          | Pune     |        107 | Vikram Joshi | Clerk             |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
```

#### Question 13. Display employees those are not getting any commission.
```sql
SELECT * FROM emp WHERE Commission IS NULL;
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | EmployeeID | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai   |        101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|           20 | IT             | Mumbai   |        102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
|           40 | HR             | Delhi    |        104 | Ananya Gupta | ANAYLST           |       103 | 55000.00 |       NULL | 2023-04-05 |
|           70 | Admin          | Pune     |        107 | Vikram Joshi | Clerk             |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------------+----------------+----------+------------+--------------+-------------------+-----------+----------+------------+------------+
```

#### Question 14. Display all the employees name along with their jobs.
```sql
SELECT Name, Job
 FROM emp;
+--------------+-------------------+
| Name         | Job               |
+--------------+-------------------+
| ram Kumar    | Software Engineer |
| Priya Sharma | Software Engineer |
| Rahul Singh  | HR Manager        |
| Ananya Gupta | ANAYLST           |
| Rajesh Patel | Manager           |
| Neha Kapoor  | Manager           |
| Vikram Joshi | Clerk             |
+--------------+-------------------+
```

#### Question 15. Display all the employees having ‘A’ in their names.
```sql
SELECT *
FROM emp
WHERE Name LIKE '%A%';
+--------+-------------+----------+--------+--------------+-------------------+-----------+----------+------------+------------+
| emp_id | dep_name    | Location | emp_id | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------+-------------+----------+--------+--------------+-------------------+-----------+----------+------------+------------+
|     10 | IT          | Mumbai   |    101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|     20 | IT          | Mumbai   |    102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
|     30 | HR          | Delhi    |    103 | Rahul Singh  | HR Manager        |      NULL | 80000.00 |    5000.00 | 2023-03-10 |
|     40 | HR          | Delhi    |    104 | Ananya Gupta | ANAYLST           |       103 | 55000.00 |       NULL | 2023-04-05 |
|     50 | Finance     | Bangalore|    105 | Rajesh Patel | Manager           |       301 | 80000.00 |    3000.00 | 2023-05-12 |
|     60 | Marketing   | Chennai  |    106 | Neha Kapoor  | Manager           |       302 | 60000.00 |    2000.00 | 2023-06-25 |
|     70 | Admin       | Pune     |    107 | Vikram Joshi | Clerk             |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------+-------------+----------+--------+--------------+-------------------+-----------+----------+------------+------------+
```

#### Question 16. Display all the employees having T and ‘R’ in their names.
```sql
SELECT *
FROM emp
WHERE Name LIKE '%T%' AND Name LIKE '%R%';
+--------+------------+----------+--------+--------------+---------+-----------+----------+------------+------------+
| emp_id | dep_name   | Location | emp_id | Name         | Job     | ManagerID | Salary   | Commission | HireDate   |
+--------+------------+----------+--------+--------------+---------+-----------+----------+------------+------------+
|     50 | Finance    | Bangalore|    105 | Rajesh Patel | Manager |       301 | 80000.00 |    3000.00 | 2023-05-12 |
+--------+------------+----------+--------+--------------+---------+-----------+----------+------------+------------+
```

#### Question 17. Display Department located in ‘pune’.
```sql
SELECT *
FROM emp
WHERE Location = 'Pune';
+--------+---------+-------+--------+--------------+-------+-----------+----------+------------+------------+
| emp_id | dep_name| Location | emp_id | Name         | Job   | ManagerID | Salary   | Commission | HireDate|
+--------+---------+-------+--------+--------------+-------+-----------+----------+------------+------------+
|     70 | Admin   | Pune  |    107 | Vikram Joshi | Clerk |      7698 | 50000.00 |       NULL | 2023-07-10 |
+--------+---------+-------+--------+--------------+-------+-----------+----------+------------+------------+
```

#### Question 18. Display all the employees who are not ‘SALESMAN’ or ‘CLERK’.
```sql
SELECT *
FROM emp
WHERE Job NOT IN ('SALESMAN', 'CLERK');
+--------+-----------+-----------+--------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id | dep_name  | Location  | emp_id | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------+-----------+-----------+--------+--------------+-------------------+-----------+----------+------------+------------+
|     10 | IT        | Mumbai    |    101 | ram Kumar    | Software Engineer |       201 | 13000.00 |       NULL | 2023-01-15 |
|     20 | IT        | Mumbai    |    102 | Priya Sharma | Software Engineer |       201 | 70000.00 |       NULL | 2001-02-20 |
|     30 | HR        | Delhi     |    103 | Rahul Singh  | HR Manager        |      NULL | 80000.00 |    5000.00 | 2023-03-10 |
|     40 | HR        | Delhi     |    104 | Ananya Gupta | ANAYLST           |       103 | 55000.00 |       NULL | 2023-04-05 |
|     50 | Finance   | Bangalore |    105 | Rajesh Patel | Manager           |       301 | 80000.00 |    3000.00 | 2023-05-12 |
|     60 | Marketing | Chennai   |    106 | Neha Kapoor  | Manager           |       302 | 60000.00 |    2000.00 | 2023-06-25 |
+--------+-----------+-----------+--------+--------------+-------------------+-----------+----------+------------+------------+
```

#### Question 19. Display all the employees Names in lowercase.
```sql
SELECT LOWER(Name) AS LowercaseName
FROM emp;
+---------------+
| LowercaseName |
+---------------+
| ram kumar     |
| priya sharma  |
| rahul singh   |
| ananya gupta  |
| rajesh patel  |
| neha kapoor   |
| vikram joshi  |
+---------------+

```

#### Question 20. Display all employees name with their length.
```sql
SELECT Name, LENGTH(Name) AS NameLength
FROM emp;
+--------------+------------+
| Name         | NameLength |
+--------------+------------+
| ram Kumar    |          9 |
| Priya Sharma |         12 |
| Rahul Singh  |         11 |
| Ananya Gupta |         12 |
| Rajesh Patel |         12 |
| Neha Kapoor  |         11 |
| Vikram Joshi |         12 |
+--------------+------------+
```




