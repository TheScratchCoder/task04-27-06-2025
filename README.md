# task04-27-06-2025

## Table : Employees

```
CREATE TABLE Employees (
    EmployeeID INT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Department VARCHAR(50),
    Salary DECIMAL(10, 2),
    JoiningDate DATE
);
```

### Common aggregate functions:

<code> COUNT() – counts rows

SUM() – totals numeric values

AVG() – average

MIN() / MAX() – lowest / highest </code>

Examples ->

```
-- Count all employees

SELECT COUNT(*) AS TotalEmployees FROM Employees;


-- Total salary paid

SELECT SUM(Salary) AS TotalSalary FROM Employees;


-- Average salary

SELECT AVG(Salary) AS AverageSalary FROM Employees;


-- Minimum and maximum salary

SELECT MIN(Salary) AS MinSalary, MAX(Salary) AS MaxSalary FROM Employees;
```

### Use GROUP BY to Categorize Data
Use GROUP BY to get summaries per category, e.g., department-wise:

```
-- Count of employees in each department

SELECT Department, COUNT(*) AS NumEmployees
FROM Employees
GROUP BY Department;


-- Average salary in each department

SELECT Department, AVG(Salary) AS AvgSalary
FROM Employees
GROUP BY Department;
```

### Filter Groups Using HAVING
Use HAVING to filter groups (after GROUP BY) — unlike WHERE, which filters rows before grouping.

```
-- Departments with more than 2 employees

SELECT Department, COUNT(*) AS NumEmployees
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 2;


-- Departments with average salary above 70,000

SELECT Department, AVG(Salary) AS AvgSalary
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 70000;
```

