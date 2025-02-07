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
   ```

5. **Dropping a Database**
```
DROP DATABASE my_database;
```
6. **Using a Database**
```
USE my_database;
```
7. **SQL Data Types**
- Learn about INT, VARCHAR, DATE, BOOLEAN, etc.

8. **Creating a Table**

```
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
```
9. **Dropping a Table**

```
DROP TABLE users;
```
10. **Inserting Data into a Table**

```
INSERT INTO users (id, name) VALUES (1, 'John Doe');
```
## Basic SQL Queries 🛠️
11. **Selecting Data**

```
SELECT * FROM users;
```
12. **Selecting Specific Columns**
```
SELECT name FROM users;
```
13. **Limiting Results**
```
SELECT * FROM users LIMIT 5;
```
14. **Aliasing Columns**

```
SELECT name AS full_name FROM users;
```
15. **Concatenating Columns**
```
SELECT CONCAT(name, ' - ', id) AS user_info FROM users;
```
16. **Using DISTINCT**
```
SELECT DISTINCT name FROM users;
```
17. **Counting Rows**
```
SELECT COUNT(*) FROM users;
```
18. **Basic Arithmetic in SQL**
```
SELECT (price * quantity) AS total_cost FROM orders;
```
19. **Commenting in SQL**

```
-- This is a single-line comment
/* This is a multi-line comment */
```
20. **Using NULL Values**
```
SELECT * FROM users WHERE name IS NULL;
```

## Filtering Data 🔍
21. **WHERE Clause**
```
SELECT * FROM users WHERE id = 1;
```

22. **Comparison Operators**

Learn about =, !=, >, <, >=, <=.

23. **Logical Operators**
Learn about AND, OR, NOT.

24. **Filtering with BETWEEN**

```
SELECT * FROM users WHERE age BETWEEN 18 AND 30;
```

25. **Filtering with IN**
```
SELECT * FROM users WHERE id IN (1, 2, 3);
```
26. **Filtering with LIKE**

```
SELECT * FROM users WHERE name LIKE 'J%';
```
27. **Filtering with Wildcards**
- Learn about % and _.

28. **Combining Conditions**
```
SELECT * FROM users WHERE age > 18 AND name LIKE 'J%';
```
29. **Using NOT with Conditions**
```
SELECT * FROM users WHERE NOT age > 18;
```
30. **Filtering Dates**
```
SELECT * FROM orders WHERE order_date = '2023-10-01';
```
## Sorting Data 🔄
31. **ORDER BY Clause**
```
SELECT * FROM users ORDER BY name ASC;
```
32. **Sorting by Multiple Columns**
```
SELECT * FROM users ORDER BY name ASC, age DESC;
```
33. **Sorting with NULL Values**
```
SELECT * FROM users ORDER BY name ASC NULLS LAST;
```
34. **Random Sorting**
```
SELECT * FROM users ORDER BY RAND();
```
35. **Sorting with Expressions**
```
SELECT * FROM users ORDER BY LENGTH(name) DESC;
```
## Aggregate Functions 📊
36. **SUM Function**

```
SELECT SUM(price) FROM orders;
```

37. **AVG Function**

```
SELECT AVG(age) FROM users;
```
38. **MIN Function**

```
SELECT MIN(price) FROM orders;
```
39. **MAX Function**
```
SELECT MAX(age) FROM users;
```
40. **COUNT Function**

```
SELECT COUNT(*) FROM users;
```
41. **GROUP_CONCAT Function**
```
SELECT GROUP_CONCAT(name) FROM users;
```
42. **Using Aggregate Functions with WHERE**
```
SELECT AVG(age) FROM users WHERE age > 18;
```
43. **Handling NULLs in Aggregates**
```
SELECT AVG(COALESCE(age, 0)) FROM users;
```
44. **Aggregates with DISTINCT**
```
SELECT COUNT(DISTINCT name) FROM users;
```
45. **Nested Aggregates**
```
SELECT MAX(AVG(price)) FROM orders;
```
## Grouping Data 🧩
46. **GROUP BY Clause**
```
SELECT age, COUNT(*) FROM users GROUP BY age;
```
47. **HAVING Clause**
```
SELECT age, COUNT(*) FROM users GROUP BY age HAVING COUNT(*) > 5;
```
46. **GROUP BY with Multiple Columns**
```
SELECT age, gender, COUNT(*) FROM users GROUP BY age, gender;
```
47. **GROUP BY with ORDER BY**
```
SELECT age, COUNT(*) FROM users GROUP BY age ORDER BY COUNT(*) DESC;
```
48. **GROUP BY with WHERE**
```
SELECT age, COUNT(*) FROM users WHERE age > 18 GROUP BY age;
```
## Joins 🤝
49. **Inner Join**
```
SELECT users.name, orders.price 
FROM users 
INNER JOIN orders ON users.id = orders.user_id;
```
50. **Left Join**
```
SELECT users.name, orders.price 
FROM users 
LEFT JOIN orders ON users.id = orders.user_id;
```
51. **Right Join**
```
SELECT users.name, orders.price 
FROM users 
RIGHT JOIN orders ON users.id = orders.user_id;
```
52. **Full Outer Join**
```
SELECT users.name, orders.price 
FROM users 
FULL OUTER JOIN orders ON users.id = orders.user_id;
```
53. **Cross Join**
```
SELECT users.name, orders.price 
FROM users 
CROSS JOIN orders;
```
54. **Self Join**
```
SELECT a.name, b.name 
FROM users a, users b 
WHERE a.id = b.manager_id;
```
55. **Natural Join**
```
SELECT * FROM users NATURAL JOIN orders;
```
56. **Join with WHERE Clause**
```
SELECT users.name, orders.price 
FROM users 
JOIN orders ON users.id = orders.user_id 
WHERE orders.price > 100;
```
57. **Join with Aggregate Functions**
```
SELECT users.name, SUM(orders.price) 
FROM users 
JOIN orders ON users.id = orders.user_id 
GROUP BY users.name;
```
58. **Join with Subqueries**
```
SELECT users.name, orders.price 
FROM users 
JOIN (SELECT * FROM orders WHERE price > 100) AS orders 
ON users.id = orders.user_id;
```
## Subqueries 🧠
59. **Basic Subquery**
```
SELECT name FROM users WHERE id = (SELECT user_id FROM orders WHERE price > 100);
```
60. **Subquery in WHERE Clause**
```
SELECT * FROM users WHERE age > (SELECT AVG(age) FROM users);
```
61. **Subquery in SELECT Clause**
```
SELECT name, (SELECT COUNT(*) FROM orders WHERE orders.user_id = users.id) AS order_count 
FROM users;
```
62. **Subquery in FROM Clause**
```
SELECT * FROM (SELECT * FROM users WHERE age > 18) AS adults;
```
63. **Correlated Subquery**
```
SELECT name FROM users WHERE EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
```
64. **Subquery with IN**
```
SELECT * FROM users WHERE id IN (SELECT user_id FROM orders);
```
65. **Subquery with ANY/SOME**
```
SELECT * FROM users WHERE age > ANY (SELECT age FROM users WHERE gender = 'Male');
```
66. **Subquery with ALL**
```
SELECT * FROM users WHERE age > ALL (SELECT age FROM users WHERE gender = 'Female');
```
67. **Subquery with EXISTS**
```
SELECT * FROM users WHERE EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
```
68. **Subquery with NOT EXISTS**
```
SELECT * FROM users WHERE NOT EXISTS (SELECT 1 FROM orders WHERE orders.user_id = users.id);
```
## Advanced SQL Concepts 🚀
69. **Window Functions**

```
SELECT name, ROW_NUMBER() OVER (ORDER BY age) FROM users;
```
70. **Common Table Expressions (CTEs)**

```
WITH adult_users AS (SELECT * FROM users WHERE age > 18) 
SELECT * FROM adult_users;
```
71. **Recursive CTEs**
```
WITH RECURSIVE numbers AS (
    SELECT 1 AS n 
    UNION ALL 
    SELECT n + 1 FROM numbers WHERE n < 10
) 
SELECT * FROM numbers;
```
72. **Pivoting Data**
```
SELECT * FROM crosstab('SELECT name, age, COUNT(*) FROM users GROUP BY name, age');
```
73. **Unpivoting Data**
```
SELECT name, key, value FROM users UNPIVOT (value FOR key IN (age, gender));
```
74. **Indexes**
```
CREATE INDEX idx_name ON users (name);
```
75. **Views**
```
CREATE VIEW adult_users AS SELECT * FROM users WHERE age > 18;
```
76. **Stored Procedures**
```
CREATE PROCEDURE GetAdultUsers() 
BEGIN 
    SELECT * FROM users WHERE age > 18; 
END;
```
77. **Triggers**

```
CREATE TRIGGER before_insert_users 
BEFORE INSERT ON users 
FOR EACH ROW 
SET NEW.created_at = NOW();
```
78. **Transactions**
```
BEGIN;
INSERT INTO users (name) VALUES ('John Doe');
COMMIT;
```
## Practice Exercises 🏋️‍♂️
```Exercise: Basic Queries
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
```
## Bonus Lessons 🎁
**SQL Injection Prevention**
- Use parameterized queries to prevent SQL injection.

**Optimizing Queries**
- Learn about query execution plans and indexing.

**Database Normalization**
- Understand 1NF, 2NF, 3NF, and BCNF.

**Denormalization**
- When and why to denormalize a database.

**Backup and Recovery**
- Learn how to backup and restore databases.

**Database Security**
- Implement user roles and permissions.

**SQL in Web Development**
- Integrate SQL with backend frameworks like Django or Node.js.

**SQL in Data Science**
- Use SQL for data analysis and visualization.

**SQL in Cloud Platforms**
- Learn about SQL on AWS, GCP, and Azure.

**SQL Certifications**
- Explore SQL certifications like MySQL, PostgreSQL, and Oracle.

## Final Notes 📝
**Practice Regularly*
- SQL is best learned by doing. Practice daily!

**Join SQL Communities*
- Engage with SQL communities on Reddit, Stack Overflow, and Discord.

**Read SQL Documentation*
- Always refer to official documentation for your SQL dialect.

**Build Projects*
- Apply SQL in real-world projects like e-commerce or analytics dashboards.

**Stay Updated*
- SQL evolves. Stay updated with new features and best practices.

**Teach Others*
- Teaching is the best way to solidify your knowledge.

**Explore Advanced Topics*
- Dive into advanced topics like partitioning, sharding, and replication.

**Use SQL Tools*
- Explore tools like pgAdmin, MySQL Workbench, and DBeaver.

**Contribute to Open Source*
- Contribute to open-source SQL projects on GitHub.

**Never Stop Learning*
- SQL is vast. Keep exploring and learning new concepts.**

## Happy querying! 🎉

### How to Use:
1. Copy the above content.
2. Paste it into a `README.md` file in your repository.
3. Push it to GitHub or your preferred platform.

Let me know if you need further assistance! 😊
