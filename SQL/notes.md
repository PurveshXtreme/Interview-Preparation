### 1. What is SQL?

**SQL (Structured Query Language)** is the standard language used to interact with relational databases. It allows you to:

- **Create** database structures (tables, schemas)
- **Read** data using queries
- **Update** existing records
- **Delete** unnecessary data (CRUD operations)

In addition to data manipulation, SQL also supports **schema definition**, **access control**, **data integrity constraints**, and **transaction management**, making it essential for both developers and database administrators.
----

### 2. What is a database?

A **database** is an organized, structured collection of data that is stored electronically. It typically stores data in **tables**, where:

- **Rows** represent records (individual entries)
- **Columns** represent attributes (fields of the data)

Databases are managed using a **Database Management System (DBMS)**, which provides functionalities like:

- Efficient **data storage** and **retrieval**
- Data **manipulation** (insert, update, delete)
- Ensuring **data integrity** and **security**
- Supporting **concurrent access** and **transactions**

Databases are fundamental to modern applications — from websites and mobile apps to enterprise systems.
---

### 3. What are the main types of SQL commands?

SQL commands are categorized based on their purpose in interacting with databases:

#### 1. **DDL (Data Definition Language)**  
Used to define and modify the structure of database objects like tables and schemas.
- `CREATE`: Create new tables, views, or schemas.
- `ALTER`: Modify existing database objects.
- `DROP`: Delete database objects.
- `TRUNCATE`: Remove all records from a table quickly without logging each row deletion.

#### 2. **DML (Data Manipulation Language)**  
Used to manipulate data stored in the database.
- `SELECT`: Retrieve data.
- `INSERT`: Add new records.
- `UPDATE`: Modify existing records.
- `DELETE`: Remove records.

#### 3. **DCL (Data Control Language)**  
Used to control access to data within the database.
- `GRANT`: Give privileges to users.
- `REVOKE`: Remove privileges from users.

#### 4. **TCL (Transaction Control Language)**  
Used to manage transactions and ensure data consistency.
- `COMMIT`: Save all changes made during a transaction.
- `ROLLBACK`: Undo changes made in a transaction.
- `SAVEPOINT`: Define a point to roll back to within a transaction.

These classifications help in organizing SQL operations based on their scope — from schema-level to data-level and access control.
----
### 4. What is the difference between CHAR and VARCHAR2 data types?

#### **CHAR**  
- *Fixed-length* data type.
- If you define `CHAR(10)` and insert a string of 4 characters, the remaining 6 characters will be padded with spaces.
- Always allocates the full defined space, which can lead to wasted storage.

#### **VARCHAR2**  
- *Variable-length* data type.
- If you define `VARCHAR2(10)` and insert 4 characters, it stores exactly those 4 characters without padding.
- More efficient in terms of storage, especially when the actual data size varies.

#### **Key Differences**  
| Feature        | CHAR                | VARCHAR2             |
|----------------|---------------------|-----------------------|
| Length         | Fixed               | Variable              |
| Padding        | Yes (with spaces)   | No                    |
| Storage usage  | Always full size    | Based on actual input |
| Performance    | Slightly faster for fixed-length | Better space efficiency |

**In interviews**, prefer `VARCHAR2` for fields where data length varies, and `CHAR` only when length is guaranteed to be fixed (like country codes, gender, etc.).
-----

### 5. What is a primary key?

A **primary key** is a column or a set of columns in a table that **uniquely identifies each row** in that table. It enforces **entity integrity** by ensuring:

- **Uniqueness**: No two rows can have the same value in the primary key column(s).
- **Non-nullability**: Primary key columns cannot contain NULL values.

#### **Key Characteristics**
- There can be **only one primary key** per table.
- A primary key can consist of a **single column** or a **composite** (multiple columns).
- Automatically creates a **unique index** on the primary key column(s).

#### **Example**
```sql
CREATE TABLE Employees (
  emp_id INT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(100)
);
```

#### **In Interviews**  
> Use primary keys to ensure each record is uniquely identifiable — it's fundamental to maintaining data integrity in relational databases.
----
### 6. What is a foreign key?

A **foreign key** is a column or combination of columns in one table that refers to the **primary key** in another table. It is used to establish a **referential integrity constraint** between the data in the two tables.

#### **Key Characteristics**
- A foreign key creates a **parent-child** relationship between tables.
- It ensures that the value in the foreign key column must exist in the **referenced table**.
- Prevents actions that would leave **orphan records** in the child table.

#### **Example**
```sql
CREATE TABLE Departments (
  dept_id INT PRIMARY KEY,
  dept_name VARCHAR(50)
);

CREATE TABLE Employees (
  emp_id INT PRIMARY KEY,
  name VARCHAR(50),
  dept_id INT,
  FOREIGN KEY (dept_id) REFERENCES Departments(dept_id)
);
```

#### **In Interviews**
> A foreign key ensures the relational aspect of a database — helping maintain data consistency by enforcing that related records must exist in the referenced table.

-----
### 7. What is the purpose of the DEFAULT constraint?

The **DEFAULT constraint** is used to assign a predefined value to a column **when no explicit value is provided during an INSERT operation**. It ensures that the column always has a valid value, maintaining data consistency and reducing the need for NULLs.

#### **Key Points**
- Applies when a column value is omitted during insert.
- Can be used with most data types (e.g., numbers, strings, dates).
- Useful for setting system-generated defaults like current timestamps, default statuses, etc.

#### **Example**
```sql
CREATE TABLE Users (
  id INT PRIMARY KEY,
  username VARCHAR(50),
  status VARCHAR(20) DEFAULT 'active'
);

INSERT INTO Users (id, username) VALUES (1, 'purvesh');
-- status will default to 'active'
```

#### **In Interviews**
> The DEFAULT constraint improves data quality by automatically assigning fallback values, reducing the need for manual input and avoiding NULLs in many cases.
-----
### 8. What is normalization in databases?

**Normalization** is a systematic process used in relational databases to **organize data efficiently**, reduce **redundancy**, and enhance **data integrity**. It involves breaking down large, unstructured tables into smaller, related tables and defining proper **foreign key relationships** among them.

#### **Key Objectives**
- Eliminate duplicate data.
- Ensure logical data storage.
- Prevent anomalies in insert, update, and delete operations.
- Improve data consistency.

#### **Normal Forms**
- **1NF (First Normal Form):** No repeating groups, atomic values only.
- **2NF (Second Normal Form):** 1NF + no partial dependency on primary key.
- **3NF (Third Normal Form):** 2NF + no transitive dependency.

#### **Example**
Imagine a single table storing both student and course data, with repeated course names. Normalization would split this into a `Students` table and a `Courses` table linked by a foreign key.

#### **In Interviews**
> Normalization enhances the logical structure of data, reduces storage waste, and prevents update anomalies — making it essential for designing scalable and maintainable databases.
----

### 9. What is denormalization, and when is it used?

**Denormalization** is the process of intentionally introducing **redundancy** into a database by **combining normalized tables**. This is typically done to **improve read performance** and reduce the complexity of **joins** in frequent or critical queries.

#### **Why Denormalize?**
- Faster data retrieval (fewer joins).
- Simplified query logic.
- Better performance in **read-heavy** applications like dashboards or reporting systems.

#### **When to Use Denormalization**
- When join operations between normalized tables become a bottleneck.
- In analytical or OLAP (Online Analytical Processing) systems where reads are prioritized over writes.
- When you need real-time performance and are okay with some data redundancy.

#### **Example**
Instead of keeping `Customer` and `Order` in separate tables, you might store the customer name directly in the `Order` table to avoid a join during reporting.

#### **In Interviews**
> Denormalization is a performance optimization technique. While it goes against the principles of normalization, it’s useful in scenarios where **read performance** is critical and you can afford **redundancy** for the sake of speed.


-----

### 10. What is a query in SQL?

A **query** in SQL is a **command or statement** used to interact with data stored in a **relational database**. It can be used to **retrieve, insert, update, or delete** data.

#### **Types of Queries**
- **SELECT**: Fetches data based on conditions.
- **INSERT**: Adds new records.
- **UPDATE**: Modifies existing records.
- **DELETE**: Removes records.

#### **Example**
```sql
SELECT name, age FROM Students WHERE grade = 'A';
```

This fetches names and ages of all students with grade A.

#### **In Interviews**
> A query is the primary way to interact with a database using SQL. Whether you're fetching user data, updating inventory, or generating reports — you're using queries. The **SELECT** statement is the most commonly used query to read data from one or more tables.
----

