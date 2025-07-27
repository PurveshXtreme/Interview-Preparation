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

-- Group by
