## **50 SQL Multiple Choice Questions (MCQ)**

### **Basic SELECT & WHERE**

1. Which query returns all employees with salary greater than 50000?

   ```sql
   ? 
   ```

   - a) `SELECT * FROM employees WHERE salary >= 50000;`
   - b) `SELECT * FROM employees WHERE salary > 50000;`
   - c) `SELECT * FROM employees HAVING salary > 50000;`
   - d) `SELECT * FROM employees ORDER BY salary > 50000;`



2. Which query gives unique department IDs from employees table?
   - a) `SELECT DISTINCT dept_id FROM employees;`
   - b) `SELECT dept_id FROM employees GROUP BY dept_id;`
   - c) Both a and b
   - d) `SELECT UNIQUE dept_id FROM employees;`



3. Which query returns employees whose name starts with 'A'?
   - a) `SELECT * FROM employees WHERE name = 'A%';`
   - b) `SELECT * FROM employees WHERE name LIKE 'A%';`
   - c) `SELECT * FROM employees WHERE name LIKE '%A';`
   - d) `SELECT * FROM employees WHERE name LIKE '%A%';`



4. To get the top 3 highest salaries:
   - a) `SELECT salary FROM employees ORDER BY salary LIMIT 3;`
   - b) `SELECT salary FROM employees ORDER BY salary DESC LIMIT 3;`
   - c) `SELECT TOP 3 salary FROM employees ORDER BY salary;`
   - d) Both b and c (depending on D- b)



5. Which query finds employees with NULL commission?
   - a) `SELECT * FROM employees WHERE commission = NULL;`
   - b) `SELECT * FROM employees WHERE commission != NULL;`
   - c) `SELECT * FROM employees WHERE commission IS NULL;`
   - d) `SELECT * FROM employees WHERE commission == NULL;`



### **Aggregations & GROUP BY**

6. Find the average salary of each department:
   - a) `SELECT dept_id, AVG(salary) FROM employees;`
   - b) `SELECT dept_id, AVG(salary) FROM employees GROUP BY dept_id;`
   - c) `SELECT dept_id, salary FROM employees GROUP BY dept_id;`
   - d) `SELECT dept_id, SUM(salary)/COUNT(*) FROM employees;`



7. Which clause is used to filter after aggregation?
   - a) WHERE
   - b) HAVING
   - c) GROUP BY
   - d) DISTINCT



8. Find departments having more than 10 employees:
   - a) `SELECT dept_id FROM employees WHERE COUNT(*) > 10;`
   - b) `SELECT dept_id FROM employees GROUP BY dept_id HAVING COUNT(*) > 10;`
   - c) `SELECT dept_id FROM employees GROUP BY dept_id WHERE COUNT(*) > 10;`
   - d) `SELECT dept_id FROM employees HAVING COUNT(*) > 10;`



9. Which query gives total salary paid to employees?
   - a) `SELECT COUNT(salary) FROM employees;`
   - b) `SELECT SUM(salary) FROM employees;`
   - c) `SELECT TOTAL(salary) FROM employees;`
   - d) `SELECT MAX(salary) FROM employees;`



10. To find the number of different job titles:
    - a) `SELECT COUNT(job_title) FROM employees;`
    - b) `SELECT COUNT(DISTINCT job_title) FROM employees;`
    - c) `SELECT DISTINCT COUNT(job_title) FROM employees;`
    - d) `SELECT job_title COUNT FROM employees;`



### **JOINs**

11. Which query lists employees and their department names?

```sql
employees(emp_id, name, dept_i- d)  
departments(dept_id, dept_name)
```

- a) `SELECT e.name, d.dept_name FROM employees e JOIN departments d;`
- b) `SELECT e.name, d.dept_name FROM employees e JOIN departments d ON e.dept_id = d.dept_id;`
- c) `SELECT e.name, d.dept_name FROM employees e, departments d;`
- d) `SELECT e.name, dept_name FROM employees;`



12. Which join shows employees even if no department assigned?
    - a) INNER JOIN
    - b) LEFT JOIN
    - c) RIGHT JOIN
    - d) FULL JOIN



13. Which join includes unmatched rows from both tables?
    - a) INNER JOIN
    - b) LEFT JOIN
    - c) RIGHT JOIN
    - d) FULL OUTER JOIN



14. To get employees without a department:
    - a) `SELECT * FROM employees WHERE dept_id IS NULL;`
    - b) `SELECT e.* FROM employees e LEFT JOIN departments d ON e.dept_id = d.dept_id WHERE d.dept_id IS NULL;`
    - c) Both a and b
    - d) None



15. Which query finds common dept\_ids from employees and departments?
    - a) `SELECT dept_id FROM employees INTERSECT SELECT dept_id FROM departments;`
    - b) `SELECT dept_id FROM employees JOIN departments;`
    - c) `SELECT dept_id FROM employees UNION SELECT dept_id FROM departments;`
    - d) `SELECT dept_id FROM employees MINUS SELECT dept_id FROM departments;`



### **Subqueries**

16. Find employees with salary greater than average salary:
    - a) `SELECT * FROM employees WHERE salary > AVG(salary);`
    - b) `SELECT * FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);`
    - c) `SELECT * FROM employees HAVING salary > (SELECT AVG(salary) FROM employees);`
    - d) `SELECT * FROM employees WHERE salary IN (SELECT AVG(salary) FROM employees);`



17. Which subquery finds max salary per department?
    - a) Correlated subquery
    - b) Non-correlated subquery
    - c) Both
    - d) None



18. To get the second highest salary:
    - a) `SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees);`
    - b) `SELECT TOP 2 salary FROM employees ORDER BY salary DESC;`
    - c) `SELECT salary FROM employees ORDER BY salary DESC LIMIT 1 OFFSET 1;`
    - d) All of the above (depending on D- b)



19. Which operator is used for multiple values from subquery?
    - a) =
    - b) IN
    - c) EXISTS
    - d) BOTH b and c



20. Which subquery checks if at least one row satisfies condition?
    - a) IN
    - b) ANY
    - c) ALL
    - d) EXISTS



### **Advanced SQL**

21. Find 5th to 10th highest salaries:
    - a) `SELECT salary FROM employees ORDER BY salary DESC LIMIT 5,5;`
    - b) `SELECT salary FROM employees ORDER BY salary DESC LIMIT 10 OFFSET 5;`
    - c) Use `ROW_NUMBER()` window function
    - d) All of the above (depends on D- b)



22. Which window function adds ranking without gaps?
    - a) ROW\_NUMBER()
    - b) RANK()
    - c) DENSE\_RANK()
    - d) NTILE()



23. To calculate running total of salaries:
    - a) `SUM(salary)`
    - b) `SUM(salary) OVER (ORDER BY emp_i- d)`
    - c) `SUM(salary) PARTITION BY emp_id`
    - d) `TOTAL(salary) OVER ()`



24. Which clause is used with window functions?
    - a) GROUP BY
    - b) HAVING
    - c) OVER
    - d) ORDER



25. Which query calculates percent rank?
    - a) `PERCENT_RANK() OVER (ORDER BY salary)`
    - b) `RANK() OVER (ORDER BY salary)`
    - c) `ROW_NUMBER() OVER (ORDER BY salary)`
    - d) `DENSE_RANK() OVER (ORDER BY salary)`



### **DDL / DML / Constraints**

26. Which command deletes all rows but keeps table?
    - a) DELETE
    - b) DROP
    - c) TRUNCATE
    - d) REMOVE



27. Which command removes table completely?
    - a) DELETE
    - b) TRUNCATE
    - c) DROP
    - d) ERASE



28. Which constraint ensures uniqueness but allows NULLs?
    - a) PRIMARY KEY
    - b) UNIQUE
    - c) FOREIGN KEY
    - d) CHECK



29. Which constraint prevents NULL in a column?
    - a) NOT NULL
    - b) UNIQUE
    - c) CHECK
    - d) DEFAULT



30. Which SQL keyword adds a new column?
    - a) MODIFY
    - b) ADD
    - c) UPDATE
    - d) ALTER COLUMN



### **Indexes & Performance**

31. Which improves query performance on WHERE column?
    - a) INDEX
    - b) TRIGGER
    - c) VIEW
    - d) STORED PROCEDURE



32. Which index type ensures uniqueness?
    - a) UNIQUE INDEX
    - b) CLUSTERED INDEX
    - c) NON-CLUSTERED INDEX
    - d) FULLTEXT INDEX



33. Which statement creates an index on salary?
    - a) `CREATE INDEX idx_salary ON employees(salary);`
    - b) `ALTER TABLE employees ADD INDEX salary;`
    - c) Both a and b
    - d) None



34. Which query uses index effectively?
    - a) `WHERE salary = 50000`
    - b) `WHERE salary > 50000`
    - c) `WHERE salary + 1000 = 51000`
    - d) Both a and b



35. Which is true about clustered index?
    - a) Only one per table
    - b) Data stored in sorted order
    - c) Improves range queries
    - d) All of the above



### **Views & Transactions**

36. Which query creates a view of high-paid employees?
    - a) `CREATE VIEW high_emp AS SELECT * FROM employees WHERE salary > 50000;`
    - b) `CREATE VIEWS high_emp SELECT * FROM employees WHERE salary > 50000;`
    - c) `CREATE TABLE high_emp AS SELECT * FROM employees WHERE salary > 50000;`
    - d) `VIEW high_emp AS SELECT * FROM employees WHERE salary > 50000;`



37. Which statement removes a view?
    - a) DROP TABLE
    - b) DROP VIEW
    - c) DELETE VIEW
    - d) REMOVE VIEW



38. Which command starts a transaction?
    - a) BEGIN
    - b) START
    - c) TRANSACTION
    - d) BEGIN TRANSACTION



39. Which ensures changes are permanent?
    - a) SAVEPOINT
    - b) COMMIT
    - c) ROLLBACK
    - d) CHECKPOINT



40. Which reverts transaction to previous state?
    - a) COMMIT
    - b) ROLLBACK
    - c) SAVEPOINT
    - d) REVERT



### **Miscellaneous**

41. Which keyword combines results removing duplicates?
    - a) UNION
    - b) UNION ALL
    - c) INTERSECT
    - d) JOIN



42. Which keyword keeps duplicates too?
    - a) UNION
    - b) UNION ALL
    - c) INTERSECT
    - d) EXCEPT



43. Which function returns current date in SQL?
    - a) CURDATE()
    - b) GETDATE()
    - c) CURRENT\_DATE
    - d) All of the above (depends on D- b)



44. Which query finds length of employee name?
    - a) `LEN(name)`
    - b) `LENGTH(name)`
    - c) `CHAR_LENGTH(name)`
    - d) All of the above (depends on D- b)



45. Which function converts string to uppercase?
    - a) TO\_UPPER()
    - b) UPPER()
    - c) UCASE()
    - d) Both b and c



46. Which operator is used for pattern matching?
    - a) LIKE
    - b) MATCH
    - c) IN
    - d) BETWEEN



47. Which query fetches employees hired in 2023?
    - a) `SELECT * FROM employees WHERE hire_date LIKE '2023%';`
    - b) `SELECT * FROM employees WHERE YEAR(hire_date) = 2023;`
    - c) `SELECT * FROM employees WHERE hire_date BETWEEN '2023-01-01' AND '2023-12-31';`
    - d) All of the above



48. Which is true about PRIMARY KEY?
    - a) Allows NULL
    - b) Allows duplicate
    - c) Combination of NOT NULL + UNIQUE
    - d) Can be multiple per table



49. Which operator checks value in range?
    - a) BETWEEN
    - b) IN
    - c) LIKE
    - d) ANY



50. Which query counts employees per department and sorts descending?
    - a) `SELECT dept_id, COUNT(*) FROM employees ORDER BY COUNT(*);`
    - b) `SELECT dept_id, COUNT(*) FROM employees GROUP BY dept_id ORDER BY COUNT(*) DESC;`
    - c) `SELECT dept_id, COUNT(*) FROM employees GROUP BY dept_id HAVING COUNT(*) > 0;`
    - d) Both b and c

