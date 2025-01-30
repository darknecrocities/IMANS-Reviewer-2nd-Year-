# SQL & Information Management System Tutorial

Welcome to the **Ultimate SQL & Information Management System (IMS) Guide**! This repository contains **110 lessons** designed to take you from a beginner to an advanced level in SQL and database management.

---

## 📖 Table of Contents

- [Introduction to Databases](#introduction-to-databases)
- [SQL Basics](#sql-basics)
- [Advanced SQL Queries](#advanced-sql-queries)
- [Database Design & Normalization](#database-design--normalization)
- [Stored Procedures & Functions](#stored-procedures--functions)
- [Transactions & Concurrency Control](#transactions--concurrency-control)
- [Indexing & Performance Optimization](#indexing--performance-optimization)
- [NoSQL vs SQL](#nosql-vs-sql)
- [Real-World Database Implementation](#real-world-database-implementation)
- [Project: Build an IMS](#project-build-an-ims)

---

## 🚀 Introduction to Databases

### Lesson 1: What is a Database?
- Definition and types of databases (SQL vs NoSQL)
- Use cases of databases in real-world applications
- Overview of DBMS (Database Management Systems)

**Example:**
```sql
-- Creating a sample database
CREATE DATABASE SchoolDB;
```

### Lesson 2: Relational Databases
- Understanding relational models
- Tables, rows, and columns
- Primary keys and foreign keys

**Example:**
```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);
```

---

## 🔥 SQL Basics

### Lesson 3: Introduction to SQL
- SQL syntax and structure
- Basic SQL commands: `SELECT`, `INSERT`, `UPDATE`, `DELETE`

**Example:**
```sql
SELECT * FROM Students;
```

### Lesson 4: Creating & Managing Tables
- `CREATE TABLE`, `DROP TABLE`, `ALTER TABLE`
- Data types and constraints

**Example:**
```sql
ALTER TABLE Students ADD Email VARCHAR(100);
```

### Lesson 5: Filtering Data
- `WHERE`, `BETWEEN`, `LIKE`, `IN`
- Logical operators: `AND`, `OR`, `NOT`

**Example:**
```sql
SELECT * FROM Students WHERE Age BETWEEN 18 AND 25;
```

### Lesson 6: Sorting & Grouping Data
- `ORDER BY`, `GROUP BY`
- Aggregate functions: `SUM()`, `AVG()`, `COUNT()`

**Example:**
```sql
SELECT Age, COUNT(*) FROM Students GROUP BY Age;
```

---

## 🛠️ Advanced SQL Queries

### Lesson 7: Joins in SQL
- `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`

**Example:**
```sql
SELECT Students.Name, Courses.CourseName 
FROM Students 
INNER JOIN Enrollments ON Students.StudentID = Enrollments.StudentID
INNER JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
```

### Lesson 8: Subqueries
- Writing nested queries
- Using subqueries with `SELECT`, `FROM`, `WHERE`

**Example:**
```sql
SELECT Name FROM Students WHERE StudentID IN (SELECT StudentID FROM Enrollments WHERE CourseID = 101);
```

### Lesson 9: Common Table Expressions (CTEs)
- Using `WITH` for better query readability

**Example:**
```sql
WITH StudentCount AS (
    SELECT Age, COUNT(*) as Count FROM Students GROUP BY Age
)
SELECT * FROM StudentCount;
```

### Lesson 10: Window Functions
- `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`

**Example:**
```sql
SELECT Name, Age, RANK() OVER(ORDER BY Age DESC) as Rank FROM Students;
```

---

## 🏛 Database Design & Normalization

### Lesson 11: Database Normalization
- 1NF, 2NF, 3NF, BCNF
- How normalization prevents redundancy

**Example:**
```sql
-- Splitting student addresses into a separate table
CREATE TABLE StudentAddress (
    AddressID INT PRIMARY KEY,
    StudentID INT,
    Address VARCHAR(255),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID)
);
```

### Lesson 12: Entity-Relationship (ER) Modeling
- Designing an ER diagram
- Converting ER models into tables

**Example:**
```sql
CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```

---

## ⚡ Stored Procedures & Functions

### Lesson 13: Creating Stored Procedures
- Syntax and execution
- Benefits of stored procedures

**Example:**
```sql
CREATE PROCEDURE GetStudents()
BEGIN
    SELECT * FROM Students;
END;
```

### Lesson 14: SQL Functions
- `CREATE FUNCTION`, `RETURNS`, `RETURN`
- Using functions in queries

**Example:**
```sql
CREATE FUNCTION GetStudentCount() RETURNS INT
BEGIN
    DECLARE total INT;
    SELECT COUNT(*) INTO total FROM Students;
    RETURN total;
END;
```

---

## 🔄 Transactions & Concurrency Control

### Lesson 15: ACID Properties
- Atomicity, Consistency, Isolation, Durability

**Example:**
```sql
START TRANSACTION;
UPDATE Students SET Age = 20 WHERE StudentID = 1;
COMMIT;
```

### Lesson 16: Locking & Deadlocks
- `LOCK TABLE`, Deadlock prevention

**Example:**
```sql
LOCK TABLE Students WRITE;
```

---

## 🚀 Indexing & Performance Optimization

### Lesson 17: Indexing Strategies
- `CREATE INDEX`, `DROP INDEX`

**Example:**
```sql
CREATE INDEX idx_name ON Students(Name);
```

### Lesson 18: Query Optimization Techniques
- `EXPLAIN ANALYZE`, `VACUUM`

**Example:**
```sql
EXPLAIN ANALYZE SELECT * FROM Students WHERE Age = 21;
```

---

## 📂 Real-World Database Implementation

### Lesson 21: Database Security Best Practices
- User roles and permissions

**Example:**
```sql
GRANT SELECT ON Students TO 'user1';
```

### Lesson 22: Data Backup & Recovery
- `BACKUP DATABASE`, `RESTORE DATABASE`

**Example:**
```sql
BACKUP DATABASE SchoolDB TO DISK = 'backup.bak';
```

---

## 💡 Project: Build an IMS

Create a **fully functional Information Management System** using SQL.

### Features:
✅ User authentication
✅ Inventory tracking
✅ Transaction records
✅ Data visualization

---

This README is designed for **easy readability** with clear headers, icons, and an engaging structure. 🚀

📌 **Ready to copy-paste into GitHub and get started!**

