# oracal pratical for BCA 2nd year 

#### Question 1. Display all the employees’ details that belong to department 10.
```bash
SELECT *
FROM employees
WHERE department_id = 10 ;
```
#### Question 2.Display employees' names along with their Salary who are MANAGER:

```bash
SELECT employee_name, salary
FROM employees
WHERE job = 'MANAGER';

```
#### Question 3. Display the employees who are getting a Salary between 12000 and 25000:


```bash
SELECT *
FROM employees
WHERE salary BETWEEN 12000 AND 25000;

```
#### Question 4.Display the annual Salary of employees of dept. 30:

```bash
SELECT employee_name, salary * 12 AS annual_salary
FROM employees
WHERE department_id = 30;

```
#### Question 5.Display employees that are CLERK and managed by 7698:

```bash
SELECT *
FROM employees
WHERE job = 'CLERK' AND manager_id = 7698;

```
#### Question 6.Display employees of department 10 and 20:

```bash
# query 1
SELECT *
FROM employees
WHERE department_id IN (10, 20);
____________________________________________________________
# query 2 without IN Operator
SELECT *
FROM employees
WHERE department_id = 10 OR department_id = 20;

```
#### Question 7.Display employees that are not managers:

```bash
SELECT *
FROM employees
WHERE job <> 'MANAGER';

```
#### Question 8.Display employees that are analysts but getting a salary greater than 10000:

```bash
SELECT *
FROM employees
WHERE job = 'ANALYST' AND salary > 10000;

```
#### Question 9.Display employees who are not getting any commission:

```bash
SELECT *
FROM employees
WHERE commission IS NULL;

```
#### Question 10.

```bash
```
#### Question 11.

```bash
```
#### Question 12.

```bash
```
#### Question 13.

```bash
```




