## SQL get second highest salary
To get the second highest salary from an employee record in SQL, you can use various approaches depending on the SQL database you are using. Here are some common methods that work for different SQL databases. Which one works best depends on your database system and whether salaries have duplicates.

**1. Using `LIMIT` and `OFFSET` (MySQL, PostgreSQL)**
```sql
SELECT DISTINCT salary 
FROM employees 
ORDER BY salary DESC 
LIMIT 1 OFFSET 1;
```
- `ORDER BY salary DESC` sorts the salaries in descending order.
- `LIMIT 1 OFFSET 1` skips the highest salary and fetches the second highest.

**2. Using `MAX()` and `NOT IN` (Works in most SQL databases)**
```sql
SELECT MAX(salary) 
FROM employees 
WHERE salary NOT IN (SELECT MAX(salary) FROM employees);
```
- The subquery fetches the highest salary.
- The outer query finds the highest salary excluding the first highest.

**3. Using `DENSE_RANK()` (Best for handling duplicate salaries)**
```sql
SELECT salary 
FROM (
    SELECT salary, DENSE_RANK() OVER (ORDER BY salary DESC) AS rnk 
    FROM employees
) ranked 
WHERE rnk = 2;
```
- `DENSE_RANK()` assigns the same rank to duplicate salaries.
- The outer query filters for the second-highest salary (`rnk = 2`).

**4. Using `TOP` (SQL Server)**
```sql
SELECT TOP 1 salary 
FROM (
    SELECT DISTINCT TOP 2 salary 
    FROM employees 
    ORDER BY salary DESC
) AS temp 
ORDER BY salary ASC;
```
- `TOP 2` gets the top two salaries.
- The outer query selects the second highest.

## What are JOINs in SQL?
In SQL, **JOINs** are used to combine rows from two or more tables based on a related column. This allows querying data that is stored across multiple tables.

### Types of SQL JOINs
#### 1️⃣ **INNER JOIN** (Most Common)
- Returns only the matching rows from both tables.
- Non-matching rows are excluded.

✅ **Example:**
```sql
SELECT employees.name, departments.dept_name 
FROM employees 
INNER JOIN departments 
ON employees.dept_id = departments.dept_id;
```
💡 **Result:** Only employees with a matching `dept_id` in the `departments` table are shown.

#### 2️⃣ **LEFT JOIN** (or LEFT OUTER JOIN)
- Returns all rows from the **left** table and matching rows from the **right** table.
- If there is no match, NULL values are returned for columns from the right table.

✅ **Example:**
```sql
SELECT employees.name, departments.dept_name 
FROM employees 
LEFT JOIN departments 
ON employees.dept_id = departments.dept_id;
```
💡 **Result:** All employees are listed, even those without a department.

#### 3️⃣ **RIGHT JOIN** (or RIGHT OUTER JOIN)
- Returns all rows from the **right** table and matching rows from the **left** table.
- If no match, NULL values appear for the left table’s columns.

✅ **Example:**
```sql
SELECT employees.name, departments.dept_name 
FROM employees 
RIGHT JOIN departments 
ON employees.dept_id = departments.dept_id;
```
💡 **Result:** All departments are listed, even those without employees.

#### 4️⃣ **FULL JOIN** (or FULL OUTER JOIN)
- Returns all records from **both** tables.
- If there is no match, NULL values appear for missing matches.

✅ **Example:**
```sql
SELECT employees.name, departments.dept_name 
FROM employees 
FULL JOIN departments 
ON employees.dept_id = departments.dept_id;
```
💡 **Result:** Shows all employees and all departments, including those with no match.

#### 5️⃣ **CROSS JOIN** 
- Returns the **Cartesian product** of both tables.
- Every row in Table A is combined with every row in Table B.

✅ **Example:**
```sql
SELECT employees.name, departments.dept_name 
FROM employees 
CROSS JOIN departments;
```
💡 **Result:** If there are 5 employees and 3 departments, the result will have **5 × 3 = 15 rows**.

#### 6️⃣ **SELF JOIN**
- A table is joined with itself.
- Useful for hierarchical data (e.g., employees & managers).

✅ **Example:**
```sql
SELECT e1.name AS Employee, e2.name AS Manager
FROM employees e1
JOIN employees e2 
ON e1.manager_id = e2.emp_id;
```
💡 **Result:** Shows employees along with their managers.

#### **Summary Table**
| **JOIN Type**  | **Matching Rows?** | **Non-Matching Rows?** |
|---------------|------------------|------------------|
| **INNER JOIN**  | ✅ Yes (Both Tables) | ❌ No |
| **LEFT JOIN**   | ✅ Yes (Both Tables) | ✅ Yes (Left Table) |
| **RIGHT JOIN**  | ✅ Yes (Both Tables) | ✅ Yes (Right Table) |
| **FULL JOIN**   | ✅ Yes (Both Tables) | ✅ Yes (Both Tables) |
| **CROSS JOIN**  | ❌ No Condition | ✅ All Combinations |
| **SELF JOIN**   | ✅ Yes (Same Table) | ❌ No |

👉 **Use Case Examples:**
- `INNER JOIN` → Get employees with departments.
- `LEFT JOIN` → Get all employees (even those without a department).
- `RIGHT JOIN` → Get all departments (even those with no employees).
- `FULL JOIN` → Get all employees and departments, including those without matches.
- `CROSS JOIN` → Generate all possible combinations of two tables.
- `SELF JOIN` → Find managers of employees.

## How do you optimize SQL queries for performance?
Optimizing SQL queries is crucial for improving database performance, reducing execution time, and minimizing resource consumption. Here are some key techniques:

**1️⃣ Use Proper Indexing**

## What is Indexing in SQL?

### **What is Indexing in SQL?**
Indexing in SQL is a technique used to improve the speed of data retrieval from a database table. An index is similar to a book's table of contents—it allows the database to quickly locate and fetch the requested data instead of scanning the entire table.

**Types of Indexes in SQL**

**1️⃣ Primary Index (Clustered Index)**
- Automatically created on the **Primary Key**.
- The physical order of table rows is arranged based on the index.
- Each table can have **only one** clustered index.

✅ **Example:**
```sql
CREATE CLUSTERED INDEX idx_emp_id ON employees(emp_id);
```
💡 **Effect:** The table’s data is physically sorted by `emp_id`.

**2️⃣ Unique Index**
- Ensures that all values in a column are **distinct**.
- Automatically created on **Primary Keys & Unique Constraints**.

✅ **Example:**
```sql
CREATE UNIQUE INDEX idx_unique_email ON employees(email);
```
💡 **Effect:** No two employees can have the same email.

**3️⃣ Non-Clustered Index**
- Stores only a pointer to the actual row, not the physical data.
- Used when multiple indexes are needed on a table.
- A table can have **multiple non-clustered indexes**.

✅ **Example:**
```sql
CREATE INDEX idx_salary ON employees(salary);
```
💡 **Effect:** Faster queries on `salary` but doesn’t affect row order.

** 4️⃣ Composite Index (Multi-Column Index)**
- Indexing on **multiple columns** to speed up queries involving both.

✅ **Example:**
```sql
CREATE INDEX idx_name_dept ON employees(last_name, dept_id);
```
💡 **Effect:** Optimized searches filtering both `last_name` and `dept_id`.

**5️⃣ Full-Text Index**
- Used for fast text searches in **large text fields**.
- Useful for searching documents, articles, etc.

✅ **Example (MySQL & SQL Server):**
```sql
CREATE FULLTEXT INDEX idx_description ON products(description);
```
💡 **Effect:** Enables fast keyword searches in the `description` column.

**Advantages of Indexing**  
✅ Speeds up SELECT queries (by reducing full table scans).  
✅ Improves sorting and filtering performance (e.g., `ORDER BY`, `WHERE`).  
✅ Enhances JOIN operations when indexing foreign keys.  

**Disadvantages of Indexing**  
❌ Slows down `INSERT`, `UPDATE`, `DELETE` (because indexes need to be updated).  
❌ Consumes additional storage space.  
❌ Too many indexes can degrade performance rather than improve it.  

## When to Use Indexing?
- Frequently searched or filtered columns (`WHERE`, `ORDER BY`).
- Primary keys and foreign keys.
- Large tables with millions of rows.
- Composite indexes for multiple search criteria.
