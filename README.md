# oracal pratical for BCA 2nd year 

#### Question 1. create database ems.
```sql
CREATE DATABASE EMS;
```
#### Question 2. use database 

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

```
#### Question 3. Create table emp


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
(10, 'IT', 'Mumbai', 101, 'ram Kumar', 'Software Engineer', 201, 60000.00, NULL, '2023-01-15'),
(20, 'IT', 'Mumbai', 102, 'Priya Sharma', 'Software Engineer', 201, 70000.00, NULL, '2001-02-20'),
(30, 'HR', 'Delhi', 103, 'Rahul Singh', 'HR Manager', NULL, 80000.00, 5000.00, '2023-03-10'),
(40, 'HR', 'Delhi', 104, 'Ananya Gupta', 'ANAYLST', 103, 55000.00, NULL, '2023-04-05'),
(50, 'Finance', 'Bangalore', 105, 'Rajesh Patel', 'Manager', 301, 80000.00, 3000.00, '2023-05-12'),
(60, 'Marketing', 'Chennai', 106, 'Neha Kapoor', 'Manager', 302, 60000.00, 2000.00, '2023-06-25'),
(70, 'Admin', 'Pune', 107, 'Vikram Joshi', 'Clerk', 7698, 50000.00, NULL, '2023-07-10');


--> select * from emp;
+--------------+----------------+-----------+------------+--------------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location  | emp_id     | Name         | Job               | ManagerID | Salary   | Commission | HireDate   |
+--------------+----------------+-----------+------------+--------------+-------------------+-----------+----------+------------+------------+
|           10 | IT             | Mumbai    |        101 | ram Kumar    | Software Engineer |       201 | 60000.00 |       NULL | 2023-01-15 |
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
|           10 | IT             | Mumbai   |        101 | ram Kumar | Software Engineer |       201 | 60000.00 |       NULL | 2023-01-15 |
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
1 row in set (0.001 sec)
```

#### Question 5.Display employees name along with their Salary who are MANAGER.

```sql
--> SELECT Name, Salary FROM emp WHERE job = 'MANAGER';
+--------------+----------+
| Name         | Salary   |
+--------------+----------+
| Rajesh Patel | 80000.00 |
| Neha Kapoor  | 60000.00 |
+--------------+----------+
2 rows in set (0.001 sec)AND manager_id = 7698;

```

#### Question 6.Display the employees who are getting Salary between 10000 and 25000.
#### Question 7.Display the annual Salary of employees of dept. 30.
#### Question 8.Display employees that are CLERK and managed by 7698.
#### Question 9.Display employees of department 10 and 20.
#### 10. Display employees that are not managers.
#### 11. Display employees whose name begins with Character ‘R’.
#### 12. Display employees that are analyst but getting salary greater than 10000.
#### 13. Display employees those are not getting any commission.
#### 14. Display all the employees name along with their jobs.
#### 15. Display all the employees having ‘A’ in their names.
#### 16. Display all the employees having T and ‘R’ in their names.
#### 17. Display employees that are not there in department 30.
#### 18. Display Department located in ‘xxx’.
#### 19. Display all the employees who are not ‘SALESMAN’ or ‘CLERK’.
#### 20. Display all the employees Names in lowercase.
#### 21. Display all employees name with their length.
#### 22. Display all the employees who are not MANAGERS.



