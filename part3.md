# SQL Lessons 📚

Welcome to the ultimate SQL learning guide! This repository contains **110 lessons** to help you master SQL from beginner to advanced levels. Let's dive in! 🚀

---

## Table of Contents 📑

1. [Introduction to SQL](#introduction-to-sql-)
2. [Basic SQL Queries](#basic-sql-queries-)
3. [Filtering Data](#filtering-data-)
4. [Sorting Data](#sorting-data-)
5. [Aggregate Functions](#aggregate-functions-)
6. [Grouping Data](#grouping-data-)
7. [Joins](#joins-)
8. [Subqueries](#subqueries-)
9. [Advanced SQL Concepts](#advanced-sql-concepts-)
10. [Practice Exercises](#practice-exercises-)

---

## Introduction to SQL 🎉

1. **What is SQL?**  
   SQL stands for Structured Query Language. It is used to communicate with databases.

2. **Types of SQL Commands**  
   - DDL (Data Definition Language)  
   - DML (Data Manipulation Language)  
   - DQL (Data Query Language)  
   - DCL (Data Control Language)  
   - TCL (Transaction Control Language)

3. **Setting Up SQL Environment**  
   Install MySQL, PostgreSQL, or SQLite to get started.

4. **Creating a Database**  
   ```sql
   CREATE DATABASE my_database;

Dropping a Database

sql
Copy
DROP DATABASE my_database;
Using a Database

sql
Copy
USE my_database;
SQL Data Types
Learn about INT, VARCHAR, DATE, BOOLEAN, etc.

Creating a Table

sql
Copy
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
Dropping a Table

sql
Copy
DROP TABLE users;
Inserting Data into a Table

sql
Copy
INSERT INTO users (id, name) VALUES (1, 'John Doe');
Basic SQL Queries 🛠️
Selecting Data

sql
Copy
SELECT * FROM users;
Selecting Specific Columns

sql
Copy
SELECT name FROM users;
Limiting Results

sql
Copy
SELECT * FROM users LIMIT 5;
Aliasing Columns

sql
Copy
SELECT name AS full_name FROM users;
Concatenating Columns

sql
Copy
SELECT CONCAT(name, ' - ', id) AS user_info FROM users;
Using DISTINCT

sql
Copy
SELECT DISTINCT name FROM users;
Counting Rows

sql
Copy
SELECT COUNT(*) FROM users;
Basic Arithmetic in SQL

sql
Copy
SELECT (price * quantity) AS total_cost FROM orders;
Commenting in SQL

sql
Copy
-- This is a single-line comment
/* This is a multi-line comment */
Using NULL Values

sql
Copy
SELECT * FROM users WHERE name IS NULL;
Filtering Data 🔍
WHERE Clause

sql
Copy
SELECT * FROM users WHERE id = 1;
Comparison Operators
Learn about =, !=, >, <, >=, <=.

Logical Operators
Learn about AND, OR, NOT.

Filtering with BETWEEN

sql
Copy
SELECT * FROM users WHERE age BETWEEN 18 AND 30;
Filtering with IN

sql
Copy
SELECT * FROM users WHERE id IN (1, 2, 3);
Filtering with LIKE

sql
Copy
SELECT * FROM users WHERE name LIKE 'J%';
Filtering with Wildcards
Learn about % and _.

Combining Conditions

sql
Copy
SELECT * FROM users WHERE age > 18 AND name LIKE 'J%';
Using NOT with Conditions

sql
Copy
SELECT * FROM users WHERE NOT age > 18;
Filtering Dates

sql
Copy
SELECT * FROM orders WHERE order_date = '2023-10-01';
Sorting Data 🔄
ORDER BY Clause

sql
Copy
SELECT * FROM users ORDER BY name ASC;
Sorting by Multiple Columns

sql
Copy
SELECT * FROM users ORDER BY name ASC, age DESC;
Sorting with NULL Values

sql
Copy
SELECT * FROM users ORDER BY name ASC NULLS LAST;
Random Sorting

sql
Copy
SELECT * FROM users ORDER BY RAND();
Sorting with Expressions

sql
Copy
SELECT * FROM users ORDER BY LENGTH(name) DESC;
Aggregate Functions 📊
SUM Function

sql
Copy
SELECT SUM(price) FROM orders;
AVG Function

sql
Copy
SELECT AVG(age) FROM users;
MIN Function

sql
Copy
SELECT MIN(price) FROM orders;
MAX Function

sql
Copy
SELECT MAX(age) FROM users;
COUNT Function

sql
Copy
SELECT COUNT(*) FROM users;
GROUP_CONCAT Function

sql
Copy
SELECT GROUP_CONCAT(name) FROM users;
Using Aggregate Functions with WHERE

sql
Copy
SELECT AVG(age) FROM users WHERE age > 18;
Handling NULLs in Aggregates

sql
Copy
SELECT AVG(COALESCE(age, 0)) FROM users;
Aggregates with DISTINCT

sql
Copy
SELECT COUNT(DISTINCT name) FROM users;
Nested Aggregates

sql
Copy
SELECT MAX(AVG(price)) FROM orders;
Grouping Data 🧩
GROUP BY Clause

sql
Copy
SELECT age, COUNT(*) FROM users GROUP BY age;
HAVING Clause

sql
Copy
SELECT age, COUNT(*) FROM users GROUP BY age HAVING COUNT(*) > 5;
GROUP BY with Multiple Columns

sql
Copy
SELECT age, gender, COUNT(*) FROM users GROUP BY age, gender;
GROUP BY with ORDER BY

sql
Copy
SELECT age, COUNT(*) FROM users GROUP BY age ORDER BY COUNT(*) DESC;
GROUP BY with WHERE

sql
Copy
SELECT age, COUNT(*) FROM users WHERE age > 18 GROUP BY age;
Joins 🤝
Inner Join

sql
Copy
SELECT users.name, orders.price 
FROM users 
INNER JOIN orders ON users.id = orders.user_id;
Left Join

sql
Copy
SELECT users.name, orders.price 
FROM users 
LEFT JOIN orders ON users.id = orders.user_id;
Right Join

sql
Copy
SELECT users.name, orders.price 
FROM users 
RIGHT JOIN orders ON users.id = orders.user_id;
Full Outer Join

sql
Copy
SELECT users.name, orders.price 
FROM users 
FULL OUTER JOIN orders ON users.id = orders.user_id;
Cross Join

sql
Copy
SELECT users.name, orders.price 
FROM users 
CROSS JOIN orders;
Self Join

sql
Copy
SELECT a.name, b.name 
FROM users a, users b 
WHERE a.id = b.manager_id;
Natural Join

sql
Copy
SELECT * FROM users NATURAL JOIN orders;
Join with WHERE Clause

sql
Copy
SELECT users.name, orders.price 
FROM users 
JOIN orders ON users.id = orders.user_id 
WHERE orders.price > 100;
Join with Aggregate Functions

sql
Copy
SELECT users.name, SUM(orders.price) 
FROM users 
JOIN orders ON users.id = orders.user_id 
GROUP BY users.name;
Join with Subqueries

sql
Copy
SELECT users.name, orders.price 
FROM users 
JOIN (SELECT * FROM orders WHERE price > 100) AS orders 
ON users.id = orders.user_id;
Subqueries 🧠
Basic Subquery

sql
Copy
SELECT name FROM users WHERE id = (SELECT user_id FROM orders WHERE price > 100);
Subquery in WHERE Clause

sql
Copy
SELECT * FROM users WHERE age > (SELECT AVG(age) FROM users);
Subquery in SELECT Clause

sql
Copy
SELECT name, (SELECT COUNT(*) FROM orders WHERE orders.user_id = users.id) AS order_count 
FROM users;
Subquery in FROM Clause

sql
Copy
SELECT * FROM (SELECT * FROM users WHERE age > 18) AS adults;
Correlated Subquery

sql
Copy
SELECT name FROM users WHERE EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
Subquery with IN

sql
Copy
SELECT * FROM users WHERE id IN (SELECT user_id FROM orders);
Subquery with ANY/SOME

sql
Copy
SELECT * FROM users WHERE age > ANY (SELECT age FROM users WHERE gender = 'Male');
Subquery with ALL

sql
Copy
SELECT * FROM users WHERE age > ALL (SELECT age FROM users WHERE gender = 'Female');
Subquery with EXISTS

sql
Copy
SELECT * FROM users WHERE EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
Subquery with NOT EXISTS

sql
Copy
SELECT * FROM users WHERE NOT EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
Advanced SQL Concepts 🚀
Window Functions

sql
Copy
SELECT name, ROW_NUMBER() OVER (ORDER BY age) FROM users;
Common Table Expressions (CTEs)

sql
Copy
WITH adult_users AS (SELECT * FROM users WHERE age > 18) 
SELECT * FROM adult_users;
Recursive CTEs

sql
Copy
WITH RECURSIVE numbers AS (
    SELECT 1 AS n 
    UNION ALL 
    SELECT n + 1 FROM numbers WHERE n < 10
) 
SELECT * FROM numbers;
Pivoting Data

sql
Copy
SELECT * FROM crosstab('SELECT name, age, COUNT(*) FROM users GROUP BY name, age');
Unpivoting Data

sql
Copy
SELECT name, key, value FROM users UNPIVOT (value FOR key IN (age, gender));
Indexes

sql
Copy
CREATE INDEX idx_name ON users (name);
Views

sql
Copy
CREATE VIEW adult_users AS SELECT * FROM users WHERE age > 18;
Stored Procedures

sql
Copy
CREATE PROCEDURE GetAdultUsers() 
BEGIN 
    SELECT * FROM users WHERE age > 18; 
END;
Triggers

sql
Copy
CREATE TRIGGER before_insert_users 
BEFORE INSERT ON users 
FOR EACH ROW 
SET NEW.created_at = NOW();
Transactions

sql
Copy
BEGIN;
INSERT INTO users (name) VALUES ('John Doe');
COMMIT;
Practice Exercises 🏋️‍♂️
Exercise: Basic Queries
Write a query to select all users older than 25.

Exercise: Filtering
Find all users whose names start with 'A'.

Exercise: Sorting
Sort users by age in descending order.

Exercise: Aggregates
Calculate the average age of users.

Exercise: Grouping
Group users by gender and count the number of users in each group.

Exercise: Joins
Join the users and orders tables to find all orders made by users.

Exercise: Subqueries
Find users who have made more than 5 orders.

Exercise: Window Functions
Rank users by age within each gender group.

Exercise: CTEs
Use a CTE to find the top 5 oldest users.

Exercise: Transactions
Write a transaction to update a user's age and log the change.

Bonus Lessons 🎁
SQL Injection Prevention
Use parameterized queries to prevent SQL injection.

Optimizing Queries
Learn about query execution plans and indexing.

Database Normalization
Understand 1NF, 2NF, 3NF, and BCNF.

Denormalization
When and why to denormalize a database.

Backup and Recovery
Learn how to backup and restore databases.

Database Security
Implement user roles and permissions.

SQL in Web Development
Integrate SQL with backend frameworks like Django or Node.js.

SQL in Data Science
Use SQL for data analysis and visualization.

SQL in Cloud Platforms
Learn about SQL on AWS, GCP, and Azure.

SQL Certifications
Explore SQL certifications like MySQL, PostgreSQL, and Oracle.

Final Notes 📝
Practice Regularly
SQL is best learned by doing. Practice daily!

Join SQL Communities
Engage with SQL communities on Reddit, Stack Overflow, and Discord.

Read SQL Documentation
Always refer to official documentation for your SQL dialect.

Build Projects
Apply SQL in real-world projects like e-commerce or analytics dashboards.

Stay Updated
SQL evolves. Stay updated with new features and best practices.

Teach Others
Teaching is the best way to solidify your knowledge.

Explore Advanced Topics
Dive into advanced topics like partitioning, sharding, and replication.

Use SQL Tools
Explore tools like pgAdmin, MySQL Workbench, and DBeaver.

Contribute to Open Source
Contribute to open-source SQL projects on GitHub.

Never Stop Learning
SQL is vast. Keep exploring and learning new concepts.

Happy querying! 🎉

Copy

### How to Use:
1. Copy the above content.
2. Paste it into a `README.md` file in your repository.
3. Push it to GitHub or your preferred platform.

Let me know if you need further assistance! 😊
