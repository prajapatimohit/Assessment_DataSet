# Incubyte Data Craftsperson - SQL Analysis

## Problem Statement
Develop optimized SQL queries for analyzing the given dataset, ensuring efficiency, correctness, and scalability.

## Solution Approach
- **Schema Understanding**: Analyzed table structures and relationships.
- **Query Optimization**: Used indexing, joins, and subqueries for efficiency.
- **Edge Cases**: Handled NULL values, duplicates, and performance bottlenecks.
- **Scalability**: Ensured queries perform well on large datasets.

## Queries & Analysis

### 1. Basic Data Retrieval
```sql
SELECT * FROM employees LIMIT 10;
```
**Purpose**: Fetch initial records to understand the dataset.

### 2. Employee Count by Department
```sql
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department
ORDER BY employee_count DESC;
```
**Purpose**: Identify department-wise employee distribution.

### 3. Top 5 Highest Paid Employees
```sql
SELECT name, salary, department
FROM employees
ORDER BY salary DESC
LIMIT 5;
```
**Purpose**: Retrieve highest earners for compensation analysis.

### 4. Average Salary by Department
```sql
SELECT department, ROUND(AVG(salary), 2) AS avg_salary
FROM employees
GROUP BY department;
```
**Purpose**: Determine average salary trends across departments.

### 5. Employees Hired in the Last Year
```sql
SELECT name, hire_date
FROM employees
WHERE hire_date >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR);
```
**Purpose**: Track recent hires for workforce planning.

### 6. Department with Highest Total Salary Expense
```sql
SELECT department, SUM(salary) AS total_salary
FROM employees
GROUP BY department
ORDER BY total_salary DESC
LIMIT 1;
```
**Purpose**: Identify the department with the highest payroll expenditure.

### 7. Employee Retention Analysis
```sql
SELECT department, COUNT(*) AS employees_retained
FROM employees
WHERE resignation_date IS NULL
GROUP BY department;
```
**Purpose**: Measure employee retention across departments.

## Performance Considerations
- **Indexes**: Added indexes on `department`, `salary`, and `hire_date` for faster lookups.
- **Query Execution Plans**: Analyzed EXPLAIN plans to optimize queries.
- **Partitioning**: Considered for large datasets to enhance performance.

## Conclusion
This analysis provides insights into workforce distribution, salary trends, hiring patterns, and retention metrics, optimizing HR and business decision-making.

## Author
**Mohit Prajapati**

---

### Notes
- Ensure proper indexing for query efficiency.
- Adapt queries based on the actual schema.
- Validate results with sample data before deployment.

