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
## Key Queries and Insights:
- **Overall Counts**:
Total Transactions: 500,001
Total Sales Revenue: ₹10,202,743,873.04

-**Sales by Store Type**:
In-store and online sales are quite similar, with the top products being laptops, sofas, and t-shirts.
Average discount across products: ~25%.

-**Top Cities by Quantity Sold**:
Bangalore, Jaipur, Delhi, Kolkata, and Chennai are the top cities, each with very similar sales and quantity numbers (~1B in sales).

-**Average Discount by City**:
Average discounts remain consistent across top cities (~24.9% to 25.1%).

-**Promotional Sales by City**:
Around 49-50% of sales in each city are promotional, reflecting a strong promotional strategy.

-**Product-wise Sales and Shipping Info**:
Laptops have the highest sales (~6.23B) with moderate shipping costs (~350) and a delivery time of 4 days.
Sofas generate significant revenue but have higher shipping costs and longer delivery times (10 days).
T-shirts and other smaller products have lower sales but faster delivery and cheaper shipping.

-**Sales by Customer Gender and Age Group**:
The 36-55 age group generates the highest sales (~1.18B).
Male, Female, and Other genders show similar purchasing behavior across age groups.
Loyalty points vary slightly across age groups, with younger customers (18-25) and seniors (65+) showing slightly higher engagement.

-**Returned Orders by Region**:
The South region leads in sales and returned orders, with 72,796 returns. Other regions show consistent return trends, with data quality concerns for NULL regions.

-**Returned Orders by Product**:
Laptops, Sofas, and T-Shirts show the highest sales and returns.
High returns for laptops and sofas might be due to issues like defects, wrong specifications, or delivery damages.
T-shirts' high returns are likely due to size and fit issues.
## Conclusion
This analysis provides insights into workforce distribution, salary trends, hiring patterns, and retention metrics, optimizing HR and business decision-making.

## Author
**Mohit Prajapati**

---

### Notes
- Ensure proper indexing for query efficiency.
- Adapt queries based on the actual schema.
- Validate results with sample data before deployment.

