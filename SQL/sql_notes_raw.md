# Introduction to SQL - Comprehensive Notes

# Table of Contents 
1. [ Database Fundamentals. ](#fundamentals)
2. [ SQL Datatypes and Commands. ](#datatypes)
3. [ Basic Queries and Operations. ](#basic)
4. [ Advanced Querying Techniques. ](#advanced)
5. [ Data Modification Operations. ](#modification)
6. [ Table and Database Management. ](#management)
7. [ Joins and Relationships. ](#joins)
8. [ Advanced SQL Features. ](#features)

<a name="fundamentals"></a>
# 1. Database Fundamentals

## What is Database?
A database is an organized collection of structured information, or data, typically stored electronically in a computer system. It is managed by a Database Management System (DBMS) which provides an interface for users to interact with the data.

Key characteristics:
- Organized storage of data
- Easy retrieval and manipulation
- Data integrity and security
- Concurrent access by multiple users
- Backup and recovery mechanisms

## Types of Databases

### Relational Databases (RDBMS)
- Data stored in tables with rows and columns
- Uses SQL for querying
- ACID properties (Atomicity, Consistency, Isolation, Durability)
- Examples: MySQL, PostgreSQL, Oracle, SQL Server

### NoSQL Databases
- Non-relational databases
- Flexible schema
- Types include:
  - Document databases (MongoDB)
  - Key-value stores (Redis)
  - Column-family (Cassandra)
  - Graph databases (Neo4j)

### Hierarchical Databases
- Tree-like structure
- Parent-child relationships
- Limited flexibility

### Network Databases
- Graph structure allowing multiple parent-child relationships
- More flexible than hierarchical but complex

## Database Structure

### Database Hierarchy
1. **Database Server** - The main system
2. **Database** - Collection of related tables
3. **Table** - Collection of related records
4. **Record/Row** - Individual entry in a table
5. **Field/Column** - Individual data item in a record

### Components
- **Schema** - Logical structure of database
- **Instance** - Actual data stored at a particular moment
- **Metadata** - Data about data (structure information)

## What is Table?

A table is a collection of related data organized in rows and columns within a database. It's the fundamental storage unit in relational databases.

### Table Components:
- **Rows (Records/Tuples)** - Horizontal entries representing individual data items
- **Columns (Fields/Attributes)** - Vertical entries representing data categories
- **Cell** - Intersection of row and column containing specific data value

### Table Properties:
- Each table has a unique name
- Columns have specific data types
- Each row should be unique
- Order of rows and columns doesn't matter logically

## Creating Our First Database

### Basic Database Operations:
```sql
-- Create a new database
CREATE DATABASE database_name;

-- Use a specific database
USE database_name;

-- Show all databases
SHOW DATABASES;

-- Drop a database
DROP DATABASE database_name;
```

### Best Practices:
- Use descriptive names
- Follow naming conventions
- Consider future scalability
- Plan database structure before creation

<a name="datatypes"></a>
# 2. SQL Datatypes and Commands

## Creating Our First Table

### Basic Table Creation Syntax:
```sql
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    column3 datatype constraints
);
```

### Example:
```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT,
    email VARCHAR(100) UNIQUE
);
```

### Table Operations:
```sql
-- Show all tables
SHOW TABLES;

-- Describe table structure
DESCRIBE table_name;

-- Show table creation statement
SHOW CREATE TABLE table_name;
```

## SQL Datatypes

### Numeric Types:
- **INT** - Integer values (-2,147,483,648 to 2,147,483,647)
- **BIGINT** - Large integer values
- **DECIMAL(p,s)** - Fixed-point numbers
- **FLOAT** - Single precision floating-point
- **DOUBLE** - Double precision floating-point

### String Types:
- **CHAR(n)** - Fixed-length string
- **VARCHAR(n)** - Variable-length string
- **TEXT** - Large text data
- **LONGTEXT** - Very large text data

### Date and Time Types:
- **DATE** - Date values (YYYY-MM-DD)
- **TIME** - Time values (HH:MM:SS)
- **DATETIME** - Date and time combination
- **TIMESTAMP** - Timestamp values
- **YEAR** - Year values

### Other Types:
- **BOOLEAN** - True/False values
- **BLOB** - Binary large objects
- **JSON** - JSON data (MySQL 5.7+)

## Types of SQL Commands

### DDL (Data Definition Language)
Commands that define database structure:
- **CREATE** - Create database objects
- **ALTER** - Modify database objects
- **DROP** - Delete database objects
- **TRUNCATE** - Remove all records from table

### DML (Data Manipulation Language)
Commands that manipulate data:
- **SELECT** - Retrieve data
- **INSERT** - Add new data
- **UPDATE** - Modify existing data
- **DELETE** - Remove data

### DCL (Data Control Language)
Commands that control access:
- **GRANT** - Give permissions
- **REVOKE** - Remove permissions

### TCL (Transaction Control Language)
Commands that manage transactions:
- **COMMIT** - Save transaction
- **ROLLBACK** - Undo transaction
- **SAVEPOINT** - Set transaction savepoint

## Database Related Queries

### Basic Database Operations:
```sql
-- Create database
CREATE DATABASE company;

-- Select database
USE company;

-- Show current database
SELECT DATABASE();

-- Show all databases
SHOW DATABASES;

-- Drop database
DROP DATABASE company;
```

### Database Information:
```sql
-- Show database size
SELECT 
    table_schema AS 'Database',
    ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) AS 'Size (MB)'
FROM information_schema.tables
GROUP BY table_schema;
```

<a name="basic"></a>
# 3. Basic Queries and Operations

## Table Related Queries

### Basic Table Operations:
```sql
-- Create table
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10,2)
);

-- Show tables
SHOW TABLES;

-- Describe table
DESCRIBE employees;
DESC employees;

-- Show table info
SHOW TABLE STATUS LIKE 'employees';

-- Drop table
DROP TABLE employees;
```

## SELECT Command

The SELECT statement retrieves data from database tables.

### Basic Syntax:
```sql
SELECT column1, column2, ...
FROM table_name;

-- Select all columns
SELECT * FROM table_name;

-- Select specific columns
SELECT name, age FROM students;
```

### SELECT Variations:
```sql
-- Select distinct values
SELECT DISTINCT column_name FROM table_name;

-- Select with alias
SELECT name AS student_name, age AS student_age FROM students;

-- Select with calculations
SELECT name, salary, salary * 12 AS annual_salary FROM employees;
```

## INSERT Command

The INSERT statement adds new records to a table.

### Basic Syntax:
```sql
-- Insert specific columns
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);

-- Insert all columns
INSERT INTO table_name
VALUES (value1, value2, value3, value4);
```

### INSERT Variations:
```sql
-- Insert multiple rows
INSERT INTO students (name, age, email)
VALUES 
    ('John', 20, 'john@email.com'),
    ('Jane', 22, 'jane@email.com'),
    ('Bob', 21, 'bob@email.com');

-- Insert from another table
INSERT INTO table1 (column1, column2)
SELECT column1, column2 FROM table2
WHERE condition;
```

## Keys

### Primary Key
- Uniquely identifies each record in a table
- Cannot contain NULL values
- Each table can have only one primary key
- Can be composed of multiple columns (composite key)

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);

-- Or using constraint
CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    PRIMARY KEY (id)
);
```

### Foreign Key
- Links two tables together
- References primary key of another table
- Maintains referential integrity

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

### Unique Key
- Ensures uniqueness of values
- Can contain NULL values
- Multiple unique keys allowed per table

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE,
    username VARCHAR(50) UNIQUE
);
```

### Candidate Key
- Set of attributes that can uniquely identify records
- Primary key is chosen from candidate keys

### Super Key
- Set of attributes that can uniquely identify records
- Dependency on base tables

- May contain additional attributes beyond candidate key

## Constraints

### NOT NULL
Ensures column cannot have empty values:
```sql
CREATE TABLE students (
    id INT NOT NULL,
    name VARCHAR(50) NOT NULL
);
```

### UNIQUE
Ensures all values in column are different:
```sql
CREATE TABLE users (
    email VARCHAR(100) UNIQUE
);
```

### PRIMARY KEY
Combination of NOT NULL and UNIQUE:
```sql
CREATE TABLE products (
    id INT PRIMARY KEY
);
```

### FOREIGN KEY
Maintains referential integrity:
```sql
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

### CHECK
Ensures values meet specific condition:
```sql
CREATE TABLE employees (
    age INT CHECK (age >= 18),
    salary DECIMAL CHECK (salary > 0)
);
```

### DEFAULT
Provides default value:
```sql
CREATE TABLE products (
    status VARCHAR(20) DEFAULT 'active',
    created_date DATE DEFAULT CURRENT_DATE
);
```

## SELECT Command in Detail

### Advanced SELECT Features:
```sql
-- Column aliases
SELECT first_name AS 'First Name', last_name AS 'Last Name' FROM employees;

-- Calculated columns
SELECT name, salary, salary * 0.1 AS tax FROM employees;

-- Concatenation
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;

-- Case statements
SELECT name,
    CASE 
        WHEN age < 18 THEN 'Minor'
        WHEN age >= 18 AND age < 65 THEN 'Adult'
        ELSE 'Senior'
    END AS age_group
FROM people;
```

## WHERE Clause

Filters records based on specified conditions:

### Basic Syntax:
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### Examples:
```sql
-- Single condition
SELECT * FROM employees WHERE salary > 50000;

-- Multiple conditions
SELECT * FROM employees WHERE department = 'IT' AND salary > 60000;

-- Pattern matching
SELECT * FROM employees WHERE name LIKE 'J%';

-- Range
SELECT * FROM products WHERE price BETWEEN 100 AND 500;

-- List
SELECT * FROM employees WHERE department IN ('IT', 'HR', 'Finance');
```

## Operators

### Comparison Operators:
- **=** Equal to
- **!=** or **<>** Not equal to
- **>** Greater than
- **<** Less than
- **>=** Greater than or equal to
- **<=** Less than or equal to

### Logical Operators:
- **AND** - Both conditions must be true
- **OR** - At least one condition must be true
- **NOT** - Condition must be false

### Pattern Matching:
- **LIKE** - Pattern matching with wildcards
  - **%** - Zero or more characters
  - **_** - Single character

### Range Operators:
- **BETWEEN** - Value within range
- **IN** - Value in list
- **IS NULL** - Check for null values
- **IS NOT NULL** - Check for non-null values

### Examples:
```sql
SELECT * FROM employees WHERE name LIKE 'A%';
SELECT * FROM products WHERE price BETWEEN 100 AND 500;
SELECT * FROM employees WHERE department IN ('IT', 'HR');
SELECT * FROM customers WHERE phone IS NOT NULL;
```

## LIMIT Clause

Restricts number of records returned:

### Syntax:
```sql
SELECT column1, column2
FROM table_name
LIMIT number;

-- With offset
SELECT column1, column2
FROM table_name
LIMIT offset, count;
```

### Examples:
```sql
-- Get first 5 records
SELECT * FROM employees LIMIT 5;

-- Get records 6-10 (skip first 5, then get 5)
SELECT * FROM employees LIMIT 5, 5;

-- Pagination example
SELECT * FROM products LIMIT 20, 10; -- Page 3, 10 items per page
```

## ORDER BY Clause

Sorts result set by specified columns:

### Syntax:
```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 ASC|DESC, column2 ASC|DESC;
```

### Examples:
```sql
-- Sort by single column
SELECT * FROM employees ORDER BY salary DESC;

-- Sort by multiple columns
SELECT * FROM employees ORDER BY department ASC, salary DESC;

-- Sort by column position
SELECT name, salary FROM employees ORDER BY 2 DESC;

-- Sort with expressions
SELECT name, salary FROM employees ORDER BY salary * 12 DESC;
```

## Aggregate Functions

Perform calculations on multiple rows and return single value:

### Common Aggregate Functions:
- **COUNT()** - Count number of rows
- **SUM()** - Sum of numeric values
- **AVG()** - Average of numeric values
- **MAX()** - Maximum value
- **MIN()** - Minimum value

### Examples:
```sql
-- Count all employees
SELECT COUNT(*) FROM employees;

-- Count non-null values
SELECT COUNT(email) FROM employees;

-- Sum of all salaries
SELECT SUM(salary) FROM employees;

-- Average salary
SELECT AVG(salary) FROM employees;

-- Highest and lowest salary
SELECT MAX(salary), MIN(salary) FROM employees;

-- Multiple aggregates
SELECT 
    COUNT(*) as total_employees,
    AVG(salary) as avg_salary,
    MAX(salary) as max_salary
FROM employees;
```

## GROUP BY Clause

Groups rows with same values and allows aggregate functions on each group:

### Syntax:
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1;
```

### Examples:
```sql
-- Count employees by department
SELECT department, COUNT(*) as employee_count
FROM employees
GROUP BY department;

-- Average salary by department
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department;

-- Multiple grouping columns
SELECT department, job_title, COUNT(*) as count
FROM employees
GROUP BY department, job_title;

-- Group by expression
SELECT 
    YEAR(hire_date) as hire_year,
    COUNT(*) as employees_hired
FROM employees
GROUP BY YEAR(hire_date);
```

## HAVING Clause

Filters groups created by GROUP BY (WHERE filters individual rows, HAVING filters groups):

### Syntax:
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1
HAVING condition;
```

### Examples:
```sql
-- Departments with more than 5 employees
SELECT department, COUNT(*) as employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;

-- Departments with average salary > 60000
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 60000;

-- Combined WHERE and HAVING
SELECT department, AVG(salary) as avg_salary
FROM employees
WHERE hire_date > '2020-01-01'
GROUP BY department
HAVING AVG(salary) > 50000;
```

## General Order of Commands

SQL commands must be written in specific order:

### Standard Order:
1. **SELECT** - Columns to retrieve
2. **FROM** - Tables to query
3. **WHERE** - Filter individual rows
4. **GROUP BY** - Group rows
5. **HAVING** - Filter groups
6. **ORDER BY** - Sort results
7. **LIMIT** - Restrict number of results

### Example:
```sql
SELECT department, AVG(salary) as avg_salary
FROM employees
WHERE hire_date > '2020-01-01'
GROUP BY department
HAVING AVG(salary) > 50000
ORDER BY avg_salary DESC
LIMIT 5;
```

<a name="advanced"></a>
# 4. Advanced Querying Techniques

<a name="modification"></a>
# 5. Data Modification Operations

## UPDATE Command

Modifies existing records in a table:

### Syntax:
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Examples:
```sql
-- Update single record
UPDATE employees
SET salary = 75000
WHERE id = 1;

-- Update multiple columns
UPDATE employees
SET salary = salary * 1.1, department = 'Senior IT'
WHERE department = 'IT' AND experience > 5;

-- Update with subquery
UPDATE employees
SET salary = (SELECT AVG(salary) FROM employees WHERE department = 'IT')
WHERE id = 1;

-- Update all records (be careful!)
UPDATE products
SET status = 'discontinued';
```

### Safety Tips:
- Always use WHERE clause unless updating all records intentionally
- Test with SELECT first
- Use transactions for critical updates
- Backup data before major updates

## DELETE Command

Removes records from a table:

### Syntax:
```sql
DELETE FROM table_name
WHERE condition;
```

### Examples:
```sql
-- Delete specific record
DELETE FROM employees
WHERE id = 1;

-- Delete multiple records
DELETE FROM employees
WHERE department = 'IT' AND salary < 40000;

-- Delete with subquery
DELETE FROM orders
WHERE customer_id IN (SELECT id FROM customers WHERE status = 'inactive');

-- Delete all records (keeps table structure)
DELETE FROM temp_table;
```

### DELETE vs TRUNCATE vs DROP:
- **DELETE** - Removes rows, can use WHERE, slower, can rollback
- **TRUNCATE** - Removes all rows, faster, cannot rollback
- **DROP** - Removes entire table structure

## Revisiting Foreign Keys

Foreign keys maintain referential integrity between tables:

### Creating Foreign Keys:
```sql
-- During table creation
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    product_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);

-- Adding foreign key to existing table
ALTER TABLE orders
ADD FOREIGN KEY (customer_id) REFERENCES customers(id);
```

### Foreign Key Benefits:
- Prevents invalid data entry
- Maintains data consistency
- Prevents deletion of referenced records
- Enforces business rules

### Foreign Key Actions:
- **RESTRICT** - Prevent delete/update of referenced row
- **CASCADE** - Delete/update dependent rows automatically
- **SET NULL** - Set foreign key to NULL
- **SET DEFAULT** - Set foreign key to default value

## Cascading Foreign Keys

Automatic actions when referenced data changes:

### CASCADE Options:
```sql
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);
```

### Types of Cascading:
- **ON DELETE CASCADE** - Delete child records when parent is deleted
- **ON UPDATE CASCADE** - Update child records when parent key is updated
- **ON DELETE SET NULL** - Set foreign key to NULL when parent is deleted
- **ON DELETE RESTRICT** - Prevent parent deletion if children exist

### Examples:
```sql
-- Customer deletion cascades to orders
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE
);

-- Set to NULL on deletion
CREATE TABLE employees (
    id INT PRIMARY KEY,
    manager_id INT,
    FOREIGN KEY (manager_id) REFERENCES employees(id)
        ON DELETE SET NULL
);
```

## ALTER Command

Modifies existing database objects:

### ALTER TABLE Operations:
```sql
-- Add column
ALTER TABLE employees
ADD COLUMN phone VARCHAR(15);

-- Drop column
ALTER TABLE employees
DROP COLUMN phone;

-- Add constraint
ALTER TABLE employees
ADD CONSTRAINT uk_email UNIQUE (email);

-- Drop constraint
ALTER TABLE employees
DROP CONSTRAINT uk_email;

-- Add primary key
ALTER TABLE employees
ADD PRIMARY KEY (id);

-- Add foreign key
ALTER TABLE orders
ADD FOREIGN KEY (customer_id) REFERENCES customers(id);
```

## CHANGE and MODIFY Commands

### CHANGE Command:
Renames column and can change its definition:
```sql
-- Change column name and type
ALTER TABLE employees
CHANGE old_column_name new_column_name VARCHAR(100);

-- Change just the name (keep same type)
ALTER TABLE employees
CHANGE first_name fname VARCHAR(50);
```

### MODIFY Command:
Changes column definition without renaming:
```sql
-- Change column type
ALTER TABLE employees
MODIFY salary DECIMAL(12,2);

-- Add constraint
ALTER TABLE employees
MODIFY email VARCHAR(100) NOT NULL UNIQUE;

-- Change multiple columns
ALTER TABLE employees
MODIFY COLUMN name VARCHAR(100),
MODIFY COLUMN age INT NOT NULL;
```

## TRUNCATE Command

Removes all records from table while keeping structure:

### Syntax:
```sql
TRUNCATE TABLE table_name;
```

### TRUNCATE vs DELETE:
- **TRUNCATE** - Faster, removes all rows, resets auto-increment, cannot use WHERE
- **DELETE** - Slower, can be selective, maintains auto-increment counter

### Examples:
```sql
-- Remove all data from table
TRUNCATE TABLE temp_data;

-- Cannot use WHERE with TRUNCATE
-- This is INVALID:
-- TRUNCATE TABLE employees WHERE department = 'IT';

-- Use DELETE for conditional removal:
DELETE FROM employees WHERE department = 'IT';
```

<a name="management"></a>
# 6. Table and Database Management

## JOINS in SQL

Combines rows from two or more tables based on related columns:

### Types of JOINS:

#### INNER JOIN
Returns records with matching values in both tables:
```sql
SELECT columns
FROM table1
INNER JOIN table2 ON table1.column = table2.column;

-- Example
SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d ON e.department_id = d.id;
```

#### LEFT JOIN (LEFT OUTER JOIN)
Returns all records from left table and matched records from right:
```sql
SELECT columns
FROM table1
LEFT JOIN table2 ON table1.column = table2.column;

-- Example
SELECT c.name, o.order_date
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id;
```

#### RIGHT JOIN (RIGHT OUTER JOIN)
Returns all records from right table and matched records from left:
```sql
SELECT columns
FROM table1
RIGHT JOIN table2 ON table1.column = table2.column;
```

#### FULL OUTER JOIN
Returns all records when there's a match in either table:
```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2 ON table1.column = table2.column;
```

#### CROSS JOIN
Returns Cartesian product of both tables:
```sql
SELECT columns
FROM table1
CROSS JOIN table2;
```

#### SELF JOIN
Joins table with itself:
```sql
SELECT e1.name AS employee, e2.name AS manager
FROM employees e1
JOIN employees e2 ON e1.manager_id = e2.id;
```

### Complex JOIN Examples:
```sql
-- Multiple joins
SELECT 
    o.id,
    c.name AS customer_name,
    p.name AS product_name,
    o.quantity
FROM orders o
JOIN customers c ON o.customer_id = c.id
JOIN products p ON o.product_id = p.id;

-- Join with conditions
SELECT e.name, d.name
FROM employees e
JOIN departments d ON e.dept_id = d.id
WHERE e.salary > 50000;
```

<a name="features"></a>
# 7. Advanced SQL Features

## UNION in SQL

Combines results of two or more SELECT statements:

### UNION vs UNION ALL:
- **UNION** - Removes duplicates
- **UNION ALL** - Keeps duplicates (faster)

### Syntax:
```sql
SELECT column1, column2 FROM table1
UNION
SELECT column1, column2 FROM table2;
```

### Rules:
- Same number of columns
- Similar data types
- Column names from first SELECT used

### Examples:
```sql
-- Combine active and inactive customers
SELECT name, email FROM active_customers
UNION
SELECT name, email FROM inactive_customers;

-- With ORDER BY (applies to final result)
SELECT name FROM managers
UNION
SELECT name FROM employees
ORDER BY name;

-- Different tables with aliases
SELECT 'Customer' as type, name FROM customers
UNION
SELECT 'Supplier' as type, name FROM suppliers;
```

## SQL Sub Queries

Query nested inside another query:

### Types of Subqueries:

#### Single Row Subquery:
Returns one row:
```sql
SELECT name FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);
```

#### Multiple Row Subquery:
Returns multiple rows:
```sql
SELECT name FROM employees
WHERE department_id IN (
    SELECT id FROM departments 
    WHERE location = 'New York'
);
```

#### Correlated Subquery:
References outer query:
```sql
SELECT name FROM employees e1
WHERE salary > (
    SELECT AVG(salary) 
    FROM employees e2 
    WHERE e2.department_id = e1.department_id
);
```

### Subquery Operators:
- **IN** - Value exists in subquery results
- **NOT IN** - Value doesn't exist in subquery results
- **EXISTS** - Subquery returns at least one row
- **NOT EXISTS** - Subquery returns no rows
- **ANY/SOME** - Condition true for any subquery value
- **ALL** - Condition true for all subquery values

### Examples:
```sql
-- EXISTS example
SELECT name FROM customers c
WHERE EXISTS (
    SELECT 1 FROM orders o 
    WHERE o.customer_id = c.id
);

-- ALL example
SELECT name FROM employees
WHERE salary > ALL (
    SELECT salary FROM employees 
    WHERE department = 'HR'
);

-- Subquery in SELECT
SELECT 
    name,
    salary,
    (SELECT AVG(salary) FROM employees) as avg_salary
FROM employees;
```

## MySQL Views

Virtual tables based on SQL queries:

### Creating Views:
```sql
CREATE VIEW view_name AS
SELECT columns
FROM tables
WHERE conditions;

-- Example
CREATE VIEW high_salary_employees AS
SELECT name, department, salary
FROM employees
WHERE salary > 75000;
```

### Using Views:
```sql
-- Query view like a table
SELECT * FROM high_salary_employees;

-- Join with other tables
SELECT v.name, d.location
FROM high_salary_employees v
JOIN departments d ON v.department = d.name;
```

### View Operations:
```sql
-- Update view definition
CREATE OR REPLACE VIEW view_name AS
SELECT new_columns FROM tables;

-- Drop view
DROP VIEW view_name;

-- Show view definition
SHOW CREATE VIEW view_name;
```

### Types of Views:

#### Simple Views:
- Based on single table
- Can perform DML operations
```sql
CREATE VIEW emp_view AS
SELECT id, name, salary FROM employees;
```

#### Complex Views:
- Based on multiple tables or contains functions
- Limited DML operations
```sql
CREATE VIEW dept_summary AS
SELECT 
    d.name,
    COUNT(e.id) as employee_count,
    AVG(e.salary) as avg_salary
FROM departments d
LEFT JOIN employees e ON d.id = e.dept_id
GROUP BY d.id, d.name;
```

### View Benefits:
- Security (hide sensitive columns)
- Simplify complex queries
- Provide consistent interface
- Logical data independence

### View Limitations:
- Performance overhead
- Update restrictions on complex views
- Dependency on base tables
