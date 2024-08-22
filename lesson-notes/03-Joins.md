> Lesson notes - August 21th, 2024
Topic: Joins

---

Creates a table named Products
```
CREATE TABLE Products (
    ProductID SERIAL PRIMARY KEY,
    ProductName VARCHAR(255) NOT NULL,
    CategoryID INT NOT NULL,
    Unit VARCHAR(255) NOT NULL,
    Price DECIMAL(10, 2) NOT NULL
);
```

Insert 10 records into the Products table
```
INSERT INTO Products (ProductName, CategoryID, Unit, Price) VALUES
('Chais', 1, '10 boxes x 20 bags', 18.00),
('Chang', 1, '24 - 12 oz bottles', 19.00),
('Aniseed Syrup', 2, '12 - 550 ml bottles', 10.00),
('Chef Anton''s Cajun Seasoning', 2, '48 - 6 oz jars', 22.00),
('Chef Anton''s Gumbo Mix', 2, '36 boxes', 21.35),
('Grandma''s Boysenberry Spread', 2, '12 - 8 oz jars', 25.00),
('Uncle Bob''s Organic Dried Pears', 7, '12 - 1 lb pkgs.', 30.00),
('Northwoods Cranberry Sauce', 2, '12 - 12 oz jars', 40.00),
('Mishi Kobe Niku', 6, '18 - 500 g pkgs.', 97.00),
('Ikura', 8, '12 - 200 ml jars', 31.00);
```

Creates a table named Products
```
CREATE TABLE Categories (
    CategoryID SERIAL PRIMARY KEY,
    CategoryName VARCHAR(255) NOT NULL,
    Description TEXT
);
```

Insert 10 records into the Categories table
```
INSERT INTO Categories (CategoryName, Description) VALUES
('Beverages', 'Soft drinks, coffees, teas, beers, and ales'),
('Condiments', 'Sweet and savory sauces, relishes, spreads, and seasonings'),
('Confections', 'Desserts, candies, and sweet breads'),
('Dairy Products', 'Cheeses'),
('Grains/Cereals', 'Breads, crackers, pasta, and cereal'),
('Meat/Poultry', 'Prepared meats'),
('Produce', 'Dried fruit and bean curd'),
('Seafood', 'Seaweed and fish'),
('Snacks', 'Cookies, chips, and nuts'),
('Baking Goods', 'Flours, sugars, and chocolate');
```

Retrieves all columns from both the Products and Categories tables for records where the CategoryID matches in both tables.
```
SELECT * FROM Products INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID
```

- Retrieves only the ProductName and Price columns from the Products table for records where the CategoryID matches in both tables.
```
Select ProductName, Price from Products INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID
```

- Updates the CategoryID of the product named 'Chais' to 99 in the Products table.
```
UPDATE Products
SET CategoryID = 99
WHERE ProductName = 'Chais'
```

- Retrieves all columns from the Products table and any matching columns from the Categories table. If there is no match, the Categories columns will be NULL.
```
SELECT * FROM Products LEFT JOIN Categories ON Products.CategoryID = Categories.CategoryID
```

- Retrieves all columns from the Categories table and any matching columns from the Products table. If there is no match, the Products columns will be NULL.
```
SELECT * FROM Products RIGHT JOIN Categories ON Products.CategoryID = Categories.CategoryID
```
