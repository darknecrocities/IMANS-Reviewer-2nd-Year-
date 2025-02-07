# SQL Querying Lecture Notes

## 📌 Introduction to SQL Querying
SQL (Structured Query Language) is the standard language for managing and manipulating databases. It is used to perform various operations such as retrieving, updating, inserting, and deleting data in relational databases.

---

## 🔹 Types of SQL Queries
SQL queries can be categorized into different types:

### 1. **Data Query Language (DQL)**
- Used to retrieve data from databases.
- **SELECT** statement is the main component.
- Example:
  ```sql
  SELECT * FROM Customers;
  ```

### 2. **Data Manipulation Language (DML)**
- Used for modifying data.
- Includes **INSERT**, **UPDATE**, **DELETE**.
- Examples:
  ```sql
  INSERT INTO Customers (CustomerName, ContactName, Country) VALUES ('John Doe', 'John', 'USA');
  UPDATE Customers SET ContactName = 'Jane Doe' WHERE CustomerID = 1;
  DELETE FROM Customers WHERE CustomerID = 1;
  ```

### 3. **Data Definition Language (DDL)**
- Defines database schema.
- Includes **CREATE**, **ALTER**, **DROP**.
- Example:
  ```sql
  CREATE TABLE Orders (
      OrderID INT PRIMARY KEY,
      OrderDate DATE,
      CustomerID INT,
      FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
  );
  ```

### 4. **Data Control Language (DCL)**
- Manages user permissions.
- Includes **GRANT**, **REVOKE**.
- Example:
  ```sql
  GRANT SELECT ON Orders TO user1;
  REVOKE SELECT ON Orders FROM user1;
  ```

### 5. **Transaction Control Language (TCL)**
- Manages transactions.
- Includes **COMMIT**, **ROLLBACK**, **SAVEPOINT**.
- Example:
  ```sql
  BEGIN;
  UPDATE Customers SET Country = 'Canada' WHERE CustomerID = 2;
  ROLLBACK;
  ```

---

## 🔹 SQL Query Components
### 1. **SELECT Statement**
Used to fetch data from tables.
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```

### 2. **WHERE Clause**
Filters records based on conditions.
```sql
SELECT * FROM Customers WHERE Country = 'USA';
```

### 3. **ORDER BY Clause**
Sorts results.
```sql
SELECT * FROM Products ORDER BY Price DESC;
```

### 4. **GROUP BY and HAVING Clause**
Groups data and filters grouped records.
```sql
SELECT Country, COUNT(CustomerID) FROM Customers GROUP BY Country HAVING COUNT(CustomerID) > 5;
```

### 5. **JOINs in SQL**
Combines data from multiple tables.
#### - INNER JOIN
```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```
#### - LEFT JOIN
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```
#### - RIGHT JOIN
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers RIGHT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

### 6. **Subqueries**
Used within another SQL query.
```sql
SELECT CustomerName FROM Customers WHERE CustomerID IN (SELECT CustomerID FROM Orders WHERE OrderAmount > 500);
```

### 7. **Indexes**
Speeds up search queries.
```sql
CREATE INDEX idx_customer_name ON Customers(CustomerName);
```

---

## 🏆 Best Practices for Writing SQL Queries
1. **Use Proper Naming Conventions** 📌
   - Use meaningful table and column names.
2. **Optimize Queries for Performance** 🚀
   - Avoid unnecessary columns in **SELECT** statements.
   - Use indexes where appropriate.
3. **Use Proper Indexing** 🔍
   - Index columns that are frequently used in conditions and joins.
4. **Avoid Using SELECT *** ❌
   - Specify only necessary columns.
5. **Use Proper JOINs Instead of Subqueries** 💡
   - JOINs are more efficient in most cases.

---

## ✅ Summary
- SQL querying is fundamental for database management.
- Different types of queries serve different purposes (DQL, DML, DDL, DCL, TCL).
- Optimizing queries improves database performance.
- Understanding **JOINs**, **subqueries**, and **indexing** is essential.

📚 Keep practicing with real-world scenarios to master SQL queries!


