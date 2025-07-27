# Introduction to SQL - Comprehensive Notes

## Table of Contents
1. [Introduction to SQL](#introduction-to-sql)
2. [What is Database?](#what-is-database)  
3. [Types of Databases](#types-of-databases)
4. [Database Structure](#database-structure)
5. [What is Table?](#what-is-table)
6. [Creating Our First Database](#creating-our-first-database)
7. [Creating Our First Table](#creating-our-first-table)
8. [SQL Datatypes](#sql-datatypes)
9. [Types of SQL Commands](#types-of-sql-commands)
10. [Database Related Queries](#database-related-queries)
11. [Table Related Queries](#table-related-queries)
12. [SELECT Command](#select-command)
13. [INSERT Command](#insert-command)
14. [Keys](#keys)
15. [Constraints](#constraints)
16. [SELECT Command in Detail](#select-command-in-detail)
17. [WHERE Clause](#where-clause)
18. [Operators](#operators)
19. [LIMIT Clause](#limit-clause)
20. [ORDER BY Clause](#order-by-clause)
21. [Aggregate Functions](#aggregate-functions)
22. [GROUP BY Clause](#group-by-clause)
23. [HAVING Clause](#having-clause)
24. [General Order of Commands](#general-order-of-commands)
25. [UPDATE Command](#update-command)
26. [DELETE Command](#delete-command)
27. [Revisiting Foreign Keys](#revisiting-foreign-keys)
28. [Cascading Foreign Keys](#cascading-foreign-keys)
29. [ALTER Command](#alter-command)
30. [CHANGE and MODIFY Commands](#change-and-modify-commands)
31. [TRUNCATE Command](#truncate-command)
32. [JOINS in SQL](#joins-in-sql)
33. [UNION in SQL](#union-in-sql)
34. [SQL Sub Queries](#sql-sub-queries)
35. [MySQL Views](#mysql-views)

---

## Introduction to SQL

SQL (Structured Query Language) is a standard programming language designed for managing and manipulating relational databases. It provides a powerful and flexible way to create, read, update, and delete data in database systems.

Key features of SQL:
- Declarative language (specify what you want, not how to get it)
- Standardized across different database systems
- Powerful querying capabilities
- Data integrity and security features
- Support for complex operations and transactions

---

## What is Database?

A database is an organized collection of structured information, or data, typically stored electronically in a computer system. It is managed by a Database Management System (DBMS) which provides an interface for users to interact with the data.

### Key Characteristics:
- **Organized storage of data** - Data is structured in a logical manner
- **Easy retrieval and manipulation** - Efficient access to information
- **Data integrity and security** - Ensures data accuracy and protection
- **Concurrent access by multiple users** - Multiple users can access simultaneously
- **Backup and recovery mechanisms** - Data protection and restoration capabilities

### Database Benefits:
- Eliminates data redundancy
- Ensures data consistency
- Provides data security
- Enables data sharing
- Maintains data integrity
- Offers backup and recovery

---

## Types of Databases

### Relational Databases (RDBMS)
- **Structure**: Data stored in tables with rows and columns
- **Query Language**: Uses SQL for querying
- **Properties**: ACID properties (Atomicity, Consistency, Isolation, Durability)
- **Examples**: MySQL, PostgreSQL, Oracle, SQL Server, SQLite
- **Best for**: Structured data with clear relationships

### NoSQL Databases
- **Structure**: Non-relational databases with flexible schema
- **Types include**:
  - **Document databases** (MongoDB) - Store data as documents
  - **Key-value stores** (Redis) - Simple key-value pairs
  - **Column-family** (Cassandra) - Wide column storage
  - **Graph databases** (Neo4j) - Node and relationship based
- **Best for**: Unstructured data, rapid scaling, flexible schema requirements

### Hierarchical Databases
- **Structure**: Tree-like structure with parent-child relationships
- **Characteristics**: Limited flexibility, fast access to specific paths
- **Use cases**: File systems, organizational charts

### Network Databases
- **Structure**: Graph structure allowing multiple parent-child relationships
- **Characteristics**: More flexible than hierarchical but complex to manage
- **Use cases**: Complex many-to-many relationships

---

## Database Structure

### Database Hierarchy
1. **Database Server** - The main system hosting multiple databases
2. **Database** - Collection of related tables and objects
3. **Table** - Collection of related records/rows
4. **Record/Row** - Individual entry in a table
5. **Field/Column** - Individual data item in a record

### Key Components
- **Schema** - Logical structure and organization of database
- **Instance** - Actual data stored at a particular moment in time
- **Metadata** - Data about data (structure information, constraints, etc.)
- **Index** - Data structure that improves query performance
- **View** - Virtual table based on query results

---

## What is Table?

A table is a collection of related data organized in rows and columns within a database. It's the fundamental storage unit in relational databases.

### Table Components:
- **Rows (Records/Tuples)** - Horizontal entries representing individual data items
- **Columns (Fields/Attributes)** - Vertical entries representing data categories  
- **Cell** - Intersection of row and column containing specific data value

### Table Properties:
- Each table has a unique name within the database
- Columns have specific data types and constraints
- Each row should be uniquely identifiable
- Order of rows and columns doesn't matter logically
- Tables can have relationships with other tables

### Table Example:
```
Students Table:
+----+----------+-----+------------------+
| ID | Name     | Age | Email            |
+----+----------+-----+------------------+
| 1  | John Doe | 20  | john@email.com   |
| 2  | Jane Smith| 22  | jane@email.com   |
+----+----------+-----+------------------+
```

---

## Creating Our First Database

### Basic Database Operations:

```sql
-- Create a new database
CREATE DATABASE database_name;

-- Use a specific database
USE database_name;

-- Show all databases
SHOW DATABASES;

-- Drop a database (permanently delete)
DROP DATABASE database_name;

-- Check current database
SELECT DATABASE();
```

### Example:
```sql
-- Create a school database
CREATE DATABASE school;

-- Switch to the school database
USE school;

-- Verify we're using the correct database
SELECT DATABASE();
```

### Best Practices:
- Use descriptive and meaningful names
- Follow consistent naming conventions (lowercase, underscores)
- Consider future scalability requirements
- Plan database structure before creation
- Avoid reserved keywords as database names

---

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
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    age INT,
    email VARCHAR(100) UNIQUE,
    enrollment_date DATE DEFAULT CURRENT_DATE
);
```

### Table Management Commands:
```sql
-- Show all tables in current database
SHOW TABLES;

-- Describe table structure
DESCRIBE table_name;
DESC table_name;  -- Shorthand

-- Show table creation statement
SHOW CREATE TABLE table_name;

-- Show detailed table information
SHOW TABLE STATUS LIKE 'table_name';

-- Drop table (permanently delete)
DROP TABLE table_name;
```

---

## SQL Datatypes

### Numeric Types:
- **INT** - Integer values (-2,147,483,648 to 2,147,483,647)
- **BIGINT** - Large integer values
- **DECIMAL(p,s)** - Fixed-point numbers (p=precision, s=scale)
- **FLOAT** - Single precision floating-point
- **DOUBLE** - Double precision floating-point
- **TINYINT** - Very small integers (-128 to 127)
- **SMALLINT** - Small integers (-32,768 to 32,767)

### String Types:
- **CHAR(n)** - Fixed-length string (padded with spaces)
- **VARCHAR(n)** - Variable-length string (up to n characters)
- **TEXT** - Large text data (up to 65,535 characters)
- **LONGTEXT** - Very large text data (up to 4GB)
- **ENUM** - String with predefined values

### Date and Time Types:
- **DATE** - Date values (YYYY-MM-DD)
- **TIME** - Time values (HH:MM:SS)
- **DATETIME** - Date and time combination
- **TIMESTAMP** - Timestamp values (auto-updates)
- **YEAR** - Year values (2 or 4 digit format)

### Other Types:
- **BOOLEAN** - True/False values (stored as TINYINT)
- **BLOB** - Binary large objects
- **JSON** - JSON data (MySQL 5.7+)

### Examples:
```sql
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2),
    description TEXT,
    is_active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## Types of SQL Commands

### DDL (Data Definition Language)
Commands that define and modify database structure:
- **CREATE** - Create database objects (tables, indexes, views)
- **ALTER** - Modify existing database objects
- **DROP** - Delete database objects
- **TRUNCATE** - Remove all records from table (keeps structure)

### DML (Data Manipulation Language)
Commands that manipulate data within tables:
- **SELECT** - Retrieve/query data
- **INSERT** - Add new records
- **UPDATE** - Modify existing records
- **DELETE** - Remove records

### DCL (Data Control Language)
Commands that control access and permissions:
- **GRANT** - Give permissions to users
- **REVOKE** - Remove permissions from users

### TCL (Transaction Control Language)
Commands that manage database transactions:
- **COMMIT** - Save transaction permanently
- **ROLLBACK** - Undo transaction changes
- **SAVEPOINT** - Set transaction savepoint
- **START TRANSACTION** - Begin transaction

---

## Database Related Queries

### Basic Database Operations:
```sql
-- Create database with character set
CREATE DATABASE company CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

-- Select/use database
USE company;

-- Show current database
SELECT DATABASE();

-- Show all databases
SHOW DATABASES;

-- Show databases with pattern
SHOW DATABASES LIKE 'comp%';

-- Drop database with confirmation
DROP DATABASE IF EXISTS company;
```

### Database Information Queries:
```sql
-- Show database size
SELECT 
    table_schema AS 'Database',
    ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) AS 'Size (MB)'
FROM information_schema.tables
WHERE table_schema NOT IN ('information_schema', 'mysql', 'performance_schema', 'sys')
GROUP BY table_schema;

-- Show database creation info
SELECT * FROM information_schema.schemata WHERE schema_name = 'your_database';
```

---

## Table Related Queries

### Basic Table Operations:
```sql
-- Create table with various constraints
CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    employee_code VARCHAR(10) UNIQUE NOT NULL,
    name VARCHAR(100) NOT NULL,
    department VARCHAR(50),
    salary DECIMAL(10,2) CHECK (salary > 0),
    hire_date DATE DEFAULT CURRENT_DATE,
    manager_id INT,
    FOREIGN KEY (manager_id) REFERENCES employees(id)
);

-- Show all tables
SHOW TABLES;

-- Show tables with pattern
SHOW TABLES LIKE 'emp%';

-- Describe table structure
DESCRIBE employees;
DESC employees;  -- Alternative syntax

-- Show detailed table information
SHOW TABLE STATUS LIKE 'employees';

-- Show table creation statement
SHOW CREATE TABLE employees;

-- Copy table structure
CREATE TABLE employees_backup LIKE employees;

-- Copy table with data
CREATE TABLE employees_backup AS SELECT * FROM employees;

-- Drop table safely
DROP TABLE IF EXISTS employees;
```

### Table Information Queries:
```sql
-- Get column information
SELECT 
    COLUMN_NAME,
    DATA_TYPE,
    IS_NULLABLE,
    COLUMN_DEFAULT
FROM information_schema.columns 
WHERE table_name = 'employees' 
    AND table_schema = 'your_database';

-- Get table size
SELECT 
    table_name AS 'Table',
    ROUND((data_length + index_length) / 1024 / 1024, 2) AS 'Size (MB)'
FROM information_schema.tables
WHERE table_schema = 'your_database'
    AND table_name = 'employees';
```

---

## SELECT Command

The SELECT statement is used to retrieve data from database tables. It's the most commonly used SQL command.

### Basic Syntax:
```sql
SELECT column1, column2, ...
FROM table_name;
```

### SELECT Variations:
```sql
-- Select all columns
SELECT * FROM students;

-- Select specific columns
SELECT name, age FROM students;

-- Select distinct values (remove duplicates)
SELECT DISTINCT department FROM employees;

-- Select with alias
SELECT name AS student_name, age AS student_age FROM students;

-- Select with calculations
SELECT name, salary, salary * 12 AS annual_salary FROM employees;

-- Select with string functions
SELECT UPPER(name) AS name_upper, LENGTH(name) AS name_length FROM students;

-- Select with conditional logic
SELECT name,
    CASE 
        WHEN age < 18 THEN 'Minor'
        WHEN age >= 18 AND age < 65 THEN 'Adult'
        ELSE 'Senior'
    END AS age_category
FROM students;
```

### Examples:
```sql
-- Basic selection
SELECT id, name, email FROM users;

-- Select with concatenation
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;

-- Select with mathematical operations
SELECT 
    product_name,
    price,
    price * 0.1 AS tax,
    price * 1.1 AS price_with_tax
FROM products;
```

---

## INSERT Command

The INSERT statement adds new records to a table.

### Basic Syntax:
```sql
-- Insert specific columns
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);

-- Insert all columns (match table structure)
INSERT INTO table_name
VALUES (value1, value2, value3, value4);
```

### INSERT Variations:
```sql
-- Insert single record
INSERT INTO students (name, age, email)
VALUES ('John Doe', 20, 'john@email.com');

-- Insert multiple records
INSERT INTO students (name, age, email)
VALUES 
    ('John Doe', 20, 'john@email.com'),
    ('Jane Smith', 22, 'jane@email.com'),
    ('Bob Johnson', 21, 'bob@email.com');

-- Insert with default values
INSERT INTO products (name, price)
VALUES ('New Product', 99.99);  -- Other columns get default values

-- Insert from another table
INSERT INTO archived_orders (customer_id, order_date, total)
SELECT customer_id, order_date, total 
FROM orders 
WHERE order_date < '2023-01-01';

-- Insert with subquery
INSERT INTO high_performers (employee_id, name)
SELECT id, name 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### INSERT Best Practices:
- Always specify column names for clarity
- Validate data before insertion
- Use transactions for multiple related inserts
- Handle duplicate key errors appropriately

---

## Keys

Keys are essential for maintaining data integrity and establishing relationships between tables.

### Primary Key
- **Purpose**: Uniquely identifies each record in a table
- **Characteristics**: Cannot contain NULL values, must be unique
- **Limitation**: Each table can have only one primary key
- **Can be**: Single column or composite (multiple columns)

```sql
-- Single column primary key
CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50)
);

-- Composite primary key
CREATE TABLE order_items (
    order_id INT,
    product_id INT,
    quantity INT,
    PRIMARY KEY (order_id, product_id)
);

-- Adding primary key to existing table
ALTER TABLE students ADD PRIMARY KEY (id);
```

### Foreign Key
- **Purpose**: Links two tables together, maintains referential integrity
- **Characteristics**: References primary key of another table
- **Benefits**: Prevents invalid data, maintains consistency

```sql
-- Foreign key during table creation
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

-- Adding foreign key to existing table
ALTER TABLE orders 
ADD FOREIGN KEY (customer_id) REFERENCES customers(id);

-- Named foreign key constraint
ALTER TABLE orders 
ADD CONSTRAINT fk_customer 
FOREIGN KEY (customer_id) REFERENCES customers(id);
```

### Unique Key
- **Purpose**: Ensures uniqueness of values in column(s)
- **Characteristics**: Can contain NULL values (but only one NULL per column)
- **Flexibility**: Multiple unique keys allowed per table

```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE,
    username VARCHAR(50) UNIQUE,
    phone VARCHAR(15) UNIQUE
);

-- Adding unique constraint
ALTER TABLE users ADD UNIQUE (email);
ALTER TABLE users ADD CONSTRAINT uk_username UNIQUE (username);
```

### Candidate Key
- **Definition**: Set of attributes that can uniquely identify records
- **Relationship**: Primary key is chosen from candidate keys
- **Example**: In students table, both student_id and email could be candidate keys

### Super Key
- **Definition**: Set of attributes that can uniquely identify records
- **Characteristics**: May contain additional attributes beyond candidate key
- **Example**: {student_id, name, email} is a super key if student_id alone is candidate key

---

## Constraints

Constraints enforce rules on data in tables to ensure data integrity and validity.

### NOT NULL Constraint
Ensures column cannot have empty/null values:
```sql
CREATE TABLE students (
    id INT NOT NULL,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL
);

-- Adding NOT NULL to existing column
ALTER TABLE students MODIFY name VARCHAR(50) NOT NULL;
```

### UNIQUE Constraint
Ensures all values in column are different:
```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE,
    username VARCHAR(50) UNIQUE
);

-- Adding unique constraint
ALTER TABLE users ADD UNIQUE (email);
ALTER TABLE users ADD CONSTRAINT uk_email UNIQUE (email);
```

### PRIMARY KEY Constraint
Combination of NOT NULL and UNIQUE, identifies each record uniquely:
```sql
CREATE TABLE products (
    id INT PRIMARY KEY AUTO_INCREMENT,
    product_code VARCHAR(20) PRIMARY KEY  -- Alternative approach
);

-- Composite primary key
CREATE TABLE order_items (
    order_id INT,
    product_id INT,
    PRIMARY KEY (order_id, product_id)
);
```

### FOREIGN KEY Constraint
Maintains referential integrity between tables:
```sql
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    product_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);

-- With referential actions
CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);
```

### CHECK Constraint
Ensures values meet specific conditions:
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    age INT CHECK (age >= 18 AND age <= 65),
    salary DECIMAL(10,2) CHECK (salary > 0),
    gender CHAR(1) CHECK (gender IN ('M', 'F', 'O'))
);

-- Adding check constraint
ALTER TABLE employees 
ADD CONSTRAINT chk_salary CHECK (salary > 0);
```

### DEFAULT Constraint
Provides default value when no value is specified:
```sql
CREATE TABLE products (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    status VARCHAR(20) DEFAULT 'active',
    created_date DATE DEFAULT CURRENT_DATE,
    price DECIMAL(10,2) DEFAULT 0.00
);

-- Adding default constraint
ALTER TABLE products 
ALTER COLUMN status SET DEFAULT 'active';
```

---

## SELECT Command in Detail

### Advanced SELECT Features:

#### Column Aliases
```sql
-- Using AS keyword
SELECT first_name AS 'First Name', last_name AS 'Last Name' FROM employees;

-- Without AS keyword
SELECT first_name 'First Name', last_name 'Last Name' FROM employees;

-- For calculations
SELECT name, salary, salary * 12 AS annual_salary FROM employees;
```

#### String Functions
```sql
-- Concatenation
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;
SELECT CONCAT('Mr. ', name) AS formal_name FROM customers;

-- String manipulation
SELECT 
    UPPER(name) AS name_upper,
    LOWER(email) AS email_lower,
    LENGTH(name) AS name_length,
    SUBSTRING(name, 1, 3) AS name_prefix
FROM users;
```

#### Mathematical Operations
```sql
SELECT 
    product_name,
    price,
    price * 0.18 AS tax,
    price * 1.18 AS total_price,
    ROUND(price * 1.18, 2) AS rounded_total
FROM products;
```

#### Conditional Logic
```sql
SELECT 
    name,
    age,
    CASE 
        WHEN age < 18 THEN 'Minor'
        WHEN age BETWEEN 18 AND 65 THEN 'Adult'
        ELSE 'Senior'
    END AS age_category,
    CASE 
        WHEN salary > 100000 THEN 'High'
        WHEN salary > 50000 THEN 'Medium'
        ELSE 'Low'
    END AS salary_grade
FROM employees;
```

#### Date Functions
```sql
SELECT 
    name,
    hire_date,
    YEAR(hire_date) AS hire_year,
    MONTH(hire_date) AS hire_month,
    DATEDIFF(CURRENT_DATE, hire_date) AS days_employed,
    DATE_ADD(hire_date, INTERVAL 1 YEAR) AS first_anniversary
FROM employees;
```

---

## WHERE Clause

The WHERE clause filters records based on specified conditions.

### Basic Syntax:
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

### Comparison Examples:
```sql
-- Equality
SELECT * FROM employees WHERE department = 'IT';

-- Inequality
SELECT * FROM products WHERE price != 0;
SELECT * FROM products WHERE price <> 0;  -- Alternative syntax

-- Numerical comparisons
SELECT * FROM employees WHERE salary > 50000;
SELECT * FROM employees WHERE age >= 25;
SELECT * FROM products WHERE price <= 100;
```

### Multiple Conditions:
```sql
-- AND operator
SELECT * FROM employees 
WHERE department = 'IT' AND salary > 60000;

-- OR operator
SELECT * FROM employees 
WHERE department = 'IT' OR department = 'HR';

-- NOT operator
SELECT * FROM employees 
WHERE NOT department = 'IT';

-- Complex combinations with parentheses
SELECT * FROM employees 
WHERE (department = 'IT' OR department = 'HR') 
    AND salary > 50000;
```

### Advanced WHERE Conditions:
```sql
-- NULL checks
SELECT * FROM customers WHERE phone IS NULL;
SELECT * FROM customers WHERE phone IS NOT NULL;

-- Empty string checks
SELECT * FROM customers WHERE email != '';
SELECT * FROM customers WHERE TRIM(name) != '';

-- Date conditions
SELECT * FROM orders WHERE order_date >= '2024-01-01';
SELECT * FROM employees WHERE hire_date BETWEEN '2020-01-01' AND '2023-12-31';
```

---

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
- **NOT** - Negates the condition

### Pattern Matching Operators:
```sql
-- LIKE operator with wildcards
SELECT * FROM employees WHERE name LIKE 'J%';      -- Starts with 'J'
SELECT * FROM employees WHERE name LIKE '%son';    -- Ends with 'son'
SELECT * FROM employees WHERE name LIKE '%an%';    -- Contains 'an'
SELECT * FROM employees WHERE name LIKE 'J_hn';    -- 'J', any char, 'hn'

-- REGEXP for complex patterns
SELECT * FROM employees WHERE name REGEXP '^[A-M]';  -- Starts with A-M
SELECT * FROM products WHERE code REGEXP '[0-9]{3}'; -- Contains 3 digits
```

### Range and List Operators:
```sql
-- BETWEEN operator
SELECT * FROM products WHERE price BETWEEN 100 AND 500;
SELECT * FROM employees WHERE hire_date BETWEEN '2020-01-01' AND '2023-12-31';

-- IN operator
SELECT * FROM employees WHERE department IN ('IT', 'HR', 'Finance');
SELECT * FROM products WHERE category_id IN (1, 3, 5, 7);

-- NOT IN operator
SELECT * FROM employees WHERE department NOT IN ('IT', 'HR');
```

### NULL Handling Operators:
```sql
-- IS NULL / IS NOT NULL
SELECT * FROM customers WHERE phone IS NULL;
SELECT * FROM orders WHERE shipped_date IS NOT NULL;

-- COALESCE (return first non-null value)
SELECT name, COALESCE(phone, email, 'No contact') AS contact_info
FROM customers;

-- IFNULL (MySQL specific)
SELECT name, IFNULL(phone, 'No phone') AS phone_display
FROM customers;
```

---

## LIMIT Clause

The LIMIT clause restricts the number of records returned by a query.

### Basic Syntax:
```sql
SELECT column1, column2
FROM table_name
LIMIT number;

-- With offset (skip rows)
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

-- Get records 11-15
SELECT * FROM employees LIMIT 10, 5;

-- Pagination example (page 3, 10 items per page)
SELECT * FROM products LIMIT 20, 10;  -- Skip 20, get 10
```

### Practical Use Cases:
```sql
-- Top performers
SELECT name, salary FROM employees 
ORDER BY salary DESC 
LIMIT 10;

-- Recent orders
SELECT * FROM orders 
ORDER BY order_date DESC 
LIMIT 20;

-- Sample data for testing
SELECT * FROM large_table LIMIT 100;

-- Pagination with calculation
-- Page number: 3, Items per page: 10
-- Offset = (page - 1) * items_per_page = (3-1) * 10 = 20
SELECT * FROM products LIMIT 20, 10;
```

---

## ORDER BY Clause

The ORDER BY clause sorts the result set by one or more columns.

### Basic Syntax:
```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 ASC|DESC, column2 ASC|DESC;
```

### Sorting Options:
- **ASC** - Ascending order (default)
- **DESC** - Descending order

### Examples:
```sql
-- Sort by single column
SELECT * FROM employees ORDER BY salary DESC;
SELECT * FROM products ORDER BY name ASC;  -- ASC is optional

-- Sort by multiple columns
SELECT * FROM employees 
ORDER BY department ASC, salary DESC;

-- Sort by column position (not recommended)
SELECT name, salary FROM employees ORDER BY 2 DESC;  -- Sort by salary

-- Sort by calculated column
SELECT name, salary, salary * 12 AS annual_salary 
FROM employees 
ORDER BY annual_salary DESC;

-- Sort by expression
SELECT product_name, price 
FROM products 
ORDER BY price * quantity DESC;
```

### Advanced Sorting:
```sql
-- Custom sort order
SELECT * FROM employees 
ORDER BY 
    CASE department
        WHEN 'CEO' THEN 1
        WHEN 'Management' THEN 2
        WHEN 'IT' THEN 3
        ELSE 4
    END,
    salary DESC;

-- Sort with NULL handling
SELECT name, phone FROM customers 
ORDER BY phone IS NULL, phone;  -- NULLs last

-- Sort by string length
SELECT name FROM employees 
ORDER BY LENGTH(name) DESC;

-- Random order
SELECT * FROM products ORDER BY RAND() LIMIT 10;
```

---

## Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single value.

### Common Aggregate Functions:

#### COUNT Function
```sql
-- Count all rows
SELECT COUNT(*) FROM employees;

-- Count non-null values
SELECT COUNT(email) FROM employees;

-- Count distinct values
SELECT COUNT(DISTINCT department) FROM employees;

-- Count with condition
SELECT COUNT(*) FROM employees WHERE salary > 50000;
```

#### SUM Function
```sql
-- Sum of all salaries
SELECT SUM(salary) FROM employees;

-- Sum with condition
SELECT SUM(salary) FROM employees WHERE department = 'IT';

-- Sum of calculated values
SELECT SUM(price * quantity) AS total_revenue FROM order_items;
```

#### AVG Function
```sql
-- Average salary
SELECT AVG(salary) FROM employees;

-- Average with rounding
SELECT ROUND(AVG(salary), 2) AS avg_salary FROM employees;

-- Average by group
SELECT department, AVG(salary) FROM employees GROUP BY department;
```

#### MAX and MIN Functions
```sql
-- Highest and lowest salary
SELECT MAX(salary), MIN(salary) FROM employees;

-- Latest and earliest dates
SELECT MAX(order_date) AS latest_order, MIN(order_date) AS first_order 
FROM orders;

-- String MAX/MIN (alphabetical)
SELECT MAX(name) AS last_alphabetically, MIN(name) AS first_alphabetically 
FROM employees;
```

### Multiple Aggregates:
```sql
SELECT 
    COUNT(*) as total_employees,
    COUNT(DISTINCT department) as departments,
    AVG(salary) as avg_salary,
    MAX(salary) as max_salary,
    MIN(salary) as min_salary,
    SUM(salary) as total_payroll
FROM employees;
```

### Aggregate with Conditions:
```sql
-- Conditional aggregation
SELECT 
    COUNT(CASE WHEN salary > 50000 THEN 1 END) as high_earners,
    COUNT(CASE WHEN salary <= 50000 THEN 1 END) as regular_earners,
    AVG(CASE WHEN department = 'IT' THEN salary END) as avg_it_salary
FROM employees;
```

---

## GROUP BY Clause

The GROUP BY clause groups rows with the same values and allows aggregate functions to be applied to each group.

### Basic Syntax:
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1;
```

### Simple Grouping:
```sql
-- Count employees by department
SELECT department, COUNT(*) as employee_count
FROM employees
GROUP BY department;

-- Average salary by department
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department;

-- Sum of sales by product
SELECT product_id, SUM(quantity) as total_sold
FROM order_items
GROUP BY product_id;
```

### Multiple Column Grouping:
```sql
-- Group by department and job title
SELECT department, job_title, COUNT(*) as count, AVG(salary) as avg_salary
FROM employees
GROUP BY department, job_title;

-- Group by year and month
SELECT 
    YEAR(order_date) as order_year,
    MONTH(order_date) as order_month,
    COUNT(*) as order_count,
    SUM(total_amount) as monthly_revenue
FROM orders
GROUP BY YEAR(order_date), MONTH(order_date);
```

### Group by Expression:
```sql
-- Group by calculated values
SELECT 
    CASE 
        WHEN age < 30 THEN 'Young'
        WHEN age BETWEEN 30 AND 50 THEN 'Middle-aged'
        ELSE 'Senior'
    END as age_group,
    COUNT(*) as count
FROM employees
GROUP BY 
    CASE 
        WHEN age < 30 THEN 'Young'
        WHEN age BETWEEN 30 AND 50 THEN 'Middle-aged'
        ELSE 'Senior'
    END;

-- Group by date parts
SELECT 
    YEAR(hire_date) as hire_year,
    COUNT(*) as employees_hired
FROM employees
GROUP BY YEAR(hire_date)
ORDER BY hire_year;
```

### GROUP BY Rules:
- All non-aggregate columns in SELECT must be in GROUP BY
- Aggregate functions operate on each group separately
- NULL values are grouped together
- GROUP BY comes after WHERE but before ORDER BY

---

## HAVING Clause

The HAVING clause filters groups created by GROUP BY. It's like WHERE but for groups instead of individual rows.

### Key Differences: WHERE vs HAVING
- **WHERE** - Filters individual rows before grouping
- **HAVING** - Filters groups after grouping
- **WHERE** - Cannot use aggregate functions
- **HAVING** - Can use aggregate functions

### Basic Syntax:
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
WHERE condition                    -- Filter rows first
GROUP BY column1
HAVING aggregate_condition;        -- Filter groups after
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

-- Products sold more than 100 times
SELECT product_id, SUM(quantity) as total_sold
FROM order_items
GROUP BY product_id
HAVING SUM(quantity) > 100;
```

### Combined WHERE and HAVING:
```sql
-- Departments with avg salary > 50000, considering only recent hires
SELECT department, AVG(salary) as avg_salary, COUNT(*) as emp_count
FROM employees
WHERE hire_date > '2020-01-01'    -- Filter individual rows first
GROUP BY department
HAVING AVG(salary) > 50000        -- Filter groups after
    AND COUNT(*) >= 3;            -- Multiple HAVING conditions

-- Monthly sales > 10000 for active products only
SELECT 
    YEAR(order_date) as year,
    MONTH(order_date) as month,
    SUM(total_amount) as monthly_sales
FROM orders o
JOIN products p ON o.product_id = p.id
WHERE p.status = 'active'         -- Filter for active products
GROUP BY YEAR(order_date), MONTH(order_date)
HAVING SUM(total_amount) > 10000  -- Filter months with high sales
ORDER BY year, month;
```

### Complex HAVING Conditions:
```sql
-- Multiple aggregate conditions
SELECT 
    department,
    COUNT(*) as emp_count,
    AVG(salary) as avg_salary,
    MAX(salary) as max_salary
FROM employees
GROUP BY department
HAVING COUNT(*) > 5 
    AND AVG(salary) > 55000 
    AND MAX(salary) < 150000;

-- HAVING with subqueries
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > (
    SELECT AVG(salary) FROM employees
);
```

---

## General Order of Commands

SQL commands must be written in a specific logical order. Here's the standard sequence:

### Standard SQL Query Order:
```sql
SELECT          -- 1. Specify columns to retrieve
FROM            -- 2. Specify source tables
WHERE           -- 3. Filter individual rows
GROUP BY        -- 4. Group rows for aggregation
HAVING          -- 5. Filter groups
ORDER BY        -- 6. Sort the final results
LIMIT           -- 7. Limit number of results
```

### Execution Order (How SQL Engine Processes):
The SQL engine processes clauses in a different order than written:
1. **FROM** - Identify source tables
2. **WHERE** - Filter rows
3. **GROUP BY** - Create groups
4. **HAVING** - Filter groups
5. **SELECT** - Choose columns and apply functions
6. **ORDER BY** - Sort results
7. **LIMIT** - Restrict output

### Complete Example:
```sql
SELECT 
    department,
    COUNT(*) as employee_count,
    AVG(salary) as avg_salary,
    MAX(salary) as max_salary
FROM employees
WHERE hire_date > '2020-01-01'
    AND status = 'active'
GROUP BY department
HAVING COUNT(*) > 3
    AND AVG(salary) > 50000
ORDER BY avg_salary DESC, employee_count DESC
LIMIT 10;
```

### Why Order Matters:
```sql
-- This works - WHERE before GROUP BY
SELECT department, COUNT(*) 
FROM employees 
WHERE salary > 50000 
GROUP BY department;

-- This would cause error - GROUP BY before WHERE
-- SELECT department, COUNT(*) 
-- FROM employees 
-- GROUP BY department
-- WHERE salary > 50000;  -- ERROR!

-- Use HAVING for group filtering instead
SELECT department, COUNT(*) 
FROM employees 
GROUP BY department
HAVING COUNT(*) > 5;
```

---

## UPDATE Command

The UPDATE command modifies existing records in a table.

### Basic Syntax:
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Simple Updates:
```sql
-- Update single record
UPDATE employees
SET salary = 75000
WHERE id = 1;

-- Update multiple columns
UPDATE employees
SET salary = 80000, department = 'Senior IT', last_updated = NOW()
WHERE id = 1;

-- Update multiple records
UPDATE products
SET price = price * 1.1
WHERE category = 'Electronics';
```

### Advanced Updates:
```sql
-- Update with calculations
UPDATE employees
SET salary = salary * 1.15,
    bonus = salary * 0.05
WHERE performance_rating = 'Excellent';

-- Update with CASE statement
UPDATE employees
SET salary = 
    CASE 
        WHEN department = 'IT' THEN salary * 1.2
        WHEN department = 'Sales' THEN salary * 1.15
        WHEN department = 'HR' THEN salary * 1.1
        ELSE salary * 1.05
    END
WHERE hire_date < '2020-01-01';

-- Update with subquery
UPDATE employees
SET salary = (
    SELECT AVG(salary) * 1.1 
    FROM employees e2 
    WHERE e2.department = employees.department
)
WHERE performance_rating = 'Good';

-- Update using JOIN (MySQL syntax)
UPDATE employees e
JOIN departments d ON e.department_id = d.id
SET e.salary = e.salary * d.salary_multiplier;
```

### Conditional Updates:
```sql
-- Update only if condition is met
UPDATE products 
SET discount = 0.15 
WHERE price > 1000 AND stock_quantity > 50;

-- Update with current timestamp
UPDATE orders 
SET status = 'shipped', shipped_date = NOW() 
WHERE status = 'processing' AND order_date < DATE_SUB(NOW(), INTERVAL 2 DAY);

-- Increment/decrement values
UPDATE products 
SET stock_quantity = stock_quantity - 1 
WHERE id = 1 AND stock_quantity > 0;
```

### Safety Best Practices:
```sql
-- Always test with SELECT first
SELECT * FROM employees WHERE id = 1;
-- Then run the update
UPDATE employees SET salary = 75000 WHERE id = 1;

-- Use transactions for critical updates
START TRANSACTION;
UPDATE accounts SET balance = balance - 1000 WHERE account_id = 'A001';
UPDATE accounts SET balance = balance + 1000 WHERE account_id = 'A002';
-- Check if everything looks correct
SELECT * FROM accounts WHERE account_id IN ('A001', 'A002');
COMMIT;  -- or ROLLBACK if something's wrong

-- Update with LIMIT for safety
UPDATE products SET price = price * 1.1 
WHERE category = 'Electronics' 
LIMIT 10;
```

---

## DELETE Command

The DELETE command removes records from a table.

### Basic Syntax:
```sql
DELETE FROM table_name
WHERE condition;
```

### Simple Deletions:
```sql
-- Delete specific record
DELETE FROM employees WHERE id = 1;

-- Delete multiple records with condition
DELETE FROM products WHERE price < 10;

-- Delete based on date
DELETE FROM logs WHERE created_date < '2024-01-01';

-- Delete all records (keeps table structure)
DELETE FROM temp_table;
```

### Advanced Deletions:
```sql
-- Delete with subquery
DELETE FROM orders
WHERE customer_id IN (
    SELECT id FROM customers WHERE status = 'inactive'
);

-- Delete with JOIN (MySQL syntax)
DELETE e FROM employees e
JOIN departments d ON e.department_id = d.id
WHERE d.name = 'Discontinued Department';

-- Delete duplicates (keep one copy)
DELETE e1 FROM employees e1
JOIN employees e2 
WHERE e1.id > e2.id 
    AND e1.email = e2.email;

-- Delete old records
DELETE FROM audit_logs 
WHERE created_date < DATE_SUB(NOW(), INTERVAL 1 YEAR);
```

### DELETE with LIMIT:
```sql
-- Delete limited number of records
DELETE FROM error_logs 
WHERE severity = 'low' 
ORDER BY created_date ASC 
LIMIT 1000;

-- Delete in batches
DELETE FROM large_table 
WHERE status = 'processed' 
LIMIT 500;
```

### DELETE vs TRUNCATE vs DROP:

| Command | Purpose | Speed | WHERE Clause | Rollback | Auto-increment Reset |
|---------|---------|-------|--------------|----------|---------------------|
| DELETE | Remove specific rows | Slower | Yes | Yes | No |
| TRUNCATE | Remove all rows | Faster | No | No (usually) | Yes |
| DROP | Remove entire table | Fastest | No | No | N/A |

```sql
-- DELETE - Selective, slower, can rollback
DELETE FROM employees WHERE department = 'IT';

-- TRUNCATE - All rows, faster, cannot rollback
TRUNCATE TABLE temp_data;

-- DROP - Entire table structure, fastest
DROP TABLE old_table;
```

---

## Revisiting Foreign Keys

Foreign keys are crucial for maintaining referential integrity between related tables.

### Creating Foreign Keys:
```sql
-- During table creation
CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    product_id INT NOT NULL,
    order_date DATE DEFAULT CURRENT_DATE,
    quantity INT DEFAULT 1,
    
    FOREIGN KEY (customer_id) REFERENCES customers(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);

-- Named foreign key constraints
CREATE TABLE order_items (
    id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    product_id INT,
    
    CONSTRAINT fk_order_items_order 
        FOREIGN KEY (order_id) REFERENCES orders(id),
    CONSTRAINT fk_order_items_product 
        FOREIGN KEY (product_id) REFERENCES products(id)
);
```

### Adding Foreign Keys to Existing Tables:
```sql
-- Add foreign key constraint
ALTER TABLE orders
ADD FOREIGN KEY (customer_id) REFERENCES customers(id);

-- Add named foreign key constraint
ALTER TABLE orders
ADD CONSTRAINT fk_orders_customer
FOREIGN KEY (customer_id) REFERENCES customers(id);

-- Add multiple foreign keys
ALTER TABLE order_items
ADD CONSTRAINT fk_items_order 
    FOREIGN KEY (order_id) REFERENCES orders(id),
ADD CONSTRAINT fk_items_product 
    FOREIGN KEY (product_id) REFERENCES products(id);
```

### Foreign Key Benefits:
- **Data Integrity**: Prevents invalid references
- **Consistency**: Ensures related data remains consistent
- **Documentation**: Makes relationships explicit
- **Query Optimization**: Helps query planner optimize joins

### Foreign Key Restrictions:
```sql
-- This will fail if customer_id 999 doesn't exist
INSERT INTO orders (customer_id, product_id) 
VALUES (999, 1);  -- ERROR: Foreign key constraint violation

-- This will fail if there are related orders
DELETE FROM customers WHERE id = 1;  -- ERROR: Cannot delete referenced row
```

### Managing Foreign Key Constraints:
```sql
-- Show foreign key constraints
SELECT 
    CONSTRAINT_NAME,
    TABLE_NAME,
    COLUMN_NAME,
    REFERENCED_TABLE_NAME,
    REFERENCED_COLUMN_NAME
FROM information_schema.KEY_COLUMN_USAGE
WHERE REFERENCED_TABLE_NAME IS NOT NULL
    AND TABLE_SCHEMA = 'your_database';

-- Drop foreign key constraint
ALTER TABLE orders DROP FOREIGN KEY fk_orders_customer;

-- Disable/enable foreign key checks (use carefully!)
SET FOREIGN_KEY_CHECKS = 0;  -- Disable
-- Perform operations that might violate constraints
SET FOREIGN_KEY_CHECKS = 1;  -- Re-enable
```

---

## Cascading Foreign Keys

Cascading actions automatically perform operations on child records when parent records are modified or deleted.

### Types of Referential Actions:

#### ON DELETE Actions:
- **RESTRICT** - Prevent deletion of parent if children exist (default)
- **CASCADE** - Delete children when parent is deleted
- **SET NULL** - Set foreign key to NULL when parent is deleted
- **SET DEFAULT** - Set foreign key to default value when parent is deleted
- **NO ACTION** - Same as RESTRICT

#### ON UPDATE Actions:
- **RESTRICT** - Prevent update of parent key if children exist
- **CASCADE** - Update children when parent key is updated
- **SET NULL** - Set foreign key to NULL when parent key is updated
- **SET DEFAULT** - Set foreign key to default value when parent key is updated

### CASCADE Examples:
```sql
-- Delete cascades to related records
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE
);

CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    order_date DATE DEFAULT CURRENT_DATE,
    
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);

-- When customer is deleted, all their orders are automatically deleted
DELETE FROM customers WHERE id = 1;  -- Also deletes related orders
```

### SET NULL Example:
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    manager_id INT,
    
    FOREIGN KEY (manager_id) REFERENCES employees(id)
        ON DELETE SET NULL
        ON UPDATE CASCADE
);

-- When manager is deleted, manager_id becomes NULL for subordinates
DELETE FROM employees WHERE id = 5;  -- Manager deleted, subordinates' manager_id = NULL
```

### Complex Cascading Example:
```sql
-- Customer -> Orders -> Order Items hierarchy
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL
);

CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    order_date DATE DEFAULT CURRENT_DATE,
    
    FOREIGN KEY (customer_id) REFERENCES customers(id)
        ON DELETE CASCADE
);

CREATE TABLE order_items (
    id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT NOT NULL,
    product_id INT NOT NULL,
    quantity INT DEFAULT 1,
    
    FOREIGN KEY (order_id) REFERENCES orders(id)
        ON DELETE CASCADE,
    FOREIGN KEY (product_id) REFERENCES products(id)
        ON DELETE RESTRICT  -- Prevent product deletion if used in orders
);

-- Deleting customer cascades through: customer -> orders -> order_items
DELETE FROM customers WHERE id = 1;
```

### Practical Considerations:
```sql
-- Audit table - keep records even if parent is deleted
CREATE TABLE audit_logs (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    action VARCHAR(100),
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    
    FOREIGN KEY (user_id) REFERENCES users(id)
        ON DELETE SET NULL  -- Keep audit record, but user_id becomes NULL
);

-- Soft delete pattern - avoid cascading deletes
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    is_deleted BOOLEAN DEFAULT FALSE,
    deleted_at DATETIME NULL
);

-- Instead of DELETE, use UPDATE
UPDATE users SET is_deleted = TRUE, deleted_at = NOW() WHERE id = 1;
```

---

## ALTER Command

The ALTER command modifies existing database objects like tables, columns, and constraints.

### ALTER TABLE Operations:

#### Adding Columns:
```sql
-- Add single column
ALTER TABLE employees
ADD COLUMN phone VARCHAR(15);

-- Add column with constraints
ALTER TABLE employees
ADD COLUMN hire_date DATE NOT NULL DEFAULT CURRENT_DATE;

-- Add multiple columns
ALTER TABLE employees
ADD COLUMN phone VARCHAR(15),
ADD COLUMN address TEXT,
ADD COLUMN is_active BOOLEAN DEFAULT TRUE;

-- Add column at specific position
ALTER TABLE employees
ADD COLUMN middle_name VARCHAR(50) AFTER first_name;

-- Add column as first column
ALTER TABLE employees
ADD COLUMN employee_code VARCHAR(10) FIRST;
```

#### Dropping Columns:
```sql
-- Drop single column
ALTER TABLE employees
DROP COLUMN phone;

-- Drop multiple columns
ALTER TABLE employees
DROP COLUMN phone,
DROP COLUMN fax;
```

#### Constraint Management:
```sql
-- Add primary key
ALTER TABLE employees
ADD PRIMARY KEY (id);

-- Add unique constraint
ALTER TABLE employees
ADD CONSTRAINT uk_email UNIQUE (email);

-- Add foreign key
ALTER TABLE orders
ADD CONSTRAINT fk_customer
FOREIGN KEY (customer_id) REFERENCES customers(id);

-- Add check constraint
ALTER TABLE employees
ADD CONSTRAINT chk_salary CHECK (salary > 0);

-- Drop constraints
ALTER TABLE employees
DROP CONSTRAINT uk_email;

ALTER TABLE employees
DROP FOREIGN KEY fk_department;

-- Drop primary key
ALTER TABLE employees
DROP PRIMARY KEY;
```

#### Index Management:
```sql
-- Add index
ALTER TABLE employees
ADD INDEX idx_department (department);

-- Add unique index
ALTER TABLE employees
ADD UNIQUE INDEX idx_email (email);

-- Add composite index
ALTER TABLE employees
ADD INDEX idx_dept_salary (department, salary);

-- Drop index
ALTER TABLE employees
DROP INDEX idx_department;
```

### Renaming Operations:
```sql
-- Rename table
ALTER TABLE old_table_name 
RENAME TO new_table_name;

-- Alternative syntax
RENAME TABLE old_table_name TO new_table_name;

-- Rename multiple tables
RENAME TABLE 
    old_table1 TO new_table1,
    old_table2 TO new_table2;
```

### Table Options:
```sql
-- Change table engine
ALTER TABLE employees ENGINE = InnoDB;

-- Change table charset
ALTER TABLE employees 
CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

-- Add table comment
ALTER TABLE employees COMMENT = 'Employee master data';

-- Change auto_increment value
ALTER TABLE employees AUTO_INCREMENT = 1000;
```

---

## CHANGE and MODIFY Commands

Both CHANGE and MODIFY are used to alter column definitions, but they have different capabilities.

### MODIFY Command
Changes column definition without renaming:

```sql
-- Change column data type
ALTER TABLE employees
MODIFY COLUMN salary DECIMAL(12,2);

-- Add constraints to existing column
ALTER TABLE employees
MODIFY COLUMN email VARCHAR(100) NOT NULL UNIQUE;

-- Change multiple column properties
ALTER TABLE employees
MODIFY COLUMN name VARCHAR(150) NOT NULL,
MODIFY COLUMN age INT DEFAULT 0;

-- Remove constraints (make nullable)
ALTER TABLE employees
MODIFY COLUMN phone VARCHAR(15) NULL;
```

### CHANGE Command
Can rename column and change its definition:

```sql
-- Rename column and change type
ALTER TABLE employees
CHANGE COLUMN old_column_name new_column_name VARCHAR(100);

-- Rename column keeping same type
ALTER TABLE employees
CHANGE COLUMN first_name fname VARCHAR(50);

-- Change column name and add constraints
ALTER TABLE employees
CHANGE COLUMN salary monthly_salary DECIMAL(10,2) NOT NULL DEFAULT 0;
```

### Practical Examples:

#### Data Type Changes:
```sql
-- Expand varchar size
ALTER TABLE products
MODIFY COLUMN description VARCHAR(500);

-- Change number precision
ALTER TABLE financial_data
MODIFY COLUMN amount DECIMAL(15,4);

-- Convert to different data type
ALTER TABLE events
MODIFY COLUMN event_date DATETIME;
```

#### Adding/Removing Constraints:
```sql
-- Add NOT NULL constraint
ALTER TABLE customers
MODIFY COLUMN email VARCHAR(100) NOT NULL;

-- Remove NOT NULL constraint
ALTER TABLE customers
MODIFY COLUMN phone VARCHAR(15);

-- Add default value
ALTER TABLE products
MODIFY COLUMN status VARCHAR(20) DEFAULT 'active';
```

#### Column Renaming with CHANGE:
```sql
-- Standardize column names
ALTER TABLE users
CHANGE COLUMN usr_name username VARCHAR(50),
CHANGE COLUMN usr_mail email VARCHAR(100),
CHANGE COLUMN usr_phone phone VARCHAR(15);

-- Fix naming conventions
ALTER TABLE products
CHANGE COLUMN productName product_name VARCHAR(100),
CHANGE COLUMN productPrice price DECIMAL(10,2);
```

### MODIFY vs CHANGE Comparison:

| Feature | MODIFY | CHANGE |
|---------|--------|--------|
| Rename column | No | Yes |
| Change data type | Yes | Yes |
| Change constraints | Yes | Yes |
| Must specify column name | Once | Twice (old and new) |
| Syntax complexity | Simpler | More complex |

### Best Practices:
```sql
-- Always backup data before major changes
CREATE TABLE employees_backup AS SELECT * FROM employees;

-- Check data compatibility before type changes
SELECT COUNT(*) FROM employees WHERE LENGTH(name) > 50;
-- Then change if safe
ALTER TABLE employees MODIFY COLUMN name VARCHAR(50);

-- Use transactions for multiple changes
START TRANSACTION;
ALTER TABLE employees MODIFY COLUMN salary DECIMAL(12,2);
ALTER TABLE employees CHANGE COLUMN dept department VARCHAR(50);
-- Verify changes
DESCRIBE employees;
COMMIT;
```

---

## TRUNCATE Command

The TRUNCATE command removes all records from a table while preserving the table structure.

### Basic Syntax:
```sql
TRUNCATE TABLE table_name;
```

### Key Characteristics:
- Removes all rows from table
- Faster than DELETE for removing all records
- Resets AUTO_INCREMENT counter to 1
- Cannot use WHERE clause
- Cannot be rolled back in most databases
- Maintains table structure, indexes, and constraints

### Examples:
```sql
-- Remove all data from table
TRUNCATE TABLE temp_data;

-- Clear session data
TRUNCATE TABLE user_sessions;

-- Reset audit logs
TRUNCATE TABLE audit_logs;
```

### TRUNCATE vs DELETE vs DROP:

#### Performance Comparison:
```sql
-- TRUNCATE - Fastest for removing all rows
TRUNCATE TABLE large_table;

-- DELETE - Slower, but can be selective
DELETE FROM large_table;  -- Removes all rows
DELETE FROM large_table WHERE condition;  -- Removes specific rows

-- DROP - Removes entire table
DROP TABLE large_table;
```

#### Feature Comparison:

| Feature | TRUNCATE | DELETE | DROP |
|---------|----------|--------|------|
| Speed | Fast | Slow | Fastest |
| WHERE clause | No | Yes | No |
| Rollback | Limited | Yes | No |
| Structure kept | Yes | Yes | No |
| Auto-increment reset | Yes | No | N/A |
| Triggers fired | No | Yes | No |
| Foreign key checks | May fail | Yes | May fail |

### When to Use Each:

#### Use TRUNCATE when:
```sql
-- Clearing temporary/staging tables
TRUNCATE TABLE staging_data;

-- Resetting test data
TRUNCATE TABLE test_users;

-- Clearing cache tables
TRUNCATE TABLE cache_entries;
```

#### Use DELETE when:
```sql
-- Removing specific records
DELETE FROM users WHERE last_login < '2023-01-01';

-- Conditional removal
DELETE FROM products WHERE status = 'discontinued';

-- When you need transaction rollback capability
START TRANSACTION;
DELETE FROM orders WHERE order_date < '2024-01-01';
-- Can ROLLBACK if needed
COMMIT;
```

#### Use DROP when:
```sql
-- Removing table completely
DROP TABLE obsolete_table;

-- Cleaning up temporary tables
DROP TABLE temp_calculations;
```

### Foreign Key Considerations:
```sql
-- This may fail if other tables reference this table
TRUNCATE TABLE customers;  -- Error if orders table references customers

-- Solutions:
-- 1. Disable foreign key checks temporarily
SET FOREIGN_KEY_CHECKS = 0;
TRUNCATE TABLE customers;
SET FOREIGN_KEY_CHECKS = 1;

-- 2. Truncate in correct order (children first)
TRUNCATE TABLE order_items;  -- Child table first
TRUNCATE TABLE orders;       -- Parent table second
TRUNCATE TABLE customers;    -- Root table last

-- 3. Use DELETE instead for foreign key constrained tables
DELETE FROM customers;
```

---

## JOINS in SQL

JOINs combine rows from two or more tables based on related columns between them.

### Types of JOINs:

#### INNER JOIN
Returns records that have matching values in both tables:

```sql
-- Basic syntax
SELECT columns
FROM table1
INNER JOIN table2 ON table1.column = table2.column;

-- Example
SELECT 
    e.name AS employee_name,
    d.department_name
FROM employees e
INNER JOIN departments d ON e.department_id = d.id;

-- Multiple tables
SELECT 
    c.name AS customer_name,
    o.order_date,
    p.product_name,
    oi.quantity
FROM customers c
INNER JOIN orders o ON c.id = o.customer_id
INNER JOIN order_items oi ON o.id = oi.order_id
INNER JOIN products p ON oi.product_id = p.id;
```

#### LEFT JOIN (LEFT OUTER JOIN)
Returns all records from the left table and matched records from the right table:

```sql
-- Get all customers and their orders (including customers with no orders)
SELECT 
    c.name AS customer_name,
    o.order_date,
    o.total_amount
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id;

-- Find customers with no orders
SELECT c.name
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
WHERE o.customer_id IS NULL;

-- Employee and manager relationship
SELECT 
    e.name AS employee_name,
    m.name AS manager_name
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.id;
```

#### RIGHT JOIN (RIGHT OUTER JOIN)
Returns all records from the right table and matched records from the left table:

```sql
-- Get all departments and their employees (including empty departments)
SELECT 
    d.department_name,
    e.name AS employee_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.id;

-- Find departments with no employees
SELECT d.department_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.id
WHERE e.department_id IS NULL;
```

#### FULL OUTER JOIN
Returns all records when there's a match in either left or right table:

```sql
-- MySQL doesn't support FULL OUTER JOIN directly, use UNION
SELECT 
    c.name AS customer_name,
    o.order_date
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id

UNION

SELECT 
    c.name AS customer_name,
    o.order_date
FROM customers c
RIGHT JOIN orders o ON c.id = o.customer_id
WHERE c.id IS NULL;
```

#### CROSS JOIN
Returns the Cartesian product of both tables (every row from first table with every row from second table):

```sql
-- Generate all possible combinations
SELECT 
    c.color,
    s.size
FROM colors c
CROSS JOIN sizes s;

-- Useful for creating test data or combination tables
SELECT 
    u.username,
    p.permission_name
FROM users u
CROSS JOIN permissions p;
```

#### SELF JOIN
A table joined with itself:

```sql
-- Employee hierarchy - find employees and their managers
SELECT 
    e1.name AS employee,
    e2.name AS manager
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.id;

-- Find employees in the same department
SELECT 
    e1.name AS employee1,
    e2.name AS employee2,
    e1.department
FROM employees e1
JOIN employees e2 ON e1.department = e2.department
WHERE e1.id < e2.id;  -- Avoid duplicate pairs

-- Find employees earning more than their managers
SELECT 
    e.name AS employee,
    e.salary AS emp_salary,
    m.name AS manager,
    m.salary AS mgr_salary
FROM employees e
JOIN employees m ON e.manager_id = m.id
WHERE e.salary > m.salary;
```

### Advanced JOIN Examples:

#### Multiple JOINs:
```sql
-- Complex business query
SELECT 
    c.name AS customer_name,
    c.email,
    o.order_date,
    o.status AS order_status,
    p.product_name,
    p.price,
    oi.quantity,
    (p.price * oi.quantity) AS line_total,
    cat.category_name
FROM customers c
JOIN orders o ON c.id = o.customer_id
JOIN order_items oi ON o.id = oi.order_id
JOIN products p ON oi.product_id = p.id
JOIN categories cat ON p.category_id = cat.id
WHERE o.order_date >= '2024-01-01'
ORDER BY c.name, o.order_date;
```

#### JOINs with Aggregations:
```sql
-- Customer order summary
SELECT 
    c.name AS customer_name,
    COUNT(o.id) AS total_orders,
    SUM(o.total_amount) AS total_spent,
    AVG(o.total_amount) AS avg_order_value,
    MAX(o.order_date) AS last_order_date
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
GROUP BY c.id, c.name
ORDER BY total_spent DESC;

-- Product sales by category
SELECT 
    cat.category_name,
    COUNT(DISTINCT p.id) AS products_in_category,
    SUM(oi.quantity) AS total_quantity_sold,
    SUM(oi.quantity * p.price) AS total_revenue
FROM categories cat
LEFT JOIN products p ON cat.id = p.category_id
LEFT JOIN order_items oi ON p.id = oi.product_id
GROUP BY cat.id, cat.category_name
ORDER BY total_revenue DESC;
```

#### Conditional JOINs:
```sql
-- JOIN with additional conditions
SELECT 
    e.name,
    e.salary,
    b.bonus_amount
FROM employees e
LEFT JOIN bonuses b ON e.id = b.employee_id 
    AND b.year = 2024 
    AND b.status = 'approved';

-- Complex join conditions
SELECT 
    p1.product_name,
    p2.product_name AS related_product
FROM products p1
JOIN products p2 ON p1.category_id = p2.category_id
    AND p1.id != p2.id
    AND p1.price BETWEEN p2.price * 0.8 AND p2.price * 1.2;
```

### JOIN Performance Tips:
```sql
-- Use indexes on join columns
CREATE INDEX idx_employee_dept ON employees(department_id);
CREATE INDEX idx_order_customer ON orders(customer_id);

-- Use INNER JOIN when possible (faster than OUTER JOINs)
-- Use table aliases for readability
-- Join on indexed columns when possible
-- Consider the order of tables in complex joins
```

---

## UNION in SQL

UNION combines the results of two or more SELECT statements into a single result set.

### UNION vs UNION ALL:
- **UNION** - Combines results and removes duplicate rows
- **UNION ALL** - Combines results and keeps all rows (including duplicates, faster)

### Basic Syntax:
```sql
SELECT column1, column2, ... FROM table1
UNION [ALL]
SELECT column1, column2, ... FROM table2;
```

### UNION Rules:
- Same number of columns in all SELECT statements
- Corresponding columns must have compatible data types
- Column names come from the first SELECT statement
- ORDER BY can only be used at the end (applies to final result)

### Basic Examples:
```sql
-- Combine active and inactive customers
SELECT customer_id, name, email FROM active_customers
UNION
SELECT customer_id, name, email FROM inactive_customers;

-- Combine with different sources
SELECT 'Customer' as type, name, email FROM customers
UNION
SELECT 'Supplier' as type, company_name, contact_email FROM suppliers;

-- Include additional identifier
SELECT 
    'Employee' as source,
    id,
    name,
    email
FROM employees
UNION ALL
SELECT 
    'Customer' as source,
    id,
    name,
    email
FROM customers;
```

### Advanced UNION Examples:
```sql
-- Combine monthly and yearly reports
SELECT 
    'Monthly' as report_type,
    MONTH(order_date) as period,
    SUM(total_amount) as revenue
FROM orders
WHERE YEAR(order_date) = 2024
GROUP BY MONTH(order_date)

UNION ALL

SELECT 
    'Yearly' as report_type,
    YEAR(order_date) as period,
    SUM(total_amount) as revenue
FROM orders
GROUP BY YEAR(order_date);

-- Combine current and historical data
SELECT 
    product_id,
    product_name,
    current_price as price,
    'current' as price_type
FROM products
UNION ALL
SELECT 
    product_id,
    product_name,
    old_price as price,
    'historical' as price_type
FROM price_history;
```

### UNION with Sorting:
```sql
-- Sort final combined result
SELECT name, 'Manager' as role FROM managers
UNION
SELECT name, 'Employee' as role FROM employees
ORDER BY name;

-- Sort with priority
SELECT 
    name, 
    salary,
    'High Priority' as category
FROM employees 
WHERE department = 'Executive'
UNION
SELECT 
    name, 
    salary,
    'Regular' as category
FROM employees 
WHERE department != 'Executive'
ORDER BY 
    CASE category 
        WHEN 'High Priority' THEN 1 
        ELSE 2 
    END,
    salary DESC;
```

### Practical UNION Use Cases:
```sql
-- Create a comprehensive contact list
SELECT 
    CONCAT('EMP-', id) as contact_id,
    name,
    email,
    phone,
    'Employee' as contact_type
FROM employees
UNION ALL
SELECT 
    CONCAT('CUST-', id) as contact_id,
    name,
    email,
    phone,
    'Customer' as contact_type
FROM customers
UNION ALL
SELECT 
    CONCAT('SUPP-', id) as contact_id,
    company_name as name,
    contact_email as email,
    contact_phone as phone,
    'Supplier' as contact_type
FROM suppliers
ORDER BY name;

-- Audit trail combining different log tables
SELECT 
    log_date,
    user_id,
    'Login' as action,
    ip_address as details
FROM login_logs
UNION ALL
SELECT 
    transaction_date as log_date,
    user_id,
    'Purchase' as action,
    CONCAT('Amount: , amount) as details
FROM purchase_logs
UNION ALL
SELECT 
    created_at as log_date,
    user_id,
    'Profile Update' as action,
    updated_fields as details
FROM profile_update_logs
ORDER BY log_date DESC;
```

---

## SQL Sub Queries

A subquery is a query nested inside another query. It can be used in SELECT, FROM, WHERE, and HAVING clauses.

### Types of Subqueries:

#### Single Row Subquery
Returns exactly one row and one column:

```sql
-- Find employee with highest salary
SELECT name, salary 
FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);

-- Find products more expensive than average
SELECT product_name, price
FROM products
WHERE price > (SELECT AVG(price) FROM products);

-- Get employee details for a specific department
SELECT name, salary
FROM employees
WHERE department_id = (
    SELECT id FROM departments WHERE name = 'IT'
);
```

#### Multiple Row Subquery
Returns multiple rows:

```sql
-- Find employees in specific departments
SELECT name, department_id
FROM employees
WHERE department_id IN (
    SELECT id FROM departments 
    WHERE location = 'New York'
);

-- Find products never ordered
SELECT product_name
FROM products
WHERE id NOT IN (
    SELECT DISTINCT product_id 
    FROM order_items 
    WHERE product_id IS NOT NULL
);

-- Find customers with above average order amounts
SELECT name
FROM customers
WHERE id IN (
    SELECT customer_id
    FROM orders
    WHERE total_amount > (SELECT AVG(total_amount) FROM orders)
);
```

#### Correlated Subquery
References columns from the outer query:

```sql
-- Find employees earning more than department average
SELECT name, salary, department_id
FROM employees e1
WHERE salary > (
    SELECT AVG(salary)
    FROM employees e2
    WHERE e2.department_id = e1.department_id
);

-- Find customers with more than 3 orders
SELECT name
FROM customers c
WHERE (
    SELECT COUNT(*)
    FROM orders o
    WHERE o.customer_id = c.id
) > 3;

-- Find products with above-average sales in their category
SELECT product_name, category_id
FROM products p1
WHERE (
    SELECT SUM(oi.quantity)
    FROM order_items oi
    WHERE oi.product_id = p1.id
) > (
    SELECT AVG(total_sales)
    FROM (
        SELECT SUM(oi2.quantity) as total_sales
        FROM order_items oi2
        JOIN products p2 ON oi2.product_id = p2.id
        WHERE p2.category_id = p1.category_id
        GROUP BY p2.id
    ) category_avg
);
```

### Subquery Operators:

#### EXISTS and NOT EXISTS
Tests for the existence of rows in subquery:

```sql
-- Find customers who have placed orders
SELECT name
FROM customers c
WHERE EXISTS (
    SELECT 1 FROM orders o 
    WHERE o.customer_id = c.id
);

-- Find customers who haven't placed orders
SELECT name
FROM customers c
WHERE NOT EXISTS (
    SELECT 1 FROM orders o 
    WHERE o.customer_id = c.id
);

-- Find products that have been ordered
SELECT product_name
FROM products p
WHERE EXISTS (
    SELECT 1 FROM order_items oi 
    WHERE oi.product_id = p.id
);
```

#### ANY/SOME and ALL
Compare with any or all values returned by subquery:

```sql
-- Find employees earning more than ANY employee in HR
SELECT name, salary
FROM employees
WHERE salary > SOME (
    SELECT salary FROM employees 
    WHERE department = 'HR'
);

-- Find employees earning more than ALL employees in HR
SELECT name, salary
FROM employees
WHERE salary > ALL (
    SELECT salary FROM employees 
    WHERE department = 'HR'
);

-- Find products cheaper than any product in Electronics category
SELECT product_name, price
FROM products
WHERE price < ANY (
    SELECT price FROM products 
    WHERE category = 'Electronics'
);
```

### Subqueries in Different Clauses:

#### Subquery in SELECT Clause:
```sql
-- Add calculated columns using subqueries
SELECT 
    name,
    salary,
    (SELECT AVG(salary) FROM employees) as company_avg_salary,
    salary - (SELECT AVG(salary) FROM employees) as salary_diff,
    (SELECT COUNT(*) FROM employees e2 
     WHERE e2.department_id = e1.department_id) as dept_size
FROM employees e1;

-- Add related data
SELECT 
    product_name,
    price,
    (SELECT category_name FROM categories c 
     WHERE c.id = p.category_id) as category_name,
    (SELECT COUNT(*) FROM order_items oi 
     WHERE oi.product_id = p.id) as times_ordered
FROM products p;
```

#### Subquery in FROM Clause (Derived Tables):
```sql
-- Use subquery result as a table
SELECT 
    dept_name,
    avg_salary,
    emp_count
FROM (
    SELECT 
        d.name as dept_name,
        AVG(e.salary) as avg_salary,
        COUNT(*) as emp_count
    FROM departments d
    JOIN employees e ON d.id = e.department_id
    GROUP BY d.id, d.name
) as dept_stats
WHERE avg_salary > 60000;

-- Complex aggregation
SELECT 
    customer_tier,
    COUNT(*) as customer_count,
    AVG(total_orders) as avg_orders_per_customer
FROM (
    SELECT 
        c.name,
        COUNT(o.id) as total_orders,
        CASE 
            WHEN COUNT(o.id) > 10 THEN 'Premium'
            WHEN COUNT(o.id) > 5 THEN 'Regular'
            ELSE 'Basic'
        END as customer_tier
    FROM customers c
    LEFT JOIN orders o ON c.id = o.customer_id
    GROUP BY c.id, c.name
) as customer_analysis
GROUP BY customer_tier;
```

#### Subquery in HAVING Clause:
```sql
-- Filter groups based on subquery results
SELECT 
    department,
    AVG(salary) as avg_salary,
    COUNT(*) as emp_count
FROM employees
GROUP BY department
HAVING AVG(salary) > (
    SELECT AVG(salary) * 1.1 FROM employees
);

-- Find departments with more employees than average
SELECT 
    department,
    COUNT(*) as emp_count
FROM employees
GROUP BY department
HAVING COUNT(*) > (
    SELECT COUNT(*) / COUNT(DISTINCT department) 
    FROM employees
);
```

### Advanced Subquery Examples:

#### Nested Subqueries:
```sql
-- Multiple levels of nesting
SELECT name
FROM employees
WHERE department_id IN (
    SELECT id FROM departments
    WHERE location IN (
        SELECT city FROM offices
        WHERE region = 'North America'
    )
);

-- Find top customers in each region
SELECT 
    region,
    customer_name,
    total_spent
FROM (
    SELECT 
        r.region_name as region,
        c.name as customer_name,
        SUM(o.total_amount) as total_spent,
        ROW_NUMBER() OVER (
            PARTITION BY r.region_name 
            ORDER BY SUM(o.total_amount) DESC
        ) as rank_in_region
    FROM customers c
    JOIN orders o ON c.id = o.customer_id
    JOIN regions r ON c.region_id = r.id
    GROUP BY r.region_name, c.id, c.name
) ranked_customers
WHERE rank_in_region <= 3;
```

#### Performance Optimization:
```sql
-- Instead of correlated subquery (slower)
SELECT name FROM employees e1
WHERE salary > (
    SELECT AVG(salary) FROM employees e2 
    WHERE e2.department_id = e1.department_id
);

-- Use window function (faster)
SELECT name
FROM (
    SELECT 
        name,
        salary,
        AVG(salary) OVER (PARTITION BY department_id) as dept_avg
    FROM employees
) e
WHERE salary > dept_avg;

-- Instead of NOT IN with possible NULLs
SELECT product_name
FROM products
WHERE id NOT IN (
    SELECT product_id FROM order_items 
    WHERE product_id IS NOT NULL
);

-- Use LEFT JOIN with NULL check (more reliable)
SELECT p.product_name
FROM products p
LEFT JOIN order_items oi ON p.id = oi.product_id
WHERE oi.product_id IS NULL;
```

---

## MySQL Views

Views are virtual tables based on SQL queries. They don't store data physically but provide a way to present data from one or more tables.

### Creating Views:

#### Basic View Creation:
```sql
-- Simple view
CREATE VIEW active_employees AS
SELECT id, name, email, department, salary
FROM employees
WHERE status = 'active';

-- View with calculations
CREATE VIEW employee_annual_salary AS
SELECT 
    id,
    name,
    department,
    salary as monthly_salary,
    salary * 12 as annual_salary,
    salary * 12 * 0.1 as annual_bonus
FROM employees;

-- View with joins
CREATE VIEW employee_details AS
SELECT 
    e.id,
    e.name,
    e.email,
    d.department_name,
    d.location,
    e.salary
FROM employees e
JOIN departments d ON e.department_id = d.id;
```

#### Advanced View Examples:
```sql
-- Aggregated view
CREATE VIEW department_summary AS
SELECT 
    d.name as department_name,
    d.location,
    COUNT(e.id) as employee_count,
    AVG(e.salary) as avg_salary,
    MAX(e.salary) as max_salary,
    MIN(e.salary) as min_salary,
    SUM(e.salary) as total_payroll
FROM departments d
LEFT JOIN employees e ON d.id = e.department_id
WHERE e.status = 'active' OR e.status IS NULL
GROUP BY d.id, d.name, d.location;

-- Complex business view
CREATE VIEW customer_order_summary AS
SELECT 
    c.id as customer_id,
    c.name as customer_name,
    c.email,
    COUNT(DISTINCT o.id) as total_orders,
    COUNT(DISTINCT oi.product_id) as unique_products_ordered,
    SUM(oi.quantity * p.price) as lifetime_value,
    AVG(o.total_amount) as avg_order_value,
    MAX(o.order_date) as last_order_date,
    DATEDIFF(CURRENT_DATE, MAX(o.order_date)) as days_since_last_order
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
LEFT JOIN order_items oi ON o.id = oi.order_id
LEFT JOIN products p ON oi.product_id = p.id
GROUP BY c.id, c.name, c.email;
```

### Using Views:

#### Querying Views:
```sql
-- Query view like a regular table
SELECT * FROM active_employees;

-- Filter view results
SELECT name, salary 
FROM employee_annual_salary 
WHERE annual_salary > 600000;

-- Join views with other tables or views
SELECT 
    es.name,
    es.annual_salary,
    ds.avg_salary as dept_avg
FROM employee_annual_salary es
JOIN department_summary ds ON es.department = ds.department_name;

-- Aggregate view results
SELECT 
    department_name,
    AVG(avg_salary) as company_avg_by_dept
FROM department_summary
GROUP BY department_name;
```

### View Management:

#### Updating Views:
```sql
-- Replace existing view
CREATE OR REPLACE VIEW active_employees AS
SELECT 
    id, 
    name, 
    email, 
    department, 
    salary,
    hire_date
FROM employees
WHERE status = 'active' AND hire_date > '2020-01-01';

-- Modify view definition
ALTER VIEW employee_details AS
SELECT 
    e.id,
    CONCAT(e.first_name, ' ', e.last_name) as full_name,
    e.email,
    d.department_name,
    d.location,
    e.salary,
    e.hire_date
FROM employees e
JOIN departments d ON e.department_id = d.id
WHERE e.status = 'active';
```

#### View Information:
```sql
-- Show view definition
SHOW CREATE VIEW active_employees;

-- List all views
SELECT 
    table_name as view_name,
    view_definition
FROM information_schema.views
WHERE table_schema = 'your_database_name';

-- Check if view exists
SELECT COUNT(*) 
FROM information_schema.views 
WHERE table_schema = 'your_database' 
    AND table_name = 'active_employees';
```

#### Dropping Views:
```sql
-- Drop single view
DROP VIEW active_employees;

-- Drop multiple views
DROP VIEW view1, view2, view3;

-- Drop view if exists (safe)
DROP VIEW IF EXISTS active_employees;
```

### Types of Views:

#### Simple Views:
Based on single table, support DML operations:
```sql
CREATE VIEW high_salary_employees AS
SELECT id, name, email, salary
FROM employees
WHERE salary > 75000;

-- Can insert, update, delete through simple views
INSERT INTO high_salary_employees (id, name, email, salary)
VALUES (101, 'John Doe', 'john@email.com', 80000);

UPDATE high_salary_employees 
SET salary = 85000 
WHERE id = 101;
```

#### Complex Views:
Based on multiple tables, joins, or aggregations - limited DML support:
```sql
CREATE VIEW order_details AS
SELECT 
    o.id as order_id,
    c.name as customer_name,
    p.product_name,
    oi.quantity,
    p.price,
    (oi.quantity * p.price) as line_total
FROM orders o
JOIN customers c ON o.customer_id = c.id
JOIN order_items oi ON o.id = oi.order_id
JOIN products p ON oi.product_id = p.id;

-- Cannot directly insert/update complex views
-- INSERT INTO order_details VALUES (...); -- This would fail
```

### View Benefits:

#### Security:
```sql
-- Hide sensitive columns
CREATE VIEW public_employee_info AS
SELECT 
    id,
    name,
    department,
    hire_date
FROM employees;
-- Salary, SSN, and other sensitive data hidden

-- Row-level security
CREATE VIEW my_orders AS
SELECT *
FROM orders
WHERE customer_id = CURRENT_USER_ID();  -- Assuming function exists
```

#### Simplification:
```sql
-- Simplify complex queries for end users
CREATE VIEW monthly_sales_report AS
SELECT 
    DATE_FORMAT(o.order_date, '%Y-%m') as month,
    d.department_name,
    SUM(oi.quantity * p.price) as revenue,
    COUNT(DISTINCT o.id) as order_count,
    COUNT(DISTINCT o.customer_id) as unique_customers
FROM orders o
JOIN order_items oi ON o.id = oi.order_id
JOIN products p ON oi.product_id = p.id
JOIN departments d ON p.department_id = d.id
GROUP BY DATE_FORMAT(o.order_date, '%Y-%m'), d.department_name;

-- Users can now simply query:
SELECT * FROM monthly_sales_report WHERE month = '2024-01';
```

#### Consistency:
```sql
-- Ensure consistent business logic
CREATE VIEW active_customer_orders AS
SELECT 
    o.*,
    c.name as customer_name,
    c.tier as customer_tier
FROM orders o
JOIN customers c ON o.customer_id = c.id
WHERE c.status = 'active' 
    AND o.status NOT IN ('cancelled', 'refunded');

-- All applications use the same definition of "active customer orders"
```

### View Limitations:

#### Performance Considerations:
```sql
-- Views don't improve performance - they're just stored queries
-- Each view query executes the underlying SQL
-- Complex views can be slow, especially with aggregations

-- Consider materialized view pattern for better performance
CREATE TABLE monthly_sales_materialized AS
SELECT 
    DATE_FORMAT(order_date, '%Y-%m') as month,
    SUM(total_amount) as revenue
FROM orders
GROUP BY DATE_FORMAT(order_date, '%Y-%m');

-- Refresh periodically
-- TRUNCATE monthly_sales_materialized;
-- INSERT INTO monthly_sales_materialized SELECT ...;
```

#### Update Restrictions:
```sql
-- Cannot update views that contain:
-- - DISTINCT
-- - GROUP BY
-- - HAVING
-- - UNION
-- - Subqueries in SELECT
-- - Non-updatable joins

-- This view cannot be updated:
CREATE VIEW dept_employee_count AS
SELECT department, COUNT(*) as emp_count
FROM employees
GROUP BY department;

-- UPDATE dept_employee_count SET emp_count = 5; -- ERROR
```

### Best Practices:

```sql
-- Use descriptive names
CREATE VIEW vw_active_high_performers AS  -- prefix indicates it's a view
SELECT ...;

-- Document complex views
CREATE VIEW customer_ltv AS  -- LTV = Lifetime Value
SELECT 
    customer_id,
    -- Calculate customer lifetime value based on historical orders
    SUM(order_total) as lifetime_value,
    -- Include predictive component based on order frequency
    AVG(days_between_orders) as avg_order_frequency
FROM (...);

-- Avoid deeply nested view dependencies
-- Instead of: view1 -> view2 -> view3 -> table
-- Prefer: view1 -> table, view2 -> table, etc.

-- Consider indexing underlying tables for view performance
CREATE INDEX idx_employees_status_dept ON employees(status, department_id);
-- This helps views that filter by status and join with departments
```

This completes the comprehensive SQL notes covering all the major topics from basic database concepts to advanced features like views, subqueries, and joins. Each section includes practical examples and best practices to help understand and apply SQL concepts effectively.
