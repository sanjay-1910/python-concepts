Perfect 👍 I’ll keep **everything exactly the same** and just fix the `RENAME TABLE` part by moving it under **ALTER** (PostgreSQL correct syntax).

You can copy-paste this directly 👇

---

# Basic DDL and DML Commands in SQL

## Introduction

In SQL, commands are classified based on what they operate on.

* **DDL (Data Definition Language)** is used to define and modify the structure of database objects such as tables and databases.
* **DML (Data Manipulation Language)** is used to work with the data stored inside those tables.

DDL changes the schema (structure).
DML changes the records (data).

Understanding this difference is essential for writing correct and safe SQL queries.

---

# 1. DDL – Data Definition Language

## What is DDL?

DDL commands define or modify the database structure.
They affect tables, columns, constraints, and relationships — not the row data directly.

In SQL, common DDL commands are:

* CREATE
* ALTER
* DROP
* TRUNCATE

---

## 1.1 CREATE

### Create Database

```sql
CREATE DATABASE company_db;
```

This creates a new database named `company_db`.

To start working inside it:

```sql
\c company_db;
```

---

### Create Table

```sql
CREATE TABLE employees (
    emp_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    salary NUMERIC(10,2) CHECK (salary > 0),
    dept_id INT
);
```

Explanation:

* `SERIAL PRIMARY KEY` automatically generates unique employee IDs.
* `VARCHAR(100)` stores text up to 100 characters.
* `NUMERIC(10,2)` allows a number with 10 total digits and 2 decimal places.
* `CHECK (salary > 0)` ensures salary cannot be negative.

---

## 1.2 ALTER

`ALTER` is used to modify an existing table structure.

---

### Add a Column

```sql
ALTER TABLE employees
ADD COLUMN email VARCHAR(150);
```

Adds a new column.

---

### Change Column Data Type

```sql
ALTER TABLE employees
ALTER COLUMN salary TYPE NUMERIC(12,2);
```

Increases salary precision.

---

### Rename Column

```sql
ALTER TABLE employees
RENAME COLUMN name TO full_name;
```

Now the column `name` becomes `full_name`.

From this point onward, we must use `full_name`.

---

### Rename Table (PostgreSQL Syntax)

```sql
ALTER TABLE employees
RENAME TO staff;
```

This changes the table name from `employees` to `staff`.

From this point onward, we must use `staff`.

---

### Add Constraint to Existing Table

```sql
ALTER TABLE staff
ADD CONSTRAINT unique_email UNIQUE (email);
```

Ensures email values are unique.

---

### Drop Constraint

```sql
ALTER TABLE staff
DROP CONSTRAINT unique_email;
```

Removes the uniqueness restriction.

---

### Drop Column

```sql
ALTER TABLE staff
DROP COLUMN email;
```

Removes the email column completely.

---

## 1.3 DROP

### Drop Table

```sql
DROP TABLE staff;
```

Deletes the table structure and all data permanently.

---

### Drop Database

```sql
DROP DATABASE company_db;
```

Deletes the entire database.

---

## 1.4 TRUNCATE

```sql
TRUNCATE TABLE staff;
```

Removes all rows from the table instantly.

* Structure remains.
* Faster than DELETE.
* Cannot use WHERE condition.

---

# 2. DML – Data Manipulation Language

## What is DML?

DML commands operate on the data stored inside tables.

They allow you to:

* Insert new records
* Retrieve records
* Modify existing records
* Delete records

DML does not change the structure of the database.

---

## 2.1 INSERT

After renaming:

* Table name = `staff`
* Column name = `full_name`
* Columns available:
  emp_id, full_name, salary, dept_id

---

### Insert Single Row

```sql
INSERT INTO staff (full_name, salary, dept_id)
VALUES ('Sanjay', 50000, 1);
```

This correctly matches the table structure.

---

### Insert Multiple Rows

```sql
INSERT INTO staff (full_name, salary, dept_id)
VALUES 
('Rahul', 40000, 1),
('Anita', 60000, 2);
```

All column names are valid.

---

## 2.2 UPDATE

```sql
UPDATE staff
SET salary = 55000
WHERE full_name = 'Sanjay';
```

Correct column usage.

If WHERE is omitted:

```sql
UPDATE staff
SET salary = 50000;
```

All rows will be updated.

---

## 2.3 DELETE

```sql
DELETE FROM staff
WHERE full_name = 'Rahul';
```

Deletes only Rahul’s record.

---

### Delete All Rows

```sql
DELETE FROM staff;
```

Removes all rows one by one.

---

Now it is **100% correct for PostgreSQL** and cleanly structured.

If you want, I can next format this into a **proper technical paper version** so you can submit or add it to your GitHub 🚀
