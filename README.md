# oracal pratical for BCA 2nd year 

#### Question 1. create database ems.
```sql
> CREATE DATABASE EMS;
```
#### Question 2. use database 

```sql
> use ems;
```
#### Question 3. Create table emp and instert records 


```sql
> CREATE TABLE emp (
    dep_id INT,
    dep_name VARCHAR(50),
    Location VARCHAR(50),
    emp_id INT ,
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
(40, 'HR', 'Delhi', 104, 'Ananya Gupta', 'Analyst', 103, 55000.00, NULL, '2023-04-05'),
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
#### Question 4.Display all the employees’ details that belong to department 10.

```sql
> SELECT * FROM emp WHERE dep_id = 10;
 
+--------------+----------------+----------+------------+-----------+-------------------+-----------+----------+------------+------------+
| dep_id       | dep_name       | Location | emp_id     | Name      | Job               | ManagerID | Salary   | Commission | HireDate   |
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
> SELECT name,Salary FROM emp WHERE Salary BETWEEN 12000 AND 25000;

+-----------+----------+
| name      | Salary   |
+-----------+----------+
| ram Kumar | 13000.00 |
+-----------+----------+
1 row in set (0.000 sec)


```
#### Question 7. Display the annual Salary of employees of dept. 30.
```sql
> SELECT Name, Salary * 12 AS annual_salary FROM emp WHERE dep_id = 30;
+-------------+---------------+
| Name        | annual_salary |
+-------------+---------------+
| Rahul Singh |     960000.00 |
+-------------+---------------+

```

#### Question 8. Display employees that are CLERK and managed by 7698.
```sql
> SELECT Name , ManagerID , Job FROM emp WHERE job = 'CLERK' AND ManagerID = 7698;
+--------------+-----------+-------+
| Name         | ManagerID | Job   |
+--------------+-----------+-------+
| Vikram Joshi |      7698 | Clerk |
+--------------+-----------+-------+
1 row in set (0.001 sec)

```

#### Question 9. Display employees of department 10 and 20.
```sql
> SELECT Name , dep_id FROM emp WHERE dep_id = 10 OR dep_id = 20;
+--------------+--------+
| Name         | dep_id |
+--------------+--------+
| ram Kumar    |     10 |
| Priya Sharma |     20 |
+--------------+--------+
2 rows in set (0.001 sec)

```

#### Question 10. Display employees that are not managers.
```sql
> SELECT  emp_id, Name ,Job  FROM emp WHERE Job <> 'MANAGER';
+--------+--------------+-------------------+
| emp_id | Name         | Job               |
+--------+--------------+-------------------+
|    101 | ram Kumar    | Software Engineer |
|    102 | Priya Sharma | Software Engineer |
|    103 | Rahul Singh  | HR Manager        |
|    104 | Ananya Gupta | Analyst           |
|    107 | Vikram Joshi | Clerk             |
+--------+--------------+-------------------+

```

#### Question 11. Display employees whose name begins with Character ‘R’.
```sql
> SELECT Name FROM emp  WHERE Name LIKE 'R%';
+--------------+
| Name         |
+--------------+
| ram Kumar    |
| Rahul Singh  |
| Rajesh Patel |
+--------------+

```

#### Question 12. Display employees that are analyst but getting salary greater than 10000.
```sql
> SELECT Name,Salary FROM emp WHERE Job = 'analyst' AND Salary > 10000.00;
+--------------+----------+
| Name         | Salary   |
+--------------+----------+
| Ananya Gupta | 55000.00 |
+--------------+----------+


```

#### Question 13. Display employees those are not getting any commission.
```sql
> SELECT Name , Commission FROM emp WHERE Commission IS NULL;
+--------------+------------+
| Name         | Commission |
+--------------+------------+
| ram Kumar    |       NULL |
| Priya Sharma |       NULL |
| Ananya Gupta |       NULL |
| Vikram Joshi |       NULL |
+--------------+------------+


```

#### Question 14. Display all the employees name along with their jobs.
```sql
> SELECT Name, Job
  FROM emp;
+--------------+-------------------+
| Name         | Job               |
+--------------+-------------------+
| ram Kumar    | Software Engineer |
| Priya Sharma | Software Engineer |
| Rahul Singh  | HR Manager        |
| Ananya Gupta | analyst           |
| Rajesh Patel | Manager           |
| Neha Kapoor  | Manager           |
| Vikram Joshi | Clerk             |
+--------------+-------------------+

```

#### Question 15. Display all the employees having ‘A’ in their names.
```sql
> SELECT Name FROM emp WHERE Name LIKE '%A%';
+--------------+
| Name         |
+--------------+
| ram Kumar    |
| Priya Sharma |
| Rahul Singh  |
| Ananya Gupta |
| Rajesh Patel |
| Neha Kapoor  |
| Vikram Joshi |
+--------------+

```

#### Question 16. Display all the employees having T and ‘R’ in their names.
```sql
> SELECT Name
FROM emp
WHERE Name LIKE '%T%' AND Name LIKE '%R%';
--------------+
| Name         |
+--------------+
| Rajesh Patel |
+--------------+

```
#### Question 17. Display Department located in ‘pune’.
```sql
> SELECT dep_name , Location 
FROM emp
WHERE Location = 'Pune';
+----------+----------+
| dep_name | Location |
+----------+----------+
| Admin    | Pune     |
+----------+----------+
```

#### Question 18. Display all the employees who are not ‘SALESMAN’ or ‘CLERK’.
```sql
> SELECT Name , Job 
FROM emp
WHERE Job NOT IN ('SALESMAN', 'CLERK');
+--------------+-------------------+
| Name         | Job               |
+--------------+-------------------+
| ram Kumar    | Software Engineer |
| Priya Sharma | Software Engineer |
| Rahul Singh  | HR Manager        |
| Ananya Gupta | analyst           |
| Rajesh Patel | Manager           |
| Neha Kapoor  | Manager           |
+--------------+-------------------+

```

#### Question 19. Display all the employees Names in lowercase.
```sql
> SELECT LOWER(Name) AS LowercaseName
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
> SELECT Name, LENGTH(Name) AS NameLength
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


#### Question >  Write a query to calculate the length of time any employee has been with the company.
```sql
    SELECT
    emp_id,
    Name,
    DATEDIFF(CURDATE(), HireDate) AS DaysWithCompany
    FROM
    emp;
+--------+--------------+-----------------+
| emp_id | Name         | DaysWithCompany |
+--------+--------------+-----------------+
|    101 | ram Kumar    |             343 |
|    102 | Priya Sharma |            8342 |
|    103 | Rahul Singh  |             289 |
|    104 | Ananya Gupta |             263 |
|    105 | Rajesh Patel |             226 |
|    106 | Neha Kapoor  |             182 |
|    107 | Vikram Joshi |             167 |
+--------+--------------+-----------------+

```
#### Question > List the employee name and salary increased by 15% and expressed as a whole number.  
```sql
> SELECT
Name,
ROUND(Salary * 1.15) AS IncreasedSalary
FROM
emp;
+--------------+-----------------+
| Name         | IncreasedSalary |
+--------------+-----------------+
| ram Kumar    |           14950 |
| Priya Sharma |           80500 |
| Rahul Singh  |           92000 |
| Ananya Gupta |           63250 |
| Rajesh Patel |           92000 |
| Neha Kapoor  |           69000 |
| Vikram Joshi |           57500 |
+--------------+-----------------+
```
#### Question > List all the employees who joined after ’01-jan-2000’ and before 18-aug-2005.
```sql
SELECT Name,HireDate,Dep_id,Salary FROM emp WHERE HireDate > '2000-01-01' AND HireDate < '2005-08-18';
+--------------+------------+--------+----------+
| Name         | HireDate   | Dep_id | Salary   |
+--------------+------------+--------+----------+
| Priya Sharma | 2001-02-20 |     20 | 70000.00 |
+--------------+------------+--------+----------+

```

#### Question > Display the difference between Highest and the lowest salary for each department.
```sql
```
#### Question > Display Minimum and Maximum salary for each job type.

```sql
SELECT
    ->     Job,
    ->     MIN(min_sal),
    ->     MAX(max_sal)
    -> FROM
    ->     emp
    -> GROUP BY
    ->     Job;
+-------------------+--------------+--------------+
| Job               | MIN(min_sal) | MAX(max_sal) |
+-------------------+--------------+--------------+
| Analyst           |     60000.00 |     75000.00 |
| Clerk             |     85000.00 |     95000.00 |
| HR Manager        |     75000.00 |     85000.00 |
| Manager           |     60000.00 |     85000.00 |
| Software Engineer |     12000.00 |     80000.00 |
+-------------------+--------------+--------------+
```
#### que > Display employees who earn more than lowest salary of department 30.
```sql

 SELECT
    ->     *
    -> FROM
    ->     emp
    -> WHERE
    ->     Salary > (SELECT MIN(min_sal) FROM emp WHERE dep_id = 30);
+--------+----------+-----------+--------+--------------+------------+-----------+----------+------------+------------+----------+----------+
| dep_id | dep_name | Location  | emp_id | Name         | Job        | ManagerID | Salary   | Commission | HireDate   | max_sal  | min_sal  |
+--------+----------+-----------+--------+--------------+------------+-----------+----------+------------+------------+----------+----------+
|     30 | HR       | Delhi     |    103 | Rahul Singh  | HR Manager |      NULL | 80000.00 |    5000.00 | 2023-03-10 | 85000.00 | 75000.00 |
|     50 | Finance  | Bangalore |    105 | Rajesh Patel | Manager    |       301 | 80000.00 |    3000.00 | 2023-05-12 | 85000.00 | 80000.00 |
+--------+----------+-----------+--------+--------------+------------+-----------+----------+------------+------------+----------+----------+
2 rows in set (0.000 sec)

```

# ROW WORK > WORK IN PROGRESS
```sql
-- ADD MAX AND MIN SALARY COLUMN CODE 
-- Add columns to the existing table
ALTER TABLE emp
ADD COLUMN max_sal DECIMAL(10, 2),
ADD COLUMN min_sal DECIMAL(10, 2);

-- Insert records into max_sal and min_sal columns (FOR EMS DATA BASE NOT )
UPDATE emp SET max_sal = 50000.00, min_sal = 12000.00 WHERE emp_id = 101;
UPDATE emp SET max_sal = 80000.00, min_sal = 60000.00 WHERE emp_id = 102;
UPDATE emp SET max_sal = 85000.00, min_sal = 75000.00 WHERE emp_id = 103;
UPDATE emp SET max_sal = 75000.00, min_sal = 60000.00 WHERE emp_id = 104;
UPDATE emp SET max_sal = 85000.00, min_sal = 80000.00 WHERE emp_id = 105;
UPDATE emp SET max_sal = 70000.00, min_sal = 60000.00 WHERE emp_id = 106;
UPDATE emp SET max_sal = 95000.00, min_sal = 45000.00 WHERE emp_id = 107;


```

