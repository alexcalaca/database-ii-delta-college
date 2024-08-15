> Lesson notes - August 14th, 2024
Topic: Aggregate functions and SQL operators

---
---

- Max  
Retrieves the maximum quantity value from the OrderDetails table.
```
SELECT MAX(Quantity) FROM OrderDetails
```

- AVG  
Calculates the average quantity of items from the OrderDetails table.
```
SELECT AVG(Quantity) FROM OrderDetails
```

- MIN  
Finds the minimum price value in the Products table.
```
SELECT MIN(Price) FROM Products
```

- SUM
Computes the total sum of all prices in the Products table.
```
SELECT SUM(Price) FROM Products
```

Counts the number of price entries (non-null) in the Products table.
```
SELECT COUNT(Price) FROM Products
```
---

### SQL Operators

Retrieves all products where the price is greater than 15.  
```
SELECT * FROM Products WHERE Price < 15
```

Retrieves all products where the price is less than 15.
```
SELECT * FROM Products WHERE Price > 15
```

Retrieves all products where the price is less than 0 (usually for checking data integrity issues).
```
SELECT * FROM Products WHERE Price < 0
```

Retrieves all products where the price is greater than or equal to 15.
```
SELECT * FROM Products WHERE Price >= 15
```


Retrieves all products where the product name is not equal to "Chais" (Note: SQL uses <> for "not equal"; != can be used in some other SQL dialects).
```
SELECT * FROM Products WHERE ProductName <> "Chais"
```

Retrieves all products where the price is between 20 and 30 (inclusive of 20 but exclusive of 30).
```
SELECT * FROM Products WHERE Price > 20 AND Price < 30
```

Retrieves the names of products where the price is one of the specified values (18, 22, or 19).
```
SELECT ProductName FROM Products WHERE Price IN (18, 22, 19)
```

Retrieves all products where the price is not equal to 18 (Note: NOT Price = 18 is equivalent to Price <> 18).
```
SELECT * FROM Products WHERE NOT Price = 18
```


Retrieves all products where the price is not one of the specified values (18, 10, 20, or 25).
```
SELECT * FROM Products WHERE NOT Price IN (18, 10, 20, 25)
```

Retrieves all products where the product name does not end with "is" (Note: % is a wildcard for zero or more characters in SQL LIKE patterns).
```
SELECT * FROM Products WHERE NOT ProductName LIKE '%is'
```
