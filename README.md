# SQL-second-highest-salary
A simple SQL project that demonstrates how to create an employee table, insert sample records, and retrieve the second highest salary using a subquery. Useful for beginners practicing SQL fundamentals such as table creation, data insertion, aggregate functions, and nested queries.

# Second Highest Salary in SQL

This project demonstrates how to create an SQL table, insert employee records, and retrieve the **second highest salary** using a subquery.

## 📂 Table: employees
The table contains:
- `id` – Primary key  
- `name` – Employee name  
- `salary` – Employee salary  

## 📝 SQL Code Used

```sql
-- Create employee table
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    salary INT
);

-- Insert sample data
INSERT INTO employees (id, name, salary) VALUES
(1, 'Arun', 25000),
(2, 'Bhavani', 30000),
(3, 'Charan', 40000),
(4, 'Divya', 35000);

-- Query to find the second highest salary
SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
